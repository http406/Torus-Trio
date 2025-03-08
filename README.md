# Torus-Trio

### **What is the "Torus Trio" in This Code?**  
The "Torus Trio" in this code refers to the **three different torus shapes** displayed in the scene:  

1. **Ring Torus**:  
   - Created using `TorusGeometry(1, 0.5, 16, 100)`.  
   - This is a typical **doughnut shape** where the radius of the tube is smaller than the torus' main radius.  

2. **Horn Torus**:  
   - Created using `TorusGeometry(1, 1, 20, 100)`.  
   - This is a **self-touching torus** where the tube's radius is equal to the main radius.  

3. **Spindle Torus**:  
   - Created using `TorusGeometry(1, 0.6, 16, 100)`.  
   - This forms a **fat torus**, where the tube is larger than usual, giving it a thicker appearance.  

Each of these tori has a **rainbow-colored wireframe** and rotates around the X and Y axes.  

---

### **Mathematical Equation Behind the Torus**  
A **torus** is defined parametrically using the following equations in 3D space:

![Image](https://github.com/user-attachments/assets/13f1f924-15b0-4e58-90b7-b651b4c77597)

where:  
- \( R \) = Major radius (distance from center of torus to center of tube).  
- \( r \) = Minor radius (radius of the tube itself).  
- \( u \) and \( v \) are angles that vary from \( 0 \) to 2π.  
  - \( u \) controls rotation around the **main axis** (big circular loop).  
  - \( v \) controls rotation around the **tube** (small circular cross-section).  

### **How This Equation is Used in the Code**  
In Three.js, the **`TorusGeometry`** function generates vertices based on these equations:  
```js
new THREE.TorusGeometry(R, r, radialSegments, tubularSegments);
```
- **R (major radius)**: The main circle’s radius.  
- **r (minor radius)**: The thickness of the tube.  
- **radialSegments**: How many divisions around the main circle.  
- **tubularSegments**: How many divisions around the tube itself.  

For example:
```js
const ringTorusGeometry = new THREE.TorusGeometry(1, 0.5, 16, 100);
```
- **Major radius** = 1  
- **Minor radius** = 0.5  
- **16 radial segments** (vertical slices)  
- **100 tubular segments** (horizontal slices)  

This tells Three.js to **generate the torus shape** using the above equations.  

---

### **Footnote**  
🔵 The **Torus Trio** consists of three different torus shapes: Ring Torus, Horn Torus, and Spindle Torus.  
🟣 The **torus equation** uses trigonometry to define a 3D surface by sweeping a circle around another circle.  
🟢 **Three.js automates** this math via `TorusGeometry`, letting you define the major/minor radius and segment counts.  
