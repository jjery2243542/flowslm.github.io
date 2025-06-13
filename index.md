<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Flow-SLM: Joint Learning of Linguistic and Acoustic Information for Spoken Language Modeling</title>
  <style>
    body {
      background: linear-gradient(135deg, #f8fafc 0%, #e0e7ef 100%);
      min-height: 100vh;
      margin: 0;
      font-family: 'Segoe UI', 'Arial', sans-serif;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: flex-start;
    }
    .container {
      width: 100%;
      max-width: 1100px;
      margin: 32px auto 0 auto;
      background: rgba(255,255,255,0.95);
      border-radius: 18px;
      box-shadow: 0 6px 32px rgba(0,0,0,0.08);
      padding: 32px 24px 40px 24px;
      display: flex;
      flex-direction: column;
      align-items: center;
    }
    h2, h3 {
      text-align: center;
      margin-top: 0;
      margin-bottom: 12px;
      font-weight: 700;
      letter-spacing: 0.5px;
    }
    h2 {
      font-size: 2.2rem;
      color: #2a3a5a;
      margin-bottom: 8px;
    }
    h3 {
      font-size: 1.3rem;
      color: #3a4a6a;
      margin-top: 28px;
      margin-bottom: 10px;
    }
    .author-block {
      text-align: center;
      margin-bottom: 18px;
      font-size: 1.08rem;
      color: #444;
    }
    .author-block a {
      color: #3a6ea5;
      text-decoration: none;
      font-weight: 600;
      transition: color 0.2s;
    }
    .author-block a:hover {
      color: #1a3a6a;
      text-decoration: underline;
    }
    .desc {
      text-align: center;
      color: #555;
      font-size: 1.05rem;
      margin-bottom: 18px;
      margin-top: 0;
    }
    .scroll-box {
      max-height: 400px;
      overflow-y: auto;
      border: 1.5px solid #c3d0e0;
      border-radius: 12px;
      padding: 16px 10px;
      background: #f7fafd;
      margin: 0 auto 18px auto;
      width: 98%;
      box-sizing: border-box;
      box-shadow: 0 2px 12px rgba(60,80,120,0.04);
      display: flex;
      justify-content: center;
    }
    table.audio-table, .unprompted-table {
      width: 100%;
      border-collapse: collapse;
      text-align: center;
      background: #fff;
      border-radius: 10px;
      overflow: hidden;
      box-shadow: 0 1px 8px rgba(60,80,120,0.03);
    }
    table.audio-table th, table.audio-table td,
    .unprompted-table th, .unprompted-table td {
      border: 1px solid #e0e7ef;
      padding: 8px 6px;
      vertical-align: middle;
    }
    table.audio-table th, .unprompted-table th {
      background-color: #eaf1fa;
      color: #2a3a5a;
      font-weight: 600;
      font-size: 1.05rem;
    }
    audio {
      outline: none;
      border-radius: 6px;
      box-shadow: 0 1px 4px rgba(60,80,120,0.07);
      background: #f5f8fa;
      margin: 2px 0;
    }
    @media (max-width: 700px) {
      .container {
        padding: 10px 2vw 20px 2vw;
      }
      .scroll-box {
        padding: 6px 1vw;
      }
      table.audio-table, .unprompted-table {
        font-size: 0.95rem;
      }
      audio {
        width: 120px !important;
      }
    }
  </style>
</head>
<body>
  <div class="container">
    <h2>Flow-SLM: Joint Learning of Linguistic and Acoustic Information for Spoken Language Modeling</h2>
    <div class="author-block">
      <span>Ju-Chieh Chou<sup>1</sup></span>, 
      <span>Jiawei Zhou<sup>2</sup></span>, 
      <span>Karen Livescu<sup>1</sup></span>
      <br>
      <span><sup>1</sup>Toyota Technological Institute at Chicago</span>, 
      <span><sup>2</sup>Stony Brook University</span>
      <br>
      <b><a href="https://arxiv.org/abs/2406.02413" target="_blank">arxiv</a></b>
    </div>

    <h3>Audio Samples</h3>
    <div class="desc">
      Samples are randomly selected from LibriSpeech test-clean subset. First 3 seconds of the ground truth are used as audio prompt to generate 10 seconds of speech.
    </div>

    <h3>Prompted Generation</h3>
    <div class="scroll-box">
      <table class="audio-table">
        <thead>
          <tr>
            <th>Ground Truth</th>
            <th>Resynethis</th>
            <th>Prompts</th>
            <th>Continuations</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td><audio src="samples/ground_truth/00.wav" controls style="width:200px;"></audio></td>
            <td><audio src="samples/resynth/00.wav" controls style="width:200px;"></audio></td>
            <td><audio src="samples/prompts/00.wav" controls style="width:200px;"></audio></td>
            <td>
              <audio src="samples/continuations/00_00.wav" controls style="width:200px;"></audio><br>
              <audio src="samples/continuations/00_01.wav" controls style="width:200px;"></audio><br>
              <audio src="samples/continuations/00_02.wav" controls style="width:200px;"></audio><br>
              <audio src="samples/continuations/00_03.wav" controls style="width:200px;"></audio>
            </td>
          </tr>
          <tr>
            <td><audio src="samples/ground_truth/169.wav" controls style="width:200px;"></audio></td>
            <td><audio src="samples/resynth/169.wav" controls style="width:200px;"></audio></td>
            <td><audio src="samples/prompts/169.wav" controls style="width:200px;"></audio></td>
            <td>
              <audio src="samples/continuations/169_00.wav" controls style="width:200px;"></audio><br>
              <audio src="samples/continuations/169_01.wav" controls style="width:200px;"></audio><br>
              <audio src="samples/continuations/169_02.wav" controls style="width:200px;"></audio><br>
              <audio src="samples/continuations/169_03.wav" controls style="width:200px;"></audio>
            </td>
          </tr>
          <tr>
            <td><audio src="samples/ground_truth/180.wav" controls style="width:200px;"></audio></td>
            <td><audio src="samples/resynth/180.wav" controls style="width:200px;"></audio></td>
            <td><audio src="samples/prompts/180.wav" controls style="width:200px;"></audio></td>
            <td>
              <audio src="samples/continuations/180_00.wav" controls style="width:200px;"></audio><br>
              <audio src="samples/continuations/180_01.wav" controls style="width:200px;"></audio><br>
              <audio src="samples/continuations/180_02.wav" controls style="width:200px;"></audio><br>
              <audio src="samples/continuations/180_03.wav" controls style="width:200px;"></audio>
            </td>
          </tr>
          <tr>
            <td><audio src="samples/ground_truth/219.wav" controls style="width:200px;"></audio></td>
            <td><audio src="samples/resynth/219.wav" controls style="width:200px;"></audio></td>
            <td><audio src="samples/prompts/219.wav" controls style="width:200px;"></audio></td>
            <td>
              <audio src="samples/continuations/219_00.wav" controls style="width:200px;"></audio><br>
              <audio src="samples/continuations/219_01.wav" controls style="width:200px;"></audio><br>
              <audio src="samples/continuations/219_02.wav" controls style="width:200px;"></audio><br>
              <audio src="samples/continuations/219_03.wav" controls style="width:200px;"></audio>
            </td>
          </tr>
          <tr>
            <td><audio src="samples/ground_truth/280.wav" controls style="width:200px;"></audio></td>
            <td><audio src="samples/resynth/280.wav" controls style="width:200px;"></audio></td>
            <td><audio src="samples/prompts/280.wav" controls style="width:200px;"></audio></td>
            <td>
              <audio src="samples/continuations/280_00.wav" controls style="width:200px;"></audio><br>
              <audio src="samples/continuations/280_01.wav" controls style="width:200px;"></audio><br>
              <audio src="samples/continuations/280_02.wav" controls style="width:200px;"></audio><br>
              <audio src="samples/continuations/280_03.wav" controls style="width:200px;"></audio>
            </td>
          </tr>
          <tr>
            <td><audio src="samples/ground_truth/281.wav" controls style="width:200px;"></audio></td>
            <td><audio src="samples/resynth/281.wav" controls style="width:200px;"></audio></td>
            <td><audio src="samples/prompts/281.wav" controls style="width:200px;"></audio></td>
            <td>
              <audio src="samples/continuations/281_00.wav" controls style="width:200px;"></audio><br>
              <audio src="samples/continuations/281_01.wav" controls style="width:200px;"></audio><br>
              <audio src="samples/continuations/281_02.wav" controls style="width:200px;"></audio><br>
              <audio src="samples/continuations/281_03.wav" controls style="width:200px;"></audio>
            </td>
          </tr>
          <tr>
            <td><audio src="samples/ground_truth/386.wav" controls style="width:200px;"></audio></td>
            <td><audio src="samples/resynth/386.wav" controls style="width:200px;"></audio></td>
            <td><audio src="samples/prompts/386.wav" controls style="width:200px;"></audio></td>
            <td>
              <audio src="samples/continuations/386_00.wav" controls style="width:200px;"></audio><br>
              <audio src="samples/continuations/386_01.wav" controls style="width:200px;"></audio><br>
              <audio src="samples/continuations/386_02.wav" controls style="width:200px;"></audio><br>
              <audio src="samples/continuations/386_03.wav" controls style="width:200px;"></audio>
            </td>
          </tr>
          <tr>
            <td><audio src="samples/ground_truth/478.wav" controls style="width:200px;"></audio></td>
            <td><audio src="samples/resynth/478.wav" controls style="width:200px;"></audio></td>
            <td><audio src="samples/prompts/478.wav" controls style="width:200px;"></audio></td>
            <td>
              <audio src="samples/continuations/478_00.wav" controls style="width:200px;"></audio><br>
              <audio src="samples/continuations/478_01.wav" controls style="width:200px;"></audio><br>
              <audio src="samples/continuations/478_02.wav" controls style="width:200px;"></audio><br>
              <audio src="samples/continuations/478_03.wav" controls style="width:200px;"></audio>
            </td>
          </tr>
        </tbody>
      </table>
    </div>

    <h3>Unprompted Generation</h3>
    <div class="scroll-box">
      <table class="unprompted-table">
        <tbody>
          <tr>
            <td><audio src="samples/unprompted/00.wav" controls style="width:200px;"></audio></td>
            <td><audio src="samples/unprompted/01.wav" controls style="width:200px;"></audio></td>
            <td><audio src="samples/unprompted/02.wav" controls style="width:200px;"></audio></td>
          </tr>
          <tr>
            <td><audio src="samples/unprompted/03.wav" controls style="width:200px;"></audio></td>
            <td><audio src="samples/unprompted/04.wav" controls style="width:200px;"></audio></td>
            <td><audio src="samples/unprompted/05.wav" controls style="width:200px;"></audio></td>
          </tr>
          <tr>
            <td><audio src="samples/unprompted/06.wav" controls style="width:200px;"></audio></td>
            <td><audio src="samples/unprompted/07.wav" controls style="width:200px;"></audio></td>
            <td><audio src="samples/unprompted/08.wav" controls style="width:200px;"></audio></td>
          </tr>
          <tr>
            <td><audio src="samples/unprompted/09.wav" controls style="width:200px;"></audio></td>
            <td><audio src="samples/unprompted/10.wav" controls style="width:200px;"></audio></td>
            <td><audio src="samples/unprompted/11.wav" controls style="width:200px;"></audio></td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</body>
</html>
