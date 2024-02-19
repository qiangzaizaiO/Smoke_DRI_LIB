1. AdpdDrv.c；AdpdDrv.h；smoke_detect_temp_MGMJ.lib；smoke_detect.h 为Smoke detection的驱动文件
2. main.c中包含调用驱动文件接口函数的例程
3. main文件中应包含驱动代码头文件<#include "smoke_detect.h">
4. main文件中举例为以1Hz的频率读取烟雾传感器数据，故配置定时器<void TIM3_TIM4_IRQHandler(void)>
5. 调用初始化函数以初始化烟雾传感器<AdpdInit()>
6. 调用数据读取函数以获得当前烟雾传感器数据<SmokeData_Status = Smoke_Dataread(temp_data,&data_BluePTR, &data_IRPTR, &data_Ratio)> (其中temp_data为环境温度)
7. 调用数据读取函数的同时将返回当前烟雾数据/传感器状态<SmokeData_Status>
8. 