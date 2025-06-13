## 
<div align="center">Flow-SLM: Joint Learning of Linguistic and Acoustic Information for Spoken Language Modeling</div>

<div align="center">
  Ju-Chieh Chou, Jiawei Zhou, Karen Livescu
  <br>
  <b><a href="https://arxiv.org/abs/2406.02413" target="_blank">arxiv</a></b>
</div>

<div align="center"></div>

### 
<div align="center">Audio Samples</div>

<div align="left">Samples are randomly selected from LibriSpeech test-clean subset. First 3 seconds of the ground truth are used as audio prompt to generate 10 seconds of speech. </div>

### 
<div align="center">Prompted generation</div>

<div style="max-height: 400px; overflow-y: auto; border: 1px solid #ccc; border-radius: 6px; padding: 8px;">
  
| Ground Truth | Resynethis | Prompts | Continuations |
| :---: | :---: | :---: | :---: |
| <audio src="samples/ground_truth/00.wav" controls style="width:200px;"></audio> | <audio src="samples/resynth/00.wav" controls style="width:200px;"></audio> | <audio src="samples/prompts/00.wav" controls style="width:200px;"></audio> | <audio src="samples/continuations/00_00.wav" controls style="width:200px;"></audio> | 
| | | | <audio src="samples/continuations/00_01.wav" controls style="width:200px;"></audio> | 
| | | | <audio src="samples/continuations/00_02.wav" controls style="width:200px;"></audio> | 
| | | | <audio src="samples/continuations/00_03.wav" controls style="width:200px;"></audio> | 
| <audio src="samples/ground_truth/169.wav" controls style="width:200px;"></audio> | <audio src="samples/resynth/169.wav" controls style="width:200px;"></audio> | <audio src="samples/prompts/169.wav" controls style="width:200px;"></audio> | <audio src="samples/continuations/169_00.wav" controls style="width:200px;"></audio> | 
| | | | <audio src="samples/continuations/169_01.wav" controls style="width:200px;"></audio> | 
| | | | <audio src="samples/continuations/169_02.wav" controls style="width:200px;"></audio> | 
| | | | <audio src="samples/continuations/169_03.wav" controls style="width:200px;"></audio> | 
| <audio src="samples/ground_truth/180.wav" controls style="width:200px;"></audio> | <audio src="samples/resynth/180.wav" controls style="width:200px;"></audio> | <audio src="samples/prompts/180.wav" controls style="width:200px;"></audio> | <audio src="samples/continuations/180_00.wav" controls style="width:200px;"></audio> | 
| | | | <audio src="samples/continuations/180_01.wav" controls style="width:200px;"></audio> | 
| | | | <audio src="samples/continuations/180_02.wav" controls style="width:200px;"></audio> | 
| | | | <audio src="samples/continuations/180_03.wav" controls style="width:200px;"></audio> | 
| <audio src="samples/ground_truth/219.wav" controls style="width:200px;"></audio> | <audio src="samples/resynth/219.wav" controls style="width:200px;"></audio> | <audio src="samples/prompts/219.wav" controls style="width:200px;"></audio> | <audio src="samples/continuations/219_00.wav" controls style="width:200px;"></audio> | 
| | | | <audio src="samples/continuations/219_01.wav" controls style="width:200px;"></audio> | 
| | | | <audio src="samples/continuations/219_02.wav" controls style="width:200px;"></audio> | 
| | | | <audio src="samples/continuations/219_03.wav" controls style="width:200px;"></audio> | 
| <audio src="samples/ground_truth/280.wav" controls style="width:200px;"></audio> | <audio src="samples/resynth/280.wav" controls style="width:200px;"></audio> | <audio src="samples/prompts/280.wav" controls style="width:200px;"></audio> | <audio src="samples/continuations/280_00.wav" controls style="width:200px;"></audio> | 
| | | | <audio src="samples/continuations/280_01.wav" controls style="width:200px;"></audio> | 
| | | | <audio src="samples/continuations/280_02.wav" controls style="width:200px;"></audio> | 
| | | | <audio src="samples/continuations/280_03.wav" controls style="width:200px;"></audio> | 
| <audio src="samples/ground_truth/281.wav" controls style="width:200px;"></audio> | <audio src="samples/resynth/281.wav" controls style="width:200px;"></audio> | <audio src="samples/prompts/281.wav" controls style="width:200px;"></audio> | <audio src="samples/continuations/281_00.wav" controls style="width:200px;"></audio> | 
| | | | <audio src="samples/continuations/281_01.wav" controls style="width:200px;"></audio> | 
| | | | <audio src="samples/continuations/281_02.wav" controls style="width:200px;"></audio> | 
| | | | <audio src="samples/continuations/281_03.wav" controls style="width:200px;"></audio> | 
| <audio src="samples/ground_truth/386.wav" controls style="width:200px;"></audio> | <audio src="samples/resynth/386.wav" controls style="width:200px;"></audio> | <audio src="samples/prompts/386.wav" controls style="width:200px;"></audio> | <audio src="samples/continuations/386_00.wav" controls style="width:200px;"></audio> | 
| | | | <audio src="samples/continuations/386_01.wav" controls style="width:200px;"></audio> | 
| | | | <audio src="samples/continuations/386_02.wav" controls style="width:200px;"></audio> | 
| | | | <audio src="samples/continuations/386_03.wav" controls style="width:200px;"></audio> | 
| <audio src="samples/ground_truth/478.wav" controls style="width:200px;"></audio> | <audio src="samples/resynth/478.wav" controls style="width:200px;"></audio> | <audio src="samples/prompts/478.wav" controls style="width:200px;"></audio> | <audio src="samples/continuations/478_00.wav" controls style="width:200px;"></audio> | 
| | | | <audio src="samples/continuations/478_01.wav" controls style="width:200px;"></audio> | 
| | | | <audio src="samples/continuations/478_02.wav" controls style="width:200px;"></audio> | 
| | | | <audio src="samples/continuations/478_03.wav" controls style="width:200px;"></audio> | 
</div>

### 
<div align="center">Unprompted generation</div>

<div style="max-height: 400px; overflow-y: auto; border: 1px solid #ccc; border-radius: 6px; padding: 8px;">
  <div align="center">
    <table>
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
    </table>
  </div>
</div>


