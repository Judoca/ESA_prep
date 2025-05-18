# DT notes:

Unit 1: https://github.com/Judoca/ESA_prep?tab=readme-ov-file#unit-1 <br>
Unit 2: https://github.com/Judoca/ESA_prep?tab=readme-ov-file#unit-2

## Unit 1:

### Applications of AR:

- Industry and construction:
    - to visualize, plan and train
    - real time simulations of physical assets
- Medical applications:
    - overlay critical information to the surgeons view, improving precision and outcomes
    - training simulations
- E commerce and Marketing:
    - Visualize products in their own environment before purchase
    - enriches the experience for marketing

### OpenGL:

- used to render 2D and 3D objects

- rendering pipline:
    - programmable stages of the pipeline are called shaders used for custom rendering effects
- primitives are the basiuc building blocks for rendering graphics
    - effects performance and ease of use

### Digital Twin and Extended reality:

- refers to a digital replica of a physical object, allowing real time monitoring and simulation
- Extended reality (XR) encompasses AR, VR and mixed reality MR
- graphics effect the quality

### Graphics Pipeline Architecture:

- sequence of steps that tranform 3D objects to 2D images
    - vertex processing: each vertex is tranformed and colored for the next stage
    - clipping and primitive assembly: objects outside the view are clipped, remaining vertices are assembled into primitives
    - rasterization: converts primitives into fragments, determining which pixels are covered by each primitive
    - fragment processing: updates the frame buffer with color and depth information, applying effects like texture mapping

- **Vertex processing**
    - 1st stage, each vertex processed individually which allows for parallel processing
    - coordinate transforamations and color computations for each vertex
    - Output: set of tranformed vertices for next stage

- **Clipping and primitive assembly**
    - 2nd stage, remove objects that are outide the cameras field of view, only visible parts are processed
    - done by primitive-by-primitive basis, reduces number of calculations needed for invisible objects
    - Output: set of primitives whose projections appear in the image ready for rasterization

- **Rasterization**
    - also called scan conversion
    - 3rd stage, where the rasterizer determines which pixels in the frame buffer correspond to the primitives being rendered
    - each pixel that is affected by the primitive is updated with fragment information such as color and depth data
    - depth ensures that fragments behind other fragments are not rendered on top
    - Output: set of fragments for each primitive

- **Fragment Processing**
    - final stage, fragments are processed to update the frame buffer
    - operations like: texture mapping and blending
    - not all fragments will be visible due to occlusion -> depth testing performed to find out which should be visible


### Geometric concepts in 3D space:

- scalars: single values that represent magnitude
- vectros: represent magnitude and direction

- polygons:
    - multisided planar element that consists of vertices and edges
    - must not intersect (simple), convex (all interior angles less that 180), and flat (all vertices lie on the same plane)
    - triangulation is the process of diving polygons into triangles, which are the only primitives supported in modern OpenGL

### Concecpts of data flow in systems:

- Throughput: the rate of data flow through a system - how much data can be processed in a given time frame
- Latency: the time it takes a single data to travel to the system
- increase in the pipeline stages can increase latency and decrease throughput


### Abstract Data Types ADTs:

- theoretical concept that define a data type by its behavior from the point of view of the user, specifically the operations that can be performed on it
- allow for the seperation of interface and implementation, focus on what operations are available in stead of how they are implemented
- lists, stacks, queues, trees

### Affine Transformations:

- Affine space allows for the addition of vectors and points, as well as scalar multiplication of vectors, but not the addition of 2 points directly
- P = Q + alpha(R - Q)  ->  Q and R = points;   alpha = scalar
<br>

- Barycentric coorinates:
    - provide a way to express a point T in relation to points P, Q and R in the same plane
    - T(alpha, beta, gamma) = alpahP + betaQ + gammaR
    - useful in graphics for interpolation and rendering techniques

### Vector Opertaions:

- dot product: u.v = |u||v|cos(theta);  theta = angle between u and v vectors
- if u.v = 0; vectors are orthogonal, right angle between them
<br>

- cross product: results in a vector that is orthogonal to the plane formed by the original vectors, useful to calculate normals
<br>

- both products used to analyze forces and motion

### Homogeneous Coordinates and Transforms:

- allow for the representation of points and vectors in a 4D space, facilitating transformations using matrix operations
- tranformations in homogeneous can be complex, requiring tranformations for every point in a line segment

### Rigid and Non-rigid transformations:

- Rigid body transformations: include rotation and translation, preserve shape and volume of the object, do not alter geometry
- Non-rigid: scaling, resize the object, can be uniform or non-uniform. Have 6 degrees of freedom, independent scaling factors in different direcections
<br>

- Shear:
    - shearing tranformations represented by a sheer matrix alter shape of the objects without changing its area
- Concatenation:
    - Concatenations of transformations is where matrices A B and C can be arbitrary 4x4 matrices, optimizing transforms for multiple points

### Quaternions:

- complex numbers: operations related to 2D geometry mainly rotation
- quaternions extend complex numbers to 3D rotations
    - one real part and 3 imaginary parts
    - visualized as points in a 4D hypersphere

<hr>

## Unit 2:

