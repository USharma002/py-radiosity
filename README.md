# Py-Radiosity

Trying to implement Radiosity using Mitsuba Renderer

---

# Radiosity

In 3D computer graphics, radiosity is an application of the finite element method to solving the rendering equation for scenes with surfaces that reflect light diffusely.  
The basic radiosity method has its basis in the theory of thermal radiation, since radiosity relies on computing the amount of light energy transferred among surfaces.  
In order to simplify computations, the method assumes that all scattering is perfectly diffuse.

---

## Jupyter Notebook

### **(This is currently a work in progress)**

I'm currently implementing a basic radiosity algorithm and using Mitsuba for rendering.

This is kind of a 'work around' since I am doing the following which I'll eventually improve:

- Loading hte mitsuba scenes and saving the classes like **Rectangle** and **Cube** as ```obj``` files so I can load them as **Mesh** class and use ```use_attribute```
- Once loaded, I extract all the necessary information of the geometry to calculate the radiosity (vertices, normals, reflectivity, emission)
- After that I am adding a ```face_radiosity``` attribute to each triangle and putting the value of calculated radiosity in that

### Refinedment has beed removed for raw mitsuba scene but can be done for ply files as given in older version
#### Triangle before and after refinement (Worked in older version Removed in new one):
<p float="left">
  <img src="assets/tri.png" alt="Triangle" width="300"/>
  <img src="assets/rtri.png" alt="Refined Triangle" width="300"/>
</p>

#### Scene before and after refinement:
<p float="left">
  <img src="assets/cbox.png" alt="Cbox" width="300"/>
  <img src="assets/cbox_refined.png" alt="Cbox Refined" width="300"/>
</p>

- After refining each triangle, I'm making $E_i$ (Energy emitted) based on whether it was part of a light source or not.
- I'm then calculating the form factor and radiosity value for each triangle.

---

### ✅ What works:

- I'm getting a decent image for simple scenes as of now.
- Some of the components have been vectorized
- A barebones visualization of triangles is provided
- I am able to extract color from texture for albedo

---

### ❌ What needs to be fixed/implemented:
- Adaptive patching so we don't have a lot of unnecessary triangles.
- The code for radiosity and needs to be improved.
- Some class of mesh/primitives are not laoded properly
- I'm implementing in *Python* for learning now, will change this to *CUDA* once I get the time.

---

## Some Demo Renders: Radiosity (Left) and Path Tracing (Right)

### Bedroom
<p>
  <img src="assets/bedroom_radiosity.png" alt="Radiosity Result" width="100%"/>
</p>

### Bathroom
<p>
  <img src="assets/bathroom_radiosity.png" alt="Radiosity Result" width="100%"/>
</p>

### Kitchen
<p>
  <img src="assets/kitchen_radiosity.png" alt="Radiosity Result" width="100%"/>
</p>

### Cornell Box \[Older version\]

<p>
  <img src="assets/cbox_radiosity.png" alt="Radiosity Result" width="100%"/>
</p>

---

### Cornell Box with Sphere

<p float="left">
  <img src="assets/cbox_sphere_radiosity.png" alt="Radiosity Result" width="300"/>
  <img src="assets/cbox_sphere_rt.png" alt="Ray Tracing Result" width="300"/>
</p>

---

### Final Scene

<p float="left">
  <img src="assets/finalscene_radiosity.png" alt="Radiosity Result" width="300"/>
  <img src="assets/final_scene_rt.png" alt="Ray Tracing Result" width="300"/>
</p>

## GIF of passes (Left: Constant, Right:Interpolated) [Outdated! Will update soon]

<p float="left">
  <img src="assets/progressive_cbox.gif" alt="CBox Radiosity GIF" width="300"/>
  <img src="assets/progressive_cbox_smooth.gif" alt="CBox Path Tracing GIF" width="300"/>
</p>

<p float="left">
  <img src="assets/progressive_cboxs.gif" alt="CBox Sphere Radiosity GIF" width="300"/>
  <img src="assets/progressive_cboxs_smooth.gif" alt="CBox Sphere Path Tracing GIF" width="300"/>
</p>

