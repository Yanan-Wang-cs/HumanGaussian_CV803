Install the environment:
conda env create -f humangaussian.yaml
conda activate humangaussian

In case any library requires compilation and the humangaussian.yaml file doesn't function properly, please refer to the following links for guidance on installing the necessary environment:
HumanGaussian: https://github.com/alvinliu0/HumanGaussian
IP-Adapter: https://github.com/tencent-ailab/IP-Adapter/tree/main


Download the library and model from following links and extract them under the folder HumanGaussian:
IPAdapter: https://mbzuaiac-my.sharepoint.com/:u:/g/personal/yanan_wang_mbzuai_ac_ae/EcqJP9iV3TNOuMmik3LeIiABrZ3oc-jBxd2msETxWqVzPA?e=hKbtsH
models: https://mbzuaiac-my.sharepoint.com/:u:/g/personal/yanan_wang_mbzuai_ac_ae/EZtICTpr2bFHiqNmyQjfrV8BhKfaHyd7kHZVJcIS7eFWxg?e=SxUZpz
texture_structure_joint: https://mbzuaiac-my.sharepoint.com/:u:/g/personal/yanan_wang_mbzuai_ac_ae/EfF79lcejKZCnVCJq_98MhYBzKdSEZSLo5SsRXo1mrXlVg?e=KjSOp2



Additionally, you can refer to our experiment results:
CV803 1angle: https://mbzuaiac-my.sharepoint.com/:u:/g/personal/yanan_wang_mbzuai_ac_ae/EaLuT7l9vkBGjjZ9fD6PSDABLFB9xcLuXgTXUUee1aOM8w?e=98HT1I


You need to update exp_root_dir, smplx_path, model_key in configs/test.yaml.


Training the model:
sh train.sh
