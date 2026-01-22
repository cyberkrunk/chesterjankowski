---
title: Plotting Intervals on the Number Line
date: 2026-01-22
categories:
  - technology
tags:
  - python
  - math
description: I couldn’t find a ready-made function to plot intervals on the number line, so I made this one using matplotlib.
ogimage: /img/interval_plot.png
---
I’m doing a review of algebra using this nice video which is originally from the [UNC Chapel Hill Math 110](https://youtu.be/LwCRRUa8yTU) course. I'm doing this in a Jupyter notebook, with the plan of adding Python code where needed. On the section on intervals, I was looking for some code to plot intervals on the number line, but, surprisingly, a search didn't turn anything up, so I wrote the code listed below. 

(This may be yet another example of how search is now broken. Search used to give you various options for what your search term might mean; now it just decides it knows precisely what you mean, and gives you 100 variations on the one answer, with SEO and slop sites listed first.)

So far, the code works with ints and floats. It properly plots open and closed intervals. It would be nice to add support later for rationals, radicals, and the like.

```
# -----------------------------------------------------------------------------
# plot_interval is a Python function to plot an interval, e.g., [-4, 2.5)
# on the number line
# 2026-01-22
# -----------------------------------------------------------------------------

import matplotlib.pyplot as plt

def plot_interval(input_interval: str):
    """
    Plots an interval on the number line using Matplotlib

    Args:
        input_interval (str): an interval, e.g., '[-4, 2.5)'.
    """

    # Parse the input into 4 elements
    parsed_interval = ["(", "1", "2", ")"]
    parsed_interval[0] = input_interval[0]
    parsed_interval[1] = input_interval.split(",")[0][1:]
    parsed_interval[2] = input_interval.split(",")[1][:-1].strip()
    parsed_interval[3] = input_interval.split(",")[1][-1]

    # Convert the numbers to either floats or ints
    for i in range(1, 3):
        if "." in parsed_interval[i]:
            parsed_interval[i] = float(parsed_interval[i])
        else:
            parsed_interval[i] = int(parsed_interval[i])

    # Set up the number line
    x_range = [int(parsed_interval[1]) - 1, int(parsed_interval[2]) + 1]
    y_pos = 0
    fig, ax = plt.subplots(figsize=(10, 2))

    # Draw the horizontal number line
    ax.hlines(
        y_pos,
        x_range[0],
        x_range[1],
        color="gray",
        linestyles="solid",
        linewidth=0.5
    )

    # Draw the ticks and label them
    for tick in range(x_range[0], x_range[1] + 1):
        ax.vlines(tick, y_pos - 0.2, y_pos + 0.2, color="black", linewidth=1)
        ax.text(
            tick,
            y_pos - 0.8,
            str(tick),
            horizontalalignment="center",
            verticalalignment="bottom",
        )

    # Draw the line between the interval numbers
    ax.hlines(
        y_pos,
        parsed_interval[1],
        parsed_interval[2],
        color="black",
        linestyles="solid",
        linewidth=2,
    )

    # Plot the left number
    if parsed_interval[0] == "(":
        ax.plot(parsed_interval[1], y_pos, "ko", ms=10, mfc="w")
    else:
        ax.plot(parsed_interval[1], y_pos, "ko", ms=10, mfc="k")

    # Plot the right number
    if parsed_interval[-1] == ")":
        ax.plot(parsed_interval[2], y_pos, "ko", ms=10, mfc="w")
    else:
        ax.plot(parsed_interval[2], y_pos, "ko", ms=10, mfc="k")

    # Add the numbers as text above the points
    for number in parsed_interval[1:3]:
        ax.text(
            number,
            y_pos + 0.3,
            str(number),
            horizontalalignment="center",
            verticalalignment="bottom",
        )

    # Set axis limits and hide the y-axis
    ax.set_xlim(x_range[0], x_range[1])
    ax.set_ylim(-1, 1)
    ax.axis("off")  # Hide all axes and labels
    plt.title(f"Interval: {input_interval}")
    plt.show()
```