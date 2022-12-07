# 异常值处理

&emsp:异常值可能会对模型建立产生不良影响，导致模型偏离原本的拟合，异常值通常数量不多。我们使用箱线图将插补后的原始数值型变量数据可视化，如图2，红色的点为外点。我们将超过上四分位数加上1.5倍四分位数差的点，以及低于下四分位数减去1.5倍四分位数差的点定义为异常值点，通过采用删除异常值所在的行以去除不合常理的值，增加模型的预测精确度。删除异常值后，最终用于后续模型计算的样本量为41031个。

<center>
    <img style="border-radius: 0.3125em;
    box-shadow: 0 2px 4px 0 rgba(34,36,38,.12),0 2px 10px 0 rgba(34,36,38,.08);" 
    src="D:\Studyfiles\管理科学建模方法论\小组\Introduction\Management_Science_Modeling\content_4\图2.png">
    <br>
    <div style="color:orange; border-bottom: 1px solid #d9d9d9;
    display: inline-block;
    color: #999;
    padding: 2px;">图2 插补后各变量箱线图</div>
</center>

