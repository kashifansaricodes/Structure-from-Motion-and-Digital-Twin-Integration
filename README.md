# (Structure from Motion) 3D Reconstruction and Digital Twin Integration  

## Overview  
This project involves creating a high-quality 3D digital twin of a JBL speaker, starting from image capture to its final integration into simulation environments like Gazebo and Isaac Sim. The workflow includes structure-from-motion (SfM) techniques, 3D point cloud processing, and mesh optimization for simulation-ready models.  

---

<div style="display: flex; justify-content: space-around;">
  <img src="https://github.com/user-attachments/assets/d7f318a0-a1d2-4d0f-8a02-4abd00f62118" alt="Image 1" width="45%" />
  <img src="https://github.com/user-attachments/assets/8a6898d6-74ca-416e-8e62-b8d435dde0ba" alt="Image 2" width="45%" />
</div>


![1734672723911](https://github.com/user-attachments/assets/7173907b-854b-45cf-b068-11078623fb3a)

![1734668970073](https://github.com/user-attachments/assets/69e3d7d9-31b0-4e9f-a83f-b6beb552bd24)



## Workflow  

### 1. Image Capture  
- Captured high-resolution images of the JBL speaker from multiple angles.  
- Ensured optimal lighting and minimal occlusions for accurate reconstruction.  

### 2. Structure-from-Motion (SfM) Pipeline  
- **Feature Detection and Matching:** Extracted key points and matched them across images.  
- **Camera Pose Estimation:** Determined relative positions and orientations of the cameras.  
- **Sparse Point Cloud Generation:** Reconstructed initial 3D points from matched features.  
- **Dense Reconstruction:** Enhanced the sparse point cloud to generate a dense representation.  

### 3. Point Cloud Refinement  
- Imported the dense point cloud into MeshLab for noise removal and accuracy improvement.  
- Refined point cloud data to ensure clean and precise geometry.  

### 4. 3D Mesh Conversion and Texturing  
- Converted the refined point cloud into a 3D mesh using Blender.  
- Applied high-resolution textures and optimized the mesh for simulation compatibility.  

### 5. Simulation Environment Integration  
- Imported the final textured and optimized digital twin into:  
  - **Gazebo:** For physics-based simulation and analysis.  
  - **Isaac Sim:** For advanced robotic simulation and visualization.  

## Tools and Technologies  
- **Structure-from-Motion:** OpenMVG/OpenMVS, COLMAP.  
- **Point Cloud Processing:** MeshLab.  
- **3D Modeling and Texturing:** Blender.  
- **Simulation Environments:** Gazebo, Isaac Sim.  

## Key Highlights  
- Achieved accurate 3D reconstruction with minimal noise.  
- Generated a simulation-ready digital twin suitable for robotics and analysis.  
- Demonstrated seamless integration into multiple simulation environments.  

## Repository Structure  
```bash  
.  
├── images/               # High-resolution input images  
├── sfm_pipeline/         # Scripts and tools for SfM processing  
├── point_cloud/          # Intermediate point cloud files  
├── meshes/               # Final 3D mesh and texture files  
├── simulation_files/    

# Installing Prerequisites

### Conda or Mamba Environment
```sh
conda create -n <name> python=3.9

or

mamba create -n <name> python=3.9
```

### Activate Environment
```sh
mamba activate <name>

or

conda activate <name>
```

### Install Packages
```sh
pip install numpy opencv-python

CMAKE_ARGS="-DOPENCV_ENABLE_NONFREE=ON" pip install -v --no-binary=opencv-contrib-python opencv-contrib-python
```

### Running the app (current Version)
```
cd src/v1
python featmatch.py --data_dir ../../data/fountain-P11/images/ --out_dir ../../data/fountain-P11/ --features SURF
python sfm.py --dataset fountain-P11 --features SURF --pnp_method SOLVEPNP_DLS
```

