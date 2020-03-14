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
## Set customed font in r-base plot:

If you use Rmarkdown, you should add `{r, echo=FALSE, fig.showtext=TRUE ,message=FALSE}` to the chunk head.
```r
>>>library(showtext)
>>>showtext_auto(enable = TRUE)
>>>font_add('...', '....ttf')
>>>pdf('~/Desktop/test2/test.pdf')
>>>plot(c(1:10), xlab = 'ddsd', ylab = 'asdfsd', 
     main = '更改的字体', family = '...')
>>>dev.off()
```
```r
>>>library(ggplot2)
>>>ggplot(mtcars, aes(x=wt, y=mpg)) + geom_point() SegoePrint+
...        ggtitle("Fuel Efficiency of 32 Cars") +
...        xlab("you can 更改r-base中的字体 now") + ylab("Miles per Gallon")+
...        theme(text=element_text(family="..."))
```
## How to input Chinese character in RStudio on Linux?

See [here](https://github.com/JackieMium/libfcitxplatforminputcontextplugin.so). This is the only way works for me!

## How to custom template in RStudio?

See [here](https://chester.rbind.io/ecots2k16/template_pkg/). And you can also recustom in your r template package easily.

## How to mix python and r up in Rmarkdown?

See instruction from `fix.pdf` in the folder.
