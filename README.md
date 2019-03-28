# 优达数据分析项目一：探索未来气候发展趋势

**步骤：**

1. 用 SQL 语句搜了上海，city_list 表中有这个城市  `SELECT * FROM city_list  WHERE city = 'Shanghai';`

2. 用 SQL 语句取 city_data 表中的年平均气温，并下载 CSV 文件  `SELECT * FROM city_data  WHERE city = 'Shanghai';`

3. 用 SQL 语句取 global_data 表中的年平均气温，并下载 CSV 文件  `SELECT * FROM global_data；`

4. 用 EXCEL 打开 CSV 文件并计算七年的移动平均值：以七年为单位，计算每一年与前六年的平均温度的平均值。

5. 在决定如何将趋势可视化时，你考虑的关键是什么？

将趋势可视化时，主要考虑图表是否能够很好的展示年份和温度移动平均值的趋势关系。
>扩展知识
一次性将两个数据都提取到一个表格的方法示例：
SELECT c.year, c.avg_temp as city_temp, g.avg_temp as global_temp
FROM city_data c, global_data g
WHERE c.year = g.year
AND c.city = 'Shanghai';
>
**线图：选取了相同年份的数据：**

![image.png](https://upload-images.jianshu.io/upload_images/5392836-7b195016d598ba2b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![image.png](https://upload-images.jianshu.io/upload_images/5392836-a4d5b55635708207.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


全球所有年份的数据：

![image.png](https://upload-images.jianshu.io/upload_images/5392836-32284d224e8617ae.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

- 全球气温与上海平均气温整体呈上升趋势；

- 与全球平均气温相比，上海平均气温比较高；

- 长期以来，上海气温变化比全球平均气温变化要剧烈的多；

- 世界越来越热；

- 现在世界气温走势与过去几百年气温走势不同，过去几百年波动较大并且有下降趋势，现在气温波动不大，并且呈上升趋势。

- 相关系数用Excel中的PEARSON函数计算，数据需要选择相同年份的数据，计算出相关系数r = 0.864，代表1847年到2013年，全球与上海年平均气温移动平均值正相关；

- 根据全球气温不能估算上海的平均气温，但是能估算气温趋势，趋势都是相似的；

![image.png](https://upload-images.jianshu.io/upload_images/5392836-cce87c5433191e29.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


杭州整体气温也是向上的，世界整体气温趋势向上的原因是每个城市的整体气温趋势都是向上的
