# CurvatureCalulator
A set of Wolfram Mathematica notebooks for calculating curvature tensors from a given metric and vielbein.

Welcome to Curvature Calculator!

You choose a metric and a vielbein in any dimension. Curvature Calculator calculates all curvatures for you.

## Instructions for installation

Make sure you have Wolfram Mathematica 10 or above. 
Download the contents of the repository. Make sure all .nb files are located in the same folder.

If you want to jump right to the calculation, simply open 
CurvatureCalculator_3.23.nb and ListOfMetrics_2.0.nb and you can get started.
(read below for instructions)

## What is Curvature Calculator?

CurvatureCalculator is designed with the following freedom in mind: to calculate curvatures (and connections) in an arbitrary holonomic or anholonomic frame representation of the metric. This can greatly improve the calculation time but also help you practice and understand the intuition that comes working with anholonomic vielbein frames adapted to certain situations.

You can use CurvatureCalculator to study in detail how components of connection and curvatures have different form in different vielbein frames (and coordinates) and the same for the curvatures and their invariants.

In addition to this basic functionality, CurvatureCalculator offers the possibility to calculate parts of connections and curvatures that arise as a consequence of splitting the metric into scale (determinant) and shape (conformal) parts, i.e. due to the unimodular decomposition. 

## Steps

There are several functions which you should be aware of.
Only steps 1, 2, 3 and 4 below are necessary for the usual calculations.

IMPORTANT REMARK: only a smart choice of the anholonomic vielbein frame is going to lead to an efficient calculation; I found it illuminating to choose the vielbein frame to be the same (obey the same symmetry) as the vielbein used in an orthonormal frame of the flat space metric representation.

Steps 5 and 6 are there if you want to study the scale and shape parts of connections and curvatures in specific coordinates. 

IMPORTANT REMARK: Only a smart choice of the unimodular decomposition basis is going to lead to an efficient calculation. I found it useful and illuminating to take into account the previous important remark. Roughly speaking, you want to choose the frame and coordinates so that your shape metric is of the form as close to the flat metric as possible and your scale part as close to a coordinate-independent form as possible.

The last function, 7, is the one that displays results in the form of a list.

1. Initialize[list_] ------------------------------------------------

This function takes a list of three (no more, no less!) elements:

 {list of coordinates, tetrad matrix, metric matrix}

Some pre-defined lists corresponding to some commonly discussed
geometries can be found in ListOfMetrics_2.0.nb. If you want to study
one of the pre-defined geometries, then simply copy/paste the desired defined
list from ListOfMetrics_2.0.nb into Initialize[...] function and
you are good to go (for example, list SchwarzschildSol lets you study Schwarzschild solution).

Alternatively, you can define other metrics, but be sure to define
the coordinates, the tetrad and the metric. Also make sure that all these three elements have compatible dimension corresponding to the dimension of the space!


2. Connections ------------------------------------------------------

This procedure calculates all the connections (see ???.pdf to understand
what exactly does it calculate). It is necessary to call Connections if
you want to calculate the curvatures (3).


3. Curvatures -------------------------------------------------------

This procedure calculates various curvatures. It depends on Connections. It is necessary to call Curvatures if you want to calculate the curvature invariants (4).


4. Invariants -------------------------------------------------------

This one calculates Ricci, Kretschmann and Weyl invariants. It depends on 
Curvatures.


5. UnimodConnections ------------------------------------------------

This calculates parts of connections arrising from the unimodular decomposition.


6. UnimodCurvatures -------------------------------------------------

Calculates parts of curvatures based on parts of connection calculated in 5.


7. DisplayResults ---------------------------------------------------

Creates a menu with lists of everything that the program has calculated.
It classifies the calculated objects according to their kind (connections,
curvatures, traces of curvatures, etc...). You simply have to choose a
category from the drop-down menu, and then click on a triangle to choose
a prticular object which is then displayed as a column of components.

## How to run the program

1. Choose a list corresponding to the desired metric (as explained in 1.
above). copy/paste it into the argument of Initialize[...] and evaluate
that cell - it will give you the form of the metric which you can check 
that is the one you want. (will be updated to display the whole line element)

2. Choose which objects you want to calculate by commenting out (or deleting)
the ones which you are not interested. This is of importance mainly
because of the time consumption that CPU requires for the calculation,
and this time depends on a computer you are running your program on. That
is why Timinig[...] function has been used when caling the above-mentioned
procedures: it will give you the rough idea of time consuption of the
calculation for a specific procedure.

3. Evaluate the notebook and play a game of chess while the calculation
is taking place (couple of minutes tops) :)

4. Once your calculation is complete, it would be useful to save such
>evaluated< notebook under a name which corresponds to your geometric
model - all results will be saved, and you REALLY want the manu with 
list of results to be saved, so you can access it any time in the future.

5. Share your results with your colleagues! Whenever you calculate some
model which is not already in the ListOfMetrics, send me an email with
the results-notebook and the geometric model and I will update the list, 
so that we can have ever-growing database of metrics and curvatures.

6. You are absolutely obliged to share, improve, upgrade, sofisticate
this program and help the growth of the database. ;)

7. Check the link before you want to use your calculator again, improvement
is ongoing.
