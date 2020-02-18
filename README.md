# God-pit

## How to configurate default custom fonts in matplotlib?

1. 下载ttf文件到/usr/share/fonts/truetype/
2. 同时复制到matplotlib的安装文件夹的mpl-data/fonts/ttf/
3. 再复制到/usr/.fonts/
4. sudo fc-cache -fv
5. ~/.cache/matplotlib -fr
6. 查看ttf文件对应的字体名称<br>
from matplotlib.font_manager import FontManager<br>
FontManager().ttflist
7. 修改配置文件matplotlibrc<br>
font.family         : sans-serif<br>
font.sans-serif     : ..., Bitstream Vera Sans, Lucida Grande, Verdana, Geneva, Lucid, Arial, Helvetica, Avant Garde, sans-serif<br>
axes.unicode_minus  :False
8. 运行下面内容<br>
from matplotlib.font_manager import _rebuild<br>
_rebuild()
9. 重启

## How to use scatter method with a given radius series?

See [hear](https://stackoverflow.com/questions/48172928/scale-matplotlib-pyplot-axes-scatter-markersize-by-x-scale/48174228#48174228)!
