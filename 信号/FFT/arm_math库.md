# ARM_MATH库使用
## 基本工作
在意法半导体下载包含CMSIS_DSP的外设库[下载网址](https://www.st.com/en/embedded-software/stsw-stm32065.html)
STM32F4使用M4内核,采用小端地址，有FPU
- arm_cortexM4lf_math.lib
- arm_cortexM4bf_math.lib
- arm_cortexM4l_math.lib
- arm_cortexM4b_math.lib
<br>
其中字母l代表小端地址,b代表大端地址,f代表使用浮点计算单元(FPU)，只需将arm_cortexM4lf_math.lib加入Keil MDK工程，再将arm_math.h加入包含路径即可
DSP_Lib中包含了
1. BasicMathFunctions:基本数学函数
2. CommonTables:数字信号处理常用参数表
3. ComplexMathFunctions:副书记算数学函数
4. ControllerFunctions:控制算法函数：如正弦余弦，PID电机控制，矢量Clarke变换，矢量Clarke逆变换
5. FastMathFunctions:快速算法的数学函数
6. FilteringFunctions:滤波功能函数
7. MatrixFunctions:矩阵处理函数，矩阵加法，矩阵初始化，矩阵求逆。矩阵乘法，矩阵转置等函数
8. StatisticsFunctions:统计功能函数:求平均值，最大值，最小值，计算均方根，计算方差标准差
9. SupportFunctions:支持功能函数：如数据拷贝Q格式浮点格式呼唤
10. TransformFunctions:变换函数，FFT
需要在options的宏定义中加入如下宏：
- ARM_MATH_CM4
- __CC_ARM
- ARM_MATH_MATRIX_CHECK
- ARM_MATH_ROUNDING
且需要在魔法棒中使能FPU

### Reference
- [博客园ARM FFT](https://www.cnblogs.com/helesheng/p/15671138.html)