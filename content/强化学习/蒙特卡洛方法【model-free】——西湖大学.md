# Motivating example
1. **投硬币**：![[Pasted image 20240522151653.png]]
	1. **基于模型的**：这么精确的模型我们可能无法知道！![[Pasted image 20240522151737.png]]
	2. **无模型**【大量采样+实验】：投掷硬币很多次，采样很多次，把采样求平均![[Pasted image 20240522151913.png]]![[Pasted image 20240522151949.png]]***注***：当N很小的时候不精确，当N越来越大的时候越来越精确【大数定理】![[Pasted image 20240522152246.png]]
# The simplest MC-based RL algorithm
1. 值迭代到无模型的转变：![[Pasted image 20240522153852.png]]
	* Action value的计算——有模型+无模型![[Pasted image 20240522154117.png]]***注***：无模型就是action value最初的定义，s状态下采取动作a得到return的期望
	* Monte Carlo estimation：![[Pasted image 20240522154626.png]]
2. **The MC Basic algorithm**：与有模型的值迭代最后一步都是一样的![[Pasted image 20240522154814.png]]![[Pasted image 20240522154945.png]]***注***：效率较低、不实用
3. 例：
	1. 简单例子：![[Pasted image 20240522155415.png]]![[Pasted image 20240522155508.png]]![[Pasted image 20240522155748.png]]![[Pasted image 20240522160104.png]]![[Pasted image 20240522155840.png]]![[Pasted image 20240522155921.png]]
	2. Episode length：**探索半径的长度**，设置为几说明几步可以达到目标![[Pasted image 20240522160315.png]]![[Pasted image 20240522160406.png]]***注***：这里长度设置为1说明只走一次就停下【必须要求一步到位】，这时候得到的r作为return【估计不准确】![[Pasted image 20240522160800.png]]![[Pasted image 20240522160926.png]]***注***：episode越大，optimal state value和真值就一模一样了![[Pasted image 20240522161044.png]]
# MC Exploring Starts
1. **Visit**：在episode当中，每出现一个state-action pair都相当于对这个episode有一次访问 【MC-basic：Initial-visit method】![[Pasted image 20240522182425.png]]![[Pasted image 20240522182633.png]]***注***：对于first visit【第一次出现才能估计】出现一次s1，a2再出现一次就不能用它后面的episode来计算return；对于every-visit，每一次访问visit后面的episode都可以用来估计当前visit的return—q。
2. **策略更新**：
	1. 法一：需要收集所有的episode并计算 average return【MC-Basic】![[Pasted image 20240522184332.png]]
	2. 法二：只用一个episiode来立刻估计action value，然后直接开始改进策略![[Pasted image 20240522184349.png]]![[Pasted image 20240522184707.png]] **GPI**：策略评估【不需要把state/action value 精确估计出来】和策略提升交替切换![[Pasted image 20240522182912.png]]
4. MC Exporing Starts：倒退计算提高效率![[Pasted image 20240522185035.png]]
# MC without exploring starts
1. **Soft policies**：对每一个action都有可能做选择【episode比较长，从一个s/a出发就可以完全覆盖其他所有的s/a】
2. **ε-greedy**：贪心选择于一个策略【概率最大】，但存在一定的探索性![[Pasted image 20240522185924.png]]![[Pasted image 20240522190106.png]]![[Pasted image 20240522190315.png]]***注***：Exploitation是充分利用——充分利用return大的；Exploration是探索，探索return可能大的其他action。
	* Greedy policy：从所有可能的策略做选择![[Pasted image 20240522191557.png]]
	* ε-Greedy policy：从ε-greedy策略中去找![[Pasted image 20240522192730.png]]![[Pasted image 20240522192851.png]]
3. 例子：
	1. ε=1：探索性最强，只需要从某一些(s,a)出发就能覆盖到所有(s,a)![[Pasted image 20240522192931.png]]
	2. ε偏小，偏好性强 ![[Pasted image 20240522193338.png]]
	3. MC ε-greedy:![[Pasted image 20240522193542.png]]![[Pasted image 20240522193827.png]]![[Pasted image 20240522194015.png]]***注***：伴随ε的增大，最优性越来越差！——ε不能设置太大【上面的例子为0.1时，他的最优策略和greedy是一致的】；亦或者一开始ε比较大，后面逐渐变小——得到最优策略

# 总结：![[Pasted image 20240522194623.png]]