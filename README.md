# DAGAME

基于 Godot 4.6 的村庄生存管理游戏。

## 游戏简介

玩家在游戏中管理一个村庄，通过采集资源、建造建筑、养殖动物等方式发展村庄。居民会自动进行工作，如采集资源、搬运物品、务农等。

## 项目结构

```
example2/
├── art/                    # 游戏美术资源
│   ├── Map/               # 地图纹理
│   ├── Menu/              # 菜单UI
│   ├── buildings/         # 建筑素材
│   ├── characters/        # 角色素材
│   ├── crops/             # 作物素材
│   ├── objects/           # 物体素材
│   └── tools/             # 工具素材
├── audio/                  # 音频资源
│   ├── ambient/           # 环境音
│   ├── bgm/               # 背景音乐
│   └── sfx/               # 音效
├── Font/                   # 字体文件
├── resources/              # 游戏资源定义
├── scenes/                 # 游戏场景
├── scripts/                # 游戏脚本
│   ├── core/              # 核心模块
│   │   ├── EventBus.gd    # 事件总线
│   │   ├── GameManager.gd
│   │   ├── SaveManager.gd
│   │   └── SettingsManager.gd
│   ├── entities/          # 实体类
│   │   ├── Animal.gd      # 动物
│   │   ├── Building.gd    # 建筑
│   │   ├── ItemDrop.gd   # 物品掉落
│   │   ├── ResourceNode.gd # 资源节点
│   │   └── Villager.gd   # 村民
│   ├── managers/          # 管理器模块
│   │   ├── AudioManager.gd
│   │   ├── BuildManager.gd
│   │   ├── FarmManager.gd
│   │   ├── HaulManager.gd
│   │   ├── InventoryManager.gd
│   │   ├── JobManager.gd
│   │   ├── RoomManager.gd
│   │   ├── StockpileManager.gd
│   │   ├── TimeManager.gd
│   │   └── WolfManager.gd
│   ├── ui/                # UI脚本
│   └── world/             # 世界脚本
└── project.godot          # Godot项目配置
```

## 核心系统

### 事件总线模式
通过 `EventBus` 实现模块间解耦通信，各 Manager 通过订阅和发布事件进行交互。

### 资源系统
- **木材 (Wood)**：通过砍伐树木获得
- **石头 (Stone)**：通过开采岩石获得
- **肉类 (Meat)**：通过狩猎动物获得
- **纤维 (Fiber)**：通过采集获得

### 建筑系统
支持多种建筑类型：
- 墙壁类：木墙、石墙、栅栏
- 门类：木门、石门、栅栏门
- 功能建筑：工作台、篝火、床铺、农场

### 居民系统
居民会自动执行各种任务：
- 采集资源
- 搬运物品到仓库
- 务农
- 建造

### 时间系统
游戏内时间推进，包含昼夜循环。

## 运行方式

1. 安装 [Godot 4.6](https://godotengine.org/) 或更高版本
2. 使用 Godot 打开项目文件夹
3. 点击运行按钮或按 `F5` 启动游戏

## 操作说明

- **移动视角**：鼠标拖拽或使用小键盘
- **建造**：打开建造菜单选择建筑放置
- **采集**：靠近资源节点自动采集

## 技术栈

- **引擎**：Godot 4.6
- **语言**：GDScript
- **渲染**：Forward Plus
- **物理**：Jolt Physics

## 开发说明

项目采用模块化架构设计，每个 Manager 职责单一，便于维护和扩展。详细设计文档请参阅 [PLAN.md](PLAN.md)。
