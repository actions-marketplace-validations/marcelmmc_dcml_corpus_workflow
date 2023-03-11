```python
import os
from git import Repo
import dimcat as dc
from ms3 import __version__ as ms3_version
```


```python
corpus_path = os.environ.get('CORPUS_PATH')
```


```python
repo = Repo(corpus_path)
notebook_repo = Repo('.', search_parent_directories=True)
notebook_repo_path = notebook_repo.git.rev_parse("--show-toplevel")
print(f"Notebook repository '{os.path.basename(notebook_repo_path)}' @ {notebook_repo.commit().hexsha[:7]}")
print(f"Data repo '{os.path.basename(corpus_path)}' @ {repo.commit().hexsha[:7]}")
print(f"dimcat version {dc.__version__}")
print(f"ms3 version {ms3_version}")
```

    Notebook repository 'dimcat' @ de5198b
    Data repo 'ligeti_etudes' @ d1b39b6
    dimcat version 0.3.0.post1.dev3+gde5198b
    ms3 version 1.2.4.post0.dev3+g5df6c9f



```python
from fractions import Fraction
import ms3
from IPython.display import HTML
from git import Repo
import plotly.express as px
import colorlover
import pandas as pd
pd.set_option("display.max_columns", 100)
```


```python
STD_LAYOUT = {
 'paper_bgcolor': '#FFFFFF',
 'plot_bgcolor': '#FFFFFF',
 'margin': {'l': 40, 'r': 0, 'b': 0, 't': 40, 'pad': 0},
 'font': {'size': 15}
}
#OUTPUT_DIR = "/home/hentsche/Documents/phd/romantic_piano_corpus_report/figures/"
OUTPUT_DIR = os.path.join(corpus_path, 'figures')
os.makedirs(OUTPUT_DIR, exist_ok=True)
#HTML(colorlover.to_html(colorlover.scales))
HTML(colorlover.to_html(colorlover.scales['9']['qual']['Paired']))
```




<div style="background-color:rgb(166,206,227);height:20px;width:20px;margin-bottom:0px;display:inline-block;"></div><div style="background-color:rgb(31,120,180);height:20px;width:20px;margin-bottom:0px;display:inline-block;"></div><div style="background-color:rgb(178,223,138);height:20px;width:20px;margin-bottom:0px;display:inline-block;"></div><div style="background-color:rgb(51,160,44);height:20px;width:20px;margin-bottom:0px;display:inline-block;"></div><div style="background-color:rgb(251,154,153);height:20px;width:20px;margin-bottom:0px;display:inline-block;"></div><div style="background-color:rgb(227,26,28);height:20px;width:20px;margin-bottom:0px;display:inline-block;"></div><div style="background-color:rgb(253,191,111);height:20px;width:20px;margin-bottom:0px;display:inline-block;"></div><div style="background-color:rgb(255,127,0);height:20px;width:20px;margin-bottom:0px;display:inline-block;"></div><div style="background-color:rgb(202,178,214);height:20px;width:20px;margin-bottom:0px;display:inline-block;"></div>




```python
fig = px.colors.qualitative.swatches()
fig.show()
```


        <script type="text/javascript">
        window.PlotlyConfig = {MathJaxConfig: 'local'};
        if (window.MathJax && window.MathJax.Hub && window.MathJax.Hub.Config) {window.MathJax.Hub.Config({SVG: {font: "STIX-Web"}});}
        if (typeof require !== 'undefined') {
        require.undef("plotly");
        define('plotly', function(require, exports, module) {
            /**
* plotly.js v2.18.2
* Copyright 2012-2023, Plotly, Inc.
* All rights reserved.
* Licensed under the MIT license
*/
/*! For license information please see plotly.min.js.LICENSE.txt */
        });
        require(['plotly'], function(Plotly) {
            window._Plotly = Plotly;
        });
        }
        </script>




<div>                            <div id="ae49ef2b-7929-4278-9715-deddf4341f8a" class="plotly-graph-div" style="height:760px; width:100%;"></div>            <script type="text/javascript">                require(["plotly"], function(Plotly) {                    window.PLOTLYENV=window.PLOTLYENV || {};                                    if (document.getElementById("ae49ef2b-7929-4278-9715-deddf4341f8a")) {                    Plotly.newPlot(                        "ae49ef2b-7929-4278-9715-deddf4341f8a",                        [{"customdata":[0,1,2,3,4,5,6,7,8,9,10],"hovertemplate":"%{y}[%{customdata}] = %{marker.color}<extra></extra>","marker":{"color":["rgb(229, 134, 6)","rgb(93, 105, 177)","rgb(82, 188, 163)","rgb(153, 201, 69)","rgb(204, 97, 176)","rgb(36, 121, 108)","rgb(218, 165, 27)","rgb(47, 138, 196)","rgb(118, 78, 159)","rgb(237, 100, 90)","rgb(165, 170, 153)"]},"orientation":"h","x":[1,1,1,1,1,1,1,1,1,1,1],"y":["Vivid","Vivid","Vivid","Vivid","Vivid","Vivid","Vivid","Vivid","Vivid","Vivid","Vivid"],"type":"bar"},{"customdata":[0,1,2,3,4,5,6,7,8,9,10],"hovertemplate":"%{y}[%{customdata}] = %{marker.color}<extra></extra>","marker":{"color":["rgb(136, 204, 238)","rgb(204, 102, 119)","rgb(221, 204, 119)","rgb(17, 119, 51)","rgb(51, 34, 136)","rgb(170, 68, 153)","rgb(68, 170, 153)","rgb(153, 153, 51)","rgb(136, 34, 85)","rgb(102, 17, 0)","rgb(136, 136, 136)"]},"orientation":"h","x":[1,1,1,1,1,1,1,1,1,1,1],"y":["Safe","Safe","Safe","Safe","Safe","Safe","Safe","Safe","Safe","Safe","Safe"],"type":"bar"},{"customdata":[0,1,2,3,4,5,6,7,8,9,10],"hovertemplate":"%{y}[%{customdata}] = %{marker.color}<extra></extra>","marker":{"color":["rgb(95, 70, 144)","rgb(29, 105, 150)","rgb(56, 166, 165)","rgb(15, 133, 84)","rgb(115, 175, 72)","rgb(237, 173, 8)","rgb(225, 124, 5)","rgb(204, 80, 62)","rgb(148, 52, 110)","rgb(111, 64, 112)","rgb(102, 102, 102)"]},"orientation":"h","x":[1,1,1,1,1,1,1,1,1,1,1],"y":["Prism","Prism","Prism","Prism","Prism","Prism","Prism","Prism","Prism","Prism","Prism"],"type":"bar"},{"customdata":[0,1,2,3,4,5,6,7,8,9,10],"hovertemplate":"%{y}[%{customdata}] = %{marker.color}<extra></extra>","marker":{"color":["rgb(102, 197, 204)","rgb(246, 207, 113)","rgb(248, 156, 116)","rgb(220, 176, 242)","rgb(135, 197, 95)","rgb(158, 185, 243)","rgb(254, 136, 177)","rgb(201, 219, 116)","rgb(139, 224, 164)","rgb(180, 151, 231)","rgb(179, 179, 179)"]},"orientation":"h","x":[1,1,1,1,1,1,1,1,1,1,1],"y":["Pastel","Pastel","Pastel","Pastel","Pastel","Pastel","Pastel","Pastel","Pastel","Pastel","Pastel"],"type":"bar"},{"customdata":[0,1,2,3,4,5,6,7,8,9,10],"hovertemplate":"%{y}[%{customdata}] = %{marker.color}<extra></extra>","marker":{"color":["rgb(127, 60, 141)","rgb(17, 165, 121)","rgb(57, 105, 172)","rgb(242, 183, 1)","rgb(231, 63, 116)","rgb(128, 186, 90)","rgb(230, 131, 16)","rgb(0, 134, 149)","rgb(207, 28, 144)","rgb(249, 123, 114)","rgb(165, 170, 153)"]},"orientation":"h","x":[1,1,1,1,1,1,1,1,1,1,1],"y":["Bold","Bold","Bold","Bold","Bold","Bold","Bold","Bold","Bold","Bold","Bold"],"type":"bar"},{"customdata":[0,1,2,3,4,5,6,7,8,9,10],"hovertemplate":"%{y}[%{customdata}] = %{marker.color}<extra></extra>","marker":{"color":["rgb(133, 92, 117)","rgb(217, 175, 107)","rgb(175, 100, 88)","rgb(115, 111, 76)","rgb(82, 106, 131)","rgb(98, 83, 119)","rgb(104, 133, 92)","rgb(156, 156, 94)","rgb(160, 97, 119)","rgb(140, 120, 93)","rgb(124, 124, 124)"]},"orientation":"h","x":[1,1,1,1,1,1,1,1,1,1,1],"y":["Antique","Antique","Antique","Antique","Antique","Antique","Antique","Antique","Antique","Antique","Antique"],"type":"bar"},{"customdata":[0,1,2,3,4,5,6,7,8,9,10,11],"hovertemplate":"%{y}[%{customdata}] = %{marker.color}<extra></extra>","marker":{"color":["rgb(141,211,199)","rgb(255,255,179)","rgb(190,186,218)","rgb(251,128,114)","rgb(128,177,211)","rgb(253,180,98)","rgb(179,222,105)","rgb(252,205,229)","rgb(217,217,217)","rgb(188,128,189)","rgb(204,235,197)","rgb(255,237,111)"]},"orientation":"h","x":[1,1,1,1,1,1,1,1,1,1,1,1],"y":["Set3","Set3","Set3","Set3","Set3","Set3","Set3","Set3","Set3","Set3","Set3","Set3"],"type":"bar"},{"customdata":[0,1,2,3,4,5,6,7],"hovertemplate":"%{y}[%{customdata}] = %{marker.color}<extra></extra>","marker":{"color":["rgb(179,226,205)","rgb(253,205,172)","rgb(203,213,232)","rgb(244,202,228)","rgb(230,245,201)","rgb(255,242,174)","rgb(241,226,204)","rgb(204,204,204)"]},"orientation":"h","x":[1,1,1,1,1,1,1,1],"y":["Pastel2","Pastel2","Pastel2","Pastel2","Pastel2","Pastel2","Pastel2","Pastel2"],"type":"bar"},{"customdata":[0,1,2,3,4,5,6,7],"hovertemplate":"%{y}[%{customdata}] = %{marker.color}<extra></extra>","marker":{"color":["rgb(102,194,165)","rgb(252,141,98)","rgb(141,160,203)","rgb(231,138,195)","rgb(166,216,84)","rgb(255,217,47)","rgb(229,196,148)","rgb(179,179,179)"]},"orientation":"h","x":[1,1,1,1,1,1,1,1],"y":["Set2","Set2","Set2","Set2","Set2","Set2","Set2","Set2"],"type":"bar"},{"customdata":[0,1,2,3,4,5,6,7],"hovertemplate":"%{y}[%{customdata}] = %{marker.color}<extra></extra>","marker":{"color":["rgb(27,158,119)","rgb(217,95,2)","rgb(117,112,179)","rgb(231,41,138)","rgb(102,166,30)","rgb(230,171,2)","rgb(166,118,29)","rgb(102,102,102)"]},"orientation":"h","x":[1,1,1,1,1,1,1,1],"y":["Dark2","Dark2","Dark2","Dark2","Dark2","Dark2","Dark2","Dark2"],"type":"bar"},{"customdata":[0,1,2,3,4,5,6,7,8],"hovertemplate":"%{y}[%{customdata}] = %{marker.color}<extra></extra>","marker":{"color":["rgb(251,180,174)","rgb(179,205,227)","rgb(204,235,197)","rgb(222,203,228)","rgb(254,217,166)","rgb(255,255,204)","rgb(229,216,189)","rgb(253,218,236)","rgb(242,242,242)"]},"orientation":"h","x":[1,1,1,1,1,1,1,1,1],"y":["Pastel1","Pastel1","Pastel1","Pastel1","Pastel1","Pastel1","Pastel1","Pastel1","Pastel1"],"type":"bar"},{"customdata":[0,1,2,3,4,5,6,7,8],"hovertemplate":"%{y}[%{customdata}] = %{marker.color}<extra></extra>","marker":{"color":["rgb(228,26,28)","rgb(55,126,184)","rgb(77,175,74)","rgb(152,78,163)","rgb(255,127,0)","rgb(255,255,51)","rgb(166,86,40)","rgb(247,129,191)","rgb(153,153,153)"]},"orientation":"h","x":[1,1,1,1,1,1,1,1,1],"y":["Set1","Set1","Set1","Set1","Set1","Set1","Set1","Set1","Set1"],"type":"bar"},{"customdata":[0,1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20,21,22,23],"hovertemplate":"%{y}[%{customdata}] = %{marker.color}<extra></extra>","marker":{"color":["#FD3216","#00FE35","#6A76FC","#FED4C4","#FE00CE","#0DF9FF","#F6F926","#FF9616","#479B55","#EEA6FB","#DC587D","#D626FF","#6E899C","#00B5F7","#B68E00","#C9FBE5","#FF0092","#22FFA7","#E3EE9E","#86CE00","#BC7196","#7E7DCD","#FC6955","#E48F72"]},"orientation":"h","x":[1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1],"y":["Light24","Light24","Light24","Light24","Light24","Light24","Light24","Light24","Light24","Light24","Light24","Light24","Light24","Light24","Light24","Light24","Light24","Light24","Light24","Light24","Light24","Light24","Light24","Light24"],"type":"bar"},{"customdata":[0,1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20,21,22,23],"hovertemplate":"%{y}[%{customdata}] = %{marker.color}<extra></extra>","marker":{"color":["#2E91E5","#E15F99","#1CA71C","#FB0D0D","#DA16FF","#222A2A","#B68100","#750D86","#EB663B","#511CFB","#00A08B","#FB00D1","#FC0080","#B2828D","#6C7C32","#778AAE","#862A16","#A777F1","#620042","#1616A7","#DA60CA","#6C4516","#0D2A63","#AF0038"]},"orientation":"h","x":[1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1],"y":["Dark24","Dark24","Dark24","Dark24","Dark24","Dark24","Dark24","Dark24","Dark24","Dark24","Dark24","Dark24","Dark24","Dark24","Dark24","Dark24","Dark24","Dark24","Dark24","Dark24","Dark24","Dark24","Dark24","Dark24"],"type":"bar"},{"customdata":[0,1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25],"hovertemplate":"%{y}[%{customdata}] = %{marker.color}<extra></extra>","marker":{"color":["#AA0DFE","#3283FE","#85660D","#782AB6","#565656","#1C8356","#16FF32","#F7E1A0","#E2E2E2","#1CBE4F","#C4451C","#DEA0FD","#FE00FA","#325A9B","#FEAF16","#F8A19F","#90AD1C","#F6222E","#1CFFCE","#2ED9FF","#B10DA1","#C075A6","#FC1CBF","#B00068","#FBE426","#FA0087"]},"orientation":"h","x":[1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1],"y":["Alphabet","Alphabet","Alphabet","Alphabet","Alphabet","Alphabet","Alphabet","Alphabet","Alphabet","Alphabet","Alphabet","Alphabet","Alphabet","Alphabet","Alphabet","Alphabet","Alphabet","Alphabet","Alphabet","Alphabet","Alphabet","Alphabet","Alphabet","Alphabet","Alphabet","Alphabet"],"type":"bar"},{"customdata":[0,1,2,3,4,5,6,7,8,9],"hovertemplate":"%{y}[%{customdata}] = %{marker.color}<extra></extra>","marker":{"color":["#4C78A8","#F58518","#E45756","#72B7B2","#54A24B","#EECA3B","#B279A2","#FF9DA6","#9D755D","#BAB0AC"]},"orientation":"h","x":[1,1,1,1,1,1,1,1,1,1],"y":["T10","T10","T10","T10","T10","T10","T10","T10","T10","T10"],"type":"bar"},{"customdata":[0,1,2,3,4,5,6,7,8,9],"hovertemplate":"%{y}[%{customdata}] = %{marker.color}<extra></extra>","marker":{"color":["#3366CC","#DC3912","#FF9900","#109618","#990099","#0099C6","#DD4477","#66AA00","#B82E2E","#316395"]},"orientation":"h","x":[1,1,1,1,1,1,1,1,1,1],"y":["G10","G10","G10","G10","G10","G10","G10","G10","G10","G10"],"type":"bar"},{"customdata":[0,1,2,3,4,5,6,7,8,9],"hovertemplate":"%{y}[%{customdata}] = %{marker.color}<extra></extra>","marker":{"color":["#1F77B4","#FF7F0E","#2CA02C","#D62728","#9467BD","#8C564B","#E377C2","#7F7F7F","#BCBD22","#17BECF"]},"orientation":"h","x":[1,1,1,1,1,1,1,1,1,1],"y":["D3","D3","D3","D3","D3","D3","D3","D3","D3","D3"],"type":"bar"},{"customdata":[0,1,2,3,4,5,6,7,8,9],"hovertemplate":"%{y}[%{customdata}] = %{marker.color}<extra></extra>","marker":{"color":["#636EFA","#EF553B","#00CC96","#AB63FA","#FFA15A","#19D3F3","#FF6692","#B6E880","#FF97FF","#FECB52"]},"orientation":"h","x":[1,1,1,1,1,1,1,1,1,1],"y":["Plotly","Plotly","Plotly","Plotly","Plotly","Plotly","Plotly","Plotly","Plotly","Plotly"],"type":"bar"}],                        {"bargap":0.5,"barmode":"stack","barnorm":"fraction","height":760,"margin":{"b":10},"showlegend":false,"template":{"data":{"barpolar":[{"marker":{"line":{"color":"#E5ECF6","width":0.5},"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"barpolar"}],"bar":[{"error_x":{"color":"#2a3f5f"},"error_y":{"color":"#2a3f5f"},"marker":{"line":{"color":"#E5ECF6","width":0.5},"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"bar"}],"carpet":[{"aaxis":{"endlinecolor":"#2a3f5f","gridcolor":"white","linecolor":"white","minorgridcolor":"white","startlinecolor":"#2a3f5f"},"baxis":{"endlinecolor":"#2a3f5f","gridcolor":"white","linecolor":"white","minorgridcolor":"white","startlinecolor":"#2a3f5f"},"type":"carpet"}],"choropleth":[{"colorbar":{"outlinewidth":0,"ticks":""},"type":"choropleth"}],"contourcarpet":[{"colorbar":{"outlinewidth":0,"ticks":""},"type":"contourcarpet"}],"contour":[{"colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"type":"contour"}],"heatmapgl":[{"colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"type":"heatmapgl"}],"heatmap":[{"colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"type":"heatmap"}],"histogram2dcontour":[{"colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"type":"histogram2dcontour"}],"histogram2d":[{"colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"type":"histogram2d"}],"histogram":[{"marker":{"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"histogram"}],"mesh3d":[{"colorbar":{"outlinewidth":0,"ticks":""},"type":"mesh3d"}],"parcoords":[{"line":{"colorbar":{"outlinewidth":0,"ticks":""}},"type":"parcoords"}],"pie":[{"automargin":true,"type":"pie"}],"scatter3d":[{"line":{"colorbar":{"outlinewidth":0,"ticks":""}},"marker":{"colorbar":{"outlinewidth":0,"ticks":""}},"type":"scatter3d"}],"scattercarpet":[{"marker":{"colorbar":{"outlinewidth":0,"ticks":""}},"type":"scattercarpet"}],"scattergeo":[{"marker":{"colorbar":{"outlinewidth":0,"ticks":""}},"type":"scattergeo"}],"scattergl":[{"marker":{"colorbar":{"outlinewidth":0,"ticks":""}},"type":"scattergl"}],"scattermapbox":[{"marker":{"colorbar":{"outlinewidth":0,"ticks":""}},"type":"scattermapbox"}],"scatterpolargl":[{"marker":{"colorbar":{"outlinewidth":0,"ticks":""}},"type":"scatterpolargl"}],"scatterpolar":[{"marker":{"colorbar":{"outlinewidth":0,"ticks":""}},"type":"scatterpolar"}],"scatter":[{"fillpattern":{"fillmode":"overlay","size":10,"solidity":0.2},"type":"scatter"}],"scatterternary":[{"marker":{"colorbar":{"outlinewidth":0,"ticks":""}},"type":"scatterternary"}],"surface":[{"colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"type":"surface"}],"table":[{"cells":{"fill":{"color":"#EBF0F8"},"line":{"color":"white"}},"header":{"fill":{"color":"#C8D4E3"},"line":{"color":"white"}},"type":"table"}]},"layout":{"annotationdefaults":{"arrowcolor":"#2a3f5f","arrowhead":0,"arrowwidth":1},"autotypenumbers":"strict","coloraxis":{"colorbar":{"outlinewidth":0,"ticks":""}},"colorscale":{"diverging":[[0,"#8e0152"],[0.1,"#c51b7d"],[0.2,"#de77ae"],[0.3,"#f1b6da"],[0.4,"#fde0ef"],[0.5,"#f7f7f7"],[0.6,"#e6f5d0"],[0.7,"#b8e186"],[0.8,"#7fbc41"],[0.9,"#4d9221"],[1,"#276419"]],"sequential":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"sequentialminus":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]},"colorway":["#636efa","#EF553B","#00cc96","#ab63fa","#FFA15A","#19d3f3","#FF6692","#B6E880","#FF97FF","#FECB52"],"font":{"color":"#2a3f5f"},"geo":{"bgcolor":"white","lakecolor":"white","landcolor":"#E5ECF6","showlakes":true,"showland":true,"subunitcolor":"white"},"hoverlabel":{"align":"left"},"hovermode":"closest","mapbox":{"style":"light"},"paper_bgcolor":"white","plot_bgcolor":"#E5ECF6","polar":{"angularaxis":{"gridcolor":"white","linecolor":"white","ticks":""},"bgcolor":"#E5ECF6","radialaxis":{"gridcolor":"white","linecolor":"white","ticks":""}},"scene":{"xaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","gridwidth":2,"linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white"},"yaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","gridwidth":2,"linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white"},"zaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","gridwidth":2,"linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white"}},"shapedefaults":{"line":{"color":"#2a3f5f"}},"ternary":{"aaxis":{"gridcolor":"white","linecolor":"white","ticks":""},"baxis":{"gridcolor":"white","linecolor":"white","ticks":""},"bgcolor":"#E5ECF6","caxis":{"gridcolor":"white","linecolor":"white","ticks":""}},"title":{"x":0.05},"xaxis":{"automargin":true,"gridcolor":"white","linecolor":"white","ticks":"","title":{"standoff":15},"zerolinecolor":"white","zerolinewidth":2},"yaxis":{"automargin":true,"gridcolor":"white","linecolor":"white","ticks":"","title":{"standoff":15},"zerolinecolor":"white","zerolinewidth":2}}},"title":{"text":"plotly.colors.qualitative"},"xaxis":{"range":[-0.02,1.02],"showgrid":false,"showticklabels":false}},                        {"responsive": true}                    ).then(function(){

var gd = document.getElementById('ae49ef2b-7929-4278-9715-deddf4341f8a');
var x = new MutationObserver(function (mutations, observer) {{
        var display = window.getComputedStyle(gd).display;
        if (!display || display === 'none') {{
            console.log([gd, 'removed!']);
            Plotly.purge(gd);
            observer.disconnect();
        }}
}});

// Listen for the removal of the full notebook cells
var notebookContainer = gd.closest('#notebook-container');
if (notebookContainer) {{
    x.observe(notebookContainer, {childList: true});
}}

// Listen for the clearing of the current output cell
var outputEl = gd.closest('.output');
if (outputEl) {{
    x.observe(outputEl, {childList: true});
}}

                        })                };                });            </script>        </div>



```python
corpus_color_scale = px.colors.qualitative.D3
```

# Overview


```python
dataset = dc.Dataset(directory=corpus_path)
dataset.data
```




    [[1mdefault[0;0m|all]
    All corpora
    -----------
    View: This view is called 'default'. It 
    	- excludes fnames that are not contained in the metadata,
    	- filters out file extensions requiring conversion (such as .xml), and
    	- excludes review files and folders.
    
                       has   active   scores measures           notes       
                  metadata     view detected detected parsed detected parsed
    corpus                                                                  
    ligeti_etudes      yes  default        1        1      1        1      1




```python
all_metadata = dataset.data.metadata()
print(f"Concatenated 'metadata.tsv' files cover {len(all_metadata)} of the {dataset.data.n_pieces} scores.")
all_metadata.groupby(level=0).nth(0)
```

    Concatenated 'metadata.tsv' files cover 1 of the 1 scores.





<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>TimeSig</th>
      <th>KeySig</th>
      <th>last_mc</th>
      <th>last_mn</th>
      <th>length_qb</th>
      <th>last_mc_unfolded</th>
      <th>last_mn_unfolded</th>
      <th>length_qb_unfolded</th>
      <th>all_notes_qb</th>
      <th>n_onsets</th>
      <th>n_onset_positions</th>
      <th>guitar_chord_count</th>
      <th>form_label_count</th>
      <th>label_count</th>
      <th>composed_start</th>
      <th>composed_end</th>
      <th>composed_source</th>
      <th>composer</th>
      <th>workTitle</th>
      <th>movementNumber</th>
      <th>movementTitle</th>
      <th>workNumber</th>
      <th>poet</th>
      <th>lyricist</th>
      <th>arranger</th>
      <th>copyright</th>
      <th>creationDate</th>
      <th>mscVersion</th>
      <th>platform</th>
      <th>source</th>
      <th>translator</th>
      <th>title_text</th>
      <th>subtitle_text</th>
      <th>composer_text</th>
      <th>musescore</th>
      <th>ms3_version</th>
      <th>subdirectory</th>
      <th>rel_path</th>
      <th>has_drumset</th>
      <th>ambitus</th>
      <th>wdt:P86</th>
      <th>wikidata</th>
      <th>musicbrainz</th>
      <th>originalFormat</th>
      <th>staff_1_ambitus</th>
      <th>staff_1_instrument</th>
      <th>staff_2_ambitus</th>
      <th>staff_2_instrument</th>
      <th>staff_3_ambitus</th>
      <th>staff_3_instrument</th>
    </tr>
    <tr>
      <th>corpus</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>ligeti_etudes</th>
      <td>1: 4/4</td>
      <td>1: 0</td>
      <td>39</td>
      <td>39</td>
      <td>156.0</td>
      <td>39</td>
      <td>39</td>
      <td>156.0</td>
      <td>384.04</td>
      <td>1114</td>
      <td>703</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1985</td>
      <td>1985</td>
      <td>https://en.wikipedia.org/wiki/%C3%89tudes_(Lig...</td>
      <td>György Ligeti</td>
      <td>Études pour piano, Book 1</td>
      <td>2</td>
      <td>Cordes à vide</td>
      <td>13</td>
      <td>NaN</td>
      <td>Friedrich Rückert</td>
      <td>NaN</td>
      <td>OpenScore (CC0)</td>
      <td>2018-06-10</td>
      <td>3.02</td>
      <td>Microsoft Windows</td>
      <td>https://musescore.com/openscore-lieder-corpus/...</td>
      <td>NaN</td>
      <td>Étude 2: Cordes à vide</td>
      <td>vol2no2</td>
      <td>Ligeti</td>
      <td>3.6.2</td>
      <td>1.2.4</td>
      <td>MS3</td>
      <td>MS3/vol1no2.mscx</td>
      <td>False</td>
      <td>21-96 (A0-B#6)</td>
      <td>https://www.wikidata.org/wiki/Q154331</td>
      <td>https://www.wikidata.org/wiki/Q3592623</td>
      <td>https://musicbrainz.org/work/e48a5e9a-dca2-4b3...</td>
      <td>musicxml</td>
      <td>34-96 (Bb1-B#6)</td>
      <td>Grand Piano</td>
      <td>53-92 (F3-G#6)</td>
      <td>Grand Piano</td>
      <td>21-84 (A0-B#5)</td>
      <td>Grand Piano</td>
    </tr>
  </tbody>
</table>
</div>




```python
annotated = dc.IsAnnotatedFilter().process_data(dataset)
print(f"Before: {len(dataset.indices[()])} IDs, after filtering: {len(annotated.indices[()])}")
```


    ---------------------------------------------------------------------------

    KeyError                                  Traceback (most recent call last)

    Cell In[10], line 2
          1 annotated = dc.IsAnnotatedFilter().process_data(dataset)
    ----> 2 print(f"Before: {len(dataset.indices[()])} IDs, after filtering: {len(annotated.indices[()])}")


    KeyError: ()


**Choose here if you want to see stats for all or only for annotated scores.**


```python
#selected = dataset
selected = annotated
```

**Compute chronological order**


```python
summary = all_metadata[all_metadata.label_count > 0]
print(f"Selected metadata rows cover {len(summary)} of the {len(sum((ixs for _, ixs in selected.iter_groups()), start=[]))} scores.")
mean_composition_years = summary.groupby(level=0).composed_end.mean().astype(int).sort_values()
chronological_order = mean_composition_years.index.to_list()
dataset_colors = dict(zip(chronological_order, corpus_color_scale))
chronological_order
```


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    Cell In[12], line 2
          1 summary = all_metadata[all_metadata.label_count > 0]
    ----> 2 print(f"Selected metadata rows cover {len(summary)} of the {len(sum((ixs for _, ixs in selected.iter_groups()), start=[]))} scores.")
          3 mean_composition_years = summary.groupby(level=0).composed_end.mean().astype(int).sort_values()
          4 chronological_order = mean_composition_years.index.to_list()


    Cell In[12], line 2, in <genexpr>(.0)
          1 summary = all_metadata[all_metadata.label_count > 0]
    ----> 2 print(f"Selected metadata rows cover {len(summary)} of the {len(sum((ixs for _, ixs in selected.iter_groups()), start=[]))} scores.")
          3 mean_composition_years = summary.groupby(level=0).composed_end.mean().astype(int).sort_values()
          4 chronological_order = mean_composition_years.index.to_list()


    File /dimcat/src/dimcat/data.py:132, in Data.iter_groups(self)
        122 """Iterate through groups of indices as defined by the previously applied Groupers.
        123 
        124 Yields
       (...)
        129     A list of IDs belonging to the same group.
        130 """
        131 if len(self.indices) == 0:
    --> 132     raise ValueError("No data has been loaded.")
        133 if any(len(index_list) == 0 for index_list in self.indices.values()):
        134     print("Data object contains empty groups.")


    ValueError: No data has been loaded.


## Notes


```python
all_notes = selected.get_facet('notes')
print(f"{len(all_notes.index)} notes over {len(all_notes.groupby(level=[0,1]))} files.")
all_notes.head()
```


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    Cell In[13], line 1
    ----> 1 all_notes = selected.get_facet('notes')
          2 print(f"{len(all_notes.index)} notes over {len(all_notes.groupby(level=[0,1]))} files.")
          3 all_notes.head()


    File /dimcat/src/dimcat/data.py:384, in Dataset.get_facet(self, what, unfold)
        369 def get_facet(self, what, unfold=False):
        370     """Uses _.iter_facet() to collect and concatenate all DataFrames for a particular facet.
        371 
        372     Parameters
       (...)
        382     :obj:`pandas.DataFrame`
        383     """
    --> 384     group_dfs = {
        385         group: df
        386         for group, dfs in self.iter_facet(
        387             what=what, unfold=unfold, concatenate=True
        388         )
        389         for df in dfs.values()
        390     }
        391     if len(group_dfs) == 1:
        392         return list(group_dfs.values())[0]


    File /dimcat/src/dimcat/data.py:384, in <dictcomp>(.0)
        369 def get_facet(self, what, unfold=False):
        370     """Uses _.iter_facet() to collect and concatenate all DataFrames for a particular facet.
        371 
        372     Parameters
       (...)
        382     :obj:`pandas.DataFrame`
        383     """
    --> 384     group_dfs = {
        385         group: df
        386         for group, dfs in self.iter_facet(
        387             what=what, unfold=unfold, concatenate=True
        388         )
        389         for df in dfs.values()
        390     }
        391     if len(group_dfs) == 1:
        392         return list(group_dfs.values())[0]


    File /dimcat/src/dimcat/data.py:612, in Dataset.iter_facet(self, what, unfold, concatenate, ignore_groups)
        607 if sum((concatenate, ignore_groups)) > 1:
        608     raise ValueError(
        609         "Arguments 'concatenate' and 'ignore_groups' are in conflict, choose one "
        610         "or use the method get_facet()."
        611     )
    --> 612 for group, index_group in self.iter_groups():
        613     result = {}
        614     missing_id = []


    File /dimcat/src/dimcat/data.py:132, in Data.iter_groups(self)
        122 """Iterate through groups of indices as defined by the previously applied Groupers.
        123 
        124 Yields
       (...)
        129     A list of IDs belonging to the same group.
        130 """
        131 if len(self.indices) == 0:
    --> 132     raise ValueError("No data has been loaded.")
        133 if any(len(index_list) == 0 for index_list in self.indices.values()):
        134     print("Data object contains empty groups.")


    ValueError: No data has been loaded.



```python
def weight_notes(nl, group_col='midi', precise=True):
    summed_durations = nl.groupby(group_col).duration_qb.sum()
    summed_durations /= summed_durations.min() # normalize such that the shortest duration results in 1 occurrence
    if not precise:
        # This simple trick reduces compute time but also precision:
        # The rationale is to have the smallest value be slightly larger than 0.5 because
        # if it was exactly 0.5 it would be rounded down by repeat_notes_according_to_weights()
        summed_durations /= 1.9999999
    return repeat_notes_according_to_weights(summed_durations)
    
def repeat_notes_according_to_weights(weights):
    counts = weights.round().astype(int)
    counts_reflecting_weights = []
    for pitch, count in counts.iteritems():
        counts_reflecting_weights.extend([pitch]*count)
    return pd.Series(counts_reflecting_weights)


```
grouped_notes = all_notes.groupby(level=0)
weighted_midi = pd.concat([weight_notes(nl, 'midi', precise=False) for _, nl in grouped_notes], axis=1, keys=grouped_notes.groups.keys())

yaxis=dict(tickmode= 'array',
           tickvals= [12, 24, 36, 48, 60, 72, 84, 96],
           ticktext = ["C0", "C1", "C2", "C3", "C4", "C5", "C6", "C7"],
           gridcolor='lightgrey',
           )
fig = px.violin(weighted_midi, labels=dict(variable='', value='pitch'), box=True, height=500,
               category_orders=chronological_order,
               ) #, title="Distribution of pitches per dataset"
fig.update_layout(yaxis=yaxis, **STD_LAYOUT)
fig.write_image(os.path.join(OUTPUT_DIR, "ambitus_per_dataset.png"), scale=2)
fig.show()

```python
dataset_names = dict(
    beethoven_piano_sonatas='Beethoven Sonatas',
    chopin_mazurkas='Chopin Mazurkas',
    debussy_suite_bergamasque='Debussy Suite',
    dvorak_silhouettes="Dvořák Silhouettes",
    grieg_lyric_pieces="Grieg Lyric Pieces",
    liszt_pelerinage="Liszt Années",
    medtner_tales="Medtner Tales",
    schumann_kinderszenen="Schumann Kinderszenen",
    tchaikovsky_seasons="Tchaikovsky Seasons"
)
dataset_name_colors = {dataset_names[corp]: color for corp, color in dataset_colors.items()}
chronological_dataset_names = [dataset_names[corp] for corp in chronological_order]
all_notes['dataset_name'] = all_notes.index.get_level_values(0).map(dataset_names)
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[15], line 12
          1 dataset_names = dict(
          2     beethoven_piano_sonatas='Beethoven Sonatas',
          3     chopin_mazurkas='Chopin Mazurkas',
       (...)
         10     tchaikovsky_seasons="Tchaikovsky Seasons"
         11 )
    ---> 12 dataset_name_colors = {dataset_names[corp]: color for corp, color in dataset_colors.items()}
         13 chronological_dataset_names = [dataset_names[corp] for corp in chronological_order]
         14 all_notes['dataset_name'] = all_notes.index.get_level_values(0).map(dataset_names)


    NameError: name 'dataset_colors' is not defined



```python
grouped_notes = all_notes.groupby('dataset_name')
weighted_midi = pd.concat([weight_notes(nl, 'midi', precise=False) for _, nl in grouped_notes], keys=grouped_notes.groups.keys()).reset_index(level=0)
weighted_midi.columns = ['dataset', 'midi']
weighted_midi
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[16], line 1
    ----> 1 grouped_notes = all_notes.groupby('dataset_name')
          2 weighted_midi = pd.concat([weight_notes(nl, 'midi', precise=False) for _, nl in grouped_notes], keys=grouped_notes.groups.keys()).reset_index(level=0)
          3 weighted_midi.columns = ['dataset', 'midi']


    NameError: name 'all_notes' is not defined



```python
yaxis=dict(tickmode= 'array',
           tickvals= [12, 24, 36, 48, 60, 72, 84, 96],
           ticktext = ["C0", "C1", "C2", "C3", "C4", "C5", "C6", "C7"],
           gridcolor='lightgrey',
           )
fig = px.violin(weighted_midi, x='dataset', y='midi', color='dataset', box=True,
                labels=dict(
                    dataset='',
                    midi='distribution of pitches by duration'
                ),
                category_orders=dict(dataset=chronological_dataset_names),
                color_discrete_map=dataset_name_colors,
                width=1000, height=600,
               )
fig.update_traces(spanmode='hard') # do not extend beyond outliers
fig.update_layout(yaxis=yaxis, **STD_LAYOUT,
                 showlegend=False)
fig.write_image(os.path.join(OUTPUT_DIR, "ambitus_per_dataset_colored.png"), scale=2)
fig.show()
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[17], line 6
          1 yaxis=dict(tickmode= 'array',
          2            tickvals= [12, 24, 36, 48, 60, 72, 84, 96],
          3            ticktext = ["C0", "C1", "C2", "C3", "C4", "C5", "C6", "C7"],
          4            gridcolor='lightgrey',
          5            )
    ----> 6 fig = px.violin(weighted_midi, x='dataset', y='midi', color='dataset', box=True,
          7                 labels=dict(
          8                     dataset='',
          9                     midi='distribution of pitches by duration'
         10                 ),
         11                 category_orders=dict(dataset=chronological_dataset_names),
         12                 color_discrete_map=dataset_name_colors,
         13                 width=1000, height=600,
         14                )
         15 fig.update_traces(spanmode='hard') # do not extend beyond outliers
         16 fig.update_layout(yaxis=yaxis, **STD_LAYOUT,
         17                  showlegend=False)


    NameError: name 'weighted_midi' is not defined

weighted_tpc = pd.concat([weight_notes(nl, 'tpc') for _, nl in grouped_notes], axis=1, keys=grouped_notes.groups.keys())
weighted_tpcyaxis=dict(
    tickmode= 'array',
    tickvals= [-12, -9, -6, -3, 0, 3, 6, 9, 12, 15, 18],
    ticktext = ["Dbb", "Bbb", "Gb", "Eb", "C", "A", "F#", "D#", "B#", "G##", "E##"],
    gridcolor='lightgrey',
    zerolinecolor='lightgrey',
    zeroline=True
           )
fig = px.violin(weighted_tpc, labels=dict(variable='', value='pitch class'), box=True, height=500)
fig.update_layout(yaxis=yaxis, **STD_LAYOUT)
fig.write_image(os.path.join(OUTPUT_DIR, "tpc_per_dataset.png"), scale=2)
fig.show()# adapted from https://plotly.com/python/violin/#ridgeline-plot
fig = go.Figure()
for corp, data_line in weighted_tpc.iteritems():
    fig.add_trace(go.Violin(x=data_line, name=corp))

fig.update_traces(side='positive', orientation='h', width=2, points=False)
fig.update_layout(xaxis_showgrid=False, xaxis_zeroline=True, height=600)
fig.show()

```python
bar_data = all_notes.groupby('tpc').duration_qb.sum().reset_index()
bar_data.to_csv('romantic_tpc_profile.tsv.zip', sep='\t')
x_values = list(range(bar_data.tpc.min(), bar_data.tpc.max()+1))
x_names = ms3.fifths2name(x_values)
fig = px.bar(bar_data, x='tpc', y='duration_qb',
                 labels=dict(tpc='Named pitch class',
                             duration_qb='Duration in quarter notes'
                            ),
             color_discrete_sequence=corpus_color_scale,
             width=1000, height=300,
            )
fig.update_layout(**STD_LAYOUT)
fig.update_yaxes(gridcolor='lightgrey')
fig.update_xaxes(gridcolor='lightgrey', zerolinecolor='grey', tickmode='array', 
                 tickvals=x_values, ticktext = x_names, dtick=1, ticks='outside', tickcolor='black', 
                 minor=dict(dtick=6, gridcolor='grey', showgrid=True),
                )
fig.write_image(os.path.join(OUTPUT_DIR, "tpc_distribution_overall.png"), scale=2)
fig.show()
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[18], line 1
    ----> 1 bar_data = all_notes.groupby('tpc').duration_qb.sum().reset_index()
          2 bar_data.to_csv('romantic_tpc_profile.tsv.zip', sep='\t')
          3 x_values = list(range(bar_data.tpc.min(), bar_data.tpc.max()+1))


    NameError: name 'all_notes' is not defined



```python
scatter_data = all_notes.groupby(['dataset_name', 'tpc']).duration_qb.sum().reset_index()
fig = px.scatter(scatter_data, x='tpc', y='duration_qb', color='dataset_name', 
                 labels=dict(
                     duration_qb='duration',
                     tpc='named pitch class',
                 ),
                 category_orders=dict(dataset=chronological_dataset_names),
                 color_discrete_map=dataset_name_colors,
                 facet_col='dataset_name', facet_col_wrap=3, facet_col_spacing=0.03,
                 width=1000, height=500,
                )
fig.update_traces(mode='lines+markers')
fig.for_each_annotation(lambda a: a.update(text=a.text.split("=")[-1]))
fig.update_layout(**STD_LAYOUT, showlegend=False)
fig.update_xaxes(gridcolor='lightgrey', zerolinecolor='lightgrey', tickmode='array', tickvals= [-12, -6, 0, 6, 12, 18],
    ticktext = ["Dbb", "Gb", "C", "F#", "B#", "E##"], visible=True, )
fig.update_yaxes(gridcolor='lightgrey', zeroline=False, matches=None, showticklabels=True)
fig.write_image(os.path.join(OUTPUT_DIR, "tpc_line_per_dataset_compact.png"), scale=2)
fig.show()
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[19], line 1
    ----> 1 scatter_data = all_notes.groupby(['dataset_name', 'tpc']).duration_qb.sum().reset_index()
          2 fig = px.scatter(scatter_data, x='tpc', y='duration_qb', color='dataset_name', 
          3                  labels=dict(
          4                      duration_qb='duration',
       (...)
         10                  width=1000, height=500,
         11                 )
         12 fig.update_traces(mode='lines+markers')


    NameError: name 'all_notes' is not defined



```python
px.bar(scatter_data, x='tpc', y='duration_qb', color='dataset_name', 
                 labels=dict(
                     duration_qb='duration',
                     tpc='named pitch class',
                 ),
                 category_orders=dict(dataset=chronological_dataset_names),
                 color_discrete_map=dataset_name_colors,
                 width=1000, height=500,
                )
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[20], line 1
    ----> 1 px.bar(scatter_data, x='tpc', y='duration_qb', color='dataset_name', 
          2                  labels=dict(
          3                      duration_qb='duration',
          4                      tpc='named pitch class',
          5                  ),
          6                  category_orders=dict(dataset=chronological_dataset_names),
          7                  color_discrete_map=dataset_name_colors,
          8                  width=1000, height=500,
          9                 )


    NameError: name 'scatter_data' is not defined



```python
no_accidental = bar_data[bar_data.tpc.between(-1,5)].duration_qb.sum()
with_accidental = bar_data[~bar_data.tpc.between(-1,5)].duration_qb.sum()
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[21], line 1
    ----> 1 no_accidental = bar_data[bar_data.tpc.between(-1,5)].duration_qb.sum()
          2 with_accidental = bar_data[~bar_data.tpc.between(-1,5)].duration_qb.sum()


    NameError: name 'bar_data' is not defined



```python
entire = no_accidental + with_accidental
f"Fraction of note duration without accidental of the entire durations: {no_accidental} / {entire} = {no_accidental / entire}"
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[22], line 1
    ----> 1 entire = no_accidental + with_accidental
          2 f"Fraction of note duration without accidental of the entire durations: {no_accidental} / {entire} = {no_accidental / entire}"


    NameError: name 'no_accidental' is not defined

fig = make_subplots(rows=len(grouped_notes), cols=1, subplot_titles=list(grouped_notes.groups.keys()), shared_xaxes=True)
for i, (corp, notes) in enumerate(grouped_notes, 1):
    tpc_durations = notes.groupby('tpc').duration_qb.sum()
    tpc_durations /= tpc_durations.sum()
    fig.add_trace(go.Scatter(x=tpc_durations.index, y=tpc_durations, name=corp, mode='lines+markers'), row=i, col=1)

#fig.update_traces(side='positive', orientation='h', width=2, points=False)
fig.update_layout(**STD_LAYOUT, showlegend=False, height=800, width=300)
fig.update_xaxes(gridcolor='lightgrey', zerolinecolor='lightgrey', tickmode='array', tickvals= [-12, -6, 0, 6, 12, 18],
    ticktext = ["Dbb", "Gb", "C", "F#", "B#", "E##"],)
fig.update_yaxes(showgrid=False, zeroline=False)
fig.write_image(os.path.join(OUTPUT_DIR, "tpc_line_per_dataset.png"), scale=2)
fig.show()
### Notes and staves


```python
print("Distribution of notes over staves:")
all_notes.staff.value_counts()
```

    Distribution of notes over staves:



    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[23], line 2
          1 print("Distribution of notes over staves:")
    ----> 2 all_notes.staff.value_counts()


    NameError: name 'all_notes' is not defined



```python
print("Distribution of notes over staves for all pieces with more than two staves\n")
for group, df in all_notes.groupby(level=[0,1]):
    if (df.staff > 2).any():
        print(group)
        print(df.staff.value_counts().to_dict())
```

    Distribution of notes over staves for all pieces with more than two staves
    



    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[24], line 2
          1 print("Distribution of notes over staves for all pieces with more than two staves\n")
    ----> 2 for group, df in all_notes.groupby(level=[0,1]):
          3     if (df.staff > 2).any():
          4         print(group)


    NameError: name 'all_notes' is not defined



```python
all_notes[all_notes.staff > 2].groupby(level=[0,1]).staff.value_counts()
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[25], line 1
    ----> 1 all_notes[all_notes.staff > 2].groupby(level=[0,1]).staff.value_counts()


    NameError: name 'all_notes' is not defined
