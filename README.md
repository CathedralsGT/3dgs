这是一个用于存放第一段科研（计算机视觉相关）使用代码的文件夹。
Don't be afraid, just relax and do it.


这是第一部分，是关于论文NeRF的一些笔记：
    解决的问题：能够通过提供的关于一个三维物体的多个角度的二维图片生成任意位置视角下观察这个物体所应该产生的二维图片，且图片清晰度较高
    使用的方法：“by optimizing an underlying continuous volumetric scene function", 使用了多层感知机(MLP)来建模这个物体的参数方程<这个函数的定义域在R^5上，包括坐标分量
(x, y, z)和观察视角分量(θ，φ)，输出为一个二元向量(ρ(x, y, z),C(x, y, z)),ρ为密度，C为辐射(颜色),之后通过光线积分公式就可以得出路径终点的颜色值>，由于体积渲染（volume randering）
是可微的（参见光路积分公式），因此
