Install the environment:
conda env create -f humangaussian.yaml
conda activate humangaussian

In case any library requires compilation and the humangaussian.yaml file doesn't function properly, please refer to the following links for guidance on installing the necessary environment:
HumanGaussian: https://github.com/alvinliu0/HumanGaussian
CodeFormer: https://github.com/sczhou/CodeFormer


Download the library and model from following links and extract them under the folder HumanGaussian:
CodeFormer: https://mbzuaiac-my.sharepoint.com/:u:/g/personal/yanan_wang_mbzuai_ac_ae/EUVl9QaOMeZBnIma0_HYYsMB5lH1TJfLoVT7o2e58l9ubA?e=bxbkl3
models: https://mbzuaiac-my.sharepoint.com/:u:/g/personal/yanan_wang_mbzuai_ac_ae/EZtICTpr2bFHiqNmyQjfrV8BhKfaHyd7kHZVJcIS7eFWxg?e=SxUZpz
texture_structure_joint: https://mbzuaiac-my.sharepoint.com/:u:/g/personal/yanan_wang_mbzuai_ac_ae/EfF79lcejKZCnVCJq_98MhYBzKdSEZSLo5SsRXo1mrXlVg?e=KjSOp2



Additionally, you can refer to our experiment results:
CV806 final_name-of-this-experiment-run: https://mbzuaiac-my.sharepoint.com/:u:/g/personal/yanan_wang_mbzuai_ac_ae/Ecuhh0b_-W1Fo0LWV_P5nFYBJdJpcGQJl3657EYQk5VmLA?e=fJPNXt


You need to update exp_root_dir, smplx_path, model_key in configs/test.yaml.


Training the model:
sh train.sh
