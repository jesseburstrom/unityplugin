# unityplugin

Unity source ( Mind funny assets, taken from asset store as free assets :) ) for the client_system Flutter project.

It features websocket to communicate from flutter to unity web until issue is resolved. It is though interesting to learn how that can work anyway!
NodeJS server gets connected to Unity, sends back uuid which unity sends to flutter to use as id for server sending messages.
If connection abort it all repeats automatically so robust protocol!

I use Unity 2022.1.0b5 currently

![Editor Image](unity.jpg?raw=true "Server Database")

After build at flutter in build/web/UnityLibrary/index.html replace:
<canvas id="unity-canvas" width=960 height=600 style="width: 960px; height: 600px; background: #231F20"></canvas>
    <script src="Build/UnityLibrary.loader.js"></script>
            <script>
 
  with
  
 <script src="Build/UnityLibrary.loader.js"></script>
            <script>
              var width = (window.innerWidth-50);
              var height = (window.innerHeight-50);
              var canvas = document.createElement('canvas');
              canvas.id     = "unity-canvas";
              canvas.width  = width;
              canvas.height = height;
              canvas.style.width = width + "px";
              canvas.style.height = height + "px";
              canvas.style.background = "transparent";
              document.body.appendChild(canvas);

To maintain background transparency. Also the file TransparentBackground.jslib in assets folder is necessary.          
