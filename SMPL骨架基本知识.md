# SMPL骨架知识

## 22个主要的身体关节节点（序号对应关节树节点）
0   pelvis（骨盆）<br>
1   left_hip（左髋）<br>
2   right_hip（右髋）<br>
3   spine1（脊柱1）<br>
4   left_knee（左膝）<br>
5   right_knee（右膝）<br>
6   spine2（脊柱2）<br>
7   left_ankle（左脚踝）<br>
8   right_ankle（右脚踝）<br>
9   spine3（脊柱3）<br>
10  left_foot（左脚）<br>
11  right_foot（右脚）<br>
12  neck（颈部）<br>
13  left_collar（左锁骨）<br>
14  right_collar（右锁骨）<br>
15  head（头）<br>
16  left_shoulder（左肩）<br>
17  right_shoulder（右肩）<br>
18  left_elbow（左肘）<br>
19  right_elbow（右肘）<br>
20  left_wrist（左手腕）<br>
21  right_wrist（右手腕）<br>
22  left_hand（左手）：一般不参与整身估计<br>
23  right_hand（右手）：一般不参与整身估计<br>


## SMPL关节树


## 体型参数：betas
控制不同体型人群（高、矮、胖）<br>


## 姿态参数：pose
骨盆root_orient：相对于世界坐标系（相对动捕里定义世界坐标系的姿态）<br>
23个身体关节pose_body：相对于父节点坐标系的姿态旋转<br>


## 正向运动学计算动捕世界坐标系下的姿态
一个关节的全局姿态，就是把从它到骨盆（根节点）路径上的所有局部旋转全部乘起来<br>

## 正向运动学计算动捕世界坐标系下的位置
根据形状参数计算→各个骨骼长度→世界坐标系下的关节位置，就是从骨盆开始，沿骨架树依次将每个关节的局部旋转累乘，并将旋转后的骨骼偏移量不断累加<br>


## 相关概念：
局部关节位置：相对骨盆坐标系的位置<br>
局部关节姿态：相对骨盆坐标系的姿态<br>
世界关节位置：相对动捕世界坐标系的位置<br>
世界关节姿态：相对动捕世界坐标系的姿态<br>


## amass系列数据集相关数据列说明
poses：含骨盆root_orient和关节pose_body<br>
trans：骨盆在动捕世界坐标系的位置<br>
betas：人体形状参数<br>

注意：正向运动学利用骨盆pose和身体关节poses计算各个关节世界坐标系下的姿态和位置。所以，amass一般不保存世界坐标系下的关节位置和姿态）
