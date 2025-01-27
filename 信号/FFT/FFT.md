# FFT
### 常用函数
- `void arm_rfft_fast_init_f32(arm_rfft_fast_instance_f32* S,uint32_t size)`
    在进行FFT之前需要对结构体进行初始化，size为数据点数
- `void arm_rfft_fast_f32(arm_rfft_fast_instance_f32* S,float32_t* p,float32_t* pOut,uint8_t ifftFlag)`
    该函数用来求FFT,输出序列为实部虚部相间的序列
    其中`S`为控制运算的结构体，`p`为输入数据缓冲区,会被函数改变，`POut`为结果输出(为实虚数序列，实数虚数间隔出现)，`ifftFlag`为变换标志位，为0时为正变换，为1时为逆序列
    该函数只支持32,64,128,256,512,1024,2048,4096个点
- `void arm_complex_mag_f32(const float32_t* pSrc,float32_t* pDst,uint32_t numsamples)`
    `pSrc`为实部虚部相间的数组，`pDst`为实序列，`numsamples`为样本点数
- `void arm_cfft_fast_f32(arm_cfft_fast_instance_f32* S,float32_t* p,uint8_t ifftFlag,uint8_t bitReverseFlag)`
    用于求复数FFT
    `S`为复数FFT控制结构体
    `p`为数据输入，结果输出，输入和输出均是虚序列，排列方式为实部虚部相间
    `ifftflag` 为0时为正变换 为1时为逆变换
    `bitReverseFlag` 为0时禁用输出位反转 1使能输出为翻转
### 其余细节
- 加窗：防止能量泄露
- 如何观察输出频谱：首先要清楚采样频率即ADC采样的频率，采样点数即用于进行FFT转换的点数，分辨率=${\frac{采样频率}{采样点数}}$,则经mag函数输出的数组每个下标对应的频率间隔为分辨率
### Reference
- [个人博客ARM_FFT](https://www.huangrongzhen.ink/?p=259)
- [(不强相关)嵌入式个人博客](https://www.huangrongzhen.ink/?author=1)
- [(不强相关)硬汉嵌入式论坛](https://www.armbbs.cn/forum.php)
- [博客园ARM FFT](https://www.cnblogs.com/helesheng/p/15671138.html)
- [(不强相关)Markdown中插入LaTex](https://blog.csdn.net/wzk4869/article/details/126863936)
- [小学生都能懂的FFT原理](https://www.cnblogs.com/RabbitHu/p/FFT.html)
- [WhyCan Forum](https://whycan.com/index.html)