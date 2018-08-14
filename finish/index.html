<!DOCTYPE html>
<html>
	<head>

    <!--
    AR.js workshop
    Author: Matt Nutsch
    Date Created: 6-20-2018
    Date Last Edited: 8-13-2018
    Description: This is sample code for a workshop on developing an AR.js app.
    Notes:
    The implementations of AR.js are based in part on Jerome Etienne's examples of AR.js at: https://github.com/jeromeetienne/AR.js/tree/master/aframe
    The implementations of AFrame.js are also based in part on the AFrame documentation, available at: https://aframe.io/docs

    Go to this URL to run this code in a mobile web browser: https://mnutsch.github.io/arjs_workshop/start/index.html
    Download and print this image for the AR target marker: https://github.com/mnutsch/mnutsch.github.io/raw/master/arjs_workshop/start/Hiro%20pattern%20with%20border.pdf
    -->

    <!-- include a-frame -->
    <script src="https://mnutsch.github.io/arjs_workshop/start/vendor/aframe/build/aframe.min.js"></script>
    <!-- include ar.js for aframe -->
    <script src='https://mnutsch.github.io/arjs_workshop/start/vendor/arjs/build/aframe-ar.js'></script>
    <script>ARjs.Context.baseURL = 'https://mnutsch.github.io/arjs_workshop/start/vendor/three.js/'</script>
    <!-- Note: the above libraries are included with absolute URL's, because Github.io seems to prefer those. Change them to relative URL's -->

    <script>		
      //wait until the page loads to perform the following
      window.onload = function () 
      {

        var intervalLength = 20; //determines the speed of the animation (milliseconds to wait between ticks)

        //define the scene, for ease of interacting with it
        var scene = document.querySelector('a-scene');       

        //for keeping track of scores
        var player1Score = 0;
        var player2Score = 0;
        
        //for tracking border collisions
        var maxX = 1;
        var maxY = 1;
        var maxZ = 1;
        var minX = -1;
        var minY = -1;
        var minZ = -1;
        var bumperWidth = 0.1;

        //for tracking border color cooldown
        var topBumperCoolDown = 0;
        var rightBumperCoolDown = 0;
        var leftBumperCoolDown = 0;
        var bottomBumperCoolDown = 0;
        var topPaddleCoolDown = 0;
        var bottomPaddleCoolDown = 0;

        //bind variables to entities
        var myBox = document.getElementById('myBox');      
        var myText = document.getElementById('myText');      
        var mySphere = document.getElementById('mySphere');        
        var leftBumper = document.getElementById('leftBumper');
        var rightBumper = document.getElementById('rightBumper');
        var topBumper = document.getElementById('topBumper');
        var bottomBumper = document.getElementById('bottomBumper');
        var topPaddle = document.getElementById('topPaddle');
        var bottomPaddle = document.getElementById('bottomPaddle');

        //initialize variables to track position of objects
        var myBoxPosition = {};
          myBoxPosition.x = 0;
          myBoxPosition.y = 0;
          myBoxPosition.z = 0;
        var mySpherePosition = {};
          mySpherePosition.x = 0;
          mySpherePosition.y = 0;
          mySpherePosition.z = 0;
        var myTextPosition = {};
          myTextPosition.x = 0;
          myTextPosition.y = 0;
          myTextPosition.z = 0;
        var topPaddlePosition = {};
          topPaddlePosition.x = 0;
          topPaddlePosition.y = 0.05;
          topPaddlePosition.z = -0.86;
        var bottomPaddlePosition = {};
          bottomPaddlePosition.x = 0;
          bottomPaddlePosition.y = 0.05;
          bottomPaddlePosition.z = 0.86;

        //initialize variables to track object properties
        var topPaddleProperties = {};
          topPaddleProperties.width = 0.1;
          topPaddleProperties.height = 0.1;
          topPaddleProperties.depth = 0.49;
        var bottomPaddleProperties = {};
          bottomPaddleProperties.width = 0.1;
          bottomPaddleProperties.height = 0.1;
          bottomPaddleProperties.depth = 0.49;
        var mySphereProperties = {};
          mySphereProperties.radius = 0.05;

        //create variables to track movement vectors      
        var mySphereVector = {};
          mySphereVector.x = 0;
          mySphereVector.y = 0;
          mySphereVector.z = 0; 
        var topPaddleVector = {};
          topPaddleVector.x = 0;
          topPaddleVector.y = 0;
          topPaddleVector.z = 0;
        var bottomPaddleVector = {};
          bottomPaddleVector.x = 0;
          bottomPaddleVector.y = 0;
          bottomPaddleVector.z = 0;

        //pick a random number between 0.020 and 0.030 for both x and z vectors
        mySphereVector.x = ((Math.floor(Math.random() * 30) + 20) / 1000)
        mySphereVector.z = ((Math.floor(Math.random() * 30) + 20) / 1000)

        //Timer for animations
        setInterval(function()
        {

          //reset the colors of the bumpers
          if(leftBumperCoolDown > 0){
            leftBumperCoolDown = leftBumperCoolDown - 1;
          }
          else{
            leftBumper.setAttribute('color', 'blue');
          }
          if(rightBumperCoolDown > 0){
            rightBumperCoolDown = rightBumperCoolDown - 1;
          }
          else{
            rightBumper.setAttribute('color', 'blue');
          }

          if(topBumperCoolDown > 0){
            topBumperCoolDown = topBumperCoolDown - 1;
          }
          else{
            topBumper.setAttribute('color', 'purple');
          }
          if(bottomBumperCoolDown > 0){
            bottomBumperCoolDown = bottomBumperCoolDown - 1;
          }
          else{
            bottomBumper.setAttribute('color', 'green');
          }
          
          if(topPaddleCoolDown > 0){
            topPaddleCoolDown = topPaddleCoolDown - 1;
          }
          else{
            topPaddle.setAttribute('color', 'purple');
          }
          if(bottomPaddleCoolDown > 0){
            bottomPaddleCoolDown = bottomPaddleCoolDown - 1;
          }
          else{
            bottomPaddle.setAttribute('color', 'green');
          }

          //move the sphere
          mySpherePosition.x = mySpherePosition.x + mySphereVector.x;
          mySpherePosition.y = mySpherePosition.y + mySphereVector.y;
          mySpherePosition.z = mySpherePosition.z + mySphereVector.z;
          mySphere.setAttribute('position', mySpherePosition.x + ' ' + mySpherePosition.y + ' ' + mySpherePosition.z);
          //console.log("mySphere.getAttribute('position') == ", mySphere.getAttribute('position'));

          //randomly change the vectors of the paddles
          //top paddle
          var randomNumber = Math.floor(Math.random() * 30);
          if(randomNumber == 0){
            topPaddleVector.x = 0;
          }
          else if(randomNumber == 1){
            topPaddleVector.x = -0.02;
          }
          else if(randomNumber == 2){
            topPaddleVector.x = 0.02;
          }
          //bottom paddle
          randomNumber = Math.floor(Math.random() * 30);
          if(randomNumber == 0){
            bottomPaddleVector.x = 0;
          }
          else if(randomNumber == 1){
            bottomPaddleVector.x = -0.02;
          }
          else if(randomNumber == 2){
            bottomPaddleVector.x = 0.02;
          }

          //move the paddles
          topPaddlePosition.x = topPaddlePosition.x + topPaddleVector.x;
          topPaddlePosition.y = topPaddlePosition.y + topPaddleVector.y;
          topPaddlePosition.z = topPaddlePosition.z + topPaddleVector.z;
          bottomPaddlePosition.x = bottomPaddlePosition.x + bottomPaddleVector.x;
          bottomPaddlePosition.y = bottomPaddlePosition.y + bottomPaddleVector.y;
          bottomPaddlePosition.z = bottomPaddlePosition.z + bottomPaddleVector.z;          
          //if the paddle reaches the edge then reset it's location
          if(topPaddlePosition.x < (minX + (bumperWidth / 2) + (topPaddleProperties.depth / 2))){
            topPaddlePosition.x = minX + (bumperWidth / 2) + (topPaddleProperties.depth / 2);
          }
          if(topPaddlePosition.x > (maxX - (bumperWidth / 2) - (topPaddleProperties.depth / 2))){
            topPaddlePosition.x = (maxX - (bumperWidth / 2) - (topPaddleProperties.depth / 2));
          }
          if(bottomPaddlePosition.x < (minX + (bumperWidth / 2) + (topPaddleProperties.depth / 2))){
            bottomPaddlePosition.x = minX + (bumperWidth / 2) + (topPaddleProperties.depth / 2);
          }
          if(bottomPaddlePosition.x > (maxX - (bumperWidth / 2) - (topPaddleProperties.depth / 2))){
            bottomPaddlePosition.x = (maxX - (bumperWidth / 2) - (topPaddleProperties.depth / 2));
          }
          topPaddle.setAttribute('position', topPaddlePosition.x + ' ' + topPaddlePosition.y + ' ' + topPaddlePosition.z);
          bottomPaddle.setAttribute('position', bottomPaddlePosition.x + ' ' + bottomPaddlePosition.y + ' ' + bottomPaddlePosition.z);

          //update the text of the <span>
          myText.textContent = 'Ball Location: X = ' + mySpherePosition.x.toFixed(2) + ", Y = " + mySpherePosition.y.toFixed(2) + ", Z = " + mySpherePosition.z.toFixed(2);
          
          //detect collisions
          //if the sphere hits a boundary, then reverse it's vector
          if(mySpherePosition.x >= maxX){
            //console.log("The ball bounced off the max X border.")
            mySphereVector.x = mySphereVector.x * -1;
            rightBumper.setAttribute('color', 'yellow');
            rightBumperCoolDown = 10;
          }
          if(mySpherePosition.x <= minX){
            //console.log("The ball bounced off the min X border.")
            mySphereVector.x = mySphereVector.x * -1;
            leftBumper.setAttribute('color', 'yellow');
            leftBumperCoolDown = 10;
          }
          if(mySpherePosition.y >= maxY){
            //console.log("The ball bounced off the max Y border.")
            mySphereVector.y = mySphereVector.y * -1;
          }
          if(mySpherePosition.y <= minY){
            //console.log("The ball bounced off the min Y border.")
            mySphereVector.y = mySphereVector.y * -1;
          }
          if(mySpherePosition.z >= maxZ){
            //console.log("The ball bounced off the max Z border.")
            mySphereVector.z = mySphereVector.z * -1;
            bottomBumper.setAttribute('color', 'red');
            bottomBumperCoolDown = 10;
            //increment the player's score
            player2Score = player2Score + 1;
            console.log("Player 2 score == ", player2Score);
            player2ScoreText.setAttribute('text', 'value: Player 2: ' + player2Score + ' points');
          }
          if(mySpherePosition.z <= minZ){
            //console.log("The ball bounced off the min Z border.")
            mySphereVector.z = mySphereVector.z * -1;
            topBumper.setAttribute('color', 'red');
            topBumperCoolDown = 10;
            //increment the player's score
            player1Score = player1Score + 1;
            console.log("Player 1 score == ", player1Score);
            player1ScoreText.setAttribute('text', 'value: Player 1: ' + player1Score + ' points');
          }
          //if the sphere hits a paddle, then reverse it's vector
          //top paddle
          if(
            ((mySpherePosition.x) > (topPaddlePosition.x + mySphereProperties.radius - (topPaddleProperties.depth / 2)))
            && ((mySpherePosition.x + mySphereProperties.radius) < (topPaddlePosition.x + (topPaddleProperties.depth / 2)))
            && ((mySpherePosition.z + mySphereProperties.radius) > (topPaddlePosition.z - (topPaddleProperties.height / 2)))
            && ((mySpherePosition.z + mySphereProperties.radius) < (topPaddlePosition.z + (topPaddleProperties.height / 2)))
            ){
            //console.log("The ball bounced off the top paddle.")
            mySphereVector.z = mySphereVector.z * -1;
            topPaddle.setAttribute('color', 'yellow');
            topPaddleCoolDown = 10;
          } 
          //bottom paddle
          if(
            ((mySpherePosition.x) > (bottomPaddlePosition.x + mySphereProperties.radius - (bottomPaddleProperties.depth / 2)))
            && ((mySpherePosition.x + mySphereProperties.radius) < (bottomPaddlePosition.x + (bottomPaddleProperties.depth / 2)))
            && ((mySpherePosition.z + mySphereProperties.radius) > (bottomPaddlePosition.z - (bottomPaddleProperties.height / 2)))
            && ((mySpherePosition.z + mySphereProperties.radius) < (bottomPaddlePosition.z + (bottomPaddleProperties.height / 2)))
            ){
            //console.log("The ball bounced off the bottom paddle.")
            mySphereVector.z = mySphereVector.z * -1;
            bottomPaddle.setAttribute('color', 'yellow');
            bottomPaddleCoolDown = 10;
          } 

        }, intervalLength);

      }
    </script>

  </head>

  <!-- start the body of your page -->
  <body style='margin : 0px; overflow: hidden;'>

    <!-- add some info at the top of the page -->
    <div style='top: 0px; width:100%; text-align: center; z-index: 1; color: white; background-color: #444444;'>
      AR Pong
    </div>    

    <!-- Define your 3d scene and enabled ar.js -->
    <a-scene debug embedded arjs='trackingMethod: best; debugUIEnabled: false;'>

      <!-- Create a anchor to attach your augmented reality -->
      <a-anchor hit-testing-enabled='true'>

        <!-- Adding augmented reality items here -->

        <!--text fit onto a plane -->
        <a-plane
          id = "centerTextLabel"
          geometry="primitive: plane; width: 1; height: 1; height: auto"
          material="opacity: 0.5; color: white;"
          position='0 0.25 0'>
          <a-entity id="planeText" position='0.8 0 0' rotation='290 0 0' scale='2 2 2' text="value: AR Pong" align-"center"></a-entity>
        </a-plane>
        <a-plane
          id = "player1Label"
          geometry="primitive: plane; width: 1; height: 1; height: auto"
          material="opacity: 0.5; color: white;" 
          position='0 0 1.2'>
          <a-entity id="player1ScoreText" position="0 0 0 " rotation='290 0 0' scale='2 2 2' text="value: Player 1" align-"center"></a-entity>
        </a-plane>
        <a-plane
          id = "player2Label"
          geometry="primitive: plane; width: 1; height: 1; height: auto"
          material="opacity: 0.5; color: white;" 
          position='0 0 -1.2'>
          <a-entity id="player2ScoreText" position="0 0 0 " rotation='290 0 0' scale='2 2 2' text="value: Player 2" align-"center"></a-entity>
        </a-plane>

        <!-- Basic Box -->             
        <!-- see: https://aframe.io/docs/0.8.0 -->
        <!-- Bumpers -->
        <a-box id="leftBumper" rotation="0 0 0" position='-1 0.05 0' depth="1.95" height="0.1" width="0.1" material='opacity: 0.9; side:double; color:blue;'></a-box>
        <a-box id="rightBumper" rotation="0 180 0" position='1 0.05 0' depth="1.95" height="0.1" width="0.1" material='opacity: 0.9; side:double; color:blue;'></a-box>
        <a-box id="topBumper" rotation="0 90 0" position='0 0.05 -1' depth="1.95" height="0.1" width="0.1" material='opacity: 0.9; side:double; color:purple;'></a-box>
        <a-box id="bottomBumper" rotation="0 270 0" position='0 0.05 1' depth="1.95" height="0.1" width="0.1" material='opacity: 0.9; side:double; color:green;'></a-box>
        <!-- Paddles -->
        <a-box id="topPaddle" rotation="0 90 0" position='0 0.05 -0.86' depth="0.49" height="0.1" width="0.1" material='opacity: 0.9; side:double; color:purple;'></a-box>
        <a-box id="bottomPaddle" rotation="0 270 0" position='0 0.05 0.86' depth="0.49" height="0.1" width="0.1" material='opacity: 0.9; side:double; color:green;'></a-box>

        <!-- Basic Sphere --> 
        <!-- see: https://aframe.io/docs/0.8.0/primitives/a-sphere.html -->
        <a-sphere id="mySphere" position='0 0 0' color="yellow" radius="0.05"></a-sphere>

      </a-anchor>

      <!-- Define a static camera -->
      <a-camera-static/>

    </a-scene>

    <!-- add some info at the bottom of the page -->
    <div>
      <span id="myText" style='z-index: 1; color: white; position: fixed; left: 50px; bottom: 10px; background-color: #444444;'>Ball coordinates will appear here.</span>
    </div>

  </body>

</html>
