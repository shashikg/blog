---
layout: post
title: Scoring a job through Robotics Internship
excerpt_separator: <!--more-->
---
##### When you plan it right!

This blog post is about my experience while developing a C++ library for motion
planning during my third year “internship”. This is about how after failing to
secure an internship for summers, I try to rescue my self-confidence by taking up
an ambitious summer project. Going in a direction orthogonal to what was
planned and finally making something I am proud of. This is both, my
experiences and a very short introduction to the library I developed.
<!--more-->


This time, I studied a few standard
motion planning algorithms and started
thinking of how to simulate them. At
this point, I must admit the MATLAB is
not one of my favourites and I always
try to find a reason for using C++. This
was the perfect opportunity since I
could not find a simple framework to
simulate these algorithms and I admit
that I did not try hard enough (or try at
all! ). I convinced myself that this task
was too computationally intensive to be
handled by python and the only option I had was to use C++. I ended up writing about 200 lines of code to display a minimal (ugly) GUI which allowed the user to
load a map (Illustration 1) and select the starting and ending points for
computing the path and the program would then show an animation of the
planning algorithm finding the path. I showed it to my mentor, he liked it and
encouraged me to simulate another algorithm. This time, I decided, as any good
software engineer would do, that I should divide my program into modules which
share their functionality instead of replicating the code for every simulation I
make. It was this second simulation which changed the direction of my summer
project altogether.

Long story short, I had now completely forgotten about the original problem
statement and was focusing on problems like: How to factor out the pathplanning
algorithms into composable components? What are the basic
components of a path planning problem? What would a sensible API for path
planning look like? I tackled these questions for 5-6 weeks while writing some
prototypes, making flowcharts etc.


Workspace contains the map of the environment. I defined it as a separate class
so that it is possible to hide the implementation from other modules. Problem
definition contains start and end points at the moment. It can be extended to
incorporate way-points or other path constraints that the user might be interested
in. The graph builder takes a workspace and discards all the information not
required for planning the path thus forming a good representation of the
