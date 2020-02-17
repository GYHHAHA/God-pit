# God-pit

## Default custom font configuration in matplotlib

1. 下载ttf文件到/usr/share/fonts/truetype/
2. 同时复制到matplotlib的安装文件夹的mpl-data/fonts/ttf/
3. 再复制到/usr/.fonts/
4. sudo fc-cache -fv
5. ~/.cache/matplotlib -fr
6. 修改配置文件matplotlibrc<br>
font.family         : sans-serif<br>
font.sans-serif     : ..., Bitstream Vera Sans, Lucida Grande, Verdana, Geneva, Lucid, Arial, Helvetica, Avant Garde, sans-serif<br>
axes.unicode_minus  :False
7. 运行下面内容<br>
from matplotlib.font_manager import _rebuild<br>
_rebuild()
8. 重启
