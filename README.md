
<div align="center">


  <h1 align="center">
        3D Depth Mapping via MiDaS
    </h1>
    <p align="center"> 
        <i><b>Monocular Depth Estimation with a Single Image (MiDaS)</b></i>
        <br /> 
    </p>

[![Github][github]][github-url]

<img src="https://res.cloudinary.com/dnz16usmk/image/upload/v1708700605/messi_vs_everyone.gif" alt="MiDas before and after" width="100" height="100"  />


 </div>

<br/>

## Table of Contents

  <ol>
    <a href="#about">📝 About</a><br/>
    <a href="#how-to-build">💻 How to build</a><br/>
    <a href="#tools-used">🔧 Tools used</a>
        <ul>
        </ul>
    <a href="#contact">👤 Contact</a>
  </ol>

<br/>

## 📝About

Using PyTorch's **MiDaS** model and Open3D's **point cloud** to map a scene in 3D.

### `main.py`

- Entry point
- Integrates the below 3 functionalities


### `depth_estimation` 

- Core logic for depth estimation (`depth_estimation/depthmap.py`)
- `DepthMapper` class responsible for setting up and utilizing a depth estimation model.
- Loads a pre-trained model (MiDaS model variants) based on the specified accuracy level, performs image transformations, and estimates the depth map from an input image.


### `imaging` 

- Handles image processing tasks (`image_processing/image_process.py`)
- `ImageProcessor`class loads, validates, and manipulates image data. 
- It includes functionalities such as loading images from disk, applying color maps, and displaying images. 
- This class is utilized to handle the input and output images in the depth mapping process.


### `point_cloud` 

- Renders point clouds from the depth data generated by the depth mapping process (`point_cloud/cloudrender.py`).
- `CloudRenderer` class in  processes the depth data to generate 3D points and renders them as a point cloud or voxel grid. 
- This visualization helps in understanding the spatial relationships in the scene represented by the depth map.


## 💻 How to build

### Requirements

```bash
pip install -r requirements.txt
```

### Deploy

When running the model on a chosen image, swap out the `PHOTO` placeholder with the complete file path and extension of the target image. For the `--accuracy_level` setting, select an integer from 1 to 3 (where 1 delivers the quickest inference speed but with less accuracy, and 3 ensures the highest accuracy, albeit with a slower inference speed).

```bash
python3 main.py --accuracy_level [1|2|3] --input_img FILENAME
```


## 🔧Tools Used

<img
src="https://img.shields.io/badge/pyTorch-EE4C2C?style=for-the-badge&logo=pyTorch&logoColor=white&color=EE4C2C"
alt="pyTorch"
/>
<img
src="https://img.shields.io/badge/MiDaS-EE4C2C?style=for-the-badge&logoColor=white&color=00b5ff"
alt="MiDaS"
/>
<img
src="https://img.shields.io/badge/OpenCV-FF6F00?style=for-the-badge&logo=opencv&logoColor=0166ff&color=black"
alt="OpenCV"
/>
<img
src="https://img.shields.io/badge/Matplotlib-3776AB?style=for-the-badge&logoColor=white&color=3776AB"
alt="matplotlib"
/>

<img
  src="https://img.shields.io/badge/C++-4F4F4F?style=for-the-badge&color=black"
  alt="Open3D"
/>

## 👤Contact

<!-- Replace placeholders with your actual contact information -->
[![Email][email]][email-url]
[![Twitter][twitter]][twitter-url]

<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->

[email]: https://img.shields.io/badge/me@vd7.io-FFCA28?style=for-the-badge&logo=Gmail&logoColor=00bbff&color=black
[email-url]: #
[github]: https://img.shields.io/badge/Github-2496ED?style=for-the-badge&logo=github&logoColor=white&color=black
[github-url]: https://github.com/vdutts7/3d-mappify
[twitter]: https://img.shields.io/badge/Twitter-FFCA28?style=for-the-badge&logo=Twitter&logoColor=00bbff&color=black
[twitter-url]: https://twitter.com/vdutts7/