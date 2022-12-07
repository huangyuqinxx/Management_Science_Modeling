# 数据缺失处理

&emsp;对数据集数据缺失情况进行可视化处理，由变量数据的缺失情况图（图1）可以大致看出Evaporation、Sunshine、Cloud9am和Cloud3pm四个变量数据的缺失率很高。
<center>
    <img style="border-radius: 0.3125em;
    box-shadow: 0 2px 4px 0 rgba(34,36,38,.12),0 2px 10px 0 rgba(34,36,38,.08);" 
    src="D:\Studyfiles\管理科学建模方法论\小组\Introduction\Management_Science_Modeling\content_4\图1.png">
    <br>
    <div style="color:orange; border-bottom: 1px solid #d9d9d9;
    display: inline-block;
    color: #999;
    padding: 2px;">图1 数据缺失率图</div>
</center>


&emsp;通过描述性统计进一步得出精确的数据缺失情况，如表2。对于Evaporation、Sunshine、Cloud9am和Cloud3pm四个变量，其数据的缺失率已经超过了30%，直接运用插补法进行插补后的数据可能会使模型运算结果产生较大偏差，加上样本数据量比较多，考虑删除这四个变量对应的缺失样本。对于变量RainToday和RainTomorrow，其分别代表今天是否下雨和明天是否下雨，考虑将数据中“yes”、“no”转变为布尔值1、0，方便之后的模型计算处理。对于其他的字符型变量，将其转变为不具有排序的数字表示。对于其他数值型变量，分布使用均值插补、中位数插补、多重插补法以及随机森林插补法进行数据插补。随机森林插补是一种机器学习技术，它可以适应非线性和相互作用，不需要指定特定的回归模型，并且随机森林插补方法相对于其他的参数MICE方法更有效，能产生更窄的置信区间（Shah A D等，2014）<sup>[32]</sup>。所以本研究最终选择随机森林方法插补数据集，插补后数据集的描述性统计以及直方图见附件1、2。

|     **列名**      | **缺失值数量** | **缺失值占比** |
|  :---:  |  :----:   |  :---:  |
|    **MinTemp**    |      1485      |     1.02%      |
|    **MaxTemp**    |      1261      |     0.86%      |
|   **Rainfall**    |      3261      |     2.24%      |
|  **Evaporation**  |     62790      |     43.17%     |
|   **Sunshine**    |     69835      |     48.01%     |
|  **WindGustDir**  |     10326      |     7.10%      |
|  **WindDir9am**   |     10566      |     7.26%      |
|  **WindDir3pm**   |      4228      |     2.90%      |
| **WindGustSpeed** |     10263      |     7.06%      |
| **WindSpeed9am**  |      1767      |     1.21%      |
| **WindSpeed3pm**  |      3062      |     2.11%      |
|  **Humidity9am**  |      2654      |     1.82%      |
|  **Humidity3pm**  |      4507      |     3.10%      |
|  **Pressure9am**  |     15065      |     10.36%     |
|  **Pressure3pm**  |     15028      |     10.33%     |
|   **Cloud9am**    |     55888      |     38.42%     |
|   **Cloud3pm**    |     59358      |     40.81%     |
|    **Temp9am**    |      1767      |     1.21%      |
|    **Temp3pm**    |      3609      |     2.48%      |
|   **RainToday**   |      3261      |     2.24%      |
| **RainTomorrow**  |      3267      |     2.25%      |

