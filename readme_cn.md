#### how to use
```
# 错误
2020-07-09 09:11:35.763940: W tensorflow/core/framework/op_kernel.cc:1502] OP_REQUIRES failed at save_restore_v2_ops.cc:184 : Out of range: Read fewer bytes than requested
Traceback (most recent call last):
  File "E:\virtualenv\ugatit\lib\site-packages\tensorflow\python\client\session.py", line 1356, in _do_call
    return fn(*args)
  File "E:\virtualenv\ugatit\lib\site-packages\tensorflow\python\client\session.py", line 1341, in _run_fn
    options, feed_dict, fetch_list, target_list, run_metadata)
  File "E:\virtualenv\ugatit\lib\site-packages\tensorflow\python\client\session.py", line 1429, in _call_tf_sessionrun
    run_metadata)
tensorflow.python.framework.errors_impl.OutOfRangeError: Read fewer bytes than requested
         [[{{node save/RestoreV2}}]]

# 使用
1.基于python3.6的环境，安装requirements.txt包
pip install -r requirements.txt -i https://mirrors.aliyun.com/pypi/simple/
2.下载百度网盘的checkpoints
网盘/IT学习/UGATIT/100_epoch_selfie2anime_checkpoint/这个解压有问题，可能需要在linux或者mac的环境下解压，暂不使用这个
网盘/IT学习/UGATIT/UGATIT_model/checkpoint/UGATIT_selfie2anime_lsgan_4resblock_6dis_1_1_10_10_1000_sn_smoothing 下载这个文件夹的所有东西
3.解压下载的内容，进行处理
在UGATIT主目录下创建文件夹checkpoint/UGATIT_selfie2anime_lsgan_4resblock_6dis_1_1_10_10_1000_sn_smoothing/
里面放解压出来的内容，如下
-rw-r--r-- 1 lazyh 197609  297  7月  9 22:06 checkpoint
-rw-r--r-- 1 lazyh 197609 7.5G 11月  5  2018 UGATIT.model-1000000.data-00000-of-00001
-rw-r--r-- 1 lazyh 197609  31K  7月  9 22:06 UGATIT.model-1000000.index
-rw-r--r-- 1 lazyh 197609  15M  7月  9 09:47 UGATIT.model-1000000.meta
4.创建照片文件夹
在UGATIT主目录下创建文件夹如下：
dataset\selfie2anime\testA
dataset\selfie2anime\testB
testA放要转换的人脸照片
testB放要转换的动漫照片
5.运行命令
python main.py --dataset selfie2anime --phase test
6.结果
结果在新生成的目录results\UGATIT_selfie2anime_lsgan_4resblock_6dis_1_1_10_10_1000_sn_smoothing下

trainA/trainB中的数据用于训练使用的，使用命令
python main.py --dataset selfie2anime 进行训练

testA/testB用于测试的使用命令
python main.py --dataset selfie2anime --phase test
```
> [taki0112/UGATIT](https://github.com/taki0112/UGATIT)

> [issue55](https://github.com/taki0112/UGATIT/issues/55)

> [issue52](https://github.com/taki0112/UGATIT/issues/52)