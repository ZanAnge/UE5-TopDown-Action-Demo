# UE5 Top-Down Action Demo

基于 Unreal Engine 5 制作的俯视角动作游戏课程实践项目。项目以 Blueprint 为主要开发方式，围绕角色控制、动画表现、投射物攻击、敌人 AI、伤害反馈与基础战斗流程进行搭建，用于学习和验证 UE5 Gameplay 开发工作流。

> 项目性质：个人课程实践 / 持续开发中  
> 开发方向：UE5 游戏客户端、Gameplay、Blueprint  
> 引擎版本：Unreal Engine 5.5

## Demo 演示

- [下载查看项目运行录屏（MKV）](Docs/UE5-TopDown-Action-Demo.mkv)
- 当前录屏用于展示阶段性成果，后续将随功能迭代更新。

## 已实现内容

- **角色控制**：使用 Enhanced Input 处理角色移动，并实现俯视角下的鼠标朝向控制。
- **角色架构**：通过角色基类组织玩家与敌人的公共逻辑，并分别维护玩家、普通敌人等 Blueprint 类型。
- **动画系统**：使用 Animation Blueprint、1D Blend Space 和 Animation Montage 组织待机、移动、攻击、受击与死亡表现。
- **攻击与投射物**：实现基础攻击、火球投射物及投射物相关行为，联动角色动画与战斗反馈。
- **敌人 AI**：使用 AI Controller、Behavior Tree 等资源组织敌人的移动与战斗行为。
- **伤害反馈**：串联伤害事件、受击/死亡状态和 Damage Numbers UI，提供可视化战斗反馈。
- **关卡流程**：配置单人 GameMode、PlayerController 与默认游戏地图，形成可运行的单人战斗场景。
- **Windows 配置**：项目面向桌面端开发，采用 DirectX 12 与 Shader Model 6 配置。

## 核心资源结构

```text
Content/
├─ AI/BehaviorTrees/             # 敌人与投射物相关行为树
├─ AnimBP/                       # 玩家动画蓝图、动画与混合空间
├─ BP_Character/                 # 角色基类、玩家、敌人与投射物蓝图
├─ GameBasics/                   # GameMode、PlayerController、AI Controller
├─ Map/                          # 默认游戏关卡
└─ UI/                           # 伤害数字等战斗反馈UI
```

主要 Blueprint 资源：

- `BP_CharacterBase`：角色公共逻辑基类
- `BP_PlayerCharacter`：玩家角色控制与战斗逻辑
- `BP_EnemyBase` / `BP_Enemy`：敌人基础与具体实现
- `BP_ProjectileBase` / `FireBall`：投射物基础与火球实现
- `ABP_Player`：玩家动画蓝图
- `AIC_Enemy` / `AIC_Fireball`：AI Controller
- `GM_SinglePlayer` / `PC_Player`：单人游戏模式与玩家控制器
- `DamageNumbers`：伤害数字反馈UI

## 技术栈

- Unreal Engine 5.5
- Blueprint Visual Scripting
- Enhanced Input
- Animation Blueprint / Blend Space / Animation Montage
- AI Controller / Behavior Tree
- UMG
- Windows / DirectX 12
- Git

## 运行方式

1. 安装 Unreal Engine 5.5。
2. 克隆或下载本仓库。
3. 双击 `MyProject2.uproject` 打开项目。
4. 等待引擎完成首次着色器编译。
5. 打开 `Content/Map/Game_Default_Map`。
6. 点击 Play 运行当前关卡。

## 我的工作

- 按角色、动画、投射物、AI、UI和游戏基础框架拆分并整理 Blueprint 资源。
- 配置 Enhanced Input、动画蓝图、混合空间与攻击动画流程。
- 搭建玩家攻击、火球投射物、敌人行为和伤害反馈的联动逻辑。
- 使用 Blueprint 调试工具定位事件触发、状态切换和资源引用问题。
- 使用 Git 记录角色功能、AI 行为树、伤害数字与火球特效等阶段性迭代。

## 学习来源与资源说明

本项目基于张亮002的《虚幻5纯中文全流程初学者新手到进阶系列教程合集》进行学习与实践，并在本地完成资源整合、功能搭建、调试和阶段性迭代。

- 课程链接：<https://www.bilibili.com/video/BV1Du411h7qe/>
- 项目中包含用于学习展示的第三方角色、场景和特效资源；相关资源版权归原作者或原资产提供方所有。
- 本仓库不附加开源许可证，不授权第三方复制、转载或再分发其中的第三方资源。

## 当前阶段与后续计划

当前版本用于展示 UE5 Blueprint Gameplay 基础能力，后续计划包括：

- 完善玩家生命值、技能消耗和战斗UI；
- 增加不同敌人状态与更完整的战斗行为；
- 使用结构体和 Data Table 管理角色及敌人配置；
- 增加开始菜单、存档及更完整的游戏流程；
- 引入 UE C++ 基类，将基础属性或伤害逻辑下沉至 C++，由 Blueprint 配置具体表现；
- 完善 Windows 打包版本和更完整的项目演示视频。

## 说明

这是持续迭代中的学习项目，README仅描述当前仓库中能够核对的阶段性内容，不代表商业成品。项目重点是展示本人对 UE5 Blueprint、Gameplay功能拆分、动画与AI联动、调试及版本管理流程的理解。
