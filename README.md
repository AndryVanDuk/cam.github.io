


    <link href="/v1/video-js.css" rel="stylesheet">

    <!--
      -- Include video.js and videojs-contrib-hls in your page
      -->

    <script src="/v1/video.js"></script>
    <script src="/v1/videojs-contrib-hls.js"></script>
    <body style="margin: 0 auto; background: #fff;">

        <video  id=video width='640'height='480' class="video-js vjs-default-skin vjs-big-play-centered"  preload="auto" data-setup='{"controls": true, "loop": "true", "autoplay": true,  "preload": "true", "poster":"//cam.indikom.ru/camp/img32.jpg"}' muted autobuffer="true">
          <source
             src="//cam.indikom.ru/32/hls/stream.m3u8"
             type="application/x-mpegURL">
        </video>

    <script>
      (function(window, videojs) {
        var player = window.player = videojs('video',{
	errorDisplay: false
	});

        // hook up the video switcher
        var loadUrl = document.getElementById('load-url');
        var url = document.getElementById('url');
        loadUrl.addEventListener('submit', function(event) {
          event.preventDefault();
          player.src({
            src: url.value,
            type: 'application/x-mpegURL'
          });
          return false;
        });
      }(window, window.videojs));
    </script>
  </body>
</html>
