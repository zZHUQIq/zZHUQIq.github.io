1. actor与critic：![[Pasted image 20240527205029.png]]
# QAC—The simplest actor-critic
1. **定义**：θ是策略的参数，θ变策略也变；policy-based+value-based![[Pasted image 20240527205310.png]]***注***：actor就是θ这个公式，critic就是评估qt这个策略
	* qt的计算
		* MC：[[策略梯度方法——西湖大学#^c86883|REINFOCE]]
		* TD-learning![[Pasted image 20240527205948.png]]![[Pasted image 20240527210211.png]]

# A2C—Advantage actor-critic
1. **定义**：在QAC中引入新的偏执量baseline来减少估计的方差![[Pasted image 20240527210525.png]]![[Pasted image 20240527210726.png]]***注***：引入关于s的偏执b是不会影响梯度的，但baseline对它的方差是有影响的![[Pasted image 20240527210959.png]]
2. **目标**：最优化baseline **b**使得var(X)最小——这样可以保证采样的时候有更小的误差![[Pasted image 20240527211635.png]]![[Pasted image 20240527211924.png]]***注***：Vπ就是qπ的平均![[Pasted image 20240527212156.png]]![[Pasted image 20240527212237.png]]![[Pasted image 20240527212412.png]]***注***：当最优函数用TD error来近似时，只需一个神经网络来近似vt就可。
3. A2C算法：![[Pasted image 20240527212645.png]]
# Off-policy
1. 定义：利用其它方法所得到的经验来进行策略的更新
2. Example: 大数定理![[Pasted image 20240527213023.png]]![[Pasted image 20240527213140.png]]![[Pasted image 20240527213340.png]]![[Pasted image 20240527213626.png]]***注***：重要性采样的引入
3. **重要性采样**：![[Pasted image 20240527213821.png]]![[Pasted image 20240527214038.png]]![[Pasted image 20240527214142.png]]![[Pasted image 20240527214315.png]]![[Pasted image 20240527214529.png]]![[Pasted image 20240527214722.png]]
4. off-policy—policy gradient：估计p0的期望，但采样是根据p1所得到![[Pasted image 20240527214955.png]]
5. 定理：![[Pasted image 20240527215138.png]]![[Pasted image 20240527215239.png]]***注***：探索性消失，因为β是一个固定的值——只有充分利用![[Pasted image 20240527215508.png]]
# Deterministic a-c(DPG)
1. 和前面的区别：![[Pasted image 20240527215651.png]]![[Pasted image 20240527215753.png]]***注***：不确定策略——输出是有限的
2. **确定性策略定义**：直接输出a，不输出a的概率![[Pasted image 20240527220012.png]]
3. 梯度的计算：确定性策略是天然的off-policy![[Pasted image 20240527220218.png]]![[Pasted image 20240527220241.png]]![[Pasted image 20240527220543.png]]
4. 梯度上升：![[Pasted image 20240527220710.png]]![[Pasted image 20240527220804.png]]![[Pasted image 20240527220930.png]]