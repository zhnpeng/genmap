# genmap
自定义多个行政区域，然后通过调用百度地图API取得行政区域边界，转化成GeoJson格式提供下载。

## 使用方法：
<ol>
<li>把genmap.html里边http://api.map.baidu.com/api?v=1.5&ak=your_baidu_ak的your_baidu_ak替换成你的baidu api key
<a href="http://lbsyun.baidu.com/apiconsole/key">百度AK申请</a>
</li>
<li>双击genmap/genmap.html，在浏览器中打开</li>
<li>在浏览器中输入地图中心点</li>
<li>在浏览器中输入行政区域列表
注意：列表里的行政区域不应该有重叠的区域（比如上海市和浦东新区），大区域会覆盖掉小区域。
</li>
<li>.点击按钮 “生成地图并且预览"
成功的话就会在下面的预览图片里显示百度地图和紫色边框的地图轮拓，生成地图并且预览旁边会出现链接”下载地图文件“
</li>
<li>点击下载地图文件，下载地图XXX.json</li>
</ol>

## 效果图
(https://github.com/layjump/genmap/raw/master/screenshots/1508229208680.jpg)

## 输出文件格式
{% highlight json %}
{
  "type": "FeatureCollection",
  "features": [
    {
      "type": "Feature",
      "properties": {
        "name": "上海"
      },
      "geometry": {
        "type": "Polygon",
        "coordinates": [
          [
            [
              "122.029708",
              "31.144107"
            ],
            [
              "121.993529",
              "31.048415"
            ]
          ]
        ]
      }
    }
  ]
}
{% endhighlight %}
