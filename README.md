# DeMoN: Depth and Motion Network

[![License](https://img.shields.io/badge/license-GPLv3-blue.svg)](LICENSE)

**A jupyter-ready, nvidia-docker version of DeMoN without vtk visualization**

**This is a folked project from https://github.com/lmb-freiburg/demon**

DeMoN is a ConvNet architecture for solving structure from motion from two views.
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

## run docker 
```bash
nvidia-docker run -it --privileged -p 8880:8880 masahirodll/demon-jupyter
```

note that 8880 is a port for jupyter

## Build instructions

```bash
# clone repo with submodules
git clone --recursive https://github.com/masahirodll/demon.git

# build lmbspecialops
DEMON_DIR=$PWD/demon
mkdir $DEMON_DIR/lmbspecialops/build
cd $DEMON_DIR/lmbspecialops/build
cmake .. # add '-DBUILD_WITH_CUDA=OFF' to build without gpu support
# (optional) run 'ccmake .' here to adjust settings for gpu code generation
make -j

# download weights
cd $DEMON_DIR/weights
./download_weights.sh
```

## run example
After running jupyter, go to example and run myExample.ipynb

## Data reader op & evaluation

The data reader op and the evaluation code have additional dependencies.
The code for the data reader is in the ```multivih5datareaderop``` directory. 
See the corresponding [readme](multivih5datareaderop/README.md) for more details.

For the evaluation see the example [```examples/evaluation.py```](examples/evaluation.py).
The evaluation code requires the following additional python3 packages, which can be installed with ```pip```:

```
h5py
minieigen
pandas
scipy
scikit-image
xarray
```
Note that the evaluation code also depends on the data reader op.



## License

DeMoN is under the [GNU General Public License v3.0](LICENSE.txt)

