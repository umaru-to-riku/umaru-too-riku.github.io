# umaru-too-riku.github.io
<!DOCTYPE html>
<html>
  <head>
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <!-- 1. AR用のライブラリ（A-FrameとMindAR）を読み込む -->
    <script src="https://aframe.io"></script>
    <script src="https://jsdelivr.net"></script>
  </head>
  <body>
    <!-- 2. ARを表示するカメラ空間の設定 -->
    <a-scene mindar-image="imageTargetSrc: ./target.mind;" color-space="sRGB" renderer="colorManagement: true, physicallyCorrectLights" vr-mode-ui="enabled: false" device-orientation-permission-ui="enabled: false">
      <a-camera position="0 0 0" look-controls="enabled: false"></a-camera>

      <!-- 3. マーカー（ターゲット）を認識した時の処理 -->
      
        <!-- 🚨 災害エフェクト（例：赤い火災球） -->
        <a-sphere position="0 0 0" radius="0.3" color="red" animation="property: scale; to: 1.2 1.2 1.2; dir: alternate; dur: 500; loop: true"></a-sphere>
        
        <!-- 🎯 的（危険行動：タップするとイベントを発生させる） -->
        <a-box id="danger-target" position="0.5 0.5 0" width="0.2" height="0.2" depth="0.2" color="blue"></a-box>
      
    </a-scene>

    <script>
      // 4. 「的」をタップ（射撃）したときのJavaScriptロジック
      const target = document.querySelector('#danger-target');
      target.addEventListener('click', () => {
         alert('【解説】火災時にエレベーターを使ってはいけません！階段で避難しましょう。');
         // ここでスコアを加算したり、Pythonサーバーにデータを送る
      });
    </script>
  </body>
</html>
