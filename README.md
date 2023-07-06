# -# 准备环境
```
cd /2022_bishe/q2l
pip install -r requirments.txt
```
# 准备数据集
按照注释执行data/Untitled.ipynb的代码块，生成annotation
# 训练
1. 先在q2l/lib/dataset下进行如下修改：
   + get_dataset.py：heart分支的img_root为所有图像所在路径，coco_root为之前生成的annotation路径。
   +  heartTUdataset.py：修改CAT2IDX的分类类别和编号；同时修改heartTUDataset中的get方法，使其与数据集中图像的命名格式相符。

2. 修改完成后执行以下代码进行训练：
```
cd /2022_bishe/q2l
sh train_san.sh
```
3. 可以通过q2l_train.py中的writer监视训练过程中的变量。
4. 测试
```
cd /2022_bishe/q2l
sh infer.sh
```
# 成果展示
修改q2l.py中image_root和image_path为需要判断的图像路径，修改weithts_path为模型路径。执行：
```
python q2l.py
```
即可输出判断结果。
