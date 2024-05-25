# 值迭代算法
1. **value iteration**【值迭代】：![[Pasted image 20240521200335.png]]![[Pasted image 20240521200518.png]]***注***：这里的Vk不是state value，他只是一个向量、一个值
	1. 步骤1：采用**贪心策略**更新策略![[Pasted image 20240521201013.png]]
	2. 步骤2：值迭代——对应q最大的概率是1![[Pasted image 20240521201209.png]]
	3. **总结**：![[Pasted image 20240521201432.png]]
	* 例：![[Pasted image 20240521201607.png]]![[Pasted image 20240521201722.png]]![[Pasted image 20240521201922.png]]

# 策略迭代
1. 定义：![[Pasted image 20240521203626.png]]![[Pasted image 20240521203732.png]]
2. **Policy evaluation**：![[Pasted image 20240521203840.png]]
3. **Policy improvement**?![[Pasted image 20240521203928.png]]![[Pasted image 20240521204034.png]]
4. 策略迭代的具体实现：![[Pasted image 20240521204306.png]]![[Pasted image 20240521204427.png]]![[Pasted image 20240521210128.png]]
	* 例：【简单问题】一次迭代就可完成![[Pasted image 20240521210312.png]]![[Pasted image 20240521210405.png]]![[Pasted image 20240521210512.png]]
	* 【复杂问题】5x5的网格：先接近目标的状态它的策略会先变好，越远离目标的状态会后变好。![[Pasted image 20240521210605.png]]![[Pasted image 20240521210743.png]]

# Truncated policy iteration algorithm
1. 值迭代和策略迭代算法的**比较**：一个初始化值，从值出发；一个初始化策略，从一个策略出发![[Pasted image 20240521211622.png]]![[Pasted image 20240521211843.png]]![[Pasted image 20240521212156.png]]
	* 区别1：Vπ1不等于v1![[Pasted image 20240521212453.png]]
2. Truncated policy iteration：策略评估过程还没结束时就把v提取出来带到下一步的策略更新/策略提升![[Pasted image 20240521212754.png]]***注***：J=1，就是value iteration；J=∞，就是policy iteration【实际上算不了无穷多步，只需计算两次之间的error足够小就行，最够小就停止迭代】![[Pasted image 20240521213042.png]]***注***：设置个迭代次数就行![[Pasted image 20240521213159.png]]![[Pasted image 20240521213310.png]]***注***：收敛性没有改变
	* 例：策略评估迭代次数的设置——越大迭代次数越小，state value收敛越快，但效果不明显——要选择折中的方案![[Pasted image 20240521213344.png]]![[Pasted image 20240521214342.png]]![[Pasted image 20240521213549.png]]

# 总结![[Pasted image 20240521214135.png]]