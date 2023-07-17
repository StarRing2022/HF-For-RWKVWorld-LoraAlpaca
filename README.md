# HF-For-RWKVWorld-LoraAlpaca
将RWKV World/World-CHN系列模型由原生pth转为HF格式，并进行基于peft库的Lora增量微调+Alpaca全量微调。


环境：WIN10+Torch1.31+Cuda11.6 <br>
注意：peft需要0.2版本，或使用RingPeft库 https://github.com/StarRing2022/ChatGPTX-Uni <br>


代码说明：<br>
convert_rwkv_checkpoint_to_hf.py：RWKV的原生pth格式转为HF格式<br>
generate_hf.py：使用HF的RWKV模型架设服务<br>
hello_hf.py：测试HF的RWKV模型<br>
cover_alpaca2jsonl.py：将json数据集转为jsonl数据集<br>
tokenize_dataset_rowsjsonl.py：对jsonl数据集转为transfomers的datasets文件夹<br>
finetunejsonl_hf.py：利用Peft库对RWKV HF模型进行Lora微调，在datasets文件夹上<br>
alpacatrain.py：使用test.json的alpaca全量微调模型<br>
alpacatest.py：测试alpaca全量微调模型<br>

RWKV-4-Word模型（World-CHN可直接参照）转换范例：<br>
https://huggingface.co/StarRing2022/RWKV-4-World-1.5B <br>
https://huggingface.co/StarRing2022/RWKV-4-World-3B <br>
https://huggingface.co/StarRing2022/RWKV-4-World-7B <br>

一个基于RWKV-4-World-1.5B的Lora增量微调范例（2条数据，100个epoch，仅测试）：<br>
HF开源地址：<br>
https://huggingface.co/StarRing2022/RWKV-4-World-1.5B-Lora <br>

一个基于RWKV-4-World-1.5B的Alpaca全量微调范例（2条数据，1个epoch，仅测试）：<br>
HF开源地址：<br>
https://huggingface.co/StarRing2022/RWKV-4-World-1.5B-Alpaca <br>
