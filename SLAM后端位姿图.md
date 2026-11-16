# 定义
用于表示多个位姿变量之间的约束关系，并通过联合优化这些约束，估计一组相互一致的位姿

# 要素
1.节点：待优化的目标位姿<br>
2.边(约束因子）：观测数据+残差函数+不确定性权重<br>
<img width="822" height="572" alt="image" src="https://github.com/user-attachments/assets/c8d8527d-7459-4312-826f-f5f64edc80f4" />


# 流程：
1.根据位姿图约束因子误差构建优化目标：<br>
<img width="867" height="500" alt="image" src="https://github.com/user-attachments/assets/93a0e00d-0351-4453-82d2-cf382b721b2f" />
2.选择初始化位姿输入进行迭代优化输出结果

