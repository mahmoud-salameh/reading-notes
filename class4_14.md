# Matplotlib Tutorial

## What is Matplotlib?

__Matplotlib is a low level graph plotting library in python that serves as a visualization utility.__

**Matplotlib was created by John D. Hunter.**

Matplotlib is open source and we can use it freely.

Matplotlib is mostly written in python, a few segments are written in C, Objective-C and Javascript for Platform compatibility.

## Installation of Matplotlib


__If you have Python and PIP already installed on a system, then installation of Matplotlib is very easy.__

**Install it using this command:**

    install matplotlib

### Import Matplotlib

**Once Matplotlib is installed, import it in your applications by adding the import module statement:**

    import matplotlib

### Matplotlib Pyplot

__Pyplot__

Most of the Matplotlib utilities lies under the pyplot submodule, and are usually imported under the plt alias:

    import matplotlib.pyplot as plt

__**Example**__

Draw a line in a diagram from position (0,0) to position (6,250):

    import matplotlib.pyplot as plt
    import numpy as np

    xpoints = np.array([0, 6])
    ypoints = np.array([0, 250])

    plt.plot(xpoints, ypoints)
    plt.show()

Result:

![](https://www.w3schools.com/python/img_matplotlib_pyplot.png)

__**Plotting x and y points**__


The plot() function is used to draw points (markers) in a diagram.

By default, the plot() function draws a line from point to point.

The function takes parameters for specifying points in the diagram.

Parameter 1 is an array containing the points on the x-axis.

Parameter 2 is an array containing the points on the y-axis.

__Example__

    import matplotlib.pyplot as plt
    import numpy as np

    xpoints = np.array([1, 8])
    ypoints = np.array([3, 10])

    plt.plot(xpoints, ypoints)
    plt.show()


Result:

![](https://www.w3schools.com/python/img_matplotlib_plotting1.png)

### Plotting Without Line

To plot only the markers, you can use shortcut string notation parameter ‘o’, which means ‘rings’.

Example

    import matplotlib.pyplot as plt
    import numpy as np

    xpoints = np.array([1, 8])
    ypoints = np.array([3, 10])

    plt.plot(xpoints, ypoints, 'o')
    plt.show()

![](https://www.w3schools.com/python/img_matplotlib_plot_o.png)


__Default X-Points__

If we do not specify the points in the x-axis, they will get the default values 0, 1, 2, 3, (etc. depending on the length of the y-points.

Example

    import matplotlib.pyplot as plt
    import numpy as np

    ypoints = np.array([3, 8, 1, 10, 5, 7])

    plt.plot(ypoints)
    plt.show()

![](https://www.w3schools.com/python/img_matplotlib_plotting4.png)


