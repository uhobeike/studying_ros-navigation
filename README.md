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


