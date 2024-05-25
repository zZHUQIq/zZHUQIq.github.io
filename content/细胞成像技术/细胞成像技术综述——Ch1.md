# Microscope Introduction——光镜
1. Microscopy Introduction：
	1. [镜头](https://zhuanlan.zhihu.com/p/37171453)、[**光的折射和反射**](https://zhuanlan.zhihu.com/p/480405520)：![[Pasted image 20231207115941.png]]***注***：LENS的作用是**汇聚光线**，在CMOS/CCD上形成景物的图像，为了成像清晰，减少像差，镜头用多片镜片组合，根据需要通过调整LENS获得拍照所需要的焦距。![[Pasted image 20231207120509.png]]
	2. **Working distance**：物镜和被摄体距离![[Pasted image 20231207120746.png]]
	3. [景深](https://zhuanlan.zhihu.com/p/83720676)：基于镜头、拍摄距离等因素，在焦点前、后仍然会有一段距离的景物能够被清晰显示，不致于落入模糊地带，这个清晰的范围便称为景深。![[Pasted image 20231207121437.png]]
	4. 焦点深度：显微镜调焦到看清标本某一点时，不仅是这一物点，而且它的上下两侧也能看清楚两侧的厚度叫做焦点深度。看到标本的全厚度，必须调节螺旋仔细地从上到下进行观察。
	5. How to see？![[Pasted image 20231207125431.png]]![[Pasted image 20231207125528.png]]![[Pasted image 20231215221715.png]]
2. 为什么需要显微镜？
	1. Observe the Genetics Directly：![[Pasted image 20231207125926.png]]
	2. 肌凝蛋白在微管上行走：![[Pasted image 20231207130204.png]]
	3. Keep Sample Alive：![[Pasted image 20231207130410.png]]
	4. From 2D to 3D：![[Pasted image 20231207130457.png]]
	5. Highlight the Target：![[Pasted image 20231207130553.png]]
3. 现代显微镜：![[Pasted image 20231207130910.png]]![[Pasted image 20231207130921.png]]
# 显微镜的分类
1. 明场：![[Pasted image 20231207131357.png]]
2. [[细胞生物学——知识汇总#^4cbe3a|暗场]]：![[Pasted image 20231207131450.png]] ^770a59
3. [相差](https://www.zhihu.com/question/59231315)：**相衬显微镜的核心是要将到光线通过样品时产生的相位差(相位导致的衬度)变化，转换成光强变化，从而能被探测器探测到，而转换的方法就是利用光的干涉。**![[Pasted image 20231207131526.png]] ^a0822e
4. [微分干涉](https://zhuanlan.zhihu.com/p/380737084)：微分干涉显微镜是以平面偏振光为光源，光线经棱镜折射后分成两束，在不同时间经过样品的相邻部位，然后经过另一棱镜将这两束光汇合，从而样品中厚度上的微小差别就会转化成明暗区别，增加了样品反差，造成了标本的人为三维立体感，类似大理石上的浮雕。![[Pasted image 20231207131606.png]] ^21cc6c
5. [偏光显微镜](https://baike.baidu.com/item/%E5%81%8F%E5%85%89%E6%98%BE%E5%BE%AE%E9%95%9C/2010374):![[Pasted image 20231207131740.png]] ^1dc4eb
6. [荧光显微镜](https://baike.baidu.com/item/%E8%8D%A7%E5%85%89%E6%98%BE%E5%BE%AE%E9%95%9C/8063074)：![[Pasted image 20231207194204.png]]![[Pasted image 20231207194742.png]] ![[Pasted image 20231226192533.png]]![[Pasted image 20231226192552.png]]^31b9d5

# 显微镜技术的前沿
1. 概述：双光子、数字扫描激光显微镜、自适应光学、超分辨
2. **高分辨**显微镜： ^4c97d1
	1. 显微镜的分辨率：分辨极限![[Pasted image 20231207200513.png]]![[Pasted image 20231207201251.png]]
	2. **紫外线及X射线**显微镜：优势在于短波长，具有更好的穿透性![[Pasted image 20231207200955.png]]![[Pasted image 20231207201059.png]]
	3. [[电子显微成像技术——透射电镜|电镜]]：![[Pasted image 20231207202059.png]]
	4. Touching Microscope：![[Pasted image 20231207202348.png]]
		1. [**扫描隧道**显微镜](https://zhuanlan.zhihu.com/p/607455337)(Scanning Tunneling Microscope)：原理：(1)一个导电尖端被放置在离被检测表面很近的地方，在两者之间施加电压可以使电子通过它们之间的真空隧穿。(2)所得的隧穿电流是针尖位置、外加电压和样品的局部态密度的函数。(3)当尖端的位置扫描表面时，通过监测电流来获取信息，并且通常以图像形式显示。![[Pasted image 20231207202746.png]]***注***：由于尖端与样品之间距离的超灵敏度，STM具有看到原子的能力。但在生物学上很难实现，原因如下![[Pasted image 20231207203835.png]]![[Pasted image 20231207204044.png]]
		2. [**近场光学**](https://baike.baidu.com/item/%E8%BF%91%E5%9C%BA%E5%85%89%E5%AD%A6)：利用**倏逝波的特性突破远场分辨率限制。这是通过放置探测器非常接近(距离远小于波长λ)试样表面来完成的。![[Pasted image 20231207205346.png]]![[Pasted image 20231207205359.png]]![[Pasted image 20231207205444.png]]
		3. [**原子力显微镜**](https://zhuanlan.zhihu.com/p/646820382#:~:text=AFM%E5%85%A8%E7%A7%B0Atomic%20Force%20Microscope%EF%BC%8C%E5%8D%B3%E5%8E%9F%E5%AD%90%E5%8A%9B%E6%98%BE%E5%BE%AE%E9%95%9C%EF%BC%8C%E5%AE%83%E6%98%AF%E7%BB%A7%E6%89%AB%E6%8F%8F%E9%9A%A7%E9%81%93%E6%98%BE%E5%BE%AE%E9%95%9C%EF%BC%88Scanning,Tunneling%20Microscope%EF%BC%89%E4%B9%8B%E5%90%8E%E5%8F%91%E6%98%8E%E7%9A%84%E4%B8%80%E7%A7%8D%E5%85%B7%E6%9C%89%E5%8E%9F%E5%AD%90%E7%BA%A7%E9%AB%98%E5%88%86%E8%BE%A8%E7%9A%84%E6%96%B0%E5%9E%8B%E4%BB%AA%E5%99%A8%EF%BC%8C%20%E5%8F%AF%E4%BB%A5%E5%9C%A8%E5%A4%A7%E6%B0%94%E5%92%8C%E6%B6%B2%E4%BD%93%E7%8E%AF%E5%A2%83%E4%B8%8B%E5%AF%B9%E5%90%84%E7%A7%8D%E6%9D%90%E6%96%99%E5%92%8C%E6%A0%B7%E5%93%81%E8%BF%9B%E8%A1%8C%E7%BA%B3%E7%B1%B3%E5%8C%BA%E5%9F%9F%E7%9A%84%E7%89%A9%E7%90%86%E6%80%A7%E8%B4%A8%E5%8C%85%E6%8B%AC%E5%BD%A2%E8%B2%8C%E8%BF%9B%E8%A1%8C%E6%8E%A2%E6%B5%8B%20%EF%BC%8C%E6%88%96%E8%80%85%E7%9B%B4%E6%8E%A5%E8%BF%9B%E8%A1%8C%E7%BA%B3%E7%B1%B3%E6%93%8D%E7%BA%B5%E3%80%82)：用探针与样品之间的范德华相互作用研究表面。根据样品的机械性能来区分样品。![[Pasted image 20231207205636.png]]![[Pasted image 20231207205707.png]]![[Pasted image 20240106200007.png]] ^775f1c
3. 未来：![[Pasted image 20231207210621.png]]