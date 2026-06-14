# worldcup-skill
世界杯赛事分析预测 Claude Skill

## 📌 项目简介
这是一个用于 Claude 的 Skill 扩展，包含世界杯赛事相关的分析逻辑、数据参考和使用说明。
你可以通过 Claude 桌面客户端 或 Claude CLI 两种方式加载使用。

## 📂 文件说明
| 文件            | 作用                                                       |
| :-------------- | :--------------------------------------------------------- |
| `SKILL.md`      | 核心技能定义文件，包含 Claude 可调用的指令、逻辑和功能说明 |
| `references.md` | 参考资料与数据源，包含赛事规则、历史数据和分析依据         |

---

## 方式一：Claude 桌面客户端 安装教程
适合新手用户，图形化操作更直观。

### 前置条件
- 已安装支持 Skills 功能的 Claude 桌面客户端
- 已登录你的 Claude 账号

### 安装步骤
1.  **下载仓库**
    - 方式A（Git）：
    ```bash
    git clone https://github.com/chenxiangbei/world-cup-skill.git
    ```
    - 方式B（手动下载）：点击仓库右上角 `Code` → `Download ZIP`，解压到本地文件夹。

2.  **添加本地 Skill**
    1.  打开 Claude 客户端，点击左下角 `Settings`（设置）
    2.  进入 `Developer` → `Local Skills` 页面
    3.  点击 `Add Local Skill`，选择你解压/克隆后的 `worldcup-skill` 文件夹
    4.  等待加载完成，页面出现 `worldcup-skill` 即代表安装成功。

3.  **使用示例**
    在 Claude 对话中直接调用技能：
    ```
    @worldcup-skill 巴西vs摩洛哥
    ```

---

## 🛠️方式二：Claude CLI 安装教程
适合习惯命令行的用户，支持脚本化和自动化场景。

### 前置条件
- 已安装 Claude CLI（需 Node.js 环境）

### 安装步骤
1.  **准备仓库文件**
    ```bash
    # 克隆仓库到本地
    git clone https://github.com/chenxiangbei/world-cup-skill.git
    cd worldcup-skill
    ```

2.  **在 CLI 中加载 Skill**
    方式A：单次对话临时加载（每次启动都要指定）
    ```bash
    claude --skill ./SKILL.md --skill ./references.md
    ```
    方式B：配置全局 Skill（永久生效）
    1.  找到你的 Claude CLI 配置目录：
        - Windows: `%APPDATA%\Claude\cli\config.json`
        - macOS/Linux: `~/.config/claude/cli/config.json`
    2.  在配置文件中添加 `skills` 字段：
        ```json
        {
          "skills": [
            "/你的本地路径/worldcup-skill/SKILL.md",
            "/你的本地路径/worldcup-skill/references.md"
          ]
        }
        ```
    3.  保存配置后，直接运行 `claude` 即可自动加载所有技能。

3.  **使用示例**
    在 CLI 对话中直接输入指令即可调用：
    ```
    请用worldcup技能分析一下阿根廷队的世界杯夺冠概率
    ```

---

## ⚠️ 注意事项
- 本技能仅用于学习与分析参考，不构成任何投注建议
- 如需更新技能，修改文件后：
  - 桌面客户端：重启 Claude 或在 `Local Skills` 页面点击刷新
  - CLI：重启会话或重新加载配置
- 请勿将本技能用于非法用途

## 📄 License
本项目采用 MIT 协议开源，详情见 LICENSE 文件。
```
