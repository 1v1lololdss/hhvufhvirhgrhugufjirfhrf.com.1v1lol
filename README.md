<html>
  <head>
    <meta charset="utf-8">
    <meta http-equiv="Content-Type" content="text/html; charset=utf-8">
    <style>
      /* Buton stili kaldırıldı, gereksiz kod temizlendi */
    </style>
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/n-101-1/1@main/style.css">
    <script src="https://cdn.jsdelivr.net/gh/n-101-1/1@main/UnityProgress.js"></script>
    <script src="https://cdn.jsdelivr.net/gh/n-101-1/1@main/2.7.js"></script>
    <script type="text/javascript">
      var gameInstance;

      window.onload = function () {
        gameInstance = UnityLoader.instantiate("gameContainer", "https://cdn.jsdelivr.net/gh/n-101-1/1@main/2.7.json", {
          onProgress: UnityProgress,
          Module: {
            onRuntimeInitialized: function () {
              UnityProgress(gameInstance, "complete");
            },
          },
        });
      };
    </script>
  </head>
  <body>
    <div class="webgl-content">
      <div id="gameContainer" style="width: 100%; height: 100%; margin: auto;"></div>
    </div>
    <script src="https://cdn.jsdelivr.net/gh/n-101-1/1@main/1firebase-app.js"></script>

    <!-- Add Firebase products that you want to use -->
    <script src="https://cdn.jsdelivr.net/gh/n-101-1/1@main/1firebase-auth.js"></script>
    <script src="https://cdn.jsdelivr.net/gh/n-101-1/1@main/1firebase-firestore.js"></script>

    <script src="https://cdn.jsdelivr.net/gh/n-101-1/1@main/1firebase.js"></script>
    <script src="https://cdn.jsdelivr.net/gh/n-101-1/1@main/1login.js?v=2"></script>
    <script src="https://cdn.jsdelivr.net/gh/n-101-1/1@main/1firestore.js"></script>

    <script>
      initializeFireBase();

      function showAds() {
        console.log("show ads");
      }
      function requestNewAd() {
        // Show video ad
        unityAdFinishedCallback();
      }
      function unityAdFinishedCallback() {
        try {
          if (gameInstance) gameInstance.SendMessage("AdsManager", "OnWebCallback");
        } catch (error) {
          console.log(error);
        }
      }
    </script>
  </body>
</html>
