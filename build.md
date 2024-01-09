1、克隆sagernet项目
```
git clone https://github.com/sagernet/sing-box
```
2、克隆puerNya项目
```
git clone -b building https://github.com/PuerNya/sing-box sing-box_unofficial
```
3、得到两个文件夹，分别是sing-box，sing-box_unofficial
进入sing-box目录，执行
```
for /f %i in ('go run .\cmd\internal\read_tag') do ( set VERSION=%i )
```
命令；此步骤的目的是拉取版本号，并定义变量VERSION
