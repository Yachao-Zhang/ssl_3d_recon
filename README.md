# Self-supervised 3D Reconstruction
Source code for the paper "From Image Collections to Point Clouds with Self-supervised Shape and Pose Networks".</br>
Accepted at *IEEE Conference on Computer Vision and Pattern Recognition (CVPR-20)*

## Dataset
We use the ShapeNet dataset in our experiments. We use the <a href="https://github.com/shubhtuls/drc/blob/master/docs/snet.md#rendering" target="_blank" >code</a> provided by Tulsiani et al. to obtain the rendered images and part segmentation maps. Download links for the ShapeNet point cloud dataset is provided below: <br>
ShapeNet pointclouds (~2.8 GB): https://drive.google.com/open?id=1cfoe521iTgcB_7-g_98GYAqO553W8Y0g <br>

Download the the folder, extract and move it into *data/*. Save the rendered images in *data/ShapeNet_rendered/*.<br>

## Usage

Install [TensorFlow](https://www.tensorflow.org/install/). We recommend installing version 1.3 so that the additional TensorFlow ops can be compiled. <br>
Clone the repository:
```shell
git clone https://github.com/klnavaneet/ssl_3d_recon.git
cd ssl_3d_recon
```

### Training

#### Geometric and Pose Consistency Loss only (OURS-CC Model)
Train the model using geometric and pose consistency losses. Nearest neighbour loss is not included. This corresponds to the OURS-CC model refered to in the paper. Adjust the hyperparameters as necessary. The default parameters used for the first stage of training are provided in the bash script.
```shell
bash run.sh
```

#### Complete model training (OURS-NN Model)
Train the model using all losses - geometric and pose consistency and nearest neighbour loss. This corresponds to the OURS-NN model referred to in the paper. Adjust the hyperparameters as necessary. The default parameters used for the first stage of training are provided in the bash script.
```shell
bash multiple_mask_run.sh
```

## Citation
If you make use of the code, please cite the following work:
```
@inproceedings{navaneet2019differ,
 author = {Navaneet, K L and Mathew, Ansu and Kashyap, Shashank and Hung, Wei-Chih and Jampani, Varun and Babu, R Venkatesh},
 booktitle = {IEEE Conference on Computer Vision and Pattern Recognition (CVPR)},
 title = {From Image Collections to Point Clouds with Self-supervised Shape and Pose Networks},
 year = {2020}
}
```