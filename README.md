# graphviz-py
[![package version](https://img.shields.io/pypi/v/graphviz-py?style=flat-square&color=%2300AA00)](https://pypi.org/project/graphviz-py/)
[![py versions](https://img.shields.io/pypi/pyversions/graphviz-py?style=flat-square)](https://pypi.org/project/graphviz-py/)
[![pypi](https://img.shields.io/github/workflow/status/Alwinator/graphviz-py/Publish%20to%20PyPi?style=flat-square)](https://pypi.org/project/graphviz-py/)
[![license](https://img.shields.io/github/license/Alwinator/graphviz-py?style=flat-square&color=%2300AA00)](LICENSE)

Allows Python code execution inside of [graphviz](https://graphviz.org/) diagrams

## Example
```dot
graph python_graph {
{{
import math

value = 0.5
sin = math.sin(value)
cos = math.cos(value)
}}

A [label="{{= value }}"];
B [label="{{= sin }}"];
C [label="{{= cos }}"];

A -- B [headlabel="sin"];
A -- C [headlabel="cos"];

}
```

### Output
![output](https://raw.githubusercontent.com/Alwinator/graphviz-py/main/assets/output.svg)

## Installation
```bash
pip install graphviz-py
```

**Important: Make sure graphviz is installed!** See [graphviz installation instructions](https://graphviz.org/download/).


## Usage
### Using files
```bash
graphviz-py -Tsvg example/example.py.dot -o output.svg
graphviz-py -Tpng example/example.py.dot -o output.png
```

### Using stdin / pipes
```bash
echo 'digraph { A -> B [label="{{= 38 * 73 }}"] }' | graphviz-py -Tsvg > output.svg
```

graphviz-py passes all unknown arguments to graphviz. So you can use all [graphviz arguments](https://graphviz.org/doc/info/command.html).

## Coming soon
- Compartibility with asciidoctor-diagram
