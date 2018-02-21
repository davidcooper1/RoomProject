# CS 4331-002 Virtual Reality - Project 1
-------------------

## Video Demonstration
-------------------
TODO: Make video and put it here.

## Demo Link
------------------
[Try the Demo Here](https://davidcooper1.github.io/RoomProject/)

## Application Features
-------------------

### Handling Click Events

TODO: Add in screenshot of TV being hovered over.

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
1.) Door
2.) Lightswitch
3.) Clock
4.) TV
5.) TV Stand
6.) Couch
7.) Bookshelf
8.) Pool Table
9.) Small Table
10.) Chair
11.) Chandelier
12.) Mug
13.) Rug
14.) Desk Lamp 
15.) Desk

## External Sources
[Seamless Carpet Texture](https://hhh316.deviantart.com/art/Seamless-Carpet-Texture-270563565)
[Seamless Beige Wall Texture](https://www.sketchuptextureclub.com/textures/architecture/plaster/painted-plaster/fallingwater-house-plaster-wall-texture-seamless-06925)
