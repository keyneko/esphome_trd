# 安装home assistant
```bash
# 安装HA
sudo docker pull homeassistant/home-assistant
sudo mkdir -p /data/homeassistant/config
sudo chmod -R 777 /data/homeassistant/
sudo docker run -d \
  --restart always \
  --name homeassistant  \
  -v /data/homeassistant/config:/config \
  -e TZ=Asia/Shanghai   \
  -p 8123:8123   \
  homeassistant/home-assistant:latest

docker compose ps
docker compose logs

# 部署ESPHome
docker pull ghcr.io/esphome/esphome

# 创建项目
docker run --rm -v "${PWD}":/config -it ghcr.io/esphome/esphome wizard livingroom.yaml

switch:
  - platform: gpio
    name: "Living Room Dehumidifier"
    pin: 5

# 上传固件
docker run --rm --privileged -v "${PWD}":/config --device=/dev/ttyUSB0 -it ghcr.io/esphome/esphome run livingroom.yaml

# 通过ESPHome Web上传固件
https://web.esphome.io/

# 仪表板
docker run --rm --net=host -v "${PWD}":/config -it ghcr.io/esphome/esphome
```

# 安装ShellCrash
```bash
# Ubuntu 18.04安装clash-verge 
sudo dpkg -i clash-verge_1.5.2_amd64.deb
# 提示错误 version `GLIBC_2.28' not found (required by clash-verge)
sudo dpkg -r clash-verge

# TODO: 只能本地编译打包了, 基于tauri框架
https://tauri.app/v1/guides/getting-started/prerequisites/#setting-up-linux
git clone https://github.com/clash-verge-rev/clash-verge-rev.git


# 本地安装ShellCrash
git clone https://github.com/juewuy/ShellCrash.git
cd ShellCrash
# root用户安装
sudo su
bash ./install.sh
source /etc/profile &> /dev/null 
crash
# 订阅链接
https://www.paofusub2.com/link/fSiVabs8n3yOg1Dc?sub=1
crash -h
crash -u
```
