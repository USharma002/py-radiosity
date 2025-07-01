<<<<<<< HEAD
# py-radiosity
Trying to imeplement Radiosity using Mitsuba Renderer
=======
# Radiosity

In 3D computer graphics, radiosity is an application of the finite element method to solving the rendering equation for scenes with surfaces that reflect light diffusely.  
The basic radiosity method has its basis in the theory of thermal radiation, since radiosity relies on computing the amount of light energy transferred among surfaces. 
In order to simplify computations, the method assumes that all scattering is perfectly diffuse. 

## Jupyter notebook

(This is currently a work in progress)
I'm currently implementing a basic radiosity algorithm and using mitsuba for rendering.

This is kind of a 'work around' since I am doing following which I'll eventually improve:
- I'm saving each triangle in obj file so I can load in mitsuba (can't create triangles directly or group with each triangle with different radiance)
- After loading each triangle, I'm making $E_i$ (Energy emitted)  based on whether it was part of a loght source or not
- I'm then caculating the form factor and radiosity value for each triangle
- (work around) I'm setting each triangle as a ligth source with radiosity value as radiance

What works:
- I'm getting a decent image for simple scenes as of now
- I'm able to load obj files (not just cornell box)

What needs to be fixed:
- I'm saving each triangle separately in obj file due to not being able to create a triangle in mitsuba directly (or I don't know how).
  Hopefully I'll implement my own rendering code or fix this for mitsuba somehow in future
- The code for radiosity is kind of bruteforce and need to be improved
- The obj loading is janky for now, will fix that soon
- I'm implementing in *Python* for learning now, will change this to CUDA once I get the time.
>>>>>>> 87c742bf4084aa73f1ebc60d10fd5ed082d14da3
