# 基於ROS的機器人自動導航與地圖探索系統

## 目標
開發一個基於ROS的地圖探索機器人，並在Gazebo環境中模擬實作結果。機器人具備:建立地圖、保存地圖、開啟地圖等功能。

## 資料夾內容：
1. **robot**：包含機器人的URDF文件和環境的文件
   **URDF文件**：於描述掃地機器人的結構和組成部分
   **.world文件**：提供機器人運行的模擬環境

2. **m-explore**：開源explore_lite算法
   **explore_lite算法**：於自主探索未知環境，通過移動機器人並建立地圖，確保機器人覆蓋所有區域，適應不同場景變化

3. **auto_nav**：自動建圖和導航
   **auto_slam.launch**：利用Slam和explore_lite，機器人能夠在未知環境中自動建立地圖

4. **scripts**
   **next_goal.py**：發佈下一目標的節點
     **目標點發佈**：生成和發佈下一個目標點，確保機器人能夠連續有效地覆蓋所有區域，提高效率

## 如何操作
1. **掃描建圖**：
   指令：`roslaunch auto_nav auto_slam.launch` 

2. **儲存地圖**
   開啟另一個終端機
   指令：`roslaunch auto_nav save_map.launch` 

3. **開啟地圖**
   關閉第一個指令再操作
   指令：`roslaunch auto_nav amcl.launch`

## 如何下載
```bash
   cd ~/catkin_ws/src
   git clone https://github.com/zy0913zy/Explore_robot.git
   cd ..
   catkin_make
```
## 影片
https://youtu.be/CseWEquCzXg





