## Development Of Advanced Temperature Interpolation Methods

### Problem Statement - 
Corning manufactures world-class ceramic substrates and particulate filters that form the core of exhaust emission control systems. The manufacturing process of these cylindrical ceramic blocks is akin to brick making. Soft clay material is extruded into cylinders of the desired shape and passed through a temperature-regulated furnace. During this heating process, the clay undergoes multiple chemical reactions—both exothermic and endothermic—that transform it from a soft “green” part into a hard and brittle “fired” part. 
However, these reactions occur non-uniformly within the block, leading to differential heating and non-uniform temperature variations. Structurally, this creates space-varying temperature fields that result in thermally induced stress fields. If any region within the cylindrical block exceeds the critical stress limit, cracks may form, which is highly undesirable. 
Due to the complexity of tracking or modeling internal chemical reactions, a more effective approach is to measure the temperature variation across the block and model the associated stresses to predict potential failures. However, temperature measurement presents its own challenges. First, the high-temperature environment (in the order of hundreds of degrees Celsius) requires thermocouples (TCs) capable of withstanding extreme heat, which are expensive. Second, to insert TCs in the brittle ceramic material, drilling is performed. This prevents placement of TCs very close to each other. Additionally, malfunctioning TCs may produce unreliable temperature data, requiring the model to be robust enough to handle such scenarios without discarding the entire dataset.  
To simplify the problem, the axisymmetric nature of the cylinder and chemical reactions allow us to reduce the problem to a 2D analysis. Thus, instead of distributing TCs across the entire cylinder, we can limit the placement to one half of the cross-section.
One simple method for temperature interpolation is bilinear interpolation, where the temperature at an intermediate location within four points is calculated as the weighted average of the measured values from neighboring points However, this approach has limitations. It assumes linear temperature variation within the part, which is not accurate due to highly nonlinear reactions.
<img width="838" height="568" alt="image" src="https://github.com/user-attachments/assets/6f962b27-2ae0-4f38-9fa6-8c3739448beb" />
<img width="1319" height="615" alt="image" src="https://github.com/user-attachments/assets/72c79879-149f-4876-9232-0e05dd3b6447" />

Time varying temperature data for 15 measured locations (provided as Data A, with arrangement similar to Figure 2(a)) is the input for the model. Corresponding temperature data for 120 interpolated locations (similar to Figure 2(b)) is also provided. This data is used to compare the output of the model. Once we established our model, we used it to interpolate temperatures to 120 points in arrangement for another set of 15 TCs (Data B). 
Material properties: 
a. Part geometry: 
i. For Data A: 1m diameter, 1m height  
ii. For Data B: 0.5 m diameter, 0.5 m height 
b. Isotropic conductivity – 1 W/m/K 
c. Density and heat capacity – 1700 kg/m3, 1000 J/kg/K 
d. External heat transfer coefficient – 20 W/m2/K
