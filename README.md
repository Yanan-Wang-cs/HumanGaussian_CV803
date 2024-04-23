# CV803 - PGT3D: Personalized Personalized Generation for Text-to-3D Human

Project for the CV803 - Advanced CV course - April 2024.
<br>
<br>
[Yanan Wang](Yanan.Wang@mbzuai.ac.ae), [Sara Ghaboura](Sara.Ghaboura@mbzuai.ac.ae), [Tingting Liao](Tingting.liao@mbzuai.ac.ae)
<br>
<br>
[[Paper]()]   [[Demo]()]    [[Survey](https://docs.google.com/forms/d/e/1FAIpQLScbd-G0GG0UbHELhb9gQx7S8L_JnYxyV-X57M5DSXbMwN_-ww/viewform?vc=0&c=0&w=1&flr=0)]     

___________________________________________
 <em> The surge in virtual and augmented reality over the last decade has catalyzed a growing interest in 3D object generation. Recent years have unveiled visual-language models adept at crafting 3D objects from textual descriptions. Yet, these existing approaches falter in creating high-fidelity, human-like avatars, especially in replicating the subtleties of facial details and expressions. The introduction of 3D Gaussian splatting (3DGS) made strides in rendering character limbs but did not achieve the desired level of facial realism. We present the Personalized Generation for Text-to-3D Human (PGT3D) model to surmount these challenges. This approach merges textual prompts, specific poses, and guiding facial images to forge personalized, lifelike 3D avatars, viewable from multiple perspectives and surpassing current models' facial accuracy and expression. Our evaluations reveal that PGT3D excels beyond state-of-the-art models in depicting intricate facial features, marking a pivotal progression towards crafting expressive human avatars from text and portraits and elevating realism in digital realms.   </em> 


## General PGT3D Pipeline:
<p align="center">
   <img src=""  alt="PanFPPL" width="600" height="250" style="margin-right: 2px;" />
   <be>
   <h6> <em> Figure 1. Here. </em> </h6>
</p>


## Detailes PGT3D Framework:
<p align="center">
   <img src=""  alt="PanFPPL" width="1000" height="380" style="margin-right: 2px;" />
   <br>
  <h6> <em> Figure 2. The QET3D Framework: Following HumanGaussina, our process initiates with an SMPL-X mesh and progresses towards the generation of the Pruned Gaussians, followed by the creation of a pose skeleton. This is accompanied by the generation of rendered RGB images "x" and rendered depth images "d". The texture-structure joint model accepts textual-visual inputs, which are represented by the noisy versions of "x<sub>t</sub>" and "d<sub>t</sub>", corresponding to "x" and "d", respectively, guided by a specific prompt. The blurred RGB image produced as a result serves as the input for CodeFormer, which then restores the image to produce "I<sub>Restored</sub>". This restored image and the rendered image "I<sub>Rendered</sub>", originating from the Rendered RGB "x" branch, are subsequently evaluated using the MSE Loss function. The Framework outputs a QET3D character refined in geometry and face features. </em></h6>
</p>


## Description 


## Our Contributions
We can summarize our contributions as follows:
  - Introducing a novel approach capable of generating personalized, human-like avatars conditioned by a single prompt and portrait photograph.
  - Crafting personalized characters of high quality, infused with fine-grained details.
  - Establishing new benchmarks in the realm of digital human generation.
## News
[2024-04-16] Code is available!
<br>
[2024-03-31] Initiating the repository, and uploading the project proposed pipeline. 

## To Install the environment
```diff
# git clone this repository
git clone github.com/Yanan-Wang-cs/HumanGaussian_CV803
cd HumanGaussian_CV803

# create new anaconda env
conda env create -f humangaussian.yaml
conda activate humangaussian


# install python dependencies
pip3 install -r requirements.txt
```


### Quick Inferences
- In case any library requires compilation and the humangaussian.yaml file doesn't function properly, please refer to the following links for guidance on installing the necessary environment:
    - [HumanGaussian](https://github.com/alvinliu0/HumanGaussian)
    - [IP-Adapter](https://github.com/tencent-ailab/IP-Adapter/tree/main)


- Download the library and model from following links and extract them under the folder HumanGaussian:
     - [IPAdapter](https://mbzuaiac-my.sharepoint.com/:u:/g/personal/yanan_wang_mbzuai_ac_ae/EcqJP9iV3TNOuMmik3LeIiABrZ3oc-jBxd2msETxWqVzPA?e=hKbtsH)
     - [Model](https://mbzuaiac-my.sharepoint.com/:u:/g/personal/yanan_wang_mbzuai_ac_ae/EZtICTpr2bFHiqNmyQjfrV8BhKfaHyd7kHZVJcIS7eFWxg?e=SxUZpz)
     - [Texture-Structure Joint](https://mbzuaiac-my.sharepoint.com/:u:/g/personal/yanan_wang_mbzuai_ac_ae/EfF79lcejKZCnVCJq_98MhYBzKdSEZSLo5SsRXo1mrXlVg?e=KjSOp2)


- Additionally, you can refer to our experiment results:
    - [CV803 1angle](https://mbzuaiac-my.sharepoint.com/:u:/g/personal/yanan_wang_mbzuai_ac_ae/EaLuT7l9vkBGjjZ9fD6PSDABLFB9xcLuXgTXUUee1aOM8w?e=98HT1I)


- In configs/test.yaml, you need to update:
    - exp_root_dir
    - smplx_path
    - model_key 


- Training the model:
```diff 
sh train.sh
```

## Visualization 
<p align="center">
   <img src="Images/QET3D-Results.png"  alt="PanFPPL" width="800" height="250" style="margin-right: 2px;" />
   <be>
   <h6> <em> Figure 3. The PGT3D Pipeline Results. </em> </h6>
</p>

  
## Acknowledgement
This project is based on 2 main models: 

```diff
HumanGaussian:
 @article{liu2023humangaussian,
    title={HumanGaussian: Text-Driven 3D Human Generation with Gaussian Splatting},
    author={Liu, Xian and Zhan, Xiaohang and Tang, Jiaxiang and Shan, Ying and Zeng, Gang and Lin, Dahua and Liu, Xihui and Liu, Ziwei},
    journal={arXiv preprint arXiv:2311.17061},
    year={2023}
}

IP-Adapter:
@article{ye2023ip,
  title={Ip-adapter: Text compatible image prompt adapter for text-to-image diffusion models},
  author={Ye, Hu and Zhang, Jun and Liu, Sibo and Han, Xiao and Yang, Wei},
  journal={arXiv preprint arXiv:2308.06721},
  year={2023}
}
