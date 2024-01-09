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
4、编译
进入sing-box_unofficial目录执行命令：
```
go build -o .\build\ -trimpath -ldflags "-X 'github.com/sagernet/sing-box/constant.Version=%VERSION%' -s -w -buildid=" -tags "with_quic with_grpc with_dhcp with_wireguard with_ech with_utls with_reality_server with_acme with_clash_api with_v2ray_api with_gvisor with_shadowsocksr with_proxy_provider" .\cmd\sing-box
```
