javascript.-

<!DOCTYPE html>
<html leng="es">

<style type="text/css">

	body
	{
		background-color:#fff6f1;
		font-family:"Helvetica",Arial;
	}
	#contenido
	{
		width:960px;
		margin:0 auto;
		text-aling:center;
	}
	h1
	{
		color:#993300;
	}
	nav ul li
	{
		  display:inline-block;
		  margin-right:20px;
		  color:#1d1d1d;
		  cursor: pointer;
	}
	#text
	{
			width:600px;
			height:300px;
			background-color:#1d1d1d;
			color:#fff;
			margin:0 auto;
			text-align:left;
			border-radius:20px;
			padding:20px;
			box-shadow:0px 0px 20px rgba(0,0,0,2);
	}

	a
	{
		color:#99ff33;
		font-weight:bold;
	}
	#canvas
	{
		position: absolute;
		button:0px;
		left:0px;
		border:solid;	
	}
	meter
	{
		width:120px;
		margin-left:20px;
	}
	label
	{
		display:block;
	}
</style>



<html lang="es">
<head>
<meta charset='utf-8'>
<link rel="stylesheet" href= "jota.css">
</head>
<body>
	<div id ='contenido'>
	<header>
		<hgroup>
			<h1>Aplicando las nuevas Etiquetas de HTML5<h1>
		</hgroup>
	</header>
	<section><div id='textoPr'>
		<hgroup>
			<center><h1>Media</h1>
		</hgroup>

		<h1>Video</h1><center>
			<video id="Video1" width = '350' height= '240' controls 'controls'> 
				<source src="Introducción a HTML5.mp4" type="video/mp4" />
     
			</video></center>

			<div id="buttonbar"><center>
				<button id="restart" onclick="restart();">[]</button> 
				<button id="rew" onclick="skip(-10)">&lt;&lt;</button>
				<button id="play" onclick="vidplay()">&gt;</button>
				<button id="fastFwd" onclick="skip(10)">&gt;&gt;</button>
			</div> </center>

		<h1>Audio</h1><center>
			<div><audio id="audio1" style="width:85%" controls>Canvas not supported</audio>
			</div>
			<div><input type="text" id="audioFile" value="11.mp3" value="2.mp3"size="30" />
			</div>
				<button id="playbutton" onclick="togglePlay();">&gt;</button>  
				<button onclick="decreaseSpeed();">&lt;&lt;</button>
				<button onclick="increaseSpeed();">&gt;&gt;</button>
				
			<div id="rate"></div></center>
  
	</section>
</body>
</html>

<script type="text/javascript"> 
	var audioElm = document.getElementById("audio1");
    var ratedisplay = document.getElementById("rate"); 
    
	audioElm.addEventListener("ratechange", function () 
	{
		ratedisplay.innerHTML = "Rate: " + audioElm.playbackRate;
    }, 
	false);

      
       function togglePlay() {
         if (document.getElementById("audio1")) {

           if (audioElm.paused == true) {
             playAudio(audioElm);   
           } else {
             pauseAudio(audioElm); 
           }
         }
       }

       function playAudio(audioElm) {
         document.getElementById("playbutton").innerHTML = "Pause"; 
         
         audioElm.src = document.getElementById('audioFile').value;
         audioElm.play();
       }

       function pauseAudio(audioElm) {
         document.getElementById("playbutton").innerHTML = "play";
         audioElm.pause();
       }

       
       function increaseSpeed() {
         audioElm.playbackRate += 1;
       }

       
       function decreaseSpeed() {
         if (audioElm.playbackRate <= 1) {
           var temp = audioElm.playbackRate;
           audioElm.playbackRate = (temp / 2); 
         } else {
           audioElm.playbackRate -= 1;
         }
       }

     </script>
	 
<script type="text/javascript">

    function vidplay() {
       var video = document.getElementById("Video1");
       var button = document.getElementById("play");
       if (video.paused) {
          video.play();
          button.textContent = "||";
       } else {
          video.pause();
          button.textContent = ">";
       }
    }

    function restart() {
        var video = document.getElementById("Video1");
        video.currentTime = 0;
    }

    function skip(value) {
        var video = document.getElementById("Video1");
        video.currentTime += value;
    }      
</script>





============
