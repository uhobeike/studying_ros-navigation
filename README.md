# studying_ros-navigation（実践編）
## 概要
用意されたturtlebot3のシミュレータ環境を用いて、ある設定された課題に挑戦してもらいます。

#### 以下クリックして飛べます。

## [実践編（Practical edition）](https://github.com/uhobeike/studying_ros-navigation/tree/Practical_edition)
## [実践編ソースコード（Turtlebot3_practice）](https://github.com/uhobeike/studying_ros-navigation/tree/Turtlebot3_practice)
## [資料室（Reference room）](https://github.com/uhobeike/studying_ros-navigation/tree/Reference_room)
## [結果発表部屋（Result announcement room）](https://github.com/uhobeike/studying_ros-navigation/tree/Result_announcement_room)

## 課題内容
マッピングを行うとマップ（pgm）(yaml)を手に入れると思います。
それを使用してnavigationを行います。

スタート地点からゴール地点までteleop等の操作無しで自律移動して完走できれば課題達成です:sunglasses:

(もし、作業の進行が早かった場合は、タイムを競い合おうと思います。)

完走できるように各自で、ゴール用のnode(waypoint navigation)(c++、python)の作成とパラメータ調整を行いましょう。

課題を達成するための参考になる資料は下にあります。

### コースについて
`roslaunch turtlebot3_gazebo turtlebot3_practice.launch`を立ち上げると下の写真のようなワールド
が立ち上がります。

走行経路に様々な障害物が置かれています。うまくゴールするには、工夫をする必要が有ります。

障害物にはなるべく衝突しないようにしましょう。

<table>
<th>スタート地点とゴール地点について</th>
<th>真上から見た時のコース</th>
<tr>
<td><img width="500" src="https://i.gyazo.com/46d1024a1766e5a5e19b4975beae9ef1.png"></td>
<td><img width="300" src="https://i.gyazo.com/0450ac0ed29d9e012507fab529a53295.png"></td>
</tr>
</table>

### 実践編の具体的ながれ
1. 使用するエディターについて

2. rosのインストールについて

3. rosのワークスペースの作り方について([こちらのパッケージをインストールします](https://github.com/uhobeike/studying_ros-navigation/tree/Turtlebot3_practice))

4. rosのナビゲーション・マッピングの使い方について

5. rosのC++のノードの作成方法について/ゴール用ノードの作成方法について

6. waypoint_navigationのノード作成方法について

7. 各自で工夫を凝らす
### マッピング方法

```
~$ roslaunch turtlebot3_gazebo turtlebot3_practice.launch
~$ roslaunch turtlebot3_slam turtlebot3_slam.launch slam_methods:=gmapping
~$ roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch
~$ rosrun map_server map_saver -f ~/map
```
```
~$ roslaunch turtlebot3_gazebo turtlebot3_practice.launch
~$ roslaunch turtlebot3_navigation turtlebot3_navigation.launch map_file:=$HOME/map.yaml
```

### ナビゲーション方法


### 参考になる資料

|  |
| - |
| ゴールを指定するやつをコード化した場合(これを工夫するとwaypoint_navigationができるようになる) |
| [ロボットプログラミングⅡ：第6週　簡単なゴール（ActionLib）！](https://demura.net/education/lecture/12372.html) |
| [roswiki: Sending Goals to the Navigation Stack](http://wiki.ros.org/ja/navigation/Tutorials/SendingSimpleGoals) |
|  |
| rosのPub&Subの書き方　コンパイルから実行まで(C++コーディングの基本的な) |
| [ROS講座03 Pub & Sub 通信](https://qiita.com/srs/items/26ca826802d07a9e3d4e) |
| [c++ classを使ったコーディング](https://image.slidesharecdn.com/160626-170515015321/95/ros-76-638.jpg?cb=1611797140) |
| ros::spin()について　コールバック関数の動作について |
| [【ROS】ros::spin()とros::spinOnce()の違い](http://lilaboc.work/archives/16182817.html) |
|  |
| rosのナビゲーションのパラメータについて |
| [ROS move baseでdwa local plannerを使ってみる](https://sy-base.com/myrobotics/ros/ros-dwa-local-planner/) |
| [ROSのナビゲーションamclについて理解を深めてみる](https://sy-base.com/myrobotics/ros/ros-amcl/) |
| [ROSのナビゲーションmove_baseについて理解を深めてみる](https://sy-base.com/myrobotics/ros/ros-move_base/) |
| [パラメータを調整する](https://github.com/TukamotoRyuzo/rostest/wiki/%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%82%92%E8%AA%BF%E6%95%B4%E3%81%99%E3%82%8B) |
| [勉強会一回目move_base](https://github.com/uhobeike/studying_ros-navigation/blob/master/%E5%8B%89%E5%BC%B7%E4%BC%9A%E8%B3%87%E6%96%99/CIT%E8%87%AA%E5%BE%8B%E7%A7%BB%E5%8B%95_%E5%8B%89%E5%BC%B7%E4%BC%9A_1%E5%9B%9E%E7%9B%AE(ros%E3%83%8A%E3%83%93%E3%82%B2%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3).pdf) |
| [勉強会二回amcl](https://github.com/uhobeike/studying_ros-navigation/blob/master/%E5%8B%89%E5%BC%B7%E4%BC%9A%E8%B3%87%E6%96%99/CIT%E8%87%AA%E5%BE%8B%E7%A7%BB%E5%8B%95_%E5%8B%89%E5%BC%B7%E4%BC%9A_2%E5%9B%9E%E7%9B%AE(ros%E3%83%8A%E3%83%93%E3%82%B2%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3).pdf) |
|  |
| turtlebotについて |
| [turtlebotのナビゲーションスタックの設定](http://wiki.ros.org/ja/turtlebot_navigation/Tutorials/Setup%20the%20Navigation%20Stack%20for%20TurtleBot) |
| [turtlebot3_e-manual](http://emanual.robotis.com/docs/en/platform/turtlebot3/simulation/#ros-1-simulation) |

パラメータについては、[ROSロボットプログラミングバイブル](https://www.amazon.co.jp/ROS%E3%83%AD%E3%83%9C%E3%83%83%E3%83%88%E3%83%97%E3%83%AD%E3%82%B0%E3%83%A9%E3%83%9F%E3%83%B3%E3%82%B0%E3%83%90%E3%82%A4%E3%83%96%E3%83%AB-%E8%A1%A8-%E5%85%81%E3%80%93/dp/4274221962)という本に詳しく書かれているので、そちら見るのもありです。


