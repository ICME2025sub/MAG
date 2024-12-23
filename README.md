<!DOCTYPE html>
<html lang="zh">
<head>
  <meta charset="UTF-8" />
  <title>匿名ICME2025 投稿</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <style>
    /* ================== Global Reset ================== */
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: "Helvetica Neue", Arial, sans-serif;
    }

    body {
      background-color: #f5f5f5;
      color: #333;
      line-height: 1.6;
      padding: 1em;
    }

    /* ================== Container ================== */
    .container {
      max-width: 960px;
      margin: 0 auto;
      padding: 1em;
      background-color: #fff;
      border-radius: 4px;
      box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
    }

    /* ================== Header ================== */
    header {
      margin-bottom: 1.5em;
    }
    header h1 {
      font-size: 1.8em;
      color: #333;
      margin-bottom: 0.4em;
    }
    header p {
      font-size: 0.9em;
      color: #666;
    }

    /* ================== Navigation (Optional) ================== */
    nav {
      margin-bottom: 1.5em;
    }
    nav a {
      display: inline-block;
      margin-right: 1em;
      font-size: 0.9em;
      text-decoration: none;
      color: #007acc;
    }
    nav a:hover {
      text-decoration: underline;
    }

    /* ================== Main Content ================== */
    main h2 {
      margin-top: 1.2em;
      font-size: 1.3em;
      color: #444;
      border-bottom: 1px solid #dadada;
      padding-bottom: 0.3em;
    }

    main p {
      margin-bottom: 1.2em;
      text-align: justify;
    }

    .highlight {
      background-color: #e8f5e9;
      padding: 0.5em;
      border-left: 4px solid #4caf50;
      margin: 1em 0;
    }

    /* ================== Footer ================== */
    footer {
      margin-top: 2em;
      padding-top: 1em;
      font-size: 0.8em;
      color: #999;
      border-top: 1px solid #e0e0e0;
      text-align: center;
    }

    /* ================== Responsive ================== */
    @media (max-width: 600px) {
      header h1 {
        font-size: 1.4em;
      }
      main h2 {
        font-size: 1.2em;
      }
    }
  </style>
</head>

<body>
  <div class="container">
    <header>
      <h1>匿名ICME2025 投稿：Make-A-Game (MAG) 简介</h1>
      <p>一款基于DiT架构的交互式游戏场景生成模型</p>
    </header>

    <!-- 可选的导航部分（如有需要可自行增添其他模块链接）-->
    <nav>
      <a href="#about">项目简介</a>
      <a href="#features">主要特性</a>
      <a href="#structure">模型架构</a>
      <a href="#usage">使用说明</a>
    </nav>

    <main>
      <!-- 项目简介 -->
      <section id="about">
        <h2>项目简介</h2>
        <p>
          随着玩家对于沉浸式与个性化游戏体验的需求不断攀升，传统人工编写的游戏引擎在开发成本与时间上日益凸显局限性。
          本项目基于“匿名ICME2025 投稿”论文，提出了
          <strong>Make-A-Game (MAG)</strong>：首个将DiT（Diffusion Transformer）机制应用于交互式游戏视频生成的模型。
          在面向高度可控的游戏场景生成过程中，现有模型普遍面临多模态信号难以融合、空间对齐与非空间对齐冲突，以及自动回归漂移等挑战，MAG
          则通过统一的多模态融合策略与轻量化控制模块有效解决了上述问题。
        </p>
      </section>

      <!-- 主要特性 -->
      <section id="features">
        <h2>主要特性</h2>
        <div class="highlight">
          1. <strong>统一多模态控制</strong>：提出了
          <em>UC-3DMMAttn（Unified Control 3D MMAttention）</em>
          模块，一体化处理空间与非空间对齐信息。<br />
          2. <strong>行动提示分支 (APB)</strong>：通过可插拔轻量化分支实现对角色与背景的独立操控，有效降低画面漂移。<br />
          3. <strong>三阶段训练流程</strong>：先后对静态图像、大规模视频以及动作数据进行细化训练，兼顾环境生成与动作控制。<br />
          4. <strong>高分辨率一致性</strong>：在720P及以上分辨率下仍具备优秀的跨帧平滑与内容真实性。<br />
          5. <strong>可扩展多模态框架</strong>：DiT结构本身具备高可扩展性，为后续多语种文本、动作乃至语音提示等多模态场景提供潜力。
        </div>
      </section>

      <!-- 模型架构概览 -->
      <section id="structure">
        <h2>模型架构</h2>
        <p>
          为实现交互式游戏模拟：
          <ul>
            <li>
              <em>主干 (Backbone)</em>：由堆叠的
              <strong>UC-3DMMDiT Blocks</strong> 组成，负责复杂环境生成与多模态解耦。
            </li>
            <li>
              <em>轻量化分支 (APB)</em>：插入在主干的关键位置，实现对角色等实体的精准控制，以降低场景背景产生的干扰。
            </li>
            <li>
              <em>三阶段训练</em>：首阶段在大规模游戏领域图像数据上微调基础模型；第二阶段在精选的视频数据集上优化环境生成能力；最后阶段冻结主干，对APB进行细化，以提升角色动作控制效果。
            </li>
          </ul>
        </p>
      </section>

      <!-- 使用说明或演示 -->
      <section id="usage">
        <h2>使用说明</h2>
        <p>
          项目的源代码与安装步骤尚处于匿名阶段，如有兴趣可关注后续更新。用户可在推理阶段向模型输入：
        </p>
        <ol>
          <li>视频帧系列 (如果有历史帧供参考)</li>
          <li>视频提示 (例如场景概述)</li>
          <li>文本提示 (对环境风格或内容的描述)</li>
          <li>行动指令 (APB输入，如角色移动或攻击动作)</li>
        </ol>
        <p>
          模型会自动回归地生成下一帧的场景画面，并可动态响应用户的行动指令，实现高帧率与高分辨率的游戏视频生成。
        </p>
      </section>
    </main>

    <footer>
      <p>© 匿名ICME2025 投稿 - Make-A-Game (MAG). All rights reserved.</p>
    </footer>
  </div>

  <!-- 如果需要额外交互动效，可在此处添加JS脚本 -->
  <script>
    // 示例：平滑滚动至锚点
    document.querySelectorAll('a[href^="#"]').forEach(anchor => {
      anchor.addEventListener("click", function(e) {
        e.preventDefault();
        const target = document.querySelector(this.getAttribute("href"));
        if (target) {
          window.scrollTo({
            top: target.offsetTop - 20,
            behavior: "smooth"
          });
        }
      });
    });
  </script>
</body>
</html>
