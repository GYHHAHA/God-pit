# God-pit

## How to configurate default custom fonts in matplotlib?

1. Download 'file_name.ttf' to /usr/share/fonts/truetype/
2. Copy the file in step 1 to mpl-data/fonts/ttf/ which locates at matplotlib's install file folder
3. Then copy the same file to /usr/.fonts/
4. sudo fc-cache -fv
5. ~/.cache/matplotlib -fr
6. Check the real name for the 'ttf' file<br>
from matplotlib.font_manager import FontManager<br>
FontManager().ttflist
7. Change the default configurations in matplotlibrc<br>
font.family         : sans-serif<br>
font.sans-serif     : ..., Bitstream Vera Sans, Lucida Grande, Verdana, Geneva, Lucid, Arial, Helvetica, Avant Garde, sans-serif<br>
axes.unicode_minus  :False
8. Run the following codes<br>
from matplotlib.font_manager import _rebuild<br>
_rebuild()
9. Reboot

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
