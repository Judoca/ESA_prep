# DT notes:

Unit 1: https://github.com/Judoca/ESA_prep?tab=readme-ov-file#unit-1 <br>
Unit 2: https://github.com/Judoca/ESA_prep?tab=readme-ov-file#unit-2 <br>
Unit 3: https://github.com/Judoca/ESA_prep?tab=readme-ov-file#unit-3 <br>
Unit 4: https://github.com/Judoca/ESA_prep?tab=readme-ov-file#unit-4 <br>

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

### Digital Twin

- virtual representations of physical entities - reflect their lifecycle stages (planning, manufacturing, operations and retirement)
- integrates models, data, connectivity, analysis and actions

### Types of digital twins:
- categories based on their use cases, complexity and the problems they address
    - discrete vs composite
    - product vs facility
    - simulation vs operational
    - analytics vs physics based

### Discrete Vs Composite:

- discrete = standalone entities, at the lowest level of abstraction
- composite = formed by combining multiple discrete twins to create a more complex functional asset
    - can represent systems of a system posing more complex lifecycle management

### Product Vs Facility:

- product = individually managed products
    - track product performance post shipping
    - collects operational data to inform product improvements
    <br>

- facility = entire manufacturing or production facilities
    - monitors entire facilities for comprehensive analysis
    - predicts maintainence and operational efficiencies
    - supports decision making process by providing real time data analytics

### Simulation Vs Operational:

- simulation = used in design phases
- operational = manages real time operations

### Analysis Vs Physics:

- Analysis = Utilize historic data and uses AI/ML models in order to make predictions
- Physics = rely on engineering principles and the laws of physics to simulate real world environments and predict performance

### Characteristics of Digital Twins:

- Physical and virtual entities
- Twinning rate: the frequency of the synchronisation between the physical and virtual twin, impacting the fidelity of it
- Bi-directional connection: data flows both ways bewteen the physcial and virtual environment, allowing for real time updates

### Digital Twin achitecture:

- Physical layer: represents the actual physical entity being monitored
    - sensors and actuators that gather and transmit the data about the physical object
    - accuracy relies on the quality of the data collected. <br>

- data tranfer and collective layer: responsible for gathering the data from the physical twin
    - ensures security and complicance with regulations during the transfer process <br>

- data storage and processing layer: stores and processes the collected data for analysis
    - employs data fusion techniques to combine data to enhance accuracy
    - supports real time analytics, trend analysis and data visualization to derive insights from the data <br>

- Communication layer:
    - tranfer data between the sensors and the digital twin, ensuring reliable and secure communication
    - uses bluetooth, wifi and industrial protocols like OPC UA <br>

- Cloud computing and storage layer:
    - provides high-performance computing resources necessary for complex simulations and data analytics
    - offers scalability and elasticity for the digital twins requirements

- Virtual Layer:
    - contain the digital models and simulations that replicate the physical assets behavior
    - continuously updated with real time data allowing for predictive analysis and operational optimization
    - integrates data analysis tools

### Key applications:

- energy sector: simulation of distributed energy resources (DER) to enhance grid management
- automotive industry: feedback for design improvements and predict maintainence
- healthcare: improvement treatment efficacy

### Motion tracking and sensor fusion:

- analyze human activities
- LIDAR and IMU sensor used 

### Technical aspects of digital twin systems:

- skeleton construction
- real time pose tracking

### Real time pose tracking:

- quaternions for orientation data
- used for joint rotation -> to ensure it is smooth and continuous

### Position tracking and drift correction:

- drift correction achieved by using detected foot positions of the bone segments, ensuring accuracy over time
- particle filter used to track position of the legs

### Metrics for evaluation:

- user learnability and system usability
- task completion time
- error rate

### Data Sources and models in digital twins:

- temporal or time series: time stamped data
- master data: slow changing data that describe assets
- transactional: production and maintainence records
<br>

- physics-based model
- analytical models
- visual models

### Digital thread:

- data aggregator across all lifecycles of the product
- traceable record for each product assembly and its components capturing all interactions and assembly
- Digital twins are built on the information provided by the digital thread

### Digital Twin Vs Digital Thread:

- twin: focuses on specific use case
- thread: comprehensive view across the whole lifecycle

### Stakeholders:

- catgorised into two high level scenarios: asset users and manufacturing assets
- Original Equipment Manufacturers are increasingly seekign access to real time usage
- key stakeholders include manufacturers, engineers and data analysts

<hr>

## Unit 3:

### Simulation:

- imitation of real world systems operation over time, allowing for experimentation without real world consequences
- understand and analyze complex systems and their interactions
- enable testing of various changes and its effects on the system
- learnings from simulations may lead to enhancements in system performance and efficiency
<br>

- not needed when a problem can be solved with resources that are already available
- direct experiments may be more cost effective

### Advantages and disadvantages of simulation:

- Adv: allows to test new policies without disrupting real systems, saving resources
- Disadv: building simulation models require expertise, results hard to interpret and the process can be time-consuming and costly

### Tools of simulation:

- MATLAB/Simulink: Mathematical modelling and simulation
- FlexSim: modelling complex systems in various industries
- OpenModelica: open source modeling and simulation environment

### Areas of Application:

- Manufacturing: bottleneck detection, automated model development
- Healthcare: improve hospital performance and modeling inventory
- Military: logisitcs distribution

### Systems:

- group of interacting objects that work together to perform a common goal
- system boundaries: external factors that affect the systems operation
- components of a system:
    - entities: objects of interest
    - attributes: properties of entities
    - activities: time based procedures
<br>

- State variables:
    - describe the system at a specific point in time
    - events trigger change in state variables
<br>

- Response time calculation: Clock time - Arrival time

### Classification of Systems:

- Discrete vs continuous:
    - discrete: state variables cahnge at specific intervals
    - continuous: state variables change continously

- types of models:
    - physical
    - mathematical
    - simulation
    - static vs dynamic
    - deterministics vs stochastic

### Simulation process and benefits:

- four phases: problem formulation, model building, running the model, implementation
<br>

- benefits:
    - risk free testing
    - performance optimisation
    - cost efficiency
    - handling variability

### Discrete Event Simulation DES:

- method used to model dynamic systems over time
- characteristics:
    - dynamic systems
    - stochastic nature
    - snapshot-based evolution
- analyze and optimise complex systems
- model: abstract representation of the system

### Steps in building a digital twin model:

- data collection
- model tanslation
- verification and validation
- experimental design
- production runs and analysis
- documentation of the model
- implementation of simulation

### System modeling and simulation:

- event scheduling and time advance algorithm: ensure events occus in the correct order
- Future Event List: efficient event management
- bootstrapping process: generates a stream of future events based on current time


### Stopping condition:

- fixed time intervals

### Input Modeling:

- 