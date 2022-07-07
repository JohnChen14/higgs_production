# higgs_production
1. 如果你已经安装python以及jupyter notebook，你需要安装LHAPDF才能在`notebook/higgs_Xsec.ipynb`文件中访问部分子分布函数，详细的教程参见LHAPDF的官网：https://lhapdf.hepforge.org/install.html

2. 如果你未配置python环境，你可以选择使用Docker以及提供的带LHAPDF的jupyter notebook镜像文件来快速构建所需要的虚拟环境。Docker可以在官网 https://www.docker.com/products/docker-desktop/ 中下载。

   在安装并运行docker之后，可以在文件夹`LHAPDF_docker_build`中打开终端，并运行
     > chmod +x build_image.sh; ./build_image
   
   来构建所需要的镜像。里面使用了https://hub.docker.com/r/jupyter/scipy-notebook 提供的`python-3.8.8`版本的镜像。

   构建完镜像之后，可以在notebook文件夹里运行命令
     > docker run -it -p 8888:8888 -v "${PWD}":/home/jovyan/work lhapdf-scipy-nb:1.0
   
   来启动jupyter lab. 然后将命令行中输出的形如
     `http://127.0.0.1:8888/lab?token=...`
   的链接复制进浏览器即可打开jupyter lab. 进入`work`文件夹之后既能打开运行演示文件`higgs_Xsec.ipynb`.
