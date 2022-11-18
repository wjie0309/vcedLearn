## VCED 简介

VCED (Video Clip Extraction by description) 是一种通过文字描述来自动识别视频里符合描述的片段. 这种技术是当今搜索技术的发展趋势, 通过跨模态搜索与向量检索技术搭建, 能够实现跨模态的搜索技术.

## 环境的安装

本次 VCED 学习的课程为 DataWhale 2022.11开办的跨模态实践项目, 项目开源地址: https://github.com/datawhalechina/vced

环境的安装本次为了方便, 使用了 docker 进行环境的简化配置.

本人使用的设备方案是 win11+wsl2.
1. 之前已经通过 wsl2 配置安装了 ubuntu22.04, 这方面详细的信息可以在搜索引擎上进行搜索, 有很多分享.
2. 通过 wsl2 安装了 docker desktop 之后, 在 docker desktop 的路径 Settings/Resources/WSL intergration 中打开 Enable integration 选项.

	![](https://s1.vika.cn/space/2022/11/16/d4cd0194d47f442db5d652e3c7a35443)


3. 在开源链接处将项目 clone 到本地. 这里推荐将项目导入到 wsl2 中的地址, 这样的话在 wsl2 中可以直接安装依赖以及环境配置. 具体的实现方法推荐使用 vscode.
	1. 在 vscode 中使用终端输入 `wsl` 进入 wsl 子系统, 然后输入 `code .` 在 wsl 中安装并打开 vscode (如果已经安装过了就会直接打开).
	2. 在打开后的 vscode 就可以直接远程使用 linux 系统, 这样可以在 windows 页面下进行操作, 同样非常方便.
	3. 输入 `cd ~` 将路径导入到 wsl 中的默认 home 地址, 进行之后的操作. 也可以输入你想要将项目储存的文件夹.
	4. `git clone https://github.com/datawhalechina/vced.git` 在当前文件夹载入包

4. `cd /vced` 进入项目文件夹, 然后执行一下 docker 操作
	`docker-compose build`
	`docker-compose up -d`

	完成下载后提示如下指令的情况就是运行成功啦
	
	![](https://s1.vika.cn/space/2022/11/16/5610f80263d2483080bb65757c41ccae)

5. 通过 `docker ps -a` 可以查看我们当前 docker 内拥有的所有镜像, 并能查看它们的接口等细节信息. 也可以通过 `docker port <name>` 来直接查看指定镜像接口. vced 默认使用的接口为 8501.
6. 然后输入 `个人IP地址:接口` 即可访问 vced.

	![](https://s1.vika.cn/space/2022/11/16/7ad6f9dafd2a45128ef8e5daae08bb31)

7. 如果在访问的时候出现问题, 就在指令行输入 `docker restart` 重启一下即可.