# studying_ros-navigation

## 概要
勉強会に参加している方々および今後の後輩のための資料として作成したリポジトリ。

## 目的
利用可能なrosのナビゲーションパッケージ(実機/シュミレータ)を作成できるような技術の習得。

## 勉強会に参加して、できるようになること
* rosでの基本的な開発
* rosのC/C++ノード作成
* rosのNavigation Stackの大まかな理解
* 基本的なnavigationパッケージ作成
* シュミレータ環境(Gazebo)でのgmapping(SLAM)や、ナビゲーションや、waypoint_navigationのプログラム作成

## 予定
多分、全部で10日分あると考えている。ros2はやりません。

| 日付（仮） | やる内容                                                                               | 
| ---------- | -------------------------------------------------------------------------------------- | 
| 1/21       | ナビゲーションについて/rosのNavigation Stackの構成/move_baseについて(パラメータ) | 
| 1/28       | rosのNavigation Stackの構成/amclについて(パラメータ)                             | 
| 2/4        | move_base/amclのソースから抜粋する/抜粋したやつの計算方法やパラメータとの関係の説明    | 
| 2/11       | turtlebot3のパッケージの中を見にいこう/構成方法について話す/参考にした事例も話す       | 
| 2/18       | 実践！！！(マッピングとナビゲーションについて)                                                                            | 
| 2/25       | 実践！！！(パラメータとウェイポイントナビゲーションについて)                                                                             | 
| 3/5        | 実践！！！(各自、工夫を凝らす？！)                                                                              | 
| 3/12       | 実践！！！(各自、工夫を凝らす？！)                                                                             | 
| 3/19       | 結果発表？！                                                                           | 
| 3/26       | 反省会？？                                                                            | 

## 勉強会動画

|1回目：撮ってない|
|---|
||


|2回目：音だけ😢|
|---|
|[![](https://i.gyazo.com/863451bcc09ecbbc191b177fd92a4bfa.png)](https://www.youtube.com/watch?v=f5PWUFdF9eE&feature=youtu.be)|

|3回目：撮ってない|
|---|
||

|4回目：CIT自律移動 勉強会 turtlebot3のパッケージ|5回目：CIT自律移動 勉強会 実践(マッピングとナビゲーションについて)|
|---|---|
|[![](https://i.gyazo.com/6601d58058a014568186c57613af659b.png)](https://youtu.be/YbParNRqGQE)|[![](https://i.gyazo.com/64ff77a91809a8b5b6b60ef12fe5676f.png)](https://youtu.be/BxYfgf6fReI)|

|6回目：CIT自律移動 勉強会 実践(パラメータとウェイポイントナビゲーションについて1)|7回目：CIT自律移動 勉強会 実践(パラメータとウェイポイントナビゲーションについて2)|
|---|---|
|[![](https://i.gyazo.com/319be43a8210d9e6f870bbac83ca5803.png)](https://youtu.be/fMpScJg5gPI)|[![](https://i.gyazo.com/ee71774d1b34a110082dc594adb68de4.png)](https://youtu.be/Wlx6feSTNmc)|

|8回目：CIT自律移動 勉強会 実践(パラメータとウェイポイントナビゲーションについて3)|
|---|
|[![](https://i.gyazo.com/050df9d823fb054482a903432a863ada.png)](https://youtu.be/dqaMv6d-VM4)|

## 資料集
||
| :--- | 
|勉強会一回|
| [ROS wiki]  <br>  (1)navigationのセットアップについて  <br>  　move_baseやamcl及びcostmapなどのparams,launchファイルの書き方が記載  <br>      http://wiki.ros.org/ja/navigation/Tutorials/RobotSetup  <br>  (2)move_baseについての詳細  <br>      http://wiki.ros.org/move_base  <br>  (3)costmap2dについての詳細  <br>      http://wiki.ros.org/costmap_2d?distro=noetic  <br>  (4)(局所経路計画)dwa_local_plannerについての詳細  <br>  http://wiki.ros.org/dwa_local_planner  <br>  (5)(大域経路計画)global_plannerについての詳細  <br>       http://wiki.ros.org/global_planner<br><br> [動作方法andパラメータ調整]  <br>  (6)navigation調整ガイド(costmap,local_planner)  <br>    　(1)の資料を読んだ後に見ることをすすめます...  <br>      http://wiki.ros.org/navigation/Tutorials/Navigation%20Tuning%20Guide  <br>  (7)turtlebot3 e-manual(costmap,dwa_local_planner)  <br>    　navigationの具体的な操作方法,inflation_radius,cost_scaling_factor,dwaに関する要調整パラメータ(max_vel)などが記載  <br>  　  虎の穴レベル  <br>      https://emanual.robotis.com/docs/en/platform/turtlebot3/navigation/#tuning-guide  <br>  (8)ROS Navigation Tuning Guide by Kaiyu Zheng(cost_map,planner,amcl)  <br>    　パラメータに関して詳細な記載,困ったらこれを見ると良いレベルで秀逸  <br>      http://kaiyuzheng.me/documents/navguide.pdf  <br>  (9)DWA Plannerの設定可能パラメータ一覧<br>      https://qiita.com/np_hsgw/items/ab3d4e34f4c1c160871d | 


#### 以下クリックして飛べます。

## [準備編（ros_install）](https://github.com/uhobeike/studying_ros-navigation/tree/ros_install)
## [実践編（Practical edition）](https://github.com/uhobeike/studying_ros-navigation/tree/Practical_edition)
## [実践編ソースコード（Turtlebot3_practice）](https://github.com/uhobeike/studying_ros-navigation/tree/Turtlebot3_practice)

# Todo
pdfではなく、スライド埋め込みで情報公開する。
