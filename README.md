# studying_ros-navigation（実践編）
## 概要
用意されたturtlebot3のシミュレータ環境を用いて、ある設定された課題に挑戦してもらいます。

#### 以下クリックして飛べます。

## [実践編（Practical edition）](https://github.com/uhobeike/studying_ros-navigation/tree/Practical_edition)
## [資料室（Reference room）](https://github.com/uhobeike/studying_ros-navigation/tree/Reference_room)
## [結果発表部屋（Result announcement room）](https://github.com/uhobeike/studying_ros-navigation/tree/Result_announcement_room)
## [実践編ソースコード（Turtlebot3_practice）](https://github.com/uhobeike/studying_ros-navigation/tree/Turtlebot3_practice)

## 課題内容
マッピングを行うとマップ（pgm）(yaml)を手に入れると思います。
それを使用してnavigationを行います。

スタート地点からゴール地点までteleop等の操作無しで自律移動して完走できれば課題達成です:sunglasses:

(もし、作業の進行が早かった場合は、タイムを競い合おうと思います。)

完走できるように各自で、ゴール用のnode(waypoint navigation)(c++、python)の作成とパラメータ調整を行いましょう。

課題を達成するための参考になる資料は下にあります。

### コースについて
`roslaunch turtlebot3_gazebo turtlebot3_practice`を立ち上げると下の写真のようなワールド
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

### 参考になる資料

* パラメータについて

[狭いところ通りたい場合](http://emanual.robotis.com/docs/en/platform/turtlebot3/navigation/#tuning-guide)

[turtlebotのナビゲーションスタックの設定](http://wiki.ros.org/ja/turtlebot_navigation/Tutorials/Setup%20the%20Navigation%20Stack%20for%20TurtleBot)

[ROSのナビゲーションamclについて理解を深めてみる](https://sy-base.com/myrobotics/ros/ros-amcl/)

[ROS move baseでdwa local plannerを使ってみる](https://sy-base.com/myrobotics/ros/ros-dwa-local-planner/)

[ROSのナビゲーションmove_baseについて理解を深めてみる](https://sy-base.com/myrobotics/ros/ros-move_base/)

[ROS gmapping のパラメータ解説](https://sy-base.com/myrobotics/ros/gmapping/)

[パラメータを調整する](https://github.com/TukamotoRyuzo/rostest/wiki/%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%82%92%E8%AA%BF%E6%95%B4%E3%81%99%E3%82%8B)


* navigation(goalさせるためのプログラム)

[Sending Goals to the Navigation Stack](http://wiki.ros.org/ja/navigation/Tutorials/SendingSimpleGoals)


[ロボットプログラミングⅡ：第6週　簡単なゴール（ActionLib）！](https://demura.net/education/lecture/12372.html)


* Pub&Sub書き方例

[ROS講座03 Pub & Sub 通信](https://qiita.com/srs/items/26ca826802d07a9e3d4e)

* ros::spin()について

[【ROS】ros::spin()とros::spinOnce()の違い](http://lilaboc.work/archives/16182817.html)



* turtlebot3 e-manial

[turtlebot3_e-manual](http://emanual.robotis.com/docs/en/platform/turtlebot3/simulation/#ros-1-simulation)
