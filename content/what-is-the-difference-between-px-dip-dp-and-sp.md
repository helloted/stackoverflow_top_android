# px,dip,dp,sp之间的区别？
[What is the difference between “px”, “dip”, “dp” and “sp”?](https://stackoverflow.com/questions/2025282/what-is-the-difference-between-px-dip-dp-and-sp)

___



> 1

根据[安卓开发文档](https://developer.android.com/guide/topics/resources/more-resources#Dimension)

px:对应于屏幕上的实际像素

inch:基于屏幕的物理尺寸，1 inch = 2.54cm

mm:物理尺寸，毫米

pt:物理尺寸，1pt = 1/72inch

dp或者dip:与屏幕像素密度相关的数，当屏幕的dpi(每英寸点数)为160，这个时候1dp=1px，在其他密度屏幕上运行时，则按比例放大缩小，px = dp * (dpi / 160)

sp:跟dp类似，是用户字体进行缩放的单位

```none
+----------------+----------------+---------------+-------------------------------+
| Density Bucket | Screen Density | Physical Size | Pixel Size                    | 
+----------------+----------------+---------------+-------------------------------+
| ldpi           | 120 dpi        | 0.5 x 0.5 in  | 0.5 in * 120 dpi = 60x60 px   | 
+----------------+----------------+---------------+-------------------------------+
| mdpi           | 160 dpi        | 0.5 x 0.5 in  | 0.5 in * 160 dpi = 80x80 px   | 
+----------------+----------------+---------------+-------------------------------+
| hdpi           | 240 dpi        | 0.5 x 0.5 in  | 0.5 in * 240 dpi = 120x120 px | 
+----------------+----------------+---------------+-------------------------------+
| xhdpi          | 320 dpi        | 0.5 x 0.5 in  | 0.5 in * 320 dpi = 160x160 px | 
+----------------+----------------+---------------+-------------------------------+
| xxhdpi         | 480 dpi        | 0.5 x 0.5 in  | 0.5 in * 480 dpi = 240x240 px | 
+----------------+----------------+---------------+-------------------------------+
| xxxhdpi        | 640 dpi        | 0.5 x 0.5 in  | 0.5 in * 640 dpi = 320x320 px | 
+----------------+----------------+---------------+-------------------------------+
```