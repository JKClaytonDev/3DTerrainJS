I am not using WebGL's 3D capabilities for this project...

-instead, I am using a custom 3D projection algorithm to render this. 

What?
3D Projection is giving a computer (with a 2D screen) 3D coordinates (the position of an object, the position of the camera, and the direction of the camera) and then showing on the 2D screen where that object would be on the camera. 

Why?
I think it's important to know about low-level 3D engine code. It gives you respect for the fact that some video game engines can render millions of polygons without breaking a sweat. Every single point needs to go through a very complicated projection algorithm (like this one except probably a lot more complicated and optimized) before the engine even starts postprocessing or drawing the screen. 

How?
It requires all the coordinates for every point to be read every frame and sorted based on distance. I modified the algorithm to run better on most computers due to all the data it's crunching, but it means there is a loss in accuracy and the camera can't look up/down. I've also implemented a (sort of) version of shaders to differentiate water and grass.
