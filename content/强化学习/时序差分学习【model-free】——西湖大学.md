# Motivating examples
1. RM算法求mean回顾：![[Pasted image 20240526192828.png]]![[Pasted image 20240526193003.png]]![[Pasted image 20240526193102.png]]
# TD learning of state values
1. TD算法做policy evaluation：首先根据策略π生成一组数据，TD算法就是要用这些数据来估计π对于的state value![[Pasted image 20240526193601.png]]![[Pasted image 20240526193807.png]]![[Pasted image 20240526194124.png]]
	1. **TD target**：使得V(St)朝着TD target的方向改进，即下一时刻的V(St+1)更接近TD target![[Pasted image 20240526194428.png]]
	2. **TD error**：为什么叫时序差分——error【两个时间步骤的差异】![[Pasted image 20240526194938.png]]
	3. TD算法性质：policy evaluation——估计state value![[Pasted image 20240526195122.png]]

# TD算法的收敛性
1. TD算法的**数学性质**：在没有模型的情况下求解贝尔曼公式![[Pasted image 20240526200039.png]]![[Pasted image 20240526200227.png]]![[Pasted image 20240526200304.png]]***注***：贝尔曼需要持续的采样(s,r,s')，且Vπ未知，解决方法如下![[Pasted image 20240526200519.png]]![[Pasted image 20240526200559.png]]
2. TD算法**收敛性**分析：αt的和为无穷说明被访问了很多次![[Pasted image 20240526200926.png]]
3. **与MC-learning的比较**：TD-learning【一次采样，涉及的随机变量少，因此variance小，但是bias大！初始不准确的估计可能会进入后面的估计中，但随着数据量的增大，bias会被抵消】可以实时更新value，但MC需要等到episode完成才可以求value![[Pasted image 20240526201131.png]]![[Pasted image 20240526201506.png]]***注***：bootstrapping说明一开始我对下一个时刻的value有猜测，根据采样来实时更新猜测![[Pasted image 20240529183219.png]]

# Sarsa
1. 前情回顾：当我们要改进策略时，需要估计action value，这样的话那个value大选择哪一个策略
2. **Sarsa**：——对于给定策略进行**Action value**的估计：![[Pasted image 20240526202747.png]]***注***：解决的数学问题【求解了贝尔曼公式】如下：![[Pasted image 20240526203001.png]]![[Pasted image 20240526203105.png]]
3. **Sarsa【policy evaluation——求action value】+policy improvment**：改进策略，得到策略后产生新的experience，然后继续迭代![[Pasted image 20240526203228.png]]
	* 例：从**特定的状态**到目标状态路径的最优策略！![[Pasted image 20240526203945.png]]![[Pasted image 20240526204259.png]]

# Expected Sarsa
1. **定义**：在St+1时刻有很多动作a可以选择，因此St+1的动作价值函数可以用期望的形式表示，得到state value【这里就不是一个action value了】![[Pasted image 20240526205032.png]]![[Pasted image 20240526205206.png]]
2. **数学性质**：还是求解贝尔曼公式![[Pasted image 20240526205318.png]]
# n-step Sarsa
1. **定义**：包含了蒙特卡洛和Sarsa![[Pasted image 20240526205751.png]]![[Pasted image 20240526205956.png]]
2. n-step**性质**：需要等到t+n时刻，才能更新qt+1![[Pasted image 20240526210422.png]]

# Q-learing
1. 与TD的**区别**：直接估计optimal action value——不需要做policy evaluation和 policy improvement 这两个之间来回交替运行，它直接把最优的action value估计出来了。
2. **定义**：每一个状态看看哪一个action的q比较大就选择这个q![[Pasted image 20240526211036.png]]
3. 解决的**数学问题**：求解贝尔曼最优方程![[Pasted image 20240526211154.png]]
4. **性质**：off-target![[Pasted image 20240526211729.png]]
	1. Off-policy and on-policy：
		1. Behavior策略与环境进行交互生成experience
		2. target policy——一直在更新，最后会得到我们想要的最优策略
		3. 二者相同时为on-policy【用这个策略与环境进行交互得到experience，同时再改进这个策略】，反之Off二者可以不同【这有助于我们利用别人的经验来进行学习】![[Pasted image 20240526212259.png]]
		4. 如何判断：![[Pasted image 20240526212313.png]]
			1. **Sarsa**：on-policy【用πt来估计action value，后面用action value来更新πt从而得到更好的策略，所以πt二者皆是】![[Pasted image 20240526212941.png]]![[Pasted image 20240526213100.png]]
			2. **MC-learning**：on-policy![[Pasted image 20240526213214.png]]
			3. **Q-learning**：off-policy![[Pasted image 20240526213530.png]]![[Pasted image 20240526213637.png]]
5. Q-learing算法实施：
	1. on-policy vision：Target policy can be anything【存在一个搜索】和behaviour一样![[Pasted image 20240526214205.png]]
	2. off-policy vision：![[Pasted image 20240526214403.png]]
		* 例：![[Pasted image 20240526214716.png]]![[Pasted image 20240526214843.png]]***注***：上图为探索性比较强的例子，下面为探索性较弱的例子![[Pasted image 20240526215019.png]]

# A unified point of view【总结】：
1. **总结**：![[Pasted image 20240526215604.png]]![[Pasted image 20240526215833.png]]
