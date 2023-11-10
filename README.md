# assigment 1

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>hod assignment</title>
</head>
<body>
    <h1 style="color:red;">Contour plots</h1>
    <p style="color: blue;">A contour plot is a graphical method to visualize the 3-D surface by plotting constant Z slices called contours in a 2-D format. The contour plot is an alternative to a 3-D surface plot</p>
    <p style="color: blue;">The contour plot is formed by:

        1)Vertical axis: Independent variable 2
        2)Horizontal axis: Independent variable 1
        3)Lines: iso-response values, can be calculated with the help (x,y)</p>
        <h2 style="color: blue;">The independent variable usually restricted to a regular grid. The actual techniques for determining the correct iso-response values are rather complex and almost always computer-generated.</h2>
        <h2 style="color: blue;">The contour plot is used to depict the change in Z values as compared to X and Y values. If the data (or function) do not form a regular grid, you typically need to perform a 2-D interpolation to form a regular grid.</h2>
        <h2 style="color: blue;">For one variable data, a run sequence/ histogram is considered necessary. For two-variable data, a scatter plot is considered necessary. The contour plots can also polar co-ordinates (r,theta) instead of traditional rectangular (x, y, z) coordinates. </h2>
        <h2 style="color: red;">Types of Contour Plot:</h2>
        <p style="color: blue;"><b>*Rectangular Contour plot:</b> A projection of 2D-plot in 2D-rectangular canvas. It is the most common form of the contour plot.</p>
        <p style="color: blue;"><b>*Polar contour </b>plot: Polar contour plot is plotted by using the polar coordinates r and theta. The response variable here is the collection of values generated while passing r and theta into the given function, where r is the distance from origin and theta is the angle from the positive x axis.</p>
        <p style="color: blue;"><b>*Ternary contour plot:</b> Ternary contour plot is used to represent the relationship between 3 explanatory variables and the response variable in the form of a filled triangle.</p>
        <h2 style="color: red;">Contour plot can be plotted in different programming languages:</h2>
        <p style="color: blue;"><b>*Python/ Matplotlib:</b> Contour plot can be plotted using plt.contour or plt.contourf functions, where plt is matplotlib.pyplot. The difference between these two that plot.contour generates hollow contour plot, the plt.contourf generated filled.</p>
        <p style="color: blue;"><b>*Matlab:</b> functions such as contourf (2d-plot) and contour3 (3D-contour) can be used for contour plotting</p>
        <p style="color: blue;"><b>*R:</b> can create a contour plot with filled.contour functions in R.</p>
        <h3 style="color: brown;">Implementations:</h3>
        <p style="color: gray;"><b>*Rectangular Contour Plot:</b> Below is the sample code for plotting rectangular contour plots in Python and matplotlib.
        </p>
        <center><p style="color: red;">Python 3</p></center>
        <h4 style="color: aquamarine;">#  imports <br>

            import numpy as np <br>

            import matplotlib.pyplot as plt <br>
            # define a function <br>

def func(x, y): <br>

    return np.sin(x) ** 2 +  np.cos(y) **2<br>
# generate 50 values b/w 0 a5 <br>

x = np.linspace(0, 5, 50) <br>
y = np.linspace(0, 5, 50) <br>


# Generate combination of grids<br> 

X, Y = np.meshgrid(x, y) <br>

Z = func(X, Y)<br> 


# Draw rectangular contour plot<br> 

plt.contour(X, Y, Z, cmap='gist_rainbow_r');<br> 

            # </h4>
            <img src="c:\Users\DELL\Pictures\eyee\eyee.jpg" alt="">
            <center><h1 style="color: blueviolet;">rectangular contour plot</h1></center>

            <p style="color: gray;"><b>*polar Contour plot:</b> For plotting polar contour plot we need to define first r and theta. Below is the sample code for plotting polar contour plots using matplotlib subplots.</p>
            <center><h3 style="color: red;">python 3</h3></center>
            <h5 style="color: bisque;"># generate r and theta arrays <br>

                rad_arr = np.radians(np.linspace(0, 360, 20))<br> 

                r_arr = np.arange(0, 1, .1) <br>
                # define function <br>

                def func(r, theta):<br> 

                  return r * np.sin(theta) <br> 



                r, theta = np.meshgrid(r_arr, rad_arr)<br> 
                # get the values of response variables <br>

                values = func(r,theta) <br>


                # plot the polar coordinates<br> 

                fig, ax = plt.subplots(subplot_kw=dict<br>(projection='polar')) <br>

                ax.contourf(theta, r, values, cmap='Spectral_r') <br>


                plt.show()</h5>

                <img src="c:\Users\DELL\Pictures\eyee\eye.jpg" alt="">
                <center><h1 style="color: red;">polar contour plot</h1></center>

                <p style="color:rebeccapurple;"><b>*Ternary Contour Plot:</b> Matplotlib does not provide a definitive API for plotting Ternary Contour plot, however, there are many other package which does that. IN this example, we will be using Plotly library.</p>
                <center><h3 style="color: red;">python 3</h3></center>

                <h5 style="color: aquamarine;"># install & import plotly <br>

                    ! pip install plotly<br> 

                    import plotly.figure_factory as ff<br> 


                    # Define variables <br>

                    a = np.array([0. , 0. , 0., 0., 1./3, 1./3, 1./3, 2./3, 2./3, 1.]) <br>

                    b = np.array([0., 1./3, 2./3, 1., 0., 1./3, 2./3, 0., 1./3, 0.]) <br>

                    c = 1 - a - b <br>
                    # Define function that generates response variable <br>

                    func = (a - 0.02) * b * (a - 0.5) * (b - 0.4) * (c - 1)**2<br>


                    # plot ternary contour <br>

                    fig = ff.create_ternary_contour(np.array([a, b, c]), func, <br>

                                                    pole_labels=['a', 'b', 'c'], <br>

                                                    interp_mode='cartesian', <br>

                                                    colorscale='Viridis',) <br>
                    fig.show() 


                    <img src="c:\Users\DELL\Pictures\eyee\eyeee.jpg" alt="">
                    <center><h1 style="color: red;">ternary contour plot</h1></center>



                    </h5>
                    <body background="C:\Users\DELL\Downloads\b946af07-bb11-43ba-b397-d2f4f877713b.jpg">

                    </body>




<h1 style="color: blue;">NAME:dhanush.b</h1>
<h1 style="color: yellowgreen;">CLASS:AIDS</h1>
<h1 style="color: red;">ROLL NO:22904</h1>
<h1 style="color: green;">REG NO:510622243004</h1>
<h1 style="color: yellow;">TO:hod</h1>

</body>
</html>
2 comments on commit 5b9a509
@Userdhanush
Owner
Author
Userdhanush commented on 5b9a509 14 minutes ago
first file

@Userdhanush
Owner
Author
Userdhanush commented on 5b9a509 14 minutes ago
file file

@Userdhanush
Comment
Leave a comment
 You’re receiving notifications because you’re watching this repository.
