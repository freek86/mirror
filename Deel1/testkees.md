---
jupytext:
  text_representation:
    extension: .md
    format_name: myst
    format_version: 0.13
    jupytext_version: 1.10.3
kernelspec:
  display_name: Python 3 (ipykernel)
  language: python
  name: python3
---

<!--
  This page is for testing purposes.
-->

## Testkees

To run this code on Binder: click [here](https://mybinder.org/v2/gl/fpols/education/as/ap/polslab/master).

```{code-cell} python
:tags: [remove-input, thebe-init]
%pip install numpy
```

```{code-cell} python
:tags: [remove-input, thebe-init]
import numpy as np
a = np.arange(0,10,1)
print(a)
```


```{code-cell} ipython3
:tags: [remove-input]
 
from myst_nb import glue
from IPython.lib.display import YouTubeVideo
video = YouTubeVideo('vZPQA6G8uoM')
 
glue("vid", video, display = False)
 
```
 
<div style='text-align: center;'>
 
A center aligned header 2
 
```{glue:} vid
```
</div>
 
Voor nog werkende onderdelen.
Nieuw. Verander deze zin bij aanpassingen. 2

[link](my_plot.html)

```{code-cell} python
:tags: [remove-input]
from IPython.display import IFrame
IFrame("https://polslab.tnw.tudelft.nl/dictaat/_downloads/978027a9ccd0b6bd6e4ca59879db3918/my_plot.html", width="800", height="500")
```

<!---
```{code-cell} python
:tags: [remove-input]

from bokeh.layouts import column, row
from bokeh.models import ColumnDataSource, CustomJS, Slider
from bokeh.plotting import figure
from bokeh.io import save
from bokeh.resources import CDN
from bokeh.embed import file_html
from IPython.display import HTML

x = np.linspace(0, 10, 500)
y = 1 * x + 0

data_x = np.array([0, 1, 2, 3, 4, 5])
data_y = data_x + np.random.normal(0, 1, len(data_x))

source = ColumnDataSource(data=dict(x=x, y=y))

plot = figure(y_range=(-10, 10), width=400, height=400)
plot.square(x=data_x, y=data_y, size=5, color="black", alpha=0.5)
plot.line('x', 'y', source=source, line_width=3, line_alpha=0.6)

amp = Slider(start=0.1, end=10, value=1, step=.1, title="Amplitude")
offset = Slider(start=-9, end=9, value=0, step=.1, title="Offset")

callback = CustomJS(args=dict(source=source, amp=amp, offset=offset),
                    code="""
    const A = amp.value
    const B = offset.value

    const x = source.data.x
    const y = Array.from(x, (x) => - B + A * x)
    source.data = { x, y }
""")

amp.js_on_change('value', callback)
offset.js_on_change('value', callback)

layout = row(plot, column(amp, offset))
save(layout, filename="C:/Users/fpols/Documents/New folder/polslab/_build/html/Deel1/my_plot.html", title="My Bokeh Plot", resources=CDN)

html = file_html(plot, CDN, "my plot")
HTML(html)

```
-->

```yaml
  launch_buttons:
    thebe                  : true
```

```{code-cell} ipython3
import numpy as np
import matplotlib.pyplot as plt
plt.ion()

x = np.arange(500)
y = np.random.randn(500)

fig, ax = plt.subplots()
ax.scatter(x, y, c=y, s=x)
```


https://sphinx-subfigure.readthedocs.io/en/latest/