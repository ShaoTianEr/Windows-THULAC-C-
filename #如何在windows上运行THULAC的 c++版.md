# 如何在windows上运行THULAC的 c++版的具体步骤（包括测试和跑模型）
## （一）跑模型
###  1.安装gcc（具体下载、安装及改变环境变量的方法在网上可以搜到）www.mingw.org（下载地址）
	在THULAC_lite_c++_v1\THULAC_lite_c++_v1路径下运行命令行：mingw32-make 会得到thulac和train_c.exe（如果这一步成功可省去2,3步骤）
### 2.把include文件夹中的所有文件复制到src文件夹中
### 3.在src路径下运行：g++ -o train.exe train_c.cc 会生成train.exe
### 4.把train.exe或train_c.exe放在之前已经训练好的具有分词和词性标注的txt文件所在的文件夹data中
### 5.在data路径下运行命令行：train.exe -s / -b 1 -i 15 out_2.txt new  会生成三个文件名带有model的文件（out_2.txt是训练好的语料）
### 6.把Models_v1_v2文件夹下面的models文件夹复制到THULAC_lite_c++_v1\THULAC_lite_c++_v1路径下
### 7.把第五步生成的文件名带有model的三个文件复制到models文件夹中，覆盖以cws开头的三个文件（需要改成相应的名字）
## （二）测试
### 1.在THULAC_lite_c++_v1\THULAC_lite_c++_v1路径下用命令行：thulac <ceshi.txt> outfile.txt 进行测试（要在测试的文件名上加上尖括号，不然会没有结果）
