![作品集 · Selected Works](portfolio-grid-9.jpg)

# MOKEAIGC V25.1 · 世界观与视觉风格导演

从一句灵感或一张参考图出发，构建连贯的世界、生物与场景，并生成可直接使用的中英静帧图像提示词。

**先选一种风格，也可以跳过。** 内置 65 项视觉选项，覆盖写实、3D、2D、水墨、漫画、定格与时尚广告。模式决定交付什么，风格决定画面如何呈现。

[下载完整 Skill 包](MOKEAIGC-V25-skill.zip) · [技能入口](mokeaigc-v25/SKILL.md) · [65 项风格索引](mokeaigc-v25/references/style-index.md) · [完整工作流程](mokeaigc-v25/references/workflow.md)

## 快速开始

下载并解压技能包，将整个 `mokeaigc-v25` 文件夹放入所用宿主的技能目录。需要同时保留 `SKILL.md`、`agents/` 和 `references/`，不能只复制入口文件；风格卡和完整交付规范通过相对路径读取。

支持技能调用的宿主中，选择 `mokeaigc-v25` 后输入创作需求；支持 `$技能名` 语法时，也可以使用下面的示例。其他支持读取文件的助手可先读取 `SKILL.md`，再按入口加载所需引用文件。

**选定风格后开始：**

```text
$mokeaigc-v25
模式 A，选择 35 上美水墨。
构建一个靠潮汐记忆维持秩序的海上文明，交付世界设定和九张概览的中英提示词。
```

**跳过风格选择：**

```text
$mokeaigc-v25
跳过风格选择，直接开始模式 A。
构建一座建在巨兽背上的迁徙城市。
```

**只写设定：**

```text
$mokeaigc-v25
模式 A，仅设定：建立一个交易梦境的城市，说明资源、制度、居民生活与冲突。
```

跳过时沿用已有视觉要求；没有要求时使用默认电影写实。跳过不会省略视觉提示词，也不会随机选一张风格卡。仅设定时不询问风格、平台或画幅。

## 三种创作模式

| 模式 | 用途 | 默认交付 |
| --- | --- | --- |
| A · 世界观 | 将概念扩展为可信的想象世界 | 世界概述、设定正文、差异与一致性说明、Mermaid 关系图、视觉规范、代表性设计图提示词和九张概览提示词 |
| B · 生物与怪物 | 为物种建立结构、功能和生态关系 | 生物设定摘要与中英多视图设定表提示词；需要时增加环境叙事静帧 |
| C · 视觉构图 | 探索同一核心场景的不同拍法 | 默认九种构图，每条包含标题、构图概念和完整中英提示词 |

数量、语言、范围和画幅均可直接指定。模式 C 始终保持同一场景事实；更换风格只调整视觉表达，不自动重写世界、角色或生物结构。

```text
模式 B，选择 33 体素方块3D。
设计生活在盐晶洞穴中的六足食矿生物，输出结构一致的多视图提示词。
```

```text
模式 C，选择 29 三渲二。
核心场景：山村木桥上，一位邮差把最后一封信交给守桥老人。
只做 4 种构图，保持人物、场景和事件一致，画幅 4:3。
```

## 先选风格，也可以跳过

没有提供风格且需要视觉内容时，技能只展示一次简短入口：

- 输入编号或名称，例如 `08 赛博朋克写实`、`24 手绘厚涂融合3D`、`35 上美水墨`。
- 输入“看完整列表”，查看全部 65 项；也可以要求按题材推荐最多 3 项。
- 输入 `0`、`跳过` 或 `直接开始`，继续创作。
- 直接描述自定义风格，例如“二维像素、有限色板、硬边轮廓”。

已经指定风格或参考图画风时，直接沿用；后续扩展不会反复询问。参考图用于人物、物件或构图时，不自动把图中画风当成已选风格。

**65 项中有 63 项视觉预设和 2 项参考入口。** 39、49 需要进一步指定作品、分集、版本或可见参考图，不能把多部作品或整部选集当成统一画风。用户明确要求直接开始但仍缺少子项时，沿用已有视觉要求，或明确标注跳过细分、采用默认电影写实。

全部编号、当前名称、媒介和卡片链接见 [风格索引](mokeaigc-v25/references/style-index.md)。

## V25.1 的风格校准

所有 65 张卡片均按“核心特征、可调整项、不应自动加入、中英风格锚点、使用边界”整理。判断风格依据是媒介、形体、线条、材质、明暗与空间关系，题材物件和特效不会被当成必须出现的画风标志。

- 修正武侠预设的人物偏置、三渲二的媒介误贴，以及若干动画分类混淆。
- 将 UE、Unity、Arnold 等工具偏好与画风、题材分开，不因工具名称自动加入战场或神魔。
- 区分二维像素与体素、定格与粘土、绘画化 3D 与具体作品参考。
- 根据媒介调整摄影开头、皮肤材质、投影和负面项，避免动画提示词同时禁止 CGI，或给纯平面水墨强加浅景深。
- 材料痕迹按实际材料选择，布料木偶不会自动叠加粘土指纹；静态、正面与时尚构图可以正常使用。

## 默认输出与使用边界

默认平台为 Midjourney，画幅 16:9，提示词中英双语；用户明确要求优先。不自动添加版本、高清或画幅参数后缀；`--sref`、`--profile` 仅在用户提供且目标为 Midjourney 时沿用。

本技能默认交付文字设定与静帧图像提示词。实际生图需用户提出并由当前可用工具执行；提示词中的摄影机、渲染器名称不代表已经运行或验证了对应设备与软件。视频运动提示词和单个角色身份档案不属于本技能的主要交付范围。

已完成技能格式、65 项编号与索引、包内链接及 16 个文本使用场景检查；尚未进行 65 组实际生图验证。具体作品或分集的视觉匹配仍需调用时提供可靠参考。

## 文件结构

```text
mokeaigc-v25/
├── SKILL.md                  # 入口、风格选择和路由规则
├── agents/openai.yaml        # 宿主展示信息
└── references/
    ├── workflow.md           # A / B / C 完整交付规范
    ├── style-index.md        # 65 项索引与名称兼容规则
    └── styles/               # 65 张风格卡，按需读取
MOKEAIGC-V25-skill.zip         # 与技能目录一致的完整分发包
```

当前技能版本为 **25.1**，调用名称为 **mokeaigc-v25**。仓库保留的 V09 文档仅用于历史查阅，当前使用以本页链接的技能包为准。

## 作品展示

以下保留仓库原有作品图，供浏览视觉效果；这些图片不是本版 65 项风格的逐项验证结果。

<details>
<summary>展开作品图集</summary>

<img width="2944" height="1648" alt="moke5890_A_cinematic_photograph_Arri_65mm_camera_Cooke_anamor_956328eb-ceab-40da-b8e8-42418bcad136_2" src="https://github.com/user-attachments/assets/1b4cbd34-1d6a-415c-ae48-b51835309a7c" />
<img width="2944" height="1648" alt="moke5890_CCreate169____no_clutter_no_crowded_frame_no_blue_no_61d9e855-86c0-4ebb-b4fd-4a42d03e03af_2" src="https://github.com/user-attachments/assets/4dabab3b-e22b-456e-87e1-69e0d81da7d8" />
<img width="1456" height="816" alt="moke5890_a_mysterious_lone_traveler_in_red_staring_at_a_massi_2d1c3160-de8b-4b48-96ac-4aebfe65b6eb_3" src="https://github.com/user-attachments/assets/f69b9a02-92b5-4754-9745-94a715a328ee" />
<img width="2944" height="1648" alt="moke5890_A_cinematic_photograph_Arri_65mm_camera_Cooke_anamor_90f8f380-888e-427d-ab76-5fe2011c3269_1" src="https://github.com/user-attachments/assets/68ea186f-1445-44b9-98c8-7c9458ecb13d" />
<img width="1456" height="816" alt="moke5890__--ar_169_--profile_1lpfr9a_--v_8 1_ec802f08-8b83-4037-b1c6-501ff9292d22_3" src="https://github.com/user-attachments/assets/2655ec94-b93e-469b-b32c-b3db5114ae48" />
<img width="1456" height="816" alt="moke5890__--ar_169_--profile_1lpfr9a_--v_8 1_db10b6b4-ea3a-4064-8e90-45949a666a5b_2" src="https://github.com/user-attachments/assets/50586dd7-5238-43da-b3d0-45a033faa1dc" />
<img width="2944" height="1648" alt="moke5890_____no_clutter_no_crowded_frame_no_blue_no_green_no__7fd8a414-22cf-489f-a7af-191d964aa063_2" src="https://github.com/user-attachments/assets/d8873f5f-bc23-4166-83e9-e12af0a14cdc" />
<img width="2944" height="1648" alt="moke5890__--ar_169_--raw_--profile_jvk89q1_xrdcsnv_4txpb4m_qa_b5bec25b-3114-4bd2-887b-26ac6f6043a0_1" src="https://github.com/user-attachments/assets/072708dd-5e1d-425f-b6d7-2617b6d95419" />
<img width="2944" height="1648" alt="moke5890__8K_--ar_169_--raw_--profile_4txpb4m_xrdcsnv_qa9rsio_c530e7c0-fc08-4346-add6-a3f2199cef81_1" src="https://github.com/user-attachments/assets/6385709c-de19-4fad-bfdc-4320ce239507" />
<img width="2210" height="1196" alt="微信图片_20260705002600_45865_38" src="https://github.com/user-attachments/assets/e173f7a7-82f9-40f2-9df3-0920433aeafb" />
<img width="6336" height="2688" alt="镜头5·俯拍垂首哀悼_vxzqpy8wjx" src="https://github.com/user-attachments/assets/465f3006-ff85-4864-8d86-53187b688c56" />
<img width="2944" height="1648" alt="moke5890_An_epic_cinematic_photograph _An_epic_vista_reveals__aa429e90-5ddb-4c7f-bd7d-4ae9e44140ac_2" src="https://github.com/user-attachments/assets/b75c226f-abd5-42ce-86a7-3d2ddec4f57b" />
<img width="2944" height="1648" alt="moke5890_A_cinematic_photograph_Arri_65mm_camera_Cooke_anamor_fec6d10f-ff75-4c6a-98c6-049564059c3d_1" src="https://github.com/user-attachments/assets/fab95c50-5f20-49b6-86e9-9bd64c135292" />
<img width="2944" height="1648" alt="moke5890_A_cinematic_photograph_Arri_65mm_camera_Cooke_anamor_eadc0236-0690-4716-9638-40028b6864d5_1" src="https://github.com/user-attachments/assets/aaf98d47-df2a-4c10-b364-5fce3336f74c" />
<img width="2944" height="1648" alt="moke5890_A_cinematic_photograph_Arri_65mm_camera_Cooke_anamor_1dfe1736-6c5a-4985-afb8-e125df12f207_1" src="https://github.com/user-attachments/assets/32c88669-a0a0-4741-8265-0c19882d2ac4" />

</details>

## 关于 MOKEAIGC

- 小红书：[MOKEAIGC](https://www.xiaohongshu.com/user/profile/599e5be55e87e741c05a6bff)
- 抖音：[MokeLMa · 炽×寂×幻](https://v.douyin.com/jlQAEe47xu0/)
- GitHub：[MOKEAIGC 仓库](https://github.com/MOKEAIGC/MOKEAIGC-work-V017)

