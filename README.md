[![License](https://img.shields.io/badge/license-GPLv3-blue.svg)](LICENSE)

**A jupyter-ready, nvidia-docker version of DeMoN without vtk visualization**

**Intended for personal project, thus not a perfect guide**

**Assume you had already installed nvidia-docker in your machine with CUDA enabled**

**This is a folked project from https://github.com/lmb-freiburg/demon**

## run docker

```bash
nvidia-docker run -it -p 8880:8880 masahirodll/demon-jupyter
```

note that 8880 is a port for jupyter

## run example

After running jupyter, go to example/ and run myExample.ipynb

## About DeMoN

DeMoN is a ConvNet architecture for solving structure from motion from two views proposed by Ummenhofer et al.
It estimates the depth and relative camera motion for pairs of images.

![Teaser](teaser.png)

If you use this code for research please cite:
   
    @InProceedings{UZUMIDB17,
      author       = "B. Ummenhofer and H. Zhou and J. Uhrig and N. Mayer and E. Ilg and A. Dosovitskiy and T. Brox",
      title        = "DeMoN: Depth and Motion Network for Learning Monocular Stereo",
      booktitle    = "IEEE Conference on Computer Vision and Pattern Recognition (CVPR)",
      month        = " ",
      year         = "2017",
      url          = "http://lmb.informatik.uni-freiburg.de//Publications/2017/UZUMIDB17"
    }

See the [project website](https://lmb.informatik.uni-freiburg.de/people/ummenhof/depthmotionnet) for the paper and other material.

## License

All contents belong to original authors (lmb-freiburg).

DeMoN is under the [GNU General Public License v3.0](LICENSE.txt)

