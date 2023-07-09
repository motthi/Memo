# Matplotlib
## rcParams

```
plt.rcParams['font.family'] = 'Times New Roman'
plt.rcParams['figure.dpi'] = 300
plt.rcParams['mathtext.fontset'] = 'stix' # math font configuration
plt.rcParams["font.size"] = 15 # Overall font size

plt.rcParams['xtick.labelsize'] = 11 # Font size of x-axis
plt.rcParams['ytick.labelsize'] = 11 # Font size of y-axis
plt.rcParams['xtick.direction'] = 'in' # x axis in
plt.rcParams['ytick.direction'] = 'in' # y axis in

plt.rcParams['axes.linewidth'] = 1.0 # axis line width
plt.rcParams['axes.grid'] = True # make grid

plt.rcParams["legend.fancybox"] = False # rounded corners
plt.rcParams["legend.framealpha"] = 1 # Transparent, when 0, no fill
plt.rcParams["legend.edgecolor"] = 'white'
plt.rcParams["legend.fontsize"] = 10
plt.rcParams["legend.handlelength"] = 3 # The length of legend
plt.rcParams["legend.labelspacing"] = 1. # Vertical distance between legends
plt.rcParams["legend.handletextpad"] = 1. # Distance between legend's line and string
plt.rcParams["legend.markerscale"] = 2 # 点がある場合のmarker scale
plt.rcParams["legend.borderaxespad"] = 0.1 # 凡例の端とグラフの端を合わせる

plt.rcParams["savefig.bbox"] = 'tight'
plt.rcParams["savefig.pad_inches"] = 0.1
plt.rcParams["savefig.dpi"] = 300
```
