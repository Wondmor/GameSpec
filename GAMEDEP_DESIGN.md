# GameSpec - 游戏开发专属 AI 规范驱动开发体系

基于 OpenSpec 改造，专为游戏开发量身定制的 AI 辅助开发工作流。

## 设计目标

在 OpenSpec 优秀的规范驱动开发基础上，针对游戏开发做深度定制：

1. **内置游戏开发最佳实践** - 针对不同引擎（Godot/Unity/Unreal）内置语法规则、常见坑规避
2. **自动化验证循环** - AI 写完代码自动静态检查 → 引擎验证 → 捕获错误 → 自动修复
3. **游戏开发专用模板** - 提案、设计、任务拆分模板适配游戏开发流程
4. **引擎专属扩展** - 支持场景文件校验、资源配置检查

## 核心架构

保留 OpenSpec 原有架构，只做增量修改：

```
OpenSpec 核心不变：
├── CLI 命令行工具
├── 规范文件管理 (openspec/changes/)
├── AI 提示生成
└── 工作流管理

GameSpec 新增：
├── 引擎预设 (Godot/Unity/Unreal)
├── 自动验证钩子
├── 游戏开发模板
└── 错误输出解析
```

## 关键新增特性

### 1. 引擎预设配置

用户初始化时可以选择游戏引擎：

```bash
gamespec init --engine godot
```

内置不同引擎的：
- 语法规则（GDScript/C# 不同写法）
- 静态检查命令（`gdlint` 等）
- 项目验证命令（`godot --headless --check-only`）
- 常见错误列表和修复方法

### 2. 自动验证循环

**新增工作流环节**：AI 实现一个任务后 → 自动运行验证 → 如果有错误 → AI 自动修复 → 重新验证 → 直到通过。

```
人类：提案功能
  ↓
AI：生成提案/设计/拆分任务 → 人类审核
  ↓
AI：实现一个任务
  ↓
✅ GameSpec 自动运行：
  1. 静态检查 (gdlint)
  2. 项目验证 (godot --headless --check-only)
  3. 如果可测试，运行场景输出日志
  ↓
❌ 有错误：
  → 将错误输出交给 AI
  → AI 分析并修复
  → 回到步骤 1 重新检查
  ✔ 无错误：下个任务
  ↓
全部完成 → 归档
```

### 3. 游戏开发专用模板

#### 提案模板新增：
- 游戏类型/平台目标
- 核心玩法简述
- 美术资源需求
- 性能考量

#### 设计模板新增：
- 场景结构图
- 交互流程图
- 数据结构设计
- 资源依赖清单

### 4. 错误输出解析

自动解析引擎输出，提取错误位置和原因，给 AI 更清晰的修复指引：

- GDScript 错误解析
- C# 编译器错误解析
- Godot 场景文件错误解析

## 针对 Godot 的特殊优化

1. **GDScript 4.x 语法规则内置**
   - 提醒 `@export` 不是 `export`
   - 提醒 JSON 加载数组需要显式类型转换 `array as Array[String]`
   - 提醒必须显式类型标注

2. **tscn 场景文件处理指南**
   - 纯文本格式，AI 可以直接读写
   - 节点结构规范

3. **内置检查命令**
   ```bash
   # 静态检查
   gdlint path/to/file.gd

   # 项目整体验证
   godot --headless --check-only project.godot

   # 无头运行获取错误输出
   godot --headless project.godot
   ```

## 文件结构变化

原有 OpenSpec 文件结构保留，新增：

```
gamespec/
├── src/
│   ├── core/
│   │   └── engine-preset.ts    # 引擎预设管理
│   ├── commands/
│   │   └── verify.ts           # 新增验证命令
│   └── templates/
│       ├── godot/              # Godot 专用模板
│       ├── unity/              # Unity 专用模板 (预留)
│       └── unreal/             # Unreal 专用模板 (预留)
└── ...
```

## MIT 许可证

保持原 OpenSpec 的 MIT 许可证，开源开放。

## 开发计划

### Phase 1: 基础改造
- [ ] 改名：OpenSpec → GameSpec 全局替换
- [ ] 添加引擎预设支持
- [ ] 完成 Godot 预设模板和规则
- [ ] 添加自动验证钩子

### Phase 2: 测试完善
- [ ] 在 CardIsland 项目测试完整工作流
- [ ] 调整错误解析逻辑
- [ ] 修复发现的问题

### Phase 3: 扩展支持 (未来)
- [ ] 添加 Unity 预设
- [ ] 添加 Unreal 预设
- [ ] 支持自定义验证命令

---

*Created: 2026-04-13*
