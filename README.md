# ReproductionExperience
有些处理方法真的一眼就该想到，没经验的时候会弄很久……

## RuntimeError: CUDA error: no kernel image is available for execution on the device
试一下这段代码，看看是不是也是报这个错。
```
>>> import torch
>>> torch.tensor([1.0, 2.0]).cuda()
tensor([1., 2.], device='cuda:0')
```
原因：安装的cuda, pytorch和当前的GPU型号并不匹配

解决方法：复现论文时torch版本保持和作者一致，GPU型号通过nvidia-smi获取，去[pytorch官网](https://pytorch.org/get-started/previous-versions/)查询对应的安装命令行，conda不行就换成pip，我用的是pip3

Reference：
https://zhuanlan.zhihu.com/p/633473214  ；
https://zhuanlan.zhihu.com/p/466793485
