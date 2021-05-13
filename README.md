# studying_ros-navigation

## 概要
勉強会に参加している方々および今後の後輩のための資料として作成したリポジトリ。
ROS melodicをインストールします。

#1.はじめに
インストールする際に、環境が破壊させるなどの不具合について筆者は責任を負いません。
#2.環境
環境は以下の環境を想定しています。

- メインPC 
 - OS: Ubuntu18.04LTS (desktop) 

#3 インストールと設定
今回はROS1のubuntu18.04に対応したバージョンであるROS melodicと
tutkebot3用のパッケージをインストールしましょう
melodicのインストールについてはありがたいことに
https://github.com/ryuichiueda/ros_setup_scripts_Ubuntu18.04_desktop
なる便利なものがあるため利用しましょう！


#####3.1 ROS melodicのインストール　
```bash:メインPC
sudo apt-get update
sudo apt-get upgrade
sudo apt-get install -y curl
bash -c "$(curl -SsfL https://git.io/ros-melodic-desktop)"
```
うまく行かなかった場合にはコマンドでROSを削除後、サイトを参考にインストールしてください。
```
sudo apt-get remove ros-*
```

http://wiki.ros.org/melodic/Installation/Ubuntu

#####3.2 ROSの環境設定
この段階ではROSへパスが通っておらず、コマンドなどが利用できないためパスを通しましょう。
その後、ターミナルを起動するたびに設定するのが面倒なのでbashrc（ターミナルを起動するたびに実行させるもの）へ登録しましょう
（これをやっておかないと様々なエラーが起きるのでお忘れなく）

```bash:メインPC
echo "source /opt/ros/melodic/setup.bash" >> ~/.bashrc
source ~/.bashrc
source /opt/ros/melodic/setup.bash
```

#####3.3 rosinstallの準備
ROS installやビルド用のcatkin-ものやらライブラリをインストールします

```bash:メインPC
sudo apt  install python-rosdep python-rosinstall-generator python-wstool python-rosinstall build-essential python-catkin-tools
```

#####3.4 rosdepを設定 
```bash:メインPC
sudo apt install python-rosdep
sudo rosdep init
rosdep update
```

#####3.5 workspaceを設定 
rosで用いられる作業用スペースを作成します（よく用いられる名前のcatkin_wsで作成します）

```bash:メインPC
source ~/.bashrc
mkdir -p ~/catkin_ws/src
cd ~/catkin_ws/src
catkin_init_workspace
echo "source ~/catkin_ws/devel/setup.bash" >> ~/.bashrc
cd ~/catkin_ws　&&　catkin build
source ~/catkin_ws/devel/setup.bash
```
#####3.6 turtlebot3用の依存パッケージをインストール 
turtlebot3に必要なパッケージをインストールします。
（gmappingをgitから入れると何故かビルドできないためaptで入れましょう）

```bash:メインPC
sudo apt-get install ros-melodic-joy ros-melodic-teleop-twist-joy ros-melodic-teleop-twist-keyboard ros-melodic-laser-proc ros-melodic-rgbd-launch ros-melodic-depthimage-to-laserscan ros-melodic-rosserial-arduino ros-melodic-rosserial-python ros-melodic-rosserial-server ros-melodic-rosserial-client ros-melodic-rosserial-msgs ros-melodic-amcl ros-melodic-map-server ros-melodic-move-base ros-melodic-urdf ros-melodic-xacro ros-melodic-compressed-image-transport ros-melodic-rqt-image-view ros-melodic-gmapping ros-melodic-navigation ros-melodic-interactive-markers
```
次にturtlebot3 のパッケージをダウンロード後、ビルドします

```bash:メインPC
cd ~/catkin_ws/src  <--各自、変更をお願いします。
git clone --recursive https://github.com/uhobeike/turtlebot3_aws_2021.git
rosdep update
rosdep install -r -y --from-paths --ignore-src ./
```

インストールが終了したらPCでビルドしましょう。
ビルドした時にエラーがでなければ正常にインストールが出来ているはずです…

```bash:メインPC
source /opt/ros/melodic/setup.bash
catkin build
```

#4.実行
設定が終わったので実行してみましょう
Rvizを起動してburgerがあったら起動成功です。

```bash:メインPC
echo "export TURTLEBOT3_MODEL=burger" >> ~/.bashrc
source ~/.bashrc
roslaunch turtlebot3_fake turtlebot3_fake.launch
```

これでひと通りの設定と起動ができたはずです。
お疲れ様でした。
次に実践編へ行きましょう！！！

#.トラブルシューティング
エラーが出た場合にはパスが通ってない場合があるため

```
source /opt/ros/melodic/setup.bash
source ~/catkin_ws/devel/setup.bash
```
を実行してからcatkin buildでやり直しましょう。
それでもうまくいかない場合にはとても手間ですが

```
sudo apt-get remove ros-*
```
を利用してROSをアンインストールしてから再インストールしましょう。

