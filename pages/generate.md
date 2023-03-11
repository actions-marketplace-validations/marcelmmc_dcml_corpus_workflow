# Corpus overview plots


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




<div>                            <div id="3ebe1d38-fc1d-4439-848f-de202986ea11" class="plotly-graph-div" style="height:760px; width:100%;"></div>            <script type="text/javascript">                require(["plotly"], function(Plotly) {                    window.PLOTLYENV=window.PLOTLYENV || {};                                    if (document.getElementById("3ebe1d38-fc1d-4439-848f-de202986ea11")) {                    Plotly.newPlot(                        "3ebe1d38-fc1d-4439-848f-de202986ea11",                        [{"customdata":[0,1,2,3,4,5,6,7,8,9,10],"hovertemplate":"%{y}[%{customdata}] = %{marker.color}<extra></extra>","marker":{"color":["rgb(229, 134, 6)","rgb(93, 105, 177)","rgb(82, 188, 163)","rgb(153, 201, 69)","rgb(204, 97, 176)","rgb(36, 121, 108)","rgb(218, 165, 27)","rgb(47, 138, 196)","rgb(118, 78, 159)","rgb(237, 100, 90)","rgb(165, 170, 153)"]},"orientation":"h","x":[1,1,1,1,1,1,1,1,1,1,1],"y":["Vivid","Vivid","Vivid","Vivid","Vivid","Vivid","Vivid","Vivid","Vivid","Vivid","Vivid"],"type":"bar"},{"customdata":[0,1,2,3,4,5,6,7,8,9,10],"hovertemplate":"%{y}[%{customdata}] = %{marker.color}<extra></extra>","marker":{"color":["rgb(136, 204, 238)","rgb(204, 102, 119)","rgb(221, 204, 119)","rgb(17, 119, 51)","rgb(51, 34, 136)","rgb(170, 68, 153)","rgb(68, 170, 153)","rgb(153, 153, 51)","rgb(136, 34, 85)","rgb(102, 17, 0)","rgb(136, 136, 136)"]},"orientation":"h","x":[1,1,1,1,1,1,1,1,1,1,1],"y":["Safe","Safe","Safe","Safe","Safe","Safe","Safe","Safe","Safe","Safe","Safe"],"type":"bar"},{"customdata":[0,1,2,3,4,5,6,7,8,9,10],"hovertemplate":"%{y}[%{customdata}] = %{marker.color}<extra></extra>","marker":{"color":["rgb(95, 70, 144)","rgb(29, 105, 150)","rgb(56, 166, 165)","rgb(15, 133, 84)","rgb(115, 175, 72)","rgb(237, 173, 8)","rgb(225, 124, 5)","rgb(204, 80, 62)","rgb(148, 52, 110)","rgb(111, 64, 112)","rgb(102, 102, 102)"]},"orientation":"h","x":[1,1,1,1,1,1,1,1,1,1,1],"y":["Prism","Prism","Prism","Prism","Prism","Prism","Prism","Prism","Prism","Prism","Prism"],"type":"bar"},{"customdata":[0,1,2,3,4,5,6,7,8,9,10],"hovertemplate":"%{y}[%{customdata}] = %{marker.color}<extra></extra>","marker":{"color":["rgb(102, 197, 204)","rgb(246, 207, 113)","rgb(248, 156, 116)","rgb(220, 176, 242)","rgb(135, 197, 95)","rgb(158, 185, 243)","rgb(254, 136, 177)","rgb(201, 219, 116)","rgb(139, 224, 164)","rgb(180, 151, 231)","rgb(179, 179, 179)"]},"orientation":"h","x":[1,1,1,1,1,1,1,1,1,1,1],"y":["Pastel","Pastel","Pastel","Pastel","Pastel","Pastel","Pastel","Pastel","Pastel","Pastel","Pastel"],"type":"bar"},{"customdata":[0,1,2,3,4,5,6,7,8,9,10],"hovertemplate":"%{y}[%{customdata}] = %{marker.color}<extra></extra>","marker":{"color":["rgb(127, 60, 141)","rgb(17, 165, 121)","rgb(57, 105, 172)","rgb(242, 183, 1)","rgb(231, 63, 116)","rgb(128, 186, 90)","rgb(230, 131, 16)","rgb(0, 134, 149)","rgb(207, 28, 144)","rgb(249, 123, 114)","rgb(165, 170, 153)"]},"orientation":"h","x":[1,1,1,1,1,1,1,1,1,1,1],"y":["Bold","Bold","Bold","Bold","Bold","Bold","Bold","Bold","Bold","Bold","Bold"],"type":"bar"},{"customdata":[0,1,2,3,4,5,6,7,8,9,10],"hovertemplate":"%{y}[%{customdata}] = %{marker.color}<extra></extra>","marker":{"color":["rgb(133, 92, 117)","rgb(217, 175, 107)","rgb(175, 100, 88)","rgb(115, 111, 76)","rgb(82, 106, 131)","rgb(98, 83, 119)","rgb(104, 133, 92)","rgb(156, 156, 94)","rgb(160, 97, 119)","rgb(140, 120, 93)","rgb(124, 124, 124)"]},"orientation":"h","x":[1,1,1,1,1,1,1,1,1,1,1],"y":["Antique","Antique","Antique","Antique","Antique","Antique","Antique","Antique","Antique","Antique","Antique"],"type":"bar"},{"customdata":[0,1,2,3,4,5,6,7,8,9,10,11],"hovertemplate":"%{y}[%{customdata}] = %{marker.color}<extra></extra>","marker":{"color":["rgb(141,211,199)","rgb(255,255,179)","rgb(190,186,218)","rgb(251,128,114)","rgb(128,177,211)","rgb(253,180,98)","rgb(179,222,105)","rgb(252,205,229)","rgb(217,217,217)","rgb(188,128,189)","rgb(204,235,197)","rgb(255,237,111)"]},"orientation":"h","x":[1,1,1,1,1,1,1,1,1,1,1,1],"y":["Set3","Set3","Set3","Set3","Set3","Set3","Set3","Set3","Set3","Set3","Set3","Set3"],"type":"bar"},{"customdata":[0,1,2,3,4,5,6,7],"hovertemplate":"%{y}[%{customdata}] = %{marker.color}<extra></extra>","marker":{"color":["rgb(179,226,205)","rgb(253,205,172)","rgb(203,213,232)","rgb(244,202,228)","rgb(230,245,201)","rgb(255,242,174)","rgb(241,226,204)","rgb(204,204,204)"]},"orientation":"h","x":[1,1,1,1,1,1,1,1],"y":["Pastel2","Pastel2","Pastel2","Pastel2","Pastel2","Pastel2","Pastel2","Pastel2"],"type":"bar"},{"customdata":[0,1,2,3,4,5,6,7],"hovertemplate":"%{y}[%{customdata}] = %{marker.color}<extra></extra>","marker":{"color":["rgb(102,194,165)","rgb(252,141,98)","rgb(141,160,203)","rgb(231,138,195)","rgb(166,216,84)","rgb(255,217,47)","rgb(229,196,148)","rgb(179,179,179)"]},"orientation":"h","x":[1,1,1,1,1,1,1,1],"y":["Set2","Set2","Set2","Set2","Set2","Set2","Set2","Set2"],"type":"bar"},{"customdata":[0,1,2,3,4,5,6,7],"hovertemplate":"%{y}[%{customdata}] = %{marker.color}<extra></extra>","marker":{"color":["rgb(27,158,119)","rgb(217,95,2)","rgb(117,112,179)","rgb(231,41,138)","rgb(102,166,30)","rgb(230,171,2)","rgb(166,118,29)","rgb(102,102,102)"]},"orientation":"h","x":[1,1,1,1,1,1,1,1],"y":["Dark2","Dark2","Dark2","Dark2","Dark2","Dark2","Dark2","Dark2"],"type":"bar"},{"customdata":[0,1,2,3,4,5,6,7,8],"hovertemplate":"%{y}[%{customdata}] = %{marker.color}<extra></extra>","marker":{"color":["rgb(251,180,174)","rgb(179,205,227)","rgb(204,235,197)","rgb(222,203,228)","rgb(254,217,166)","rgb(255,255,204)","rgb(229,216,189)","rgb(253,218,236)","rgb(242,242,242)"]},"orientation":"h","x":[1,1,1,1,1,1,1,1,1],"y":["Pastel1","Pastel1","Pastel1","Pastel1","Pastel1","Pastel1","Pastel1","Pastel1","Pastel1"],"type":"bar"},{"customdata":[0,1,2,3,4,5,6,7,8],"hovertemplate":"%{y}[%{customdata}] = %{marker.color}<extra></extra>","marker":{"color":["rgb(228,26,28)","rgb(55,126,184)","rgb(77,175,74)","rgb(152,78,163)","rgb(255,127,0)","rgb(255,255,51)","rgb(166,86,40)","rgb(247,129,191)","rgb(153,153,153)"]},"orientation":"h","x":[1,1,1,1,1,1,1,1,1],"y":["Set1","Set1","Set1","Set1","Set1","Set1","Set1","Set1","Set1"],"type":"bar"},{"customdata":[0,1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20,21,22,23],"hovertemplate":"%{y}[%{customdata}] = %{marker.color}<extra></extra>","marker":{"color":["#FD3216","#00FE35","#6A76FC","#FED4C4","#FE00CE","#0DF9FF","#F6F926","#FF9616","#479B55","#EEA6FB","#DC587D","#D626FF","#6E899C","#00B5F7","#B68E00","#C9FBE5","#FF0092","#22FFA7","#E3EE9E","#86CE00","#BC7196","#7E7DCD","#FC6955","#E48F72"]},"orientation":"h","x":[1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1],"y":["Light24","Light24","Light24","Light24","Light24","Light24","Light24","Light24","Light24","Light24","Light24","Light24","Light24","Light24","Light24","Light24","Light24","Light24","Light24","Light24","Light24","Light24","Light24","Light24"],"type":"bar"},{"customdata":[0,1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20,21,22,23],"hovertemplate":"%{y}[%{customdata}] = %{marker.color}<extra></extra>","marker":{"color":["#2E91E5","#E15F99","#1CA71C","#FB0D0D","#DA16FF","#222A2A","#B68100","#750D86","#EB663B","#511CFB","#00A08B","#FB00D1","#FC0080","#B2828D","#6C7C32","#778AAE","#862A16","#A777F1","#620042","#1616A7","#DA60CA","#6C4516","#0D2A63","#AF0038"]},"orientation":"h","x":[1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1],"y":["Dark24","Dark24","Dark24","Dark24","Dark24","Dark24","Dark24","Dark24","Dark24","Dark24","Dark24","Dark24","Dark24","Dark24","Dark24","Dark24","Dark24","Dark24","Dark24","Dark24","Dark24","Dark24","Dark24","Dark24"],"type":"bar"},{"customdata":[0,1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25],"hovertemplate":"%{y}[%{customdata}] = %{marker.color}<extra></extra>","marker":{"color":["#AA0DFE","#3283FE","#85660D","#782AB6","#565656","#1C8356","#16FF32","#F7E1A0","#E2E2E2","#1CBE4F","#C4451C","#DEA0FD","#FE00FA","#325A9B","#FEAF16","#F8A19F","#90AD1C","#F6222E","#1CFFCE","#2ED9FF","#B10DA1","#C075A6","#FC1CBF","#B00068","#FBE426","#FA0087"]},"orientation":"h","x":[1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1],"y":["Alphabet","Alphabet","Alphabet","Alphabet","Alphabet","Alphabet","Alphabet","Alphabet","Alphabet","Alphabet","Alphabet","Alphabet","Alphabet","Alphabet","Alphabet","Alphabet","Alphabet","Alphabet","Alphabet","Alphabet","Alphabet","Alphabet","Alphabet","Alphabet","Alphabet","Alphabet"],"type":"bar"},{"customdata":[0,1,2,3,4,5,6,7,8,9],"hovertemplate":"%{y}[%{customdata}] = %{marker.color}<extra></extra>","marker":{"color":["#4C78A8","#F58518","#E45756","#72B7B2","#54A24B","#EECA3B","#B279A2","#FF9DA6","#9D755D","#BAB0AC"]},"orientation":"h","x":[1,1,1,1,1,1,1,1,1,1],"y":["T10","T10","T10","T10","T10","T10","T10","T10","T10","T10"],"type":"bar"},{"customdata":[0,1,2,3,4,5,6,7,8,9],"hovertemplate":"%{y}[%{customdata}] = %{marker.color}<extra></extra>","marker":{"color":["#3366CC","#DC3912","#FF9900","#109618","#990099","#0099C6","#DD4477","#66AA00","#B82E2E","#316395"]},"orientation":"h","x":[1,1,1,1,1,1,1,1,1,1],"y":["G10","G10","G10","G10","G10","G10","G10","G10","G10","G10"],"type":"bar"},{"customdata":[0,1,2,3,4,5,6,7,8,9],"hovertemplate":"%{y}[%{customdata}] = %{marker.color}<extra></extra>","marker":{"color":["#1F77B4","#FF7F0E","#2CA02C","#D62728","#9467BD","#8C564B","#E377C2","#7F7F7F","#BCBD22","#17BECF"]},"orientation":"h","x":[1,1,1,1,1,1,1,1,1,1],"y":["D3","D3","D3","D3","D3","D3","D3","D3","D3","D3"],"type":"bar"},{"customdata":[0,1,2,3,4,5,6,7,8,9],"hovertemplate":"%{y}[%{customdata}] = %{marker.color}<extra></extra>","marker":{"color":["#636EFA","#EF553B","#00CC96","#AB63FA","#FFA15A","#19D3F3","#FF6692","#B6E880","#FF97FF","#FECB52"]},"orientation":"h","x":[1,1,1,1,1,1,1,1,1,1],"y":["Plotly","Plotly","Plotly","Plotly","Plotly","Plotly","Plotly","Plotly","Plotly","Plotly"],"type":"bar"}],                        {"bargap":0.5,"barmode":"stack","barnorm":"fraction","height":760,"margin":{"b":10},"showlegend":false,"template":{"data":{"barpolar":[{"marker":{"line":{"color":"#E5ECF6","width":0.5},"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"barpolar"}],"bar":[{"error_x":{"color":"#2a3f5f"},"error_y":{"color":"#2a3f5f"},"marker":{"line":{"color":"#E5ECF6","width":0.5},"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"bar"}],"carpet":[{"aaxis":{"endlinecolor":"#2a3f5f","gridcolor":"white","linecolor":"white","minorgridcolor":"white","startlinecolor":"#2a3f5f"},"baxis":{"endlinecolor":"#2a3f5f","gridcolor":"white","linecolor":"white","minorgridcolor":"white","startlinecolor":"#2a3f5f"},"type":"carpet"}],"choropleth":[{"colorbar":{"outlinewidth":0,"ticks":""},"type":"choropleth"}],"contourcarpet":[{"colorbar":{"outlinewidth":0,"ticks":""},"type":"contourcarpet"}],"contour":[{"colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"type":"contour"}],"heatmapgl":[{"colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"type":"heatmapgl"}],"heatmap":[{"colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"type":"heatmap"}],"histogram2dcontour":[{"colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"type":"histogram2dcontour"}],"histogram2d":[{"colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"type":"histogram2d"}],"histogram":[{"marker":{"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"histogram"}],"mesh3d":[{"colorbar":{"outlinewidth":0,"ticks":""},"type":"mesh3d"}],"parcoords":[{"line":{"colorbar":{"outlinewidth":0,"ticks":""}},"type":"parcoords"}],"pie":[{"automargin":true,"type":"pie"}],"scatter3d":[{"line":{"colorbar":{"outlinewidth":0,"ticks":""}},"marker":{"colorbar":{"outlinewidth":0,"ticks":""}},"type":"scatter3d"}],"scattercarpet":[{"marker":{"colorbar":{"outlinewidth":0,"ticks":""}},"type":"scattercarpet"}],"scattergeo":[{"marker":{"colorbar":{"outlinewidth":0,"ticks":""}},"type":"scattergeo"}],"scattergl":[{"marker":{"colorbar":{"outlinewidth":0,"ticks":""}},"type":"scattergl"}],"scattermapbox":[{"marker":{"colorbar":{"outlinewidth":0,"ticks":""}},"type":"scattermapbox"}],"scatterpolargl":[{"marker":{"colorbar":{"outlinewidth":0,"ticks":""}},"type":"scatterpolargl"}],"scatterpolar":[{"marker":{"colorbar":{"outlinewidth":0,"ticks":""}},"type":"scatterpolar"}],"scatter":[{"fillpattern":{"fillmode":"overlay","size":10,"solidity":0.2},"type":"scatter"}],"scatterternary":[{"marker":{"colorbar":{"outlinewidth":0,"ticks":""}},"type":"scatterternary"}],"surface":[{"colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"type":"surface"}],"table":[{"cells":{"fill":{"color":"#EBF0F8"},"line":{"color":"white"}},"header":{"fill":{"color":"#C8D4E3"},"line":{"color":"white"}},"type":"table"}]},"layout":{"annotationdefaults":{"arrowcolor":"#2a3f5f","arrowhead":0,"arrowwidth":1},"autotypenumbers":"strict","coloraxis":{"colorbar":{"outlinewidth":0,"ticks":""}},"colorscale":{"diverging":[[0,"#8e0152"],[0.1,"#c51b7d"],[0.2,"#de77ae"],[0.3,"#f1b6da"],[0.4,"#fde0ef"],[0.5,"#f7f7f7"],[0.6,"#e6f5d0"],[0.7,"#b8e186"],[0.8,"#7fbc41"],[0.9,"#4d9221"],[1,"#276419"]],"sequential":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"sequentialminus":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]},"colorway":["#636efa","#EF553B","#00cc96","#ab63fa","#FFA15A","#19d3f3","#FF6692","#B6E880","#FF97FF","#FECB52"],"font":{"color":"#2a3f5f"},"geo":{"bgcolor":"white","lakecolor":"white","landcolor":"#E5ECF6","showlakes":true,"showland":true,"subunitcolor":"white"},"hoverlabel":{"align":"left"},"hovermode":"closest","mapbox":{"style":"light"},"paper_bgcolor":"white","plot_bgcolor":"#E5ECF6","polar":{"angularaxis":{"gridcolor":"white","linecolor":"white","ticks":""},"bgcolor":"#E5ECF6","radialaxis":{"gridcolor":"white","linecolor":"white","ticks":""}},"scene":{"xaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","gridwidth":2,"linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white"},"yaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","gridwidth":2,"linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white"},"zaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","gridwidth":2,"linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white"}},"shapedefaults":{"line":{"color":"#2a3f5f"}},"ternary":{"aaxis":{"gridcolor":"white","linecolor":"white","ticks":""},"baxis":{"gridcolor":"white","linecolor":"white","ticks":""},"bgcolor":"#E5ECF6","caxis":{"gridcolor":"white","linecolor":"white","ticks":""}},"title":{"x":0.05},"xaxis":{"automargin":true,"gridcolor":"white","linecolor":"white","ticks":"","title":{"standoff":15},"zerolinecolor":"white","zerolinewidth":2},"yaxis":{"automargin":true,"gridcolor":"white","linecolor":"white","ticks":"","title":{"standoff":15},"zerolinecolor":"white","zerolinewidth":2}}},"title":{"text":"plotly.colors.qualitative"},"xaxis":{"range":[-0.02,1.02],"showgrid":false,"showticklabels":false}},                        {"responsive": true}                    ).then(function(){

var gd = document.getElementById('3ebe1d38-fc1d-4439-848f-de202986ea11');
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
dataset = dc.Dataset()
dataset.load(directory=corpus_path)
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



## Metadata


```python
all_metadata = dataset.data.metadata()
print(f"Concatenated 'metadata.tsv' files cover {len(all_metadata)} of the {len(dataset.pieces)} scores.")
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
print("VALUE COUNTS OF THE COLUMN 'annotators'")
all_metadata.annotators.value_counts()
```

    VALUE COUNTS OF THE COLUMN 'annotators'



    ---------------------------------------------------------------------------

    AttributeError                            Traceback (most recent call last)

    Cell In[10], line 2
          1 print("VALUE COUNTS OF THE COLUMN 'annotators'")
    ----> 2 all_metadata.annotators.value_counts()


    File /usr/local/lib/python3.10/site-packages/pandas/core/generic.py:5902, in NDFrame.__getattr__(self, name)
       5895 if (
       5896     name not in self._internal_names_set
       5897     and name not in self._metadata
       5898     and name not in self._accessors
       5899     and self._info_axis._can_hold_identifiers_and_holds_name(name)
       5900 ):
       5901     return self[name]
    -> 5902 return object.__getattribute__(self, name)


    AttributeError: 'DataFrame' object has no attribute 'annotators'



```python
print(f"Composition dates range from {all_metadata.composed_start.min()} {all_metadata.composed_start.idxmin()} "
      f"to {all_metadata.composed_end.max()} {all_metadata.composed_end.idxmax()}.")
```

    Composition dates range from 1985 ('ligeti_etudes', 'vol1no2') to 1985 ('ligeti_etudes', 'vol1no2').



```python
annotated = dc.IsAnnotatedFilter().process_data(dataset)
print(f"Before: {len(dataset.indices[()])} IDs, after filtering: {len(annotated.indices[()])}")
```


    ---------------------------------------------------------------------------

    KeyError                                  Traceback (most recent call last)

    Cell In[12], line 2
          1 annotated = dc.IsAnnotatedFilter().process_data(dataset)
    ----> 2 print(f"Before: {len(dataset.indices[()])} IDs, after filtering: {len(annotated.indices[()])}")


    KeyError: ()


**Choose here if you want to see stats for all or only for annotated scores.**


```python
#selected = dataset
selected = annotated
```

## Measures


```python
all_measures = selected.get_facet('measures')
print(f"{len(all_measures.index)} measures over {len(all_measures.groupby(level=[0,1]))} files.")
all_measures.head()
```


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    Cell In[14], line 1
    ----> 1 all_measures = selected.get_facet('measures')
          2 print(f"{len(all_measures.index)} measures over {len(all_measures.groupby(level=[0,1]))} files.")
          3 all_measures.head()


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
print("Distribution of time signatures per XML measure (MC):")
all_measures.timesig.value_counts(dropna=False)
```

    Distribution of time signatures per XML measure (MC):



    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[15], line 2
          1 print("Distribution of time signatures per XML measure (MC):")
    ----> 2 all_measures.timesig.value_counts(dropna=False)


    NameError: name 'all_measures' is not defined


## Notes


```python
all_notes = selected.get_facet('notes')
print(f"{len(all_notes.index)} notes over {len(all_notes.groupby(level=[0,1]))} files.")
all_notes.head()
```


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    Cell In[16], line 1
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


### Notes and staves


```python
print("Distribution of notes over staves:")
all_notes.staff.value_counts()
```

    Distribution of notes over staves:



    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[17], line 2
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

    Cell In[18], line 2
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

    Cell In[19], line 1
    ----> 1 all_notes[all_notes.staff > 2].groupby(level=[0,1]).staff.value_counts()


    NameError: name 'all_notes' is not defined


## Harmony labels

All symbols, independent of the local key (the mode of which changes their semantics).


```python
all_annotations = annotated.get_facet('expanded')
all_annotations.head()
```


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    Cell In[20], line 1
    ----> 1 all_annotations = annotated.get_facet('expanded')
          2 all_annotations.head()


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
no_chord = all_annotations.root.isna()
print(f"Concatenated annotation tables contains {all_annotations.shape[0]} rows. {no_chord.sum()} of them are not chords. Their values are:")
all_annotations.label[no_chord].value_counts(dropna=False).to_dict()
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[21], line 1
    ----> 1 no_chord = all_annotations.root.isna()
          2 print(f"Concatenated annotation tables contains {all_annotations.shape[0]} rows. {no_chord.sum()} of them are not chords. Their values are:")
          3 all_annotations.label[no_chord].value_counts(dropna=False).to_dict()


    NameError: name 'all_annotations' is not defined



```python
all_chords = all_annotations[~no_chord].copy()
print(f"Corpus contains {all_chords.shape[0]} tokens and {len(all_chords.chord.unique())} types over {len(all_chords.groupby(level=[0,1]))} documents.")
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[22], line 1
    ----> 1 all_chords = all_annotations[~no_chord].copy()
          2 print(f"Corpus contains {all_chords.shape[0]} tokens and {len(all_chords.chord.unique())} types over {len(all_chords.groupby(level=[0,1]))} documents.")


    NameError: name 'all_annotations' is not defined



```python
#from ms3 import write_tsv
#write_tsv(all_annotations[all_annotations.pedalend.notna()], './issues/pedalpoints.tsv', pre_process=False)
```

## Corpus summary


```python
summary = all_metadata
if selected == annotated:
    summary = summary[summary.label_count > 0].copy()
summary.length_qb = all_measures.groupby(level=[0,1]).act_dur.sum() * 4.0
summary = pd.concat([summary,
                     all_notes.groupby(level=[0,1]).size().rename('notes'),
                    ], axis=1)
summary.groupby(level=0).describe().dropna(axis=1, how='all')
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[24], line 4
          2 if selected == annotated:
          3     summary = summary[summary.label_count > 0].copy()
    ----> 4 summary.length_qb = all_measures.groupby(level=[0,1]).act_dur.sum() * 4.0
          5 summary = pd.concat([summary,
          6                      all_notes.groupby(level=[0,1]).size().rename('notes'),
          7                     ], axis=1)
          8 summary.groupby(level=0).describe().dropna(axis=1, how='all')


    NameError: name 'all_measures' is not defined



```python
mean_composition_years = summary.groupby(level=0).composed_end.mean().astype(int).sort_values()
chronological_order = mean_composition_years.index.to_list()
corpus_colors = dict(zip(chronological_order, corpus_color_scale))
bar_data = pd.concat([mean_composition_years.rename('year'), 
                      summary.groupby(level='corpus').size().rename('pieces')],
                     axis=1
                    ).reset_index()
fig = px.bar(bar_data, x='year', y='pieces', color='corpus',
             color_discrete_map=corpus_colors,
            height=350, width=800,
            )
fig.update_traces(width=5)
fig.update_layout(**STD_LAYOUT)
fig.update_yaxes(gridcolor='lightgrey')
fig.write_image(os.path.join(OUTPUT_DIR, "corpus_sizes.png"), scale=2)
fig.update_traces(width=5)
```


<div>                            <div id="6c9a7ee3-9eb0-4c78-8f0e-be957c1541ff" class="plotly-graph-div" style="height:350px; width:800px;"></div>            <script type="text/javascript">                require(["plotly"], function(Plotly) {                    window.PLOTLYENV=window.PLOTLYENV || {};                                    if (document.getElementById("6c9a7ee3-9eb0-4c78-8f0e-be957c1541ff")) {                    Plotly.newPlot(                        "6c9a7ee3-9eb0-4c78-8f0e-be957c1541ff",                        [],                        {"template":{"data":{"histogram2dcontour":[{"type":"histogram2dcontour","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"choropleth":[{"type":"choropleth","colorbar":{"outlinewidth":0,"ticks":""}}],"histogram2d":[{"type":"histogram2d","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"heatmap":[{"type":"heatmap","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"heatmapgl":[{"type":"heatmapgl","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"contourcarpet":[{"type":"contourcarpet","colorbar":{"outlinewidth":0,"ticks":""}}],"contour":[{"type":"contour","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"surface":[{"type":"surface","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"mesh3d":[{"type":"mesh3d","colorbar":{"outlinewidth":0,"ticks":""}}],"scatter":[{"fillpattern":{"fillmode":"overlay","size":10,"solidity":0.2},"type":"scatter"}],"parcoords":[{"type":"parcoords","line":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatterpolargl":[{"type":"scatterpolargl","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"bar":[{"error_x":{"color":"#2a3f5f"},"error_y":{"color":"#2a3f5f"},"marker":{"line":{"color":"#E5ECF6","width":0.5},"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"bar"}],"scattergeo":[{"type":"scattergeo","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatterpolar":[{"type":"scatterpolar","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"histogram":[{"marker":{"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"histogram"}],"scattergl":[{"type":"scattergl","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatter3d":[{"type":"scatter3d","line":{"colorbar":{"outlinewidth":0,"ticks":""}},"marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scattermapbox":[{"type":"scattermapbox","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatterternary":[{"type":"scatterternary","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scattercarpet":[{"type":"scattercarpet","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"carpet":[{"aaxis":{"endlinecolor":"#2a3f5f","gridcolor":"white","linecolor":"white","minorgridcolor":"white","startlinecolor":"#2a3f5f"},"baxis":{"endlinecolor":"#2a3f5f","gridcolor":"white","linecolor":"white","minorgridcolor":"white","startlinecolor":"#2a3f5f"},"type":"carpet"}],"table":[{"cells":{"fill":{"color":"#EBF0F8"},"line":{"color":"white"}},"header":{"fill":{"color":"#C8D4E3"},"line":{"color":"white"}},"type":"table"}],"barpolar":[{"marker":{"line":{"color":"#E5ECF6","width":0.5},"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"barpolar"}],"pie":[{"automargin":true,"type":"pie"}]},"layout":{"autotypenumbers":"strict","colorway":["#636efa","#EF553B","#00cc96","#ab63fa","#FFA15A","#19d3f3","#FF6692","#B6E880","#FF97FF","#FECB52"],"font":{"color":"#2a3f5f"},"hovermode":"closest","hoverlabel":{"align":"left"},"paper_bgcolor":"white","plot_bgcolor":"#E5ECF6","polar":{"bgcolor":"#E5ECF6","angularaxis":{"gridcolor":"white","linecolor":"white","ticks":""},"radialaxis":{"gridcolor":"white","linecolor":"white","ticks":""}},"ternary":{"bgcolor":"#E5ECF6","aaxis":{"gridcolor":"white","linecolor":"white","ticks":""},"baxis":{"gridcolor":"white","linecolor":"white","ticks":""},"caxis":{"gridcolor":"white","linecolor":"white","ticks":""}},"coloraxis":{"colorbar":{"outlinewidth":0,"ticks":""}},"colorscale":{"sequential":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"sequentialminus":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"diverging":[[0,"#8e0152"],[0.1,"#c51b7d"],[0.2,"#de77ae"],[0.3,"#f1b6da"],[0.4,"#fde0ef"],[0.5,"#f7f7f7"],[0.6,"#e6f5d0"],[0.7,"#b8e186"],[0.8,"#7fbc41"],[0.9,"#4d9221"],[1,"#276419"]]},"xaxis":{"gridcolor":"white","linecolor":"white","ticks":"","title":{"standoff":15},"zerolinecolor":"white","automargin":true,"zerolinewidth":2},"yaxis":{"gridcolor":"white","linecolor":"white","ticks":"","title":{"standoff":15},"zerolinecolor":"white","automargin":true,"zerolinewidth":2},"scene":{"xaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white","gridwidth":2},"yaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white","gridwidth":2},"zaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white","gridwidth":2}},"shapedefaults":{"line":{"color":"#2a3f5f"}},"annotationdefaults":{"arrowcolor":"#2a3f5f","arrowhead":0,"arrowwidth":1},"geo":{"bgcolor":"white","landcolor":"#E5ECF6","subunitcolor":"white","showland":true,"showlakes":true,"lakecolor":"white"},"title":{"x":0.05},"mapbox":{"style":"light"}}},"xaxis":{"anchor":"y","domain":[0.0,1.0],"title":{"text":"year"}},"yaxis":{"anchor":"x","domain":[0.0,1.0],"title":{"text":"pieces"},"gridcolor":"lightgrey"},"legend":{"tracegroupgap":0},"margin":{"t":40,"l":40,"r":0,"b":0,"pad":0},"barmode":"relative","height":350,"width":800,"font":{"size":15},"paper_bgcolor":"#FFFFFF","plot_bgcolor":"#FFFFFF"},                        {"responsive": true}                    ).then(function(){

var gd = document.getElementById('6c9a7ee3-9eb0-4c78-8f0e-be957c1541ff');
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
corpus_names = dict(
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
chronological_corpus_names = [corpus_names[corp] for corp in chronological_order]
corpus_name_colors = {corpus_names[corp]: color for corp, color in corpus_colors.items()}
all_annotations['corpus_name'] = all_annotations.index.get_level_values(0).map(corpus_names)
all_chords['corpus_name'] = all_chords.index.get_level_values(0).map(corpus_names)
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[26], line 14
         12 chronological_corpus_names = [corpus_names[corp] for corp in chronological_order]
         13 corpus_name_colors = {corpus_names[corp]: color for corp, color in corpus_colors.items()}
    ---> 14 all_annotations['corpus_name'] = all_annotations.index.get_level_values(0).map(corpus_names)
         15 all_chords['corpus_name'] = all_chords.index.get_level_values(0).map(corpus_names)


    NameError: name 'all_annotations' is not defined



```python
bar_data = summary.reset_index().groupby(['composed_end', 'corpus']).size().rename('counts').reset_index()
px.bar(bar_data, x='composed_end', y='counts', color='corpus', color_discrete_map=corpus_colors)
```


<div>                            <div id="f8b988bf-0b15-43e1-825d-e622422d8be4" class="plotly-graph-div" style="height:525px; width:100%;"></div>            <script type="text/javascript">                require(["plotly"], function(Plotly) {                    window.PLOTLYENV=window.PLOTLYENV || {};                                    if (document.getElementById("f8b988bf-0b15-43e1-825d-e622422d8be4")) {                    Plotly.newPlot(                        "f8b988bf-0b15-43e1-825d-e622422d8be4",                        [],                        {"template":{"data":{"histogram2dcontour":[{"type":"histogram2dcontour","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"choropleth":[{"type":"choropleth","colorbar":{"outlinewidth":0,"ticks":""}}],"histogram2d":[{"type":"histogram2d","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"heatmap":[{"type":"heatmap","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"heatmapgl":[{"type":"heatmapgl","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"contourcarpet":[{"type":"contourcarpet","colorbar":{"outlinewidth":0,"ticks":""}}],"contour":[{"type":"contour","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"surface":[{"type":"surface","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"mesh3d":[{"type":"mesh3d","colorbar":{"outlinewidth":0,"ticks":""}}],"scatter":[{"fillpattern":{"fillmode":"overlay","size":10,"solidity":0.2},"type":"scatter"}],"parcoords":[{"type":"parcoords","line":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatterpolargl":[{"type":"scatterpolargl","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"bar":[{"error_x":{"color":"#2a3f5f"},"error_y":{"color":"#2a3f5f"},"marker":{"line":{"color":"#E5ECF6","width":0.5},"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"bar"}],"scattergeo":[{"type":"scattergeo","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatterpolar":[{"type":"scatterpolar","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"histogram":[{"marker":{"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"histogram"}],"scattergl":[{"type":"scattergl","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatter3d":[{"type":"scatter3d","line":{"colorbar":{"outlinewidth":0,"ticks":""}},"marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scattermapbox":[{"type":"scattermapbox","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatterternary":[{"type":"scatterternary","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scattercarpet":[{"type":"scattercarpet","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"carpet":[{"aaxis":{"endlinecolor":"#2a3f5f","gridcolor":"white","linecolor":"white","minorgridcolor":"white","startlinecolor":"#2a3f5f"},"baxis":{"endlinecolor":"#2a3f5f","gridcolor":"white","linecolor":"white","minorgridcolor":"white","startlinecolor":"#2a3f5f"},"type":"carpet"}],"table":[{"cells":{"fill":{"color":"#EBF0F8"},"line":{"color":"white"}},"header":{"fill":{"color":"#C8D4E3"},"line":{"color":"white"}},"type":"table"}],"barpolar":[{"marker":{"line":{"color":"#E5ECF6","width":0.5},"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"barpolar"}],"pie":[{"automargin":true,"type":"pie"}]},"layout":{"autotypenumbers":"strict","colorway":["#636efa","#EF553B","#00cc96","#ab63fa","#FFA15A","#19d3f3","#FF6692","#B6E880","#FF97FF","#FECB52"],"font":{"color":"#2a3f5f"},"hovermode":"closest","hoverlabel":{"align":"left"},"paper_bgcolor":"white","plot_bgcolor":"#E5ECF6","polar":{"bgcolor":"#E5ECF6","angularaxis":{"gridcolor":"white","linecolor":"white","ticks":""},"radialaxis":{"gridcolor":"white","linecolor":"white","ticks":""}},"ternary":{"bgcolor":"#E5ECF6","aaxis":{"gridcolor":"white","linecolor":"white","ticks":""},"baxis":{"gridcolor":"white","linecolor":"white","ticks":""},"caxis":{"gridcolor":"white","linecolor":"white","ticks":""}},"coloraxis":{"colorbar":{"outlinewidth":0,"ticks":""}},"colorscale":{"sequential":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"sequentialminus":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"diverging":[[0,"#8e0152"],[0.1,"#c51b7d"],[0.2,"#de77ae"],[0.3,"#f1b6da"],[0.4,"#fde0ef"],[0.5,"#f7f7f7"],[0.6,"#e6f5d0"],[0.7,"#b8e186"],[0.8,"#7fbc41"],[0.9,"#4d9221"],[1,"#276419"]]},"xaxis":{"gridcolor":"white","linecolor":"white","ticks":"","title":{"standoff":15},"zerolinecolor":"white","automargin":true,"zerolinewidth":2},"yaxis":{"gridcolor":"white","linecolor":"white","ticks":"","title":{"standoff":15},"zerolinecolor":"white","automargin":true,"zerolinewidth":2},"scene":{"xaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white","gridwidth":2},"yaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white","gridwidth":2},"zaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white","gridwidth":2}},"shapedefaults":{"line":{"color":"#2a3f5f"}},"annotationdefaults":{"arrowcolor":"#2a3f5f","arrowhead":0,"arrowwidth":1},"geo":{"bgcolor":"white","landcolor":"#E5ECF6","subunitcolor":"white","showland":true,"showlakes":true,"lakecolor":"white"},"title":{"x":0.05},"mapbox":{"style":"light"}}},"xaxis":{"anchor":"y","domain":[0.0,1.0],"title":{"text":"composed_end"}},"yaxis":{"anchor":"x","domain":[0.0,1.0],"title":{"text":"counts"}},"legend":{"tracegroupgap":0},"margin":{"t":60},"barmode":"relative"},                        {"responsive": true}                    ).then(function(){

var gd = document.getElementById('f8b988bf-0b15-43e1-825d-e622422d8be4');
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
hist_data = summary.reset_index()
hist_data.corpus = hist_data.corpus.map(corpus_names)
hist_data.head()
```




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
      <th>corpus</th>
      <th>fname</th>
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
  </thead>
  <tbody>
  </tbody>
</table>
</div>




```python
fig = px.histogram(hist_data, x='composed_end', color='corpus',
                   labels=dict(composed_end='decade',
                               count='pieces',
                              ),
                   color_discrete_map=corpus_name_colors,
                   width=1000, height=400,
                  )
fig.update_traces(xbins=dict(
    size=10
))
fig.update_layout(**STD_LAYOUT)
fig.update_yaxes(gridcolor='lightgrey')
fig.write_image(os.path.join(OUTPUT_DIR, "corpus_size_histogram.png"), scale=2)
fig.show()
```


<div>                            <div id="223c8393-9b7c-489f-8daf-36e5bfef3836" class="plotly-graph-div" style="height:400px; width:1000px;"></div>            <script type="text/javascript">                require(["plotly"], function(Plotly) {                    window.PLOTLYENV=window.PLOTLYENV || {};                                    if (document.getElementById("223c8393-9b7c-489f-8daf-36e5bfef3836")) {                    Plotly.newPlot(                        "223c8393-9b7c-489f-8daf-36e5bfef3836",                        [],                        {"template":{"data":{"histogram2dcontour":[{"type":"histogram2dcontour","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"choropleth":[{"type":"choropleth","colorbar":{"outlinewidth":0,"ticks":""}}],"histogram2d":[{"type":"histogram2d","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"heatmap":[{"type":"heatmap","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"heatmapgl":[{"type":"heatmapgl","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"contourcarpet":[{"type":"contourcarpet","colorbar":{"outlinewidth":0,"ticks":""}}],"contour":[{"type":"contour","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"surface":[{"type":"surface","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"mesh3d":[{"type":"mesh3d","colorbar":{"outlinewidth":0,"ticks":""}}],"scatter":[{"fillpattern":{"fillmode":"overlay","size":10,"solidity":0.2},"type":"scatter"}],"parcoords":[{"type":"parcoords","line":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatterpolargl":[{"type":"scatterpolargl","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"bar":[{"error_x":{"color":"#2a3f5f"},"error_y":{"color":"#2a3f5f"},"marker":{"line":{"color":"#E5ECF6","width":0.5},"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"bar"}],"scattergeo":[{"type":"scattergeo","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatterpolar":[{"type":"scatterpolar","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"histogram":[{"marker":{"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"histogram"}],"scattergl":[{"type":"scattergl","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatter3d":[{"type":"scatter3d","line":{"colorbar":{"outlinewidth":0,"ticks":""}},"marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scattermapbox":[{"type":"scattermapbox","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatterternary":[{"type":"scatterternary","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scattercarpet":[{"type":"scattercarpet","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"carpet":[{"aaxis":{"endlinecolor":"#2a3f5f","gridcolor":"white","linecolor":"white","minorgridcolor":"white","startlinecolor":"#2a3f5f"},"baxis":{"endlinecolor":"#2a3f5f","gridcolor":"white","linecolor":"white","minorgridcolor":"white","startlinecolor":"#2a3f5f"},"type":"carpet"}],"table":[{"cells":{"fill":{"color":"#EBF0F8"},"line":{"color":"white"}},"header":{"fill":{"color":"#C8D4E3"},"line":{"color":"white"}},"type":"table"}],"barpolar":[{"marker":{"line":{"color":"#E5ECF6","width":0.5},"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"barpolar"}],"pie":[{"automargin":true,"type":"pie"}]},"layout":{"autotypenumbers":"strict","colorway":["#636efa","#EF553B","#00cc96","#ab63fa","#FFA15A","#19d3f3","#FF6692","#B6E880","#FF97FF","#FECB52"],"font":{"color":"#2a3f5f"},"hovermode":"closest","hoverlabel":{"align":"left"},"paper_bgcolor":"white","plot_bgcolor":"#E5ECF6","polar":{"bgcolor":"#E5ECF6","angularaxis":{"gridcolor":"white","linecolor":"white","ticks":""},"radialaxis":{"gridcolor":"white","linecolor":"white","ticks":""}},"ternary":{"bgcolor":"#E5ECF6","aaxis":{"gridcolor":"white","linecolor":"white","ticks":""},"baxis":{"gridcolor":"white","linecolor":"white","ticks":""},"caxis":{"gridcolor":"white","linecolor":"white","ticks":""}},"coloraxis":{"colorbar":{"outlinewidth":0,"ticks":""}},"colorscale":{"sequential":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"sequentialminus":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"diverging":[[0,"#8e0152"],[0.1,"#c51b7d"],[0.2,"#de77ae"],[0.3,"#f1b6da"],[0.4,"#fde0ef"],[0.5,"#f7f7f7"],[0.6,"#e6f5d0"],[0.7,"#b8e186"],[0.8,"#7fbc41"],[0.9,"#4d9221"],[1,"#276419"]]},"xaxis":{"gridcolor":"white","linecolor":"white","ticks":"","title":{"standoff":15},"zerolinecolor":"white","automargin":true,"zerolinewidth":2},"yaxis":{"gridcolor":"white","linecolor":"white","ticks":"","title":{"standoff":15},"zerolinecolor":"white","automargin":true,"zerolinewidth":2},"scene":{"xaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white","gridwidth":2},"yaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white","gridwidth":2},"zaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white","gridwidth":2}},"shapedefaults":{"line":{"color":"#2a3f5f"}},"annotationdefaults":{"arrowcolor":"#2a3f5f","arrowhead":0,"arrowwidth":1},"geo":{"bgcolor":"white","landcolor":"#E5ECF6","subunitcolor":"white","showland":true,"showlakes":true,"lakecolor":"white"},"title":{"x":0.05},"mapbox":{"style":"light"}}},"xaxis":{"anchor":"y","domain":[0.0,1.0],"title":{"text":"decade"}},"yaxis":{"anchor":"x","domain":[0.0,1.0],"title":{"text":"count"},"gridcolor":"lightgrey"},"legend":{"tracegroupgap":0},"margin":{"t":40,"l":40,"r":0,"b":0,"pad":0},"barmode":"relative","height":400,"width":1000,"font":{"size":15},"paper_bgcolor":"#FFFFFF","plot_bgcolor":"#FFFFFF"},                        {"responsive": true}                    ).then(function(){

var gd = document.getElementById('223c8393-9b7c-489f-8daf-36e5bfef3836');
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
summary.columns
```




    Index(['TimeSig', 'KeySig', 'last_mc', 'last_mn', 'length_qb',
           'last_mc_unfolded', 'last_mn_unfolded', 'length_qb_unfolded',
           'all_notes_qb', 'n_onsets', 'n_onset_positions', 'guitar_chord_count',
           'form_label_count', 'label_count', 'composed_start', 'composed_end',
           'composed_source', 'composer', 'workTitle', 'movementNumber',
           'movementTitle', 'workNumber', 'poet', 'lyricist', 'arranger',
           'copyright', 'creationDate', 'mscVersion', 'platform', 'source',
           'translator', 'title_text', 'subtitle_text', 'composer_text',
           'musescore', 'ms3_version', 'subdirectory', 'rel_path', 'has_drumset',
           'ambitus', 'wdt:P86', 'wikidata', 'musicbrainz', 'originalFormat',
           'staff_1_ambitus', 'staff_1_instrument', 'staff_2_ambitus',
           'staff_2_instrument', 'staff_3_ambitus', 'staff_3_instrument'],
          dtype='object')




```python
corpus_metadata = summary.groupby(level=0)
n_pieces = corpus_metadata.size().rename('pieces')
absolute_numbers = dict(
    measures = corpus_metadata.last_mn.sum(),
    length = corpus_metadata.length_qb.sum(),
    notes = corpus_metadata.notes.sum(),
    labels = corpus_metadata.label_count.sum(),
)
absolute = pd.DataFrame.from_dict(absolute_numbers)
relative = absolute.div(n_pieces, axis=0)
complete_summary = pd.concat([pd.concat([n_pieces, absolute], axis=1), relative, absolute.iloc[:,2:].div(absolute.measures, axis=0)], axis=1, keys=['absolute', 'per piece', 'per measure'])
complete_summary = complete_summary.apply(pd.to_numeric).round(2)
complete_summary.index = complete_summary.index.map(corpus_names)
complete_summary.to_csv('romantic_summary.tsv', sep='\t')
complete_summary
```


    ---------------------------------------------------------------------------

    AttributeError                            Traceback (most recent call last)

    Cell In[31], line 6
          1 corpus_metadata = summary.groupby(level=0)
          2 n_pieces = corpus_metadata.size().rename('pieces')
          3 absolute_numbers = dict(
          4     measures = corpus_metadata.last_mn.sum(),
          5     length = corpus_metadata.length_qb.sum(),
    ----> 6     notes = corpus_metadata.notes.sum(),
          7     labels = corpus_metadata.label_count.sum(),
          8 )
          9 absolute = pd.DataFrame.from_dict(absolute_numbers)
         10 relative = absolute.div(n_pieces, axis=0)


    File /usr/local/lib/python3.10/site-packages/pandas/core/groupby/groupby.py:987, in GroupBy.__getattr__(self, attr)
        984 if attr in self.obj:
        985     return self[attr]
    --> 987 raise AttributeError(
        988     f"'{type(self).__name__}' object has no attribute '{attr}'"
        989 )


    AttributeError: 'DataFrameGroupBy' object has no attribute 'notes'



```python
sum_row = pd.DataFrame(complete_summary.sum(), columns=['sum']).T
sum_row.iloc[:,5:] = ''
summary_with_sum = pd.concat([complete_summary, sum_row])
summary_with_sum.loc[:, [('absolute', 'notes'), ('absolute', 'labels')]] = summary_with_sum[[('absolute', 'notes'), ('absolute', 'labels')]].astype(int)
summary_with_sum
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[32], line 1
    ----> 1 sum_row = pd.DataFrame(complete_summary.sum(), columns=['sum']).T
          2 sum_row.iloc[:,5:] = ''
          3 summary_with_sum = pd.concat([complete_summary, sum_row])


    NameError: name 'complete_summary' is not defined



```python
summary[summary.ambitus.isna()]
```




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
      <th>fname</th>
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
  </tbody>
</table>
</div>




```python
summary.ambitus.str.extract(r"^(\d+)-(\d+)")
```




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
      <th>0</th>
      <th>1</th>
    </tr>
  </thead>
  <tbody>
  </tbody>
</table>
</div>




```python
ambitus = summary.ambitus.str.extract(r"^(\d+)-(\d+)").astype(int)
ambitus.columns = ['low', 'high']
ambitus['range'] = ambitus.high - ambitus.low
ambitus.head()
```




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
      <th>low</th>
      <th>high</th>
      <th>range</th>
    </tr>
  </thead>
  <tbody>
  </tbody>
</table>
</div>




```python
ambitus.groupby(level=0).high.max()
```




    Series([], Name: high, dtype: int64)




```python
ambitus.groupby(level=0).low.min()
```




    Series([], Name: low, dtype: int64)




```python
ambitus.groupby(level=0).range.max()
```




    Series([], Name: range, dtype: int64)




```python
ambitus.groupby(level=0).high.max() - ambitus.groupby(level=0).low.min()
```




    Series([], dtype: int64)



# Phrases


```python
phrase_segmented = dc.PhraseSlicer().process_data(selected)
phrases = phrase_segmented.get_slice_info()
print(f"Overall number of phrases is {len(phrases.index)}")
phrases.head(20)
```


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    Cell In[40], line 1
    ----> 1 phrase_segmented = dc.PhraseSlicer().process_data(selected)
          2 phrases = phrase_segmented.get_slice_info()
          3 print(f"Overall number of phrases is {len(phrases.index)}")


    File /dimcat/src/dimcat/slicer.py:429, in SpecialFacetSlicer.process_data(self, data)
        428 def process_data(self, data: Data) -> Data:
    --> 429     data = super().process_data(data)
        430     sliced_data = self.perform_facet_slicing(data)
        431     return sliced_data


    File /dimcat/src/dimcat/slicer.py:121, in LazyFacetSlicer.process_data(self, data)
        117 slice_infos = (
        118     {}
        119 )  # for each slice, the relevant info about it, e.g. for later grouping
        120 facet_in_question = self.required_facets[0]
    --> 121 for group, dfs in data.iter_facet(facet_in_question):
        122     new_index_group = []
        123     for index, facet_df in dfs.items():


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
phrase_segments = phrase_segmented.get_facet('expanded')
phrase_segments.to_csv('romantic_phrase_segments.tsv.zip', sep='\t')
phrase_segments
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[41], line 1
    ----> 1 phrase_segments = phrase_segmented.get_facet('expanded')
          2 phrase_segments.to_csv('romantic_phrase_segments.tsv.zip', sep='\t')
          3 phrase_segments


    NameError: name 'phrase_segmented' is not defined



```python
phrases[phrases.duration_qb > 50]
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[42], line 1
    ----> 1 phrases[phrases.duration_qb > 50]


    NameError: name 'phrases' is not defined



```python
phrase2timesigs = phrase_segments.groupby(level=[0,1,2]).timesig.unique()
n_timesignatures_per_phrase = phrase2timesigs.map(len)
uniform_timesigs = phrase2timesigs[n_timesignatures_per_phrase == 1].map(lambda l: l[0])
more_than_one = n_timesignatures_per_phrase > 1
print(f"Filtered out the {more_than_one.sum()} phrases incorporating more than one time signature.")
n_timesigs = n_timesignatures_per_phrase.value_counts()
display(n_timesigs.reset_index().rename(columns=dict(index='#time signatures', timesig='#phrases')))
uniform_timesig_phrases = phrases.loc[uniform_timesigs.index]
timesig_in_quarterbeats = uniform_timesigs.map(Fraction) * 4
exact_measure_lengths = uniform_timesig_phrases.duration_qb / timesig_in_quarterbeats
uniform_timesigs = pd.concat([exact_measure_lengths.rename('duration_measures'), uniform_timesig_phrases], axis=1)
fig = px.histogram(uniform_timesigs, x='duration_measures', log_y=True,
                   labels=dict(duration_measures='phrase length bin in number of measures'),
                   color_discrete_sequence=corpus_color_scale,
                   height=400,
                   width = 1000,
                  )
fig.update_traces(xbins=dict( # bins used for histogram
        #start=0.0,
        #end=100.0,
        size=1
    ))
fig.update_layout(**STD_LAYOUT)
fig.update_xaxes(dtick=4, gridcolor='lightgrey')
fig.update_yaxes(gridcolor='lightgrey')
fig.write_image(os.path.join(OUTPUT_DIR, "phrase_lengths.png"), scale=2)
fig.show()
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[43], line 1
    ----> 1 phrase2timesigs = phrase_segments.groupby(level=[0,1,2]).timesig.unique()
          2 n_timesignatures_per_phrase = phrase2timesigs.map(len)
          3 uniform_timesigs = phrase2timesigs[n_timesignatures_per_phrase == 1].map(lambda l: l[0])


    NameError: name 'phrase_segments' is not defined



```python
uniform_timesigs[uniform_timesigs.duration_measures > 80]
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[44], line 1
    ----> 1 uniform_timesigs[uniform_timesigs.duration_measures > 80]


    NameError: name 'uniform_timesigs' is not defined


# Keys


```python
from ms3 import roman_numeral2fifths, transform, resolve_all_relative_numerals, replace_boolean_mode_by_strings
keys_segmented = dc.LocalKeySlicer().process_data(selected)
keys = keys_segmented.get_slice_info()
keys.to_csv('romantic_keys.tsv.zip', sep='\t')
print(f"Overall number of key segments is {len(keys.index)}")
keys["localkey_fifths"] = transform(keys, roman_numeral2fifths, ['localkey', 'globalkey_is_minor'])
keys.head(20)
```


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    Cell In[45], line 2
          1 from ms3 import roman_numeral2fifths, transform, resolve_all_relative_numerals, replace_boolean_mode_by_strings
    ----> 2 keys_segmented = dc.LocalKeySlicer().process_data(selected)
          3 keys = keys_segmented.get_slice_info()
          4 keys.to_csv('romantic_keys.tsv.zip', sep='\t')


    File /dimcat/src/dimcat/slicer.py:181, in OnePassFacetSlicer.process_data(self, data)
        175 slice_infos = (
        176     {}
        177 )  # for each slice, the relevant info about it, e.g. for later grouping
        178 sliced = (
        179     {}
        180 )  # for each piece, the relevant facet sliced into multiple DataFrames
    --> 181 for group, dfs in data.iter_facet(self.required_facets[0]):
        182     new_index_group = []
        183     for index, facet_df in dfs.items():


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
keys.duration_qb.sum()
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[46], line 1
    ----> 1 keys.duration_qb.sum()


    NameError: name 'keys' is not defined



```python
phrases.duration_qb.sum()
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[47], line 1
    ----> 1 phrases.duration_qb.sum()


    NameError: name 'phrases' is not defined



```python
key_durations = keys.groupby(['globalkey_is_minor', 'localkey']).duration_qb.sum().sort_values(ascending=False)
print(f"{len(key_durations)} keys overall including hierarchical such as 'III/v'.")
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[48], line 1
    ----> 1 key_durations = keys.groupby(['globalkey_is_minor', 'localkey']).duration_qb.sum().sort_values(ascending=False)
          2 print(f"{len(key_durations)} keys overall including hierarchical such as 'III/v'.")


    NameError: name 'keys' is not defined



```python
keys_resolved = resolve_all_relative_numerals(keys)
key_resolved_durations = keys_resolved.groupby(['globalkey_is_minor', 'localkey']).duration_qb.sum().sort_values(ascending=False)
print(f"{len(key_resolved_durations)} keys overall after resolving hierarchical ones.")
key_resolved_durations
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[49], line 1
    ----> 1 keys_resolved = resolve_all_relative_numerals(keys)
          2 key_resolved_durations = keys_resolved.groupby(['globalkey_is_minor', 'localkey']).duration_qb.sum().sort_values(ascending=False)
          3 print(f"{len(key_resolved_durations)} keys overall after resolving hierarchical ones.")


    NameError: name 'keys' is not defined



```python
pie_data = replace_boolean_mode_by_strings(key_resolved_durations.reset_index())
px.pie(pie_data, names='localkey', values='duration_qb', facet_col='globalkey_mode', height=700)
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[50], line 1
    ----> 1 pie_data = replace_boolean_mode_by_strings(key_resolved_durations.reset_index())
          2 px.pie(pie_data, names='localkey', values='duration_qb', facet_col='globalkey_mode', height=700)


    NameError: name 'key_resolved_durations' is not defined



```python
localkey_fifths_durations = keys.groupby(['localkey_fifths', 'localkey_is_minor']).duration_qb.sum()
# sort by stacked bar length:
localkey_fifths_durations = localkey_fifths_durations.sort_values(key=lambda S: S.index.get_level_values(0).map(S.groupby(level=0).sum()), ascending=False)
bar_data = replace_boolean_mode_by_strings(localkey_fifths_durations.reset_index())
bar_data.localkey_fifths = bar_data.localkey_fifths.map(ms3.fifths2iv)
fig = px.bar(bar_data, x='localkey_fifths', y='duration_qb', color='localkey_mode', log_y=True, barmode='group',
             labels=dict(localkey_fifths='Roots of local keys as intervallic distance from the global tonic', 
                   duration_qb='total duration in quarter notes',
                   localkey_mode='mode'
                  ),
             color_discrete_sequence=corpus_color_scale,
             width=1000)
fig.update_layout(**STD_LAYOUT)
fig.update_yaxes(gridcolor='lightgrey')
fig.write_image(os.path.join(OUTPUT_DIR, "key_segments.png"), scale=2)
fig.show()
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[51], line 1
    ----> 1 localkey_fifths_durations = keys.groupby(['localkey_fifths', 'localkey_is_minor']).duration_qb.sum()
          2 # sort by stacked bar length:
          3 localkey_fifths_durations = localkey_fifths_durations.sort_values(key=lambda S: S.index.get_level_values(0).map(S.groupby(level=0).sum()), ascending=False)


    NameError: name 'keys' is not defined



```python
localkey_fifths_durations = keys.groupby(['localkey_fifths', 'localkey_is_minor']).duration_qb.sum()
# sort by stacked bar length:
bar_data = replace_boolean_mode_by_strings(localkey_fifths_durations.reset_index())
bar_data.localkey_fifths = bar_data.localkey_fifths.map(ms3.fifths2iv)
fig = px.bar(bar_data, x='localkey_fifths', y='duration_qb', color='localkey_mode', log_y=True, barmode='group',
             labels=dict(localkey_fifths='Roots of local keys as intervallic distance from the global tonic', 
                   duration_qb='total duration in quarter notes',
                   localkey_mode='mode'
                  ),
             color_discrete_sequence=corpus_color_scale,
             width=1000)
fig.update_layout(**STD_LAYOUT)
fig.update_yaxes(gridcolor='lightgrey')
fig.write_image(os.path.join(OUTPUT_DIR, "key_segments_line_of_fifths.png"), scale=2)
fig.show()
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[52], line 1
    ----> 1 localkey_fifths_durations = keys.groupby(['localkey_fifths', 'localkey_is_minor']).duration_qb.sum()
          2 # sort by stacked bar length:
          3 bar_data = replace_boolean_mode_by_strings(localkey_fifths_durations.reset_index())


    NameError: name 'keys' is not defined



```python
localkey_fifths_durations_stacked = localkey_fifths_durations.groupby(level=0).sum().sort_values()
pd.concat([localkey_fifths_durations_stacked, localkey_fifths_durations_stacked.rename('fraction') / localkey_fifths_durations_stacked.sum()], axis=1)
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[53], line 1
    ----> 1 localkey_fifths_durations_stacked = localkey_fifths_durations.groupby(level=0).sum().sort_values()
          2 pd.concat([localkey_fifths_durations_stacked, localkey_fifths_durations_stacked.rename('fraction') / localkey_fifths_durations_stacked.sum()], axis=1)


    NameError: name 'localkey_fifths_durations' is not defined



```python
keys[keys.localkey_fifths == -9]
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[54], line 1
    ----> 1 keys[keys.localkey_fifths == -9]


    NameError: name 'keys' is not defined



```python
keys[keys.localkey_fifths == 10]
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[55], line 1
    ----> 1 keys[keys.localkey_fifths == 10]


    NameError: name 'keys' is not defined


# Cadences


```python
all_annotations.cadence.value_counts()
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[56], line 1
    ----> 1 all_annotations.cadence.value_counts()


    NameError: name 'all_annotations' is not defined



```python
all_annotations.groupby("corpus_name").cadence.value_counts()
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[57], line 1
    ----> 1 all_annotations.groupby("corpus_name").cadence.value_counts()


    NameError: name 'all_annotations' is not defined



```python
cadence_count_per_corpus = all_annotations.groupby("corpus_name").cadence.value_counts().sort_values(ascending=False)
cadence_count_per_corpus.groupby(level=0).sum()
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[58], line 1
    ----> 1 cadence_count_per_corpus = all_annotations.groupby("corpus_name").cadence.value_counts().sort_values(ascending=False)
          2 cadence_count_per_corpus.groupby(level=0).sum()


    NameError: name 'all_annotations' is not defined



```python
cadence_fraction_per_corpus = cadence_count_per_corpus / cadence_count_per_corpus.groupby(level=0).sum()
fig = px.bar(cadence_fraction_per_corpus.rename('count').reset_index(), x='corpus_name', y='count', color='cadence',
             labels=dict(count='fraction', corpus=''), 
             height=400, width=900,
       category_orders=dict(corpus_name=chronological_corpus_names))
      #color_discrete_map=cadence_colors, 

fig.update_layout(**STD_LAYOUT)
fig.update_yaxes(gridcolor='lightgrey')
fig.write_image(os.path.join(OUTPUT_DIR, "cadences.png"), scale=2)
fig.show()
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[59], line 1
    ----> 1 cadence_fraction_per_corpus = cadence_count_per_corpus / cadence_count_per_corpus.groupby(level=0).sum()
          2 fig = px.bar(cadence_fraction_per_corpus.rename('count').reset_index(), x='corpus_name', y='count', color='cadence',
          3              labels=dict(count='fraction', corpus=''), 
          4              height=400, width=900,
          5        category_orders=dict(corpus_name=chronological_corpus_names))
          6       #color_discrete_map=cadence_colors, 


    NameError: name 'cadence_count_per_corpus' is not defined


# Harmony labels
## Unigrams
For computing unigram statistics, the tokens need to be grouped by their occurrence within a major or a minor key because this changes their meaning. To that aim, the annotated corpus needs to be sliced into contiguous localkey segments which are then grouped into a major (`is_minor=False`) and a minor group.


```python
root_durations = all_chords[all_chords.root.between(-5,6)].groupby(['root', 'chord_type']).duration_qb.sum()
# sort by stacked bar length:
#root_durations = root_durations.sort_values(key=lambda S: S.index.get_level_values(0).map(S.groupby(level=0).sum()), ascending=False)
bar_data = root_durations.reset_index()
bar_data.root = bar_data.root.map(ms3.fifths2iv)
px.bar(bar_data, x='root', y='duration_qb', color='chord_type')
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[60], line 1
    ----> 1 root_durations = all_chords[all_chords.root.between(-5,6)].groupby(['root', 'chord_type']).duration_qb.sum()
          2 # sort by stacked bar length:
          3 #root_durations = root_durations.sort_values(key=lambda S: S.index.get_level_values(0).map(S.groupby(level=0).sum()), ascending=False)
          4 bar_data = root_durations.reset_index()


    NameError: name 'all_chords' is not defined



```python
relative_roots = all_chords[['numeral', 'duration_qb', 'relativeroot', 'localkey_is_minor', 'chord_type']].copy()
relative_roots['relativeroot_resolved'] = transform(relative_roots, ms3.resolve_relative_keys, ['relativeroot', 'localkey_is_minor'])
has_rel = relative_roots.relativeroot_resolved.notna()
relative_roots.loc[has_rel, 'localkey_is_minor'] = relative_roots.loc[has_rel, 'relativeroot_resolved'].str.islower()
relative_roots['root'] = transform(relative_roots, roman_numeral2fifths, ['numeral', 'localkey_is_minor'])
chord_type_frequency = all_chords.chord_type.value_counts()
replace_rare = ms3.map_dict({t: 'other' for t in chord_type_frequency[chord_type_frequency < 500].index})
relative_roots['type_reduced'] = relative_roots.chord_type.map(replace_rare)
#is_special = relative_roots.chord_type.isin(('It', 'Ger', 'Fr'))
#relative_roots.loc[is_special, 'root'] = -4
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[61], line 1
    ----> 1 relative_roots = all_chords[['numeral', 'duration_qb', 'relativeroot', 'localkey_is_minor', 'chord_type']].copy()
          2 relative_roots['relativeroot_resolved'] = transform(relative_roots, ms3.resolve_relative_keys, ['relativeroot', 'localkey_is_minor'])
          3 has_rel = relative_roots.relativeroot_resolved.notna()


    NameError: name 'all_chords' is not defined



```python
root_durations = relative_roots.groupby(['root', 'type_reduced']).duration_qb.sum().sort_values(ascending=False)
bar_data = root_durations.reset_index()
bar_data.root = bar_data.root.map(ms3.fifths2iv)
root_order = bar_data.groupby('root').duration_qb.sum().sort_values(ascending=False).index.to_list()
type_colors = dict(zip(('Mm7', 'M', 'o7', 'o', 'mm7', 'm', '%7', 'MM7', 'other'), colorlover.scales['9']['qual']['Paired']))
fig = px.bar(bar_data, x='root', y='duration_qb', color='type_reduced', barmode='group', log_y=True,
             color_discrete_map=type_colors, 
             category_orders=dict(root=root_order,
                                  type_reduced=relative_roots.type_reduced.value_counts().index.to_list(),
                                 ),
            labels=dict(root="intervallic difference between chord root to the local or secondary tonic",
                        duration_qb="duration in quarter notes",
                        type_reduced="chord type",
                       ),
             width=1000,
             height=400,
            )
fig.update_layout(**STD_LAYOUT,
                  legend=dict(
                      orientation='h',
                      xanchor="right",
                      x=1,
                      y=1,
                  )
                 )
fig.update_yaxes(gridcolor='lightgrey')
fig.write_image(os.path.join(OUTPUT_DIR, "chord_roots.png"), scale=2)
fig.show()
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[62], line 1
    ----> 1 root_durations = relative_roots.groupby(['root', 'type_reduced']).duration_qb.sum().sort_values(ascending=False)
          2 bar_data = root_durations.reset_index()
          3 bar_data.root = bar_data.root.map(ms3.fifths2iv)


    NameError: name 'relative_roots' is not defined



```python
print(f"Reduced to {len(set(bar_data.iloc[:,:2].itertuples(index=False, name=None)))} types. Paper cites the sum of types in major and types in minor (see below), treating them as distinct.")
```

    Reduced to 0 types. Paper cites the sum of types in major and types in minor (see below), treating them as distinct.



```python
dim_or_aug = bar_data[bar_data.root.str.startswith("a") | bar_data.root.str.startswith("d")].duration_qb.sum()
complete = bar_data.duration_qb.sum()
print(f"On diminished or augmented scale degrees: {dim_or_aug} / {complete} = {dim_or_aug / complete}")
```


    ---------------------------------------------------------------------------

    AttributeError                            Traceback (most recent call last)

    Cell In[64], line 1
    ----> 1 dim_or_aug = bar_data[bar_data.root.str.startswith("a") | bar_data.root.str.startswith("d")].duration_qb.sum()
          2 complete = bar_data.duration_qb.sum()
          3 print(f"On diminished or augmented scale degrees: {dim_or_aug} / {complete} = {dim_or_aug / complete}")


    File /usr/local/lib/python3.10/site-packages/pandas/core/generic.py:5902, in NDFrame.__getattr__(self, name)
       5895 if (
       5896     name not in self._internal_names_set
       5897     and name not in self._metadata
       5898     and name not in self._accessors
       5899     and self._info_axis._can_hold_identifiers_and_holds_name(name)
       5900 ):
       5901     return self[name]
    -> 5902 return object.__getattribute__(self, name)


    AttributeError: 'DataFrame' object has no attribute 'root'



```python
mode_slices = dc.ModeGrouper().process_data(keys_segmented)
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[65], line 1
    ----> 1 mode_slices = dc.ModeGrouper().process_data(keys_segmented)


    NameError: name 'keys_segmented' is not defined


### Whole dataset


```python
mode_slices.get_slice_info()
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[66], line 1
    ----> 1 mode_slices.get_slice_info()


    NameError: name 'mode_slices' is not defined



```python
unigrams = dc.ChordSymbolUnigrams(once_per_group=True).process_data(mode_slices)
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[67], line 1
    ----> 1 unigrams = dc.ChordSymbolUnigrams(once_per_group=True).process_data(mode_slices)


    NameError: name 'mode_slices' is not defined



```python
unigrams.group2pandas = "group_of_series2series"
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[68], line 1
    ----> 1 unigrams.group2pandas = "group_of_series2series"


    NameError: name 'unigrams' is not defined



```python
unigrams.get(as_pandas=True)
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[69], line 1
    ----> 1 unigrams.get(as_pandas=True)


    NameError: name 'unigrams' is not defined



```python
modes = {True: 'MINOR', False: 'MAJOR'}
for (is_minor,), ugs in unigrams.iter():
    print(f"{modes[is_minor]} UNIGRAMS\n{ugs.shape[0]} types, {ugs.sum()} tokens")
    print(ugs.head(20).to_string())
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[70], line 2
          1 modes = {True: 'MINOR', False: 'MAJOR'}
    ----> 2 for (is_minor,), ugs in unigrams.iter():
          3     print(f"{modes[is_minor]} UNIGRAMS\n{ugs.shape[0]} types, {ugs.sum()} tokens")
          4     print(ugs.head(20).to_string())


    NameError: name 'unigrams' is not defined


### Per corpus


```python
corpus_wise_unigrams = dc.Pipeline([dc.CorpusGrouper(), dc.ChordSymbolUnigrams(once_per_group=True)]).process_data(mode_slices)
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[71], line 1
    ----> 1 corpus_wise_unigrams = dc.Pipeline([dc.CorpusGrouper(), dc.ChordSymbolUnigrams(once_per_group=True)]).process_data(mode_slices)


    NameError: name 'mode_slices' is not defined



```python
corpus_wise_unigrams.get()
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[72], line 1
    ----> 1 corpus_wise_unigrams.get()


    NameError: name 'corpus_wise_unigrams' is not defined



```python
for (is_minor, corpus_name), ugs in corpus_wise_unigrams.iter():
    print(f"{corpus_name} {modes[is_minor]} unigrams ({ugs.shape[0]} types, {ugs.sum()} tokens)")
    print(ugs.head(5).to_string())
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[73], line 1
    ----> 1 for (is_minor, corpus_name), ugs in corpus_wise_unigrams.iter():
          2     print(f"{corpus_name} {modes[is_minor]} unigrams ({ugs.shape[0]} types, {ugs.sum()} tokens)")
          3     print(ugs.head(5).to_string())


    NameError: name 'corpus_wise_unigrams' is not defined



```python
types_shared_between_corpora = {}
for (is_minor, corpus_name), ugs in corpus_wise_unigrams.iter():
    if is_minor in types_shared_between_corpora:
        types_shared_between_corpora[is_minor] = types_shared_between_corpora[is_minor].intersection(ugs.index) 
    else:
        types_shared_between_corpora[is_minor] = set(ugs.index)
types_shared_between_corpora = {k: sorted(v, key=lambda x: unigrams.get()[(k, x)], reverse=True) for k, v in types_shared_between_corpora.items()}
n_types = {k: len(v) for k, v in types_shared_between_corpora.items()}
print(f"Chords which occur in all corpora, sorted by descending global frequency:\n{types_shared_between_corpora}\nCounts: {n_types}")
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[74], line 2
          1 types_shared_between_corpora = {}
    ----> 2 for (is_minor, corpus_name), ugs in corpus_wise_unigrams.iter():
          3     if is_minor in types_shared_between_corpora:
          4         types_shared_between_corpora[is_minor] = types_shared_between_corpora[is_minor].intersection(ugs.index) 


    NameError: name 'corpus_wise_unigrams' is not defined


### Per piece


```python
piece_wise_unigrams = dc.Pipeline([dc.PieceGrouper(), dc.ChordSymbolUnigrams(once_per_group=True)]).process_data(mode_slices)
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[75], line 1
    ----> 1 piece_wise_unigrams = dc.Pipeline([dc.PieceGrouper(), dc.ChordSymbolUnigrams(once_per_group=True)]).process_data(mode_slices)


    NameError: name 'mode_slices' is not defined



```python
piece_wise_unigrams.get()
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[76], line 1
    ----> 1 piece_wise_unigrams.get()


    NameError: name 'piece_wise_unigrams' is not defined



```python
types_shared_between_pieces = {}
for (is_minor, corpus_name), ugs in piece_wise_unigrams.iter():
    if is_minor in types_shared_between_pieces:
        types_shared_between_pieces[is_minor] = types_shared_between_pieces[is_minor].intersection(ugs.index) 
    else:
        types_shared_between_pieces[is_minor] = set(ugs.index)
print(types_shared_between_pieces)
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[77], line 2
          1 types_shared_between_pieces = {}
    ----> 2 for (is_minor, corpus_name), ugs in piece_wise_unigrams.iter():
          3     if is_minor in types_shared_between_pieces:
          4         types_shared_between_pieces[is_minor] = types_shared_between_pieces[is_minor].intersection(ugs.index) 


    NameError: name 'piece_wise_unigrams' is not defined


## Bigrams

### Whole dataset


```python
bigrams = dc.ChordSymbolBigrams(once_per_group=True).process_data(mode_slices)
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[78], line 1
    ----> 1 bigrams = dc.ChordSymbolBigrams(once_per_group=True).process_data(mode_slices)


    NameError: name 'mode_slices' is not defined



```python
bigrams.get()
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[79], line 1
    ----> 1 bigrams.get()


    NameError: name 'bigrams' is not defined



```python
modes = {True: 'MINOR', False: 'MAJOR'}
for (is_minor,), ugs in bigrams.iter():
    print(f"{modes[is_minor]} BIGRAMS\n{ugs.shape[0]} transition types, {ugs.sum()} tokens")
    print(ugs.head(20).to_string())
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[80], line 2
          1 modes = {True: 'MINOR', False: 'MAJOR'}
    ----> 2 for (is_minor,), ugs in bigrams.iter():
          3     print(f"{modes[is_minor]} BIGRAMS\n{ugs.shape[0]} transition types, {ugs.sum()} tokens")
          4     print(ugs.head(20).to_string())


    NameError: name 'bigrams' is not defined


### Per corpus


```python
corpus_wise_bigrams = dc.Pipeline([dc.CorpusGrouper(), dc.ChordSymbolBigrams(once_per_group=True)]).process_data(mode_slices)
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[81], line 1
    ----> 1 corpus_wise_bigrams = dc.Pipeline([dc.CorpusGrouper(), dc.ChordSymbolBigrams(once_per_group=True)]).process_data(mode_slices)


    NameError: name 'mode_slices' is not defined



```python
corpus_wise_bigrams.get()
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[82], line 1
    ----> 1 corpus_wise_bigrams.get()


    NameError: name 'corpus_wise_bigrams' is not defined



```python
for (is_minor, corpus_name), ugs in corpus_wise_bigrams.iter():
    print(f"{corpus_name} {modes[is_minor]} bigrams ({ugs.shape[0]} transition types, {ugs.sum()} tokens)")
    print(ugs.head(5).to_string())
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[83], line 1
    ----> 1 for (is_minor, corpus_name), ugs in corpus_wise_bigrams.iter():
          2     print(f"{corpus_name} {modes[is_minor]} bigrams ({ugs.shape[0]} transition types, {ugs.sum()} tokens)")
          3     print(ugs.head(5).to_string())


    NameError: name 'corpus_wise_bigrams' is not defined



```python
normalized_corpus_unigrams = {group: (100 * ugs / ugs.sum()).round(1).rename("frequency") for group, ugs in corpus_wise_unigrams.iter()}
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[84], line 1
    ----> 1 normalized_corpus_unigrams = {group: (100 * ugs / ugs.sum()).round(1).rename("frequency") for group, ugs in corpus_wise_unigrams.iter()}


    NameError: name 'corpus_wise_unigrams' is not defined



```python
transitions_from_shared_types = {
    False: {},
    True: {}
}
for (is_minor, corpus_name), bgs in corpus_wise_bigrams.iter():
    transitions_normalized_per_from = bgs.groupby(level="from").apply(lambda S: (100 * S / S.sum()).round(1))
    most_frequent_transition_per_from = transitions_normalized_per_from.rename('fraction').reset_index(level=1).groupby(level=0).nth(0)
    most_frequent_transition_per_shared = most_frequent_transition_per_from.loc[types_shared_between_corpora[is_minor]]
    unigram_frequency_of_shared = normalized_corpus_unigrams[(is_minor, corpus_name)].loc[types_shared_between_corpora[is_minor]]
    combined = pd.concat([unigram_frequency_of_shared, most_frequent_transition_per_shared], axis=1)
    transitions_from_shared_types[is_minor][corpus_name] = combined
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[85], line 5
          1 transitions_from_shared_types = {
          2     False: {},
          3     True: {}
          4 }
    ----> 5 for (is_minor, corpus_name), bgs in corpus_wise_bigrams.iter():
          6     transitions_normalized_per_from = bgs.groupby(level="from").apply(lambda S: (100 * S / S.sum()).round(1))
          7     most_frequent_transition_per_from = transitions_normalized_per_from.rename('fraction').reset_index(level=1).groupby(level=0).nth(0)


    NameError: name 'corpus_wise_bigrams' is not defined



```python
pd.concat(transitions_from_shared_types[False].values(), keys=transitions_from_shared_types[False].keys(), axis=1)
```


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    Cell In[86], line 1
    ----> 1 pd.concat(transitions_from_shared_types[False].values(), keys=transitions_from_shared_types[False].keys(), axis=1)


    File /usr/local/lib/python3.10/site-packages/pandas/util/_decorators.py:331, in deprecate_nonkeyword_arguments.<locals>.decorate.<locals>.wrapper(*args, **kwargs)
        325 if len(args) > num_allow_args:
        326     warnings.warn(
        327         msg.format(arguments=_format_argument_list(allow_args)),
        328         FutureWarning,
        329         stacklevel=find_stack_level(),
        330     )
    --> 331 return func(*args, **kwargs)


    File /usr/local/lib/python3.10/site-packages/pandas/core/reshape/concat.py:368, in concat(objs, axis, join, ignore_index, keys, levels, names, verify_integrity, sort, copy)
        146 @deprecate_nonkeyword_arguments(version=None, allowed_args=["objs"])
        147 def concat(
        148     objs: Iterable[NDFrame] | Mapping[HashableT, NDFrame],
       (...)
        157     copy: bool = True,
        158 ) -> DataFrame | Series:
        159     """
        160     Concatenate pandas objects along a particular axis.
        161 
       (...)
        366     1   3   4
        367     """
    --> 368     op = _Concatenator(
        369         objs,
        370         axis=axis,
        371         ignore_index=ignore_index,
        372         join=join,
        373         keys=keys,
        374         levels=levels,
        375         names=names,
        376         verify_integrity=verify_integrity,
        377         copy=copy,
        378         sort=sort,
        379     )
        381     return op.get_result()


    File /usr/local/lib/python3.10/site-packages/pandas/core/reshape/concat.py:425, in _Concatenator.__init__(self, objs, axis, join, keys, levels, names, ignore_index, verify_integrity, copy, sort)
        422     objs = list(objs)
        424 if len(objs) == 0:
    --> 425     raise ValueError("No objects to concatenate")
        427 if keys is None:
        428     objs = list(com.not_none(*objs))


    ValueError: No objects to concatenate



```python
pd.concat(transitions_from_shared_types[True].values(), keys=transitions_from_shared_types[False].keys(), axis=1)
```


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    Cell In[87], line 1
    ----> 1 pd.concat(transitions_from_shared_types[True].values(), keys=transitions_from_shared_types[False].keys(), axis=1)


    File /usr/local/lib/python3.10/site-packages/pandas/util/_decorators.py:331, in deprecate_nonkeyword_arguments.<locals>.decorate.<locals>.wrapper(*args, **kwargs)
        325 if len(args) > num_allow_args:
        326     warnings.warn(
        327         msg.format(arguments=_format_argument_list(allow_args)),
        328         FutureWarning,
        329         stacklevel=find_stack_level(),
        330     )
    --> 331 return func(*args, **kwargs)


    File /usr/local/lib/python3.10/site-packages/pandas/core/reshape/concat.py:368, in concat(objs, axis, join, ignore_index, keys, levels, names, verify_integrity, sort, copy)
        146 @deprecate_nonkeyword_arguments(version=None, allowed_args=["objs"])
        147 def concat(
        148     objs: Iterable[NDFrame] | Mapping[HashableT, NDFrame],
       (...)
        157     copy: bool = True,
        158 ) -> DataFrame | Series:
        159     """
        160     Concatenate pandas objects along a particular axis.
        161 
       (...)
        366     1   3   4
        367     """
    --> 368     op = _Concatenator(
        369         objs,
        370         axis=axis,
        371         ignore_index=ignore_index,
        372         join=join,
        373         keys=keys,
        374         levels=levels,
        375         names=names,
        376         verify_integrity=verify_integrity,
        377         copy=copy,
        378         sort=sort,
        379     )
        381     return op.get_result()


    File /usr/local/lib/python3.10/site-packages/pandas/core/reshape/concat.py:425, in _Concatenator.__init__(self, objs, axis, join, keys, levels, names, ignore_index, verify_integrity, copy, sort)
        422     objs = list(objs)
        424 if len(objs) == 0:
    --> 425     raise ValueError("No objects to concatenate")
        427 if keys is None:
        428     objs = list(com.not_none(*objs))


    ValueError: No objects to concatenate


### Per piece


```python
piece_wise_bigrams = dc.Pipeline([dc.PieceGrouper(), dc.ChordSymbolBigrams(once_per_group=True)]).process_data(mode_slices)
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[88], line 1
    ----> 1 piece_wise_bigrams = dc.Pipeline([dc.PieceGrouper(), dc.ChordSymbolBigrams(once_per_group=True)]).process_data(mode_slices)


    NameError: name 'mode_slices' is not defined



```python
piece_wise_bigrams.get()
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[89], line 1
    ----> 1 piece_wise_bigrams.get()


    NameError: name 'piece_wise_bigrams' is not defined
