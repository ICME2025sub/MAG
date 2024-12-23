<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Anonymous ICME2025 Submission</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <style>
    /* ========== Global Reset ========== */
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

    /* ========== Container ========== */
    .container {
      max-width: 960px;
      margin: 0 auto;
      padding: 1em;
      background-color: #fff;
      border-radius: 4px;
      box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
    }

    /* ========== Header ========== */
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

    /* ========== Navigation (Optional) ========== */
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

    /* ========== Main Content ========== */
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

    ul {
      list-style: inside;
      margin-left: 0.6em;
      margin-bottom: 1.2em;
    }

    li {
      margin-bottom: 0.6em;
    }

    /* ========== Footer ========== */
    footer {
      margin-top: 2em;
      padding-top: 1em;
      font-size: 0.8em;
      color: #999;
      border-top: 1px solid #e0e0e0;
      text-align: center;
    }

    /* ========== Responsive ========== */
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
      <h1>Anonymous ICME2025 Submission: Make-A-Game (MAG)</h1>
      <p>A DiT-Based Model for Interactive Game Video Generation</p>
    </header>

    <!-- Optional navigation section (add or remove links as needed) -->
    <nav>
      <a href="#about">Overview</a>
      <a href="#features">Key Features</a>
      <a href="#structure">Model Architecture</a>
      <a href="#usage">Usage</a>
    </nav>

    <main>
      <!-- Overview Section -->
      <section id="about">
        <h2>Overview</h2>
        <p>
          As the demand for immersive, personalized gaming experiences continues to rise, traditional manually coded game engines have become increasingly costly and time-intensive to develop. This project introduces 
          <strong>Make-A-Game (MAG)</strong>,
          the first model to employ a Diffusion Transformer (DiT) framework for real-time, interactive game video generation. Current neural models often struggle to integrate diverse control signals, failing to address challenges such as conflicting spatial and non-spatial alignments or deteriorating quality from autoregressive drift. By contrast, MAG utilizes a unified multi-modal control mechanism and lightweight control modules to deliver responsive, coherent, and visually consistent game environments.
        </p>
      </section>

      <!-- Key Features Section -->
      <section id="features">
        <h2>Key Features</h2>
        <div class="highlight">
          1. <strong>Unified Multi-Modal Control</strong>: Incorporates 
          <em>UC-3DMMAttn (Unified Control 3D MMAttention)</em> 
          for both spatially aligned and non-spatially aligned constraints.<br />
          2. <strong>Action Prompt Blocks (APBs)</strong>: Plug-and-play modules for entity-specific manipulation, mitigating autoregressive drift while enhancing real-time control.<br />
          3. <strong>Three-Stage Training</strong>: Sequentially trains on static images, curated videos, and high-quality motion data to balance environment generation and action fidelity.<br />
          4. <strong>High Resolution Consistency</strong>: Maintains 720p or higher resolution without sacrificing frame-to-frame coherence or overall fidelity.<br />
          5. <strong>DiT-Based Extensibility</strong>: The underlying DiT structure supports further integration of more modalities (e.g., multilingual text, audio cues), offering broad potential in interactive applications.
        </div>
      </section>

      <!-- Model Architecture Section -->
      <section id="structure">
        <h2>Model Architecture</h2>
        <p>
          At the core of MAG is a “backbone + lightweight branch” design:
        </p>
        <ul>
          <li>
            <em>Backbone (UC-3DMMDiT Blocks)</em>: Stacked blocks process complex environments and integrate multi-modal information in a unified manner.
          </li>
          <li>
            <em>Lightweight Branch (APB)</em>: Inserted at strategic points to control in-game entities, decoupling character movement from overall scene generation.
          </li>
          <li>
            <em>Three-Stage Training</em>: 
            (1) Fine-tune a foundational model on large-scale game images; 
            (2) Train on video data for environment dynamics; 
            (3) Freeze the backbone and tune APBs for precise motion control.
          </li>
        </ul>
        <p>
          This modular structure significantly reduces drift while enhancing both temporal coherence and responsiveness to user commands.
        </p>
      </section>

      <!-- Usage Section -->
      <section id="usage">
        <h2>Usage</h2>
        <p>
          The source code and implementation details remain under anonymous review. During inference, MAG accepts:
        </p>
        <ol>
          <li>A sequence of video frames (optional, e.g., initial states)</li>
          <li>A video prompt (high-level scene details)</li>
          <li>A text prompt (environment description, style)</li>
          <li>An action prompt (APB input, e.g., character movement or attack)</li>
        </ol>
        <p>
          The model then autoregressively generates subsequent frames. Through UC-3DMMAttn, MAG handles global scene control, while APBs modulate character actions in real time, achieving interactive, coherent, and high-resolution gameplay footage.
        </p>
      </section>
    </main>

    <footer>
      <p>© Anonymous ICME2025 Submission - Make-A-Game (MAG). All rights reserved.</p>
    </footer>
  </div>

  <!-- Optional JavaScript for interactions (e.g., smooth scrolling) -->
  <script>
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
