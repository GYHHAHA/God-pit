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

See [here](https://stackoverflow.com/questions/48172928/scale-matplotlib-pyplot-axes-scatter-markersize-by-x-scale/48174228#48174228)!

## How to fix the legend handlers into given sizes?

```python
>>>fig,ax = plt.subplots(1,1)
>>>l1 = ax.scatter([0],[0], color='', marker='o', edgecolors='r', s=2000)
>>>l2 = ax.scatter(np.random.randn(50),np.random.randn(50))
>>>lgnd = ax.legend([l1,l2],['a','b'], loc='center',title='GYH',framealpha=0.5)
>>>lgnd.legendHandles[0]._sizes = [30]
>>>lgnd.legendHandles[1]._sizes = [30]
```
## How to make a round legend without scatter method?

```python
>>>ax.legend([Line2D(range(1), range(1), color="white", marker='o', markerfacecolor="red")],['a'])
```
