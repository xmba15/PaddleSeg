# Semantic Connectivity-aware Segmentation With a Large-Scale Teleconferencing Video Dataset
Official resource for the paper *PP-HumanSeg: Connectivity-Aware Portrait Segmentation With a Large-Scale Teleconferencing Video Dataset*. [[Paper](https://arxiv.org/abs/2112.07146) | [Poster](https://paddleseg.bj.bcebos.com/dygraph/humanseg/paper/12-HAD-poster.pdf) | [YouTube](https://www.youtube.com/watch?v=FlK8R5cdD7E)]

## Semantic Connectivity-aware Learning
SCL (Semantic Connectivity-aware Learning) framework, which introduces a SC Loss (Semantic Connectivity-aware Loss) to improve the quality of segmentation results from the perspective of connectivity. Support multi-class segmentation. [[Source code](../../paddleseg/models/losses/semantic_connectivity_learning.py)]

SCL can improve the integrity of segmentation objects and increase segmentation accuracy. The experimental results on our Teleconferencing Video Dataset are shown in paper, and the experimental results on Cityscapes are as follows:

### Perfermance on Cityscapes
| Model | Backbone | Learning Strategy | GPUs * Batch Size(Per Card)| Training Iters | mIoU (%) | Config |
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
|OCRNet|HRNet-W48|-|2*2|40000|76.23| [config](../../configs/ocrnet/ocrnet_hrnetw48_cityscapes_1024x512_40k.yml) |
|OCRNet|HRNet-W48|SCL|2*2|40000|78.29(**+2.06**)|[config](../../configs/ocrnet/ocrnet_hrnetw48_cityscapes_1024x512_40k_SCL.yml) |
|FCN|HRNet-W18|-|2*4|80000|77.81|[config](../../configs/fcn/fcn_hrnetw18_cityscapes_1024x512_80k_bs4.yml)|
|FCN|HRNet-W18|SCL|2*4|80000|78.68(**+0.87**)|[config](../../configs/fcn/fcn_hrnetw18_cityscapes_1024x512_80k_bs4_SCL.yml)|
|Fast SCNN|-|-|2*4|40000|56.41|[config](../../configs/fastscnn/fastscnn_cityscapes_1024x1024_40k.yml)|
|Fast SCNN|-|SCL|2*4|40000|57.37(**+0.96**)|[config](../../configs/fastscnn/fastscnn_cityscapes_1024x1024_40k_SCL.yml)|

## Large-Scale Teleconferencing Video Dataset
A large-scale video portrait dataset that contains 291 videos from 23 conference scenes with 14K fine-labeled frames. The data can be obtained by sending an application email to paddleseg@baidu.com.


## Citation
If our project is useful in your research, please citing:

```latex
@InProceedings{Chu_2022_WACV,
    author    = {Chu, Lutao and Liu, Yi and Wu, Zewu and Tang, Shiyu and Chen, Guowei and Hao, Yuying and Peng, Juncai and Yu, Zhiliang and Chen, Zeyu and Lai, Baohua and Xiong, Haoyi},
    title     = {PP-HumanSeg: Connectivity-Aware Portrait Segmentation With a Large-Scale Teleconferencing Video Dataset},
    booktitle = {Proceedings of the IEEE/CVF Winter Conference on Applications of Computer Vision (WACV) Workshops},
    month     = {January},
    year      = {2022},
    pages     = {202-209}
}
```