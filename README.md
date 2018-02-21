# CS 4331-002 Virtual Reality - Project 1
-------------------

## Video Demonstration
-------------------
[![Image not found.](https://img.youtube.com/vi/K63kBKCB2Ho/0.jpg)](https://www.youtube.com/watch?v=K63kBKCB2Ho)

## Demo Link
------------------
[Try the Demo Here](https://davidcooper1.github.io/RoomProject/)

## Application Features
-------------------

### Handling Click Events

![A Pic Was Supposed to Go Here](https://github.com/davidcooper1/RoomProject/raw/master/screenshots/Click.png)

All click events in this program are handled by a three step process.

#### Step 1:
Initialize the camera primitive with the cursor attribute and an associated raycaster.
````html
<a-camera universal-controls>
      <a-entity raycaster="far: 150; objects: .intersectable" cursor geometry="primitive: ring; radiusOuter: 0.015;
       radiusInner: 0.01; segmentsTheta: 32" material="color: #283644; shader: flat" position="0 0 -0.75"></a-entity>
</a-camera>
````
This raycaster is set to check for intersections only with entities that match the selector ".intersectable", so entities that will be involved in click events must be a part of this class!

#### Step 2:
Make all entities that are going to be handling click events part of the "intersectable" class, and give them a unique component tag.
````html
<a-entity door-toggle class="intersectable" position="-15 2.5 8" rotation="0 0 0">...</a-entity>
````
In this example, the entity is being given the "door-toggle" component tag.

#### Step 3:
The final step is to register the component tag!

````javascript
AFRAME.registerComponent("door-toggle", {
    init: function() {
        var open = false;
        var self = this.el;
        self.addEventListener("click", function(evt) {
            ... // Click handler code here.
        })
    }
});
````
With the example code provided above every entity with the "door-toggle" component tag will be given the same click event listener. 

### Model List
1.) Door</br>
2.) Lightswitch</br>
![A Pic Was Supposed to Go Here](https://github.com/davidcooper1/RoomProject/raw/master/screenshots/DoorAndSwitch.png) 
3.) Desk</br>
4.) Desk Lamp</br>
5.) Mug</br>
![A Pic Was Supposed to Go Here](https://github.com/davidcooper1/RoomProject/raw/master/screenshots/DeskSetup.png)
6.) Couch</br>
7.) Entertainment Center</br>
8.) TV</br>
![A Pic Was Supposed to Go Here](https://github.com/davidcooper1/RoomProject/raw/master/screenshots/CouchSetup.png)
9.) Book Shelf</br>
10.) Pool Table</br>
![A Pic Was Supposed to Go Here](https://github.com/davidcooper1/RoomProject/raw/master/screenshots/ShelfAndTable.png)
11.) Ceiling Lamp</br>
12.) Clock</br>
![A Pic Was Supposed to Go Here](https://github.com/davidcooper1/RoomProject/raw/master/screenshots/ClockAndLights.png)
13.) Dining Table</br>
14.) Chair</br> 
![A Pic Was Supposed to Go Here](https://github.com/davidcooper1/RoomProject/raw/master/screenshots/TableSetup.png)
15.) Rug</br>
![A Pic Was Supposed to Go Here](https://github.com/davidcooper1/RoomProject/raw/master/screenshots/Rug.png)

## External Sources
--------------------
### Textures
[Seamless Carpet Texture](https://hhh316.deviantart.com/art/Seamless-Carpet-Texture-270563565)</br>
[Seamless Beige Wall Texture](https://www.sketchuptextureclub.com/textures/architecture/plaster/painted-plaster/fallingwater-house-plaster-wall-texture-seamless-06925)</br>
[Seamless White Wall Texture](http://seamless-pixels.blogspot.com/2012/09/free-seamless-stucco-wall-plaster.html)</br>
[Seamless Glass Wall Texture](https://1-background.com/glass_1.htm)</br>
[Seamless Grass Texture](https://mushin3d.deviantart.com/art/Seamless-tileable-Grass-texture-516838656)</br>
[Seamless Rug Texture](http://textures101.com/view/2236/Carpet/Carpet_Seamless)

### Models
[Sofa](https://skfb.ly/6sVEt)</br>
[Ceiling Lamp](https://skfb.ly/6uQAH)</br>
[TV](https://skfb.ly/68ZMs)</br>
[Desk](https://skfb.ly/XB9H)</br>
[Entertainment Center](https://skfb.ly/69DnS)</br>
[Pool Table](https://skfb.ly/VVr8)</br>
[Chair](https://skfb.ly/6v6XY)</br>
[Dining Table](https://skfb.ly/6v6WT)</br>
[Lamp](https://skfb.ly/6wqyI)</br>
[Clock](https://skfb.ly/6rvzQ)</br>
[Mug](https://skfb.ly/ZKn9)
