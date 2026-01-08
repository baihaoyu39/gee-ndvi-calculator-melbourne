# gee-ndvi-calculator-melbourne
student homework

墨尔本地区GEE NDVI交互式计算器

项目介绍
基于Google Earth Engine开发，允许用户选择墨尔本SA4区域，计算NDVI并导出结果。

功能特点
核心功能
- 选择墨尔本SA4级感兴趣区域
- 计算哨兵2号影像的NDVI（归一化植被指数）
- 可视化NDVI结果
- 导出NDVI影像（GeoTIFF格式）
- 导出SA2级NDVI统计数据（CSV格式）

使用步骤（H3）
1. 访问Web应用链接：ndvi-area-chosen  https://red-league-483507-j1.projects.earthengine.app/view/ndvi-area-chosen
2. 从下拉菜单选择SA4区域
3. 点击“运行NDVI”按钮
4. 查看NDVI可视化结果
5. 点击对应的导出按钮下载文件

技术依赖
- Google Earth Engine（GEE）平台
- JavaScript（GEE API）
- 哨兵2号卫星影像数据集

代码链接
- GEE脚本快照：https://code.earthengine.google.com/5334a6dd3702394cffe02de3bfe2da65
- Web应用链接：https://red-league-483507-j1.projects.earthengine.app/view/ndvi-area-chosen

示例代码
var ndvi = s2_comp.normalizedDifference(['B8', 'B4']).rename('NDVI');

代码块
javascript
// 计算NDVI的核心函数
function calcNDVI(img) {
  return img.normalizedDifference(BANDS_NDVI).rename('NDVI');
}
