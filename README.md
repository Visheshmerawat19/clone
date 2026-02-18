<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <link href="https://fonts.googleapis.com/css2?family=Roboto:ital,wght@0,100..900;1,100..900&display=swap" rel="stylesheet">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Spotify - Your fovourite music is here</title>
          <link rel="icon" href="/Spotify Clone/logo.png">

  <link rel="stylesheet" href="clone2.css">
</head>
<body>
  <nav>
    <ul>
      <li class="brand"><img src="/Spotify Clone/logo.png" alt="Spotify">Spotify</li>
      <li>Home</li>
      <li>About</li>
    </ul>
  </nav>


  <div class="container">
    <div class="soung-list">
      <h1>Best of indie - No copy right Sounds</h1>
 <div class="songitemcontainer">
  <div class="song-item">
    <img src="/Spotify Clone/covers/10.jpg" alt="1">
    <span>no love</span>
    <span class="songlistplay"><span class="timespand">  02:36<i class="fa-solid fa fa-circle-play"></i> </span> </span>
  </div>

  <div class="song-item">
    <img src="/Spotify Clone/covers/2.jpg" alt="2">
    <span>Born to shine</span>
    <span class="songlistplay"><span class="timespand">  03:55 <i class="fa-solid fa fa-circle-play"></i> </span> </span>
  </div>

  <div class="song-item">
    <img src="/Spotify Clone/covers/3.jpg" alt="3">
    <span>let me love you</span>
    <span class="songlistplay"><span class="timespand">  05:34 <i class="fa-solid fa fa-circle-play"></i> </span> </span>
  </div>


  <div class="song-item">
    <img src="/Spotify Clone/covers/4.jpg" alt="4">
    <span>let me love you</span>
    <span class="songlistplay"><span class="timespand">  05:34 <i class="fa-solid fa fa-circle-play"></i> </span> </span>
  </div>


  <div class="song-item">
    <img src="/Spotify Clone/covers/5.jpg" alt="5">
    <span>let me love you</span>
    <span class="songlistplay"><span class="timespand">  05:34 <i class="fa-solid fa fa-circle-play"></i> </span> </span>
  </div>


  <div class="song-item">
    <img src="/Spotify Clone/covers/6.jpg" alt="6">
    <span>let me love you</span>
    <span class="songlistplay"><span class="timespand">  05:34 <i class="fa-solid fa fa-circle-play"></i> </span> </span>
  </div>

  <div class="song-item">
    <img src="/Spotify Clone/covers/7.jpg" alt="7">
    <span>let me love you</span>
    <span class="songlistplay"><span class="timespand">  05:34 <i class="fa-solid fa fa-circle-play"></i> </span> </span>
  </div>


  <div class="song-item">
    <img src="/Spotify Clone/covers/8.jpg" alt="8">
    <span>let me love you</span>
    <span class="songlistplay"><span class="timespand">  05:34 <i class="fa-solid fa fa-circle-play"></i> </span> </span>
  </div>


  <div class="song-item">
    <img src="/Spotify Clone/covers/9.jpg" alt="9">
    <span>let me love you</span>
    <span class="songlistplay"><span class="timespand">  05:34 <i class="fa-solid fa fa-circle-play"></i> </span> </span>
  </div><div class="song-item">
    <img src="/Spotify Clone/covers/10.jpg" alt="10">
    <span>let me love you</span>
    <span class="songlistplay"><span class="timespand">  05:34 <i class="fa-solid fa fa-circle-play"></i> </span> </span>
  </div>
 </div>
    </div>
    <div class="song-banner"></div>
  </div>
<div class="bottom">
  <input type="range" name="range" id="Myprogressbar" min="0" max="100">
  <div class="icons">
  <!-- fontawesome icons -->
            <i class="fa-solid fa-3x fa-step-backward"></i>
             <i class="fa-solid fa-3x fa-circle-play"></i> 
            <i class="fa-solid fa-3x fa-step-forward"></i>
</div>

<div class="songinfo">
  <img src="/Spotify Clone/playing.gif"  width="40px"> let me love you . justin ber
</div>

</div>
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/7.0.0/css/all.min.css" integrity="sha512-DxV+EoADOkOygM4IR9yXP8Sb2qwgidEmeqAEmDKIOfPRQZOWbXCzLC6vjbZyy0vPisbH2SyW27+ddLVCN+OMzQ==" crossorigin="anonymous" referrerpolicy="no-referrer" />

<!-- result comes from backend /search?q=... -->
<div id="player"></div>

<script>
function playYouTube(videoId){
  // simple iframe embed
  document.getElementById('player').innerHTML =
    `<iframe id="ytplayer" type="text/html" width="640" height="360"
      src="https://www.youtube.com/embed/${videoId}?autoplay=1&origin=${location.origin}"
      frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>`;
}
</script>
<script src="https://sdk.scdn.co/spotify-player.js"></script>
<script>
window.onSpotifyWebPlaybackSDKReady = () => {
  const token = "USER_ACCESS_TOKEN_FROM_BACKEND";
  const player = new Spotify.Player({
    name: 'My Web Player',
    getOAuthToken: cb => { cb(token); }
  });

  player.addListener('ready', ({ device_id }) => {
    console.log('Ready with Device ID', device_id);
    // use Web API /transfer endpoint to set this device as active and start playback
  });

  player.connect();
}
</script>


</body>
<script src="clone.js"></script>
</html>
