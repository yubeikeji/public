[ecg diagnosis]:https://github.com/yubeikeji/public/blob/master/Images/ecg_diagnosis.jpg
[ecg_report_1]:https://github.com/yubeikeji/public/blob/master/Images/ecg_report_1.jpg
[ecg_report_2]:https://github.com/yubeikeji/public/blob/master/Images/ecg_report_2.jpg
[ecg_parameters]:https://github.com/yubeikeji/public/blob/master/Images/ecg_parameters.jpg

## 用户需求
### 功能性需求
- 检测心电，血压，血糖
- 给出进一步诊断建议
- 保存检测结果
### 非功能性需求
- 检测心电，血压，血糖功能要和新的 React Native 平台整合
- 诊断参数要从 React Native 平台传到检测平台
- 诊断结果要从检测平台传到 React Native 平台
- 诊断报告最好能住新的 React Native 平台展示

## 基本问题
- **[新问题]**
  - 根据对问题答案的理解，只有本地的心电数据可以通过API展示出来。如果PAD损毁或丢失，心电数据就会完全丢失。
  - 如果本地心电数据大小超过PAD存储的大小，新的心电数据还能保持吗？
  - 如果我们保持心电数据在数据库，这样的数据是不能被以心电图的方式展示？
- 监护数据是怎么管理的？
  - 数据产生
    - 开始监护后，通过蓝牙实时读取采集盒传过来的心电数据，并保存到本地
  - 数据读取
  - 数据存储管理
    - 保存规则：时间，存储空间大小？
      - 监护24小时的心电数据大约占用130M的存储空间
      - 
- 哪一个API是获取检测结果的？
  - 请查看文档第6个接口：getECGReport
- 测量过程可以中断吗？
  - 实时监护界面有结束按钮，可手动结束
- 解释数据...
```
"rdbp" : null,
"report" : "大致正常心电图,窦性心律,多发室上性早搏,若感觉症状明显,应去医院做进一步诊疗",
"lsbp" : null,
"app_report" : """{"marRadomId":"","caseId":"f051e096-f14d-417e-bb30-0cc19099aadd","T_high":0,"max_ecg_L":0,"ecg_V_r_V_max_time":0,"ecg_NN_rr_arh":0,"ecg_NN_rr_count":34,"ecg_NN_rr_num":0,"ecg_N_count":70,"ecg_P_count":0,"ecg_Pace_count":0,"ecg_QRS_w_count":0,"ecg_QRS_w_rate":0.0,"ecg_R_count":90,"ecg_ST_beat_count":0,"ecg_ST_l_count":0,"ecg_ST_l_rate":0.0,"ecg_ST_ll_count":0,"ecg_ST_u_count":0,"ecg_ST_u_rate":0.0,"ecg_ST_uu_count":0,"ecg_S_2_S_count":0,"ecg_S_2_S_max":0,"ecg_S_2_Time_count":0,"ecg_S_2_Time_max":0,"ecg_S_2_c":0,"ecg_S_3_S_count":0,"ecg_S_3_S_max":0,"ecg_S_3_Time_count":0,"ecg_S_3_Time_max":0,"ecg_S_3_c":0,"ecg_S_4_S_count":0,"ecg_S_4_S_max":0,"ecg_S_4_Time_count":0,"ecg_S_4_Time_max":0,"ecg_S_4_c":0,"ecg_S_count":5,"ecg_S_pair_c":1,"ecg_S_r_S_count":0,"ecg_S_r_S_max":1,"ecg_S_r_Time_count":0,"ecg_S_r_Time_max":0,"ecg_S_rate":0.0,"ecg_S_run_c":0,"ecg_S_single_c":0,"ecg_Stop_count":0,"ecg_T_change_count":0,"ecg_V_2_Time_count":0,"ecg_V_2_Time_max":0,"ecg_V_2_V_count":0,"ecg_V_2_V_max":0,"ecg_V_2_c":0,"ecg_V_3_Time_count":0,"ecg_V_3_Time_max":0,"ecg_V_3_V_count":0,"ecg_V_3_V_max":0,"ecg_V_3_c":0,"ecg_V_4_Time_count":0,"ecg_V_4_Time_max":0,"ecg_V_4_V_count":0,"ecg_V_4_V_max":0,"ecg_V_4_c":0,"ecg_V_cert_count":0,"ecg_V_count":0,"ecg_V_pair_c":0,"ecg_V_pair_count":0,"ecg_V_r_Time_count":0,"ecg_V_r_Time_max":0,"ecg_V_r_V_count":0,"ecg_V_r_V_max":1,"ecg_L_count":0,"ecg_V_rate":0.0,"ecg_V_run_c":0,"ecg_V_single_c":0,"ecg_V_single_count":0,"ecg_WD_beat_count":0,"ecg_Z_count":3,"ecg_dur_h":0,"ecg_dur_m":0,"ecg_dur_s":0,"ecg_dur_sec":0,"ecg_hr":91,"ecg_max_hr":0,"ecg_min_hr":0,"ecg_multi_V":0,"ecg_rhy_s_count":0,"ecg_rhy_v_count":0,"ecg_s_distribution":0,"ecg_score":84,"ecg_st_level":0.0,"ecg_sum_RR_count":0,"ecg_sum_RR_intv":0,"ecg_sum_ST_amp":-11,"ecg_sum_ST_count":90,"ecg_summary":0,"ecg_total_beat":74,"ecg_total_dots":59,"ecg_v_distribution":0,"id":194,"T_change":75,"T_down":0,"noise_rate":2,"tag":0}""",
"app_user_case" : """{"upstate":"未上传","report":"      大致正常心电图,窦性心律,多发室上性早搏,若感觉症状明显,应去医院做进一步诊疗。","model":"指夹方式","caseId":"f051e096-f14d-417e-bb30-0cc19099aadd","date":"2018-03-19 09:09:52","marRadomId":"","filePath":"/storage/emulated/0/ECGPATH/-20180319090952","fileDir":"aiHeart20180319090952","startPackNum":1,"max_ecg_L":0,"dropPackNum":0,"endPackNum":1495,"ecg_V_r_V_max_time":0,"e_sszof":0,"e_sszpf":0,"e_st1":0,"e_st2":0,"e_st3":0,"e_st4":0,"e_szcd":0,"e_szof":0,"e_szpf":0,"eb":0,"ecg_N_count":0,"ecg_S_count":5,"ecg_S_r_Time_max":0,"ecg_V_count":0,"e_ss":0,"ecg_hr":91,"ecg_max_hr":0,"ecg_min_hr":0,"ecg_summary":0,"ecg_total_beat":74,"e_hr5":0,"endtime":59,"e_hr1":0,"exceptionDataNum":4,"e_cjx3":0,"e_cjx2":0,"e_cjx1":0,"health_level":0,"id":234,"lp":0,"e_hr4":0,"e_hr3":0,"bc":0,"psvt":0,"avjrt":0,"at":0,"as":0,"spvc":0,"srdl":0,"srpb":3,"srpbs":1,"srql":0,"srtl":0,"st":0.0,"e_hr2":0,"starttime":0,"tend_report":0,"type":0,"af":0,"user_id":0,"vdl":0,"vpbp":0,"vql":0,"vt":0,"vtl":0}""",
"total_s" : "5",
"guard_mode" : "指夹-常规监护",
"app_report_fingerprint" : "050c600c089687b811c0d37fa2d6ed47",
"total_v" : "0",
"ldbp" : null,
"guard_length" : 59,
"alarm" : "未警报",
"guard_start_time" : "2018-03-19T14:09:52.000Z",
"report_keywords" : [
            "大致正常心电图",
            "窦性心律",
            "多发室上性早搏",
            "若感觉症状明显",
            "应去医院做进一步诊疗"
          ],
"hr" : "91",
"residents_uuid" : "3104d5d425a211e89cdf00163e0024fd",
"app_hr_list" : """[["11","n"],["26","n"],["45","n"],["60","n"],["78","n"],["99","n"],["114","n"],["131","n"],["147","n"],["162","n"],["177","n"],["191","n"],["205","N"],["220","N"],["237","N"],["253","N"],["268","N"],["285","N"],["297","S"],["313","N"],["327","N"],["344","N"],["358","N"],["380","N"],["401","N"],["416","N"],["434","N"],["454","N"],["469","N"],["485","N"],["500","N"],["516","N"],["534","N"],["550","N"],["564","N"],["582","N"],["598","N"],["618","N"],["633","N"],["652","N"],["670","N"],["686","N"],["703","N"],["721","N"],["739","N"],["756","N"],["769","S"],["781","S"],["800","N"],["820","N"],["838","N"],["853","N"],["870","N"],["883","N"],["904","N"],["919","N"],["933","N"],["947","N"],["961","N"],["987","N"],["999","S"],["1021","N"],["1042","N"],["1060","N"],["1078","N"],["1095","N"],["1109","N"],["1123","N"],["1136","N"],["1155","N"],["1170","N"],["1183","N"],["1200","N"],["1215","N"],["1231","N"],["1244","N"],["1258","N"],["1275","N"],["1294","N"],["1309","N"],["1329","N"],["1345","N"],["1356","S"],["1373","N"],["1387","N"],["1409","N"],["1426","N"],["1447","N"],["1465","N"],["1485","N"]]""",
"app_report_exce" : """[{"caseId":"f051e096-f14d-417e-bb30-0cc19099aadd","marRadomId":"","time":1521421808578,"packegeNum":312,"id":45,"type":8},{"caseId":"f051e096-f14d-417e-bb30-0cc19099aadd","marRadomId":"","time":1521421826655,"packegeNum":780,"id":46,"type":9},{"caseId":"f051e096-f14d-417e-bb30-0cc19099aadd","marRadomId":"","time":1521421836893,"packegeNum":1020,"id":47,"type":8},{"caseId":"f051e096-f14d-417e-bb30-0cc19099aadd","marRadomId":"","time":1521421851183,"packegeNum":1372,"id":48,"type":8}]""",
"rsbp" : null,
"data_id" : "f051e096-f14d-417e-bb30-0cc19099aadd",
"st" : "0.00"

```
-

## 管理器启动监护
```  
接口定义: string startECGMonitor(string userId, String testModel)
返回结果:
成功：{“result”:”successed”,”userId”:”220302198710151317”,”dataId”:”data1358”}
失败：{“result”:”failed”,”userId”:”220302198710151317”,”dataId”:”data1358”}
```
### 问题：
- 这个API的用途是什么？
  - 通过这个接口启动心电实时监护程序，
- 这个API的结果是一个页面吗？这个API是进入检测页面的入口吗？
  - 是一个心电监护的实时界面
![心电检测][ecg diagnosis]
- API接口的参数只有userId and testModel(指甲方式，电极贴方式)吗？现有的APP还有一个“监护时间”参数，这个参数在哪里设置？
  - **[新问题]**能回答一下这个问题吗？
![检测参数][ecg_parameters]
- 
## 管理器访问测量历史记录：
```  
接口定义:string getECGUserDataInfo(string userId)
返回结果:
成功：{“result”:”success”,”userId”:” 220302198710151317”,”datainfoList”:{“dataId”:
”data1358”,”startTime”:”20150302120405”, “expandTime”:”100”,”exception”:”1”}}
失败:{"result":"failed","userId":"uuuu","datainfoList":"[]"}
```
### 问题：
- **[新问题]**
  - 历史记录只能是PAD本地的数据，PAD损毁会丢失数据？
- 这个API的用途是什么？
  - 此接口通过用户ID获取用户的心电测量历史记录
- 这个API的结果是一个页面吗？
  - 不是一个页面
- datainfoList 是 "Array" 还是 "Object"
  - Array
- 检测结果怎么获得？是要用 userId+dataId 调用 “管理器回顾数据” API吗？还是这个API同时返回数据结果？如果是，数据结构是什么？
  - 检测结果通过调用getECGReport（）获取，如果想回顾心电监护数据通过调用reviewECGUserData（）接口弹出一个心电回顾的界面
- exception 的用途是什么？
  - exception只此次监护中出现的异常波形次数
    - **[新问题]**是不是“异常波形”意味医生和病人需要注意？

## 管理器删除数据
```
接口定义:string delECGUserData(string userId, string dataId)
返回结果:
成功：{“result”:”successed”,”userId”:”220302198710151317”,”dataId”:”data1358”}
失败：{“result”:”failed”,”userId”:”220302198710151317”,”dataId”:”data1358”}
```
### 问题：
- 这个API的用途是什么？在什么情况下需要删除数据？
  - 此接口用于删除测量的一条心电数据，根据用户需求或APP设定进行调用，没有特殊用途

## 管理器回顾数据
```
接口定义:string reviewECGUserData(string userId, string dataId)
返回结果:
成功：{“result”:”success”, ”userid”:” 220302198710151317”, “dataid”:”data1358”}
失败：{“result”:”failed”,”userId”:”220302198710151317”,”dataId”:”data1358”}
```
### 问题：
- 这个API的用途是什么？
  - 这个接口用来回顾历史测量的心电波形数据
- 这个API的结果是一个页面吗？
  - 是一个页面
  ![Report][ecg_report_2]
- 么有看到任何数据结果的结构？这个API的结果到底是什么？

## 设置界面显示
```
(1) 接口定义:void showECGSetup()
```
### 问题：
- 这个API的用途是什么？
  - 这个接口用来设置心电波形的滤波器、脉冲标记等
- 这个API的结果是一个页面吗？
  - 是一个页面
- 可以用API直接改变设置吗？不通过UI
  - 不可以通过API直接改变设置
  
## 管理器获取数据详细信息
```  
接口定义:string getECGReport(string userId, string dataId)
返回结果:
 成功:{"result":"successed","userId":"uuuu","Report":
"{"clientReport":"
	 *        异常心电图,窦性心律,多发室性早搏,短阵性室性心动过速,最长室性心动过速持续时间为1.88秒,建议去医院做进一步诊疗。",
	 *        "exception"
	 *        :"1","expandTime":"45","startTime":"2015-06-18 16:03:25"
	 *        ,"st":"0.00","hr":84,"totalL":0,"totalS":0,"totalS2":0,"totalS":0,
	 *        "totalSP"
	 *        :0,"totalSR":0,"totalSS":0,"totalV":14,"totalV2":0,"totalV3"
	 *        :0,"totalVP":0, "totalVR":2,"totalVS":3}" }
失败: {"result":"failed","userId":"uuuu","Report":"" }
```
### 问题：
- 这个API的用途是什么？
  - 这个接口用来获取心电监护结果的详细信息
- 这个API的结果是一个页面吗？
  - 不是一个页面
- 解释每一项的数据是什么用途？
  - 请查看Demo中Report类
    - private int hr;// 平均心率 	
    - private String st;// 平均st 
    - private int totalV;// 室早总数 
    - private int totalVS;// 单发室性早搏 
    - private int totalVP;// 室性早搏成对 
    - private int totalV2;// 室性二联律 
    - private int totalV3;// 室性三联律  
    - private int totalVR;// 室性心动过速 
    - private int totalS;// 室上早总数 
    - private int totalSS;// 单发室上性早搏 
    - private int totalSP;// 室上性早搏成对 
    - private int totalS2;// 室上性二联律 
    - private int totalS3;// 室上性三联律 
    - private int totalSR;// 室上性心动过速 
    - private int totalL;// 长间歇 
## 获取心电原始文件路径
```
接口定义:String getECGFilePath(String userId, String dataId)
返回结果:
成功: {"result":"successed","userId":"uuuu","dataId": "data1358","ecgFilePath":"sdcard/..."}
失败: {"result":"failed","userId":"uuuu","dataId":"data1358" ,"ecgFilePath":""}
```
### 问题：
- 这个API的用途是什么？
  - 此接口用户获取心电监护的原始数据文件
- 这个原始文件的数据结构是什么？
  - 数据结构属于公司内部机密，不予外泄
    - **[新问题]**那是不是这个文件对我们是没有任何用途的？
- 解释每一项的数据是什么用途？
  - ecgFilePath:原始文件保存路径

## 开始测量血糖（通过蓝牙获取血糖数值）
```
接口定义:void tartTestGlucose()
回调方法：void glucoseBack(String jsonStr)
成功返回：{"result":"successed","msg":"测量完成！","glucose":"80"}
失败返回:{"result":"failed","msg":"失败原因！"}
```
### 问题：
- 
## 开始测量血压（通过蓝牙获取血压数值）
```
接口定义:void startTestPressure()
回调方法：void pressureBack(String jsonStr)
成功返回：{"result":"successed","msg":"测量完成！","hr":"80","sys":"120","dia":"60"}
失败返回:{"result":"failed","msg":"失败原因！"}

```
### 问题：
- sys? 收缩压 dia? 舒张压

