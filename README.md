[![Build Status](https://travis-ci.org/nturley/netlistsvg.svg?branch=master)](https://travis-ci.org/nturley/netlistsvg)
# netlistsvg
draws an SVG schematic from a [yosys](https://github.com/cliffordwolf/yosys) JSON netlist. It uses [klayjs](https://github.com/OpenKieler/klayjs) for layout.
<details>
  <summary>JSON Source</summary>

```json
{
  "modules": {
    "up3down5": {
      "ports": {
        "clock": {
          "direction": "input",
          "bits": [ 2 ]
        },
        "data_in": {
          "direction": "input",
          "bits": [ 3, 4, 5, 6, 7, 8, 9, 10, 11 ]
        },
        "up": {
          "direction": "input",
          "bits": [ 12 ]
        },
        "down": {
          "direction": "input",
          "bits": [ 13 ]
        },
        "carry_out": {
          "direction": "output",
          "bits": [ 14 ]
        },
        "borrow_out": {
          "direction": "output",
          "bits": [ 15 ]
        },
        "count_out": {
          "direction": "output",
          "bits": [ 16, 17, 18, 19, 20, 21, 22, 23, 24 ]
        },
        "parity_out": {
          "direction": "output",
          "bits": [ 25 ]
        }
      },
      "cells": {
        "$add$input.v:17$3": {
          "type": "$add",
          "port_directions": {
            "A": "input",
            "B": "input",
            "Y": "output"
          },
          "connections": {
            "A": [ 16, 17, 18, 19, 20, 21, 22, 23, 24 ],
            "B": [ "1", "1" ],
            "Y": [ 26, 27, 28, 29, 30, 31, 32, 33, 34, 35 ]
          }
        },
        "$and$input.v:28$5": {
          "type": "$and",
          "port_directions": {
            "A": "input",
            "B": "input",
            "Y": "output"
          },
          "connections": {
            "A": [ 12 ],
            "B": [ 35 ],
            "Y": [ 36 ]
          }
        },
        "$and$input.v:29$6": {
          "type": "$and",
          "port_directions": {
            "A": "input",
            "B": "input",
            "Y": "output"
          },
          "connections": {
            "A": [ 13 ],
            "B": [ 37 ],
            "Y": [ 38 ]
          }
        },
        "$procdff$40": {
          "type": "$dff",
          "port_directions": {
            "CLK": "input",
            "D": "input",
            "Q": "output"
          },
          "connections": {
            "CLK": [ 2 ],
            "D": [ 39, 40, 41, 42, 43, 44, 45, 46, 47 ],
            "Q": [ 16, 17, 18, 19, 20, 21, 22, 23, 24 ]
          }
        },
        "$procdff$41": {
          "type": "$dff",
          "port_directions": {
            "CLK": "input",
            "D": "input",
            "Q": "output"
          },
          "connections": {
            "CLK": [ 2 ],
            "D": [ 36 ],
            "Q": [ 14 ]
          }
        },
        "$procdff$42": {
          "type": "$dff",
          "port_directions": {
            "CLK": "input",
            "D": "input",
            "Q": "output"
          },
          "connections": {
            "CLK": [ 2 ],
            "D": [ 38 ],
            "Q": [ 15 ]
          }
        },
        "$procdff$43": {
          "type": "$dff",
          "port_directions": {
            "CLK": "input",
            "D": "input",
            "Q": "output"
          },
          "connections": {
            "CLK": [ 2 ],
            "D": [ 48 ],
            "Q": [ 25 ]
          }
        },
        "$procmux$36": {
          "type": "$pmux",
          "port_directions": {
            "A": "input",
            "B": "input",
            "S": "input",
            "Y": "output"
          },
          "connections": {
            "A": [ 16, 17, 18, 19, 20, 21, 22, 23, 24 ],
            "B": [ 26, 27, 28, 29, 30, 31, 32, 33, 34, 49, 50, 51, 52, 53, 54, 55, 56, 57, 3, 4, 5, 6, 7, 8, 9, 10, 11 ],
            "S": [ 58, 59, 60 ],
            "Y": [ 39, 40, 41, 42, 43, 44, 45, 46, 47 ]
          }
        },
        "$procmux$37_CMP0": {
          "type": "$eq",
          "port_directions": {
            "A": "input",
            "B": "input",
            "Y": "output"
          },
          "connections": {
            "A": [ 13, 12 ],
            "B": [ "0", "1" ],
            "Y": [ 58 ]
          }
        },
        "$procmux$38_CMP0": {
          "type": "$eq",
          "port_directions": {
            "A": "input",
            "B": "input",
            "Y": "output"
          },
          "connections": {
            "A": [ 13, 12 ],
            "B": [ "1", "0" ],
            "Y": [ 59 ]
          }
        },
        "$procmux$39_CMP0": {
          "type": "$eq",
          "port_directions": {
            "A": "input",
            "B": "input",
            "Y": "output"
          },
          "connections": {
            "A": [ 13, 12 ],
            "B": [ "0", "0" ],
            "Y": [ 60 ]
          }
        },
        "$reduce_xor$input.v:27$4": {
          "type": "$reduce_xor",
          "port_directions": {
            "A": "input",
            "Y": "output"
          },
          "connections": {
            "A": [ 39, 40, 41, 42, 43, 44, 45, 46, 47 ],
            "Y": [ 48 ]
          }
        },
        "$sub$input.v:16$2": {
          "type": "$sub",
          "port_directions": {
            "A": "input",
            "B": "input",
            "Y": "output"
          },
          "connections": {
            "A": [ 16, 17, 18, 19, 20, 21, 22, 23, 24 ],
            "B": [ "1", "0", "1" ],
            "Y": [ 49, 50, 51, 52, 53, 54, 55, 56, 57, 37 ]
          }
        }
      }
    }
  }
}
```
</details>
<img src="https://cdn.rawgit.com/nturley/netlistsvg/d01285946e05ee5ce99dc5d0f8025be58b5936a3/doc/up3down5.svg" />

The JSON doesn't need to be produced by Yosys, of course. We can process arbitrary block diagrams.

<details>
  <summary>JSON Source</summary>

```json
{
  "modules": {
    "generics": {
      "ports": {
        "clk100": {
          "direction": "input",
          "bits": [ 2 ]
        },
        "clk40": {
          "direction": "output",
          "bits": [ 3 ]
        },
        "clk125": {
          "direction": "output",
          "bits": [ 5 ]
        }
      },
      "cells" : {
        "PLL": {
          "type": "PLL",
          "port_directions": {
            "clkin": "input",
            "clk40": "output",
            "clk200": "output",
            "clk125": "output",
            "locked": "output"
          },
          "connections": {
            "clkin": [ 2 ],
            "clk40": [3],
            "clk200": [6],
            "clk125": [5],
            "locked": [8]
          }
        },
        "MIG": {
          "type": "MIG",
          "port_directions": {
            "clk_ref": "input",
            "clk_sys": "input",
            "reset": "input"
          },
          "connections": {
            "clk_ref": [6],
            "clk_sys": [2],
            "reset": [4]
          }
        },
        "counter": {
          "type": "counter",
          "port_directions": {
            "clk": "input",
            "start": "input",
            "elapsed": "output"
          },
          "connections": {
            "clk": [2],
            "start": [8],
            "elapsed": [4]
          }
        },
        "sync": {
          "type": "sync",
          "port_directions": {
            "clk": "input",
            "in": "input",
            "out": "output"
          },
          "connections": {
            "clk": [3],
            "in": [4],
            "out": [7]
          }
        },
        "businterface": {
          "type": "businterface",
          "port_directions": {
            "clk": "input",
            "reset": "input"
          },
          "connections": {
            "clk": [3],
            "reset": [7]
          }
        }
      }
    }
  }
}
```
</details>
<img src="https://cdn.rawgit.com/nturley/netlistsvg/d01285946e05ee5ce99dc5d0f8025be58b5936a3/doc/generics.svg" >

## Skin File
It pulls the node icons and configuration options from a SVG skin file. Like this one:

<img src="https://cdn.rawgit.com/nturley/netlistsvg/369a0baa31e568995d4cc7ce825bbe50646616c8/lib/default.svg" width="700" height="250">

A skin file can use style tags or inline CSS to style the elements. That will be copied onto the output file. A skin file also defines a library of components to use. Each component has an alias list. It will use that component as a template for any cell with that type that it encounters. Each component defines the position and id of each of its ports so we know where to attach the wires to.

For example, here is a mux definition. It has two aliases: "$pmux" and "$mux". It defines a type name, and a width and height, as well as the position and id of each of it's ports. In general you can rearrange them however you like, and add whatever SVG elements you like inside the template.

```XML
<g s:type="mux" transform="translate(50, 50)" s:width="20" s:height="40">
  <s:alias val="$pmux"/>
  <s:alias val="$mux"/>

  <path d="M0,0 L20,10 L20,30 L0,40 Z"/>

  <g s:x="0" s:y="10" s:pid="A"/>
  <g s:x="0" s:y="30" s:pid="B"/>
  <g s:x="10" s:y="35" s:pid="S"/>
  <g s:x="20" s:y="20" s:pid="Y"/>
</g>
```

In addition to the library of components that are matched to cells, a skin file defines some special nodes. Input/Output ports, constants, Splits/Joins, and the generic node. Splits/Joins and the generic node are particularly tricky because the height and number of ports need to be adjusted depending on the cell. Adjustments to the splits/joins and generic node templates might end up breaking something.

The klayjs layout properties are also defined in the skin file.

```XML
<s:properties
    spacing="25"
    borderSpacing="50"
    nodeLayering="LONGEST_PATH"
/>
```
Any properties specified here will get passed along to the layout engine. Node and edge properties aren't configurable (yet). Right now I'm setting the priority of $dff.Q to be lower than everything else so that feedback edges on flip flops will go from right to left.

I'm also setting the ports to be fixed position right now, until I figure out a plan for swappable ports.

## Split/Join Wires
It does it's best to be smart about how to split and join buses. I spent a lot of time thinking about it and hacked something together using javascript strings (because I was too lazy to write my own library for processing sequences). At some point I will rewrite it with a sane implementation that doesn't use strings. I think I'm happy with the core algorithm, just the implementation is wonky.

<details>
  <summary>JSON Source</summary>

```json
{
  "modules": {
    "simple": {
      "ports": {
        "inthing": {
          "direction": "input",
          "bits": [ 2, 3, 4, 5 ]
        },
        "outthing": {
          "direction": "output",
          "bits": [ 2, 3 ]
        },
        "outthing2": {
          "direction": "output",
          "bits": [ 2, 3, 5 ]
        },
        "outthing3": {
          "direction": "output",
          "bits": [ 2, 3, 5 ]
        },
        "outthing4": {
          "direction": "output",
          "bits": [ 2 ]
        }
      },
      "cells": {}
    }
  }
}
```
</details>
<img src="https://cdn.rawgit.com/nturley/netlistsvg/d01285946e05ee5ce99dc5d0f8025be58b5936a3/doc/ports_splitjoin.svg" >

I'll read through my code some time and add more detailed notes of the algorithm, but as I recall, the basic principles are as follows:

* There should only exist one wire for each unique sequence of signals
* Always prefer using an existing signal over adding a new split or join

As I recall, I iterate over each input port and determine whether I need additional splits or joins to satisfy the port. Then I add the new signals as available signals for the rest of the ports to use.

KlayJS handles all of the wire junctions. Sometimes it does some odd things. I'm still figuring it out.
## Input JSON
This is designed to handle Yosys netlist format but we ignore most of it. This is what we are looking at. Currently, we only draw the first module in the modules object.
```json
{
  "modules": {
    "<dont care>": {
      "ports": {
        "<port name>": {
          "direction": "<input|output",
          "bits": [ 2, "1", ... ]
        },
        ...
      },
      "cells": {
        "<cell name>": {
          "type": "<type name",
          "port_directions": {
            "<port name>": "<input|output>",
            ...
          },
          "connections": {
            "<port name>": [ 3, "0", ... ],
            ...
          }
      },
      ...
    }
  }
}
```
## KlayJS
I'm super impressed with this. Layout is a non-trivial problem and this tool is amazing. Naturally, I could've used the original Klay library written in Java instead of the JS transpiled version and I fiddled with that for a while but crossing language boundaries is irritating. Which means I'd be writing this in Java or Scala and I wasn't in the mood to do that. Also, I'd already written some of this code in Javascript, so it was easier to start from here.

This tool is really powerful and not very well documented so I'm still learning the ins and outs of how to use it. For instance, Klay should be in charge of positioning labels, (which I think might prevent the wires from being routed through text). Klay is also capable of port positioning. This means that potentially I could flag certain ports as being able to be swapped or repositioned and Klay could reorder them to reduce crossings. That's obviously a win for labeled ports on the generic, and split/join, but also a win for cells whose operation is commutative.

Klay is using a layered approach (Sugiyama, Ganser), similar to dot in the Graphviz package. I was doing a lot of experiments with it and I became convinced that longest path rank assignment produced better schematics than Network Simplex. This is obviously subjective, but I think that Network Simplex attempts to make the graph uniformly distributed on the page in an effort to make it less wide (or tall in our case). In schematics, I would rather a taller graph that grouped together related logic than a compact one with node that are more uniformly distributed. Also when the flow goes from left to right, with vertically scrolling webpages, using up additional vertical space isn't as big of a cost.

Elkjs is the newer version of klayjs, so at some point, I'll migrate over to that.

# Status
Still early stages. But it's usable.

# Installation/Usage Instructions
```
(install nodejs)
git clone https://github.com/nturley/netlistsvg
cd netlistsvg
npm install
```
At the moment, the invocation looks something like this.
```
node bin/netlistsvg input_json_file [-o output_svg_file] [--skin skin_file]
```
The default value for the output file is out.svg.


## Generating `input_json_file` with Yosys

[Yosys from Clifford Wolf](https://github.com/cliffordwolf/yosys) can be used to generate the `input_json_file` using [the `write_json` command](http://www.clifford.at/yosys/cmd_json.html).

Unless you are doing something special you will want to use [the `prep` command](http://www.clifford.at/yosys/cmd_prep.html). Some examples are provided below and you can find some runnable examples which go from Verilog to diagrams in the [examples directory](./examples) (with example Makefile).

#### Generate top level diagram

This command will generate a diagram of the top module with all the inner modules shown as boxes.

```
yosys -p "prep -top my_top_module; write_json output.json" input.v
```

#### Generate logic diagram

You can give it the `-flatten` argument to  [the `prep` command](http://www.clifford.at/yosys/cmd_prep.html) if you want Yosys to convert everything into low level logic. Only basic logic cells and black boxes will exist after flattening.

```
yosys -p "prep -top my_top_module -flatten; write_json output.json" input.v
```

### Generate AND (or not) and inverter (NOT) diagram

It is also frequently common that you want to create a diagram only using AND and NOT (or NAND and NOT) cells. ([This is called an AIG](https://en.wikipedia.org/wiki/And-inverter_graph).) This can be done with Yosys' [`aigmap` command](http://www.clifford.at/yosys/cmd_proc.html).

```
yosys -p "prep -top my_top_module; aigmap; write_json output.json" input.v
```

# TODO
* Improve packaging and usability
 * browserify
 * lib should work with strings instead of files
 * allow relaxed json syntax
 * print more helpful error messages for invalid json
 * other image output formats
* better skinning
 * consistent templating abstractions
 * less hard-coded special nodes
* Better usage of klayjs
 * label handling
 * port swapping
* Better drawing
 * hex constants, (not just binary)
 * don't redraw redundant wire segments
* code refactor
 * split/join code
 * remove unnecessary module reformatting (leftover from d3)
 * Single source of truth model
* CI
 * better test suite
 * appveyour
* hierarchy (draw all modules)
