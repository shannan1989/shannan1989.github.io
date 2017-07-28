---
layout: post
title:  "WPF开发：动画基础"
date:   2017-07-25 13:33:00 +0800
categories: WPF
---

WPF中的有三种基本动画，线性插值动画、关键帧动画和路径动画。

在 **System.Windows.Media.Animation** 这个命名空间中，包含了三种动画类：
* 线性插值动画类（17个）
* 关键帧动画类（22个）
* 路径动画类（3个）

在C#代码中使用Animation类，需要引入命名空间：**System.Windows.Media.Animation** 。

### 1、线性插值动画

该动画表现为，元素的某个属性，在开始值和结束值之间逐步增加，是一种线性插值的过程。

比如，实现一个按钮的淡入效果，让它的透明度 Opacity 在0~1之间线性增长，就可以实现预期效果。 

以下是 **System.Windows.Media.Animation** 命名空间中，17个线性插值动画类：

	ByteAnimation

	ColorAnimation

	DecimalAnimation

	DoubleAnimation

	Int16Animation

	Int32Animation

	Int64Animation

	Point3DAnimation

	PointAnimation

	QuaternionAnimation

	RectAnimation

	Rotation3DAnimation

	SingleAnimation

	SizeAnimation

	ThicknessAnimation

	Vector3DAnimation

	VectorAnimation

### 2、关键帧动画

关键帧动画是以时间为节点，在指定时间节点上，属性达到某个值。

以下是 **System.Windows.Media.Animation** 命名空间中，22个关键帧动画类：　

	BooleanAnimationUsingKeyFrames

	ByteAnimationUsingKeyFrames

	CharAnimationUsingKeyFrames

	ColorAnimationUsingKeyFrames

	DecimalAnimationUsingKeyFrames

	DoubleAnimationUsingKeyFrames

	Int16AnimationUsingKeyFrames

	Int32AnimationUsingKeyFrames

	Int64AnimationUsingKeyFrames

	MatrixAnimationUsingKeyFrames

	ObjectAnimationUsingKeyFrames

	Point3DAnimationUsingKeyFrames

	PointAnimationUsingKeyFrames

	QuaternionAnimationUsingKeyFrames

	RectAnimationUsingKeyFrames

	Rotation3DAnimationUsingKeyFrames

	SingleAnimationUsingKeyFrames

	SizeAnimationUsingKeyFrames

	StringAnimationUsingKeyFrames

	ThicknessAnimationUsingKeyFrames

	Vector3DAnimationUsingKeyFrames

	VectorAnimationUsingKeyFrames

### 3、路径动画

基于路径的动画，比起前两种更加专业一些。它的表现方式是，修改数值使其符合 PathGeometry 对象描述的形状，并且让元素沿着路径移动。

以下是 **System.Windows.Media.Animation** 命名空间中，3个路径动画类：

	DoubleAnimationUsingPath

	MatrixAnimationUsingPath

	PointAnimationUsingPath

