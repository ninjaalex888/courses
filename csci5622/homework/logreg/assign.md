Logistic Regression
=

Due: 16. September (11:55pm)

Overview
--------

In this homework you'll implement a stochastic gradient ascent for
logistic regression and you'll apply it to the task of determining
whether documents are talking about hockey or baseball.

![Hockey and Baseball: Are they really that different?](baseball_hockey.jpg "Two sports I know nothing about")

This will be slightly more difficult than the last homework (the
difficulty will slowly ramp upward).  You should not use any libraries that implement any of the functionality of logistic regression
for this assignment; logistic regression is implemented in scikit
learn, but you should do everything by hand now.  You'll be able to
use library implementations of logistic regression in the future. 

You'll turn in your code and analysis on Moodle.  This assignment is worth 25
points.

What you have to do
----

Coding (20 points):

1. Understand how the code is creating feature vectors (this will help you code the solution and to do the later analysis).  You don't actually need to write any code for this, however.
2. Modify the _sg update_ function to perform non-regularized updates.
3. After that works, modify the _sg update_ function to perform regularized updates. 
4. You'll likely need to write some code to get the best/worst features (for the analysis portion).

**NOTES**: 
- You should not regularize the bias term. 
- You should implement Lazy Sparse Regularization and only update non-zero features. (See discussion [here](https://nbviewer.jupyter.org/url/grandmaster.colorado.edu/~cketelsen/files/csci5622/notebooks/lesson04/lesson04NBKAnswers.ipynb?flush_cache=true)) 

Analysis (5 points):

1. How did the learning rate affect the convergence of your SGA implementation?
2. What was your stopping criterion and how many passes over the data did you need to complete before stopping?
3. What words are the best predictors of each class?  How (mathematically) did you find them?
4. What words are the poorest predictors of classes?  How (mathematically) did you find them?

Extra credit:

1. (max 2pts) Use a schedule to update the learning rate.
    - Modify the eta_schedule function 
    - Pass it into the LogReg constructor 
    - Support it in your _sg update_
    - Show the effect in your analysis document
1.  (max 2pts) Use document frequency (provided in the vocabulary file) to modify the feature values to [tf-idf](https://en.wikipedia.org/wiki/Tf%E2%80%93idf).
    - Modify the Example to store the df vector
    - With the appropriate flag, use the df and x vectors to implement tf-idf in the update
    - Show the effect in your analysis document

Caution: When implementing extra credit, make sure your implementation of the
regular algorithms doesn't change.

What to turn in
-

1. Submit your _logreg.py_ file (include your name at the top of the source)
1. Submit your _analysis.pdf_ file
    - no more than one page
    - pictures are better than text
    - include your name at the top of the PDF

Unit Tests
=

I've provided unit tests based on the example that we worked through
in class.  Before running your code on read data, make sure it passes
all of the unit tests.

```
MacBook-Air:logreg cketelsen$ python tests.py 
[ 0.  0.  0.  0.  0.]
[ 1.  4.  3.  1.  0.]
F[ 0.  0.  0.  0.  0.]
[ 1.  4.  3.  1.  0.]
F
======================================================================
FAIL: test_reg (__main__.TestLogReg)
----------------------------------------------------------------------
Traceback (most recent call last):
  File "tests.py", line 37, in test_reg
    self.assertAlmostEqual(w[0], .5)
AssertionError: 0.0 != 0.5 within 7 places

======================================================================
FAIL: test_unreg (__main__.TestLogReg)
----------------------------------------------------------------------
Traceback (most recent call last):
  File "tests.py", line 18, in test_unreg
    self.assertAlmostEqual(w[0], .5)
AssertionError: 0.0 != 0.5 within 7 places

----------------------------------------------------------------------
Ran 2 tests in 0.005s

FAILED (failures=2)
```

Example
-

This is an example of what your runs should look like:
```
MacBook-Air:logreg cketelsen$ python logreg.py
Read in 1064 train and 133 test
Update 1    TP -784.773313  HP -97.029309   TA 0.492481 HA 0.548872
Update 6    TP -1011.819421 HP -137.626879  TA 0.506579 HA 0.436090
Update 11   TP -722.767332  HP -102.127993  TA 0.562030 HA 0.533835
Update 16   TP -1778.961499 HP -200.427139  TA 0.516917 HA 0.548872
Update 21   TP -1733.891542 HP -203.196086  TA 0.539474 HA 0.563910
Update 26   TP -872.339461  HP -109.055027  TA 0.620301 HA 0.676692
Update 31   TP -990.361704  HP -122.754359  TA 0.607143 HA 0.631579
Update 36   TP -1026.392000 HP -154.736421  TA 0.628759 HA 0.571429
Update 41   TP -738.129181  HP -110.846545  TA 0.685150 HA 0.646617
Update 46   TP -824.705062  HP -127.247866  TA 0.671992 HA 0.631579
Update 51   TP -648.078251  HP -91.395031   TA 0.718985 HA 0.699248
Update 56   TP -688.719579  HP -81.635583   TA 0.700188 HA 0.676692
Update 61   TP -642.539382  HP -78.281907   TA 0.710526 HA 0.691729
Update 66   TP -637.495965  HP -77.811552   TA 0.719925 HA 0.684211
Update 71   TP -573.508620  HP -84.597398   TA 0.746241 HA 0.706767
Update 76   TP -717.941182  HP -116.006670  TA 0.701128 HA 0.616541
Update 81   TP -529.627019  HP -77.149733   TA 0.774436 HA 0.751880
Update 86   TP -531.472742  HP -79.566616   TA 0.775376 HA 0.751880
Update 91   TP -519.578992  HP -76.696748   TA 0.792293 HA 0.759398
Update 96   TP -506.234606  HP -78.449446   TA 0.795113 HA 0.759398
Update 101  TP -518.924663  HP -84.527355   TA 0.784774 HA 0.721805
Update 106  TP -528.144934  HP -86.707245   TA 0.783835 HA 0.714286
Update 111  TP -563.051426  HP -96.626025   TA 0.783835 HA 0.706767
Update 116  TP -542.715526  HP -67.359718   TA 0.767857 HA 0.759398
Update 121  TP -547.057952  HP -66.470343   TA 0.759398 HA 0.766917
Update 126  TP -530.863907  HP -65.208550   TA 0.774436 HA 0.789474
Update 131  TP -512.835691  HP -65.395342   TA 0.789474 HA 0.804511
Update 136  TP -645.590877  HP -73.231687   TA 0.738722 HA 0.766917
Update 141  TP -527.321236  HP -61.011687   TA 0.781015 HA 0.819549
Update 146  TP -506.770544  HP -62.252280   TA 0.789474 HA 0.796992
Update 151  TP -508.571275  HP -68.103210   TA 0.798872 HA 0.774436
Update 156  TP -480.108831  HP -61.472383   TA 0.810150 HA 0.819549
Update 161  TP -477.827241  HP -60.656289   TA 0.809211 HA 0.819549
Update 166  TP -474.070439  HP -60.302379   TA 0.808271 HA 0.827068
Update 171  TP -469.784846  HP -63.261382   TA 0.816729 HA 0.812030
Update 176  TP -457.073390  HP -59.453492   TA 0.827068 HA 0.827068
Update 181  TP -444.911340  HP -62.489235   TA 0.835526 HA 0.804511
Update 186  TP -425.814020  HP -59.035132   TA 0.845865 HA 0.819549
Update 191  TP -434.137001  HP -67.736299   TA 0.844925 HA 0.812030
Update 196  TP -520.389296  HP -88.525031   TA 0.795113 HA 0.699248
Update 201  TP -518.020472  HP -88.236182   TA 0.796992 HA 0.699248
Update 206  TP -532.123818  HP -90.719871   TA 0.795113 HA 0.684211
Update 211  TP -454.557149  HP -75.264255   TA 0.832707 HA 0.774436
Update 216  TP -447.743034  HP -73.845935   TA 0.838346 HA 0.774436
Update 221  TP -431.224954  HP -71.481892   TA 0.851504 HA 0.774436
Update 226  TP -416.097210  HP -68.510129   TA 0.857143 HA 0.789474
Update 231  TP -410.322188  HP -67.162858   TA 0.856203 HA 0.789474
Update 236  TP -423.261147  HP -69.606406   TA 0.847744 HA 0.796992
Update 241  TP -471.084858  HP -81.162048   TA 0.828008 HA 0.729323
Update 246  TP -430.829858  HP -70.610690   TA 0.841165 HA 0.789474
Update 251  TP -424.328951  HP -68.973180   TA 0.846805 HA 0.804511
Update 256  TP -464.014726  HP -57.974944   TA 0.833647 HA 0.804511
Update 261  TP -460.423117  HP -57.696397   TA 0.835526 HA 0.804511
Update 266  TP -400.403773  HP -56.637774   TA 0.857143 HA 0.819549
Update 271  TP -394.420658  HP -57.924602   TA 0.859962 HA 0.812030
Update 276  TP -380.555011  HP -54.896590   TA 0.869361 HA 0.834586
Update 281  TP -372.839040  HP -56.140188   TA 0.870301 HA 0.796992
Update 286  TP -375.197179  HP -57.961641   TA 0.873120 HA 0.827068
Update 291  TP -366.173113  HP -55.160286   TA 0.877820 HA 0.834586
Update 296  TP -366.393474  HP -55.484039   TA 0.875940 HA 0.842105
Update 301  TP -368.001243  HP -54.074115   TA 0.869361 HA 0.834586
Update 306  TP -647.063224  HP -65.288608   TA 0.767857 HA 0.744361
Update 311  TP -592.881206  HP -59.504885   TA 0.794173 HA 0.774436
Update 316  TP -596.537153  HP -60.266553   TA 0.792293 HA 0.774436
Update 321  TP -393.031976  HP -47.349003   TA 0.863722 HA 0.834586
Update 326  TP -424.991277  HP -47.105473   TA 0.858083 HA 0.842105
Update 331  TP -337.473402  HP -46.508455   TA 0.875000 HA 0.894737
Update 336  TP -339.276629  HP -44.191333   TA 0.879699 HA 0.887218
Update 341  TP -340.149033  HP -44.222809   TA 0.877820 HA 0.879699
Update 346  TP -322.651623  HP -45.094370   TA 0.882519 HA 0.894737
Update 351  TP -322.331923  HP -47.056861   TA 0.889098 HA 0.894737
Update 356  TP -321.754809  HP -45.483047   TA 0.884398 HA 0.902256
Update 361  TP -325.765084  HP -47.348692   TA 0.886278 HA 0.887218
Update 366  TP -319.416347  HP -45.889204   TA 0.884398 HA 0.887218
Update 371  TP -310.706644  HP -44.475068   TA 0.895677 HA 0.887218
Update 376  TP -308.122823  HP -42.908095   TA 0.895677 HA 0.894737
Update 381  TP -300.547234  HP -40.242349   TA 0.895677 HA 0.894737
Update 386  TP -292.507620  HP -39.270480   TA 0.903195 HA 0.887218
Update 391  TP -286.258189  HP -39.420959   TA 0.906015 HA 0.902256
Update 396  TP -287.823738  HP -38.599445   TA 0.906955 HA 0.894737
Update 401  TP -305.614120  HP -39.371740   TA 0.900376 HA 0.864662
Update 406  TP -731.341376  HP -126.021619  TA 0.796053 HA 0.736842
Update 411  TP -714.774217  HP -123.144083  TA 0.801692 HA 0.729323
Update 416  TP -589.205644  HP -100.909676  TA 0.828947 HA 0.774436
Update 421  TP -613.052785  HP -107.232560  TA 0.825188 HA 0.781955
Update 426  TP -455.366004  HP -74.905268   TA 0.853383 HA 0.812030
Update 431  TP -420.796823  HP -68.956776   TA 0.852444 HA 0.812030
Update 436  TP -453.282602  HP -72.795560   TA 0.855263 HA 0.834586
Update 441  TP -450.239990  HP -72.367978   TA 0.854323 HA 0.834586
Update 446  TP -459.019632  HP -73.696419   TA 0.858083 HA 0.827068
Update 451  TP -456.443252  HP -72.034943   TA 0.852444 HA 0.819549
Update 456  TP -494.126042  HP -80.188995   TA 0.856203 HA 0.804511
Update 461  TP -510.626196  HP -82.647568   TA 0.853383 HA 0.796992
Update 466  TP -549.294061  HP -91.044609   TA 0.844925 HA 0.759398
Update 471  TP -493.169248  HP -81.257396   TA 0.855263 HA 0.796992
Update 476  TP -436.426600  HP -70.508494   TA 0.861842 HA 0.827068
Update 481  TP -400.546816  HP -65.128817   TA 0.868421 HA 0.827068
Update 486  TP -413.516148  HP -67.812409   TA 0.867481 HA 0.834586
Update 491  TP -413.918667  HP -67.809902   TA 0.865602 HA 0.834586
Update 496  TP -330.659060  HP -51.584472   TA 0.876880 HA 0.842105
Update 501  TP -313.929162  HP -53.131584   TA 0.885338 HA 0.842105
Update 506  TP -317.133660  HP -54.654180   TA 0.888158 HA 0.842105
Update 511  TP -307.999490  HP -52.505646   TA 0.885338 HA 0.849624
Update 516  TP -347.276236  HP -59.668658   TA 0.884398 HA 0.834586
Update 521  TP -306.689960  HP -53.240185   TA 0.886278 HA 0.842105
Update 526  TP -307.049750  HP -53.585948   TA 0.887218 HA 0.842105
Update 531  TP -277.590990  HP -49.303664   TA 0.895677 HA 0.842105
Update 536  TP -275.713138  HP -50.732407   TA 0.906955 HA 0.849624
Update 541  TP -267.654241  HP -47.242745   TA 0.902256 HA 0.834586
Update 546  TP -269.283357  HP -47.381481   TA 0.902256 HA 0.834586
Update 551  TP -288.061448  HP -55.120505   TA 0.904135 HA 0.842105
Update 556  TP -289.010249  HP -55.540275   TA 0.905075 HA 0.842105
Update 561  TP -286.543704  HP -55.178725   TA 0.906955 HA 0.842105
Update 566  TP -276.918328  HP -54.175077   TA 0.909774 HA 0.842105
Update 571  TP -275.266718  HP -53.849356   TA 0.908835 HA 0.842105
Update 576  TP -277.951396  HP -54.791283   TA 0.908835 HA 0.842105
Update 581  TP -267.068183  HP -53.704505   TA 0.908835 HA 0.842105
Update 586  TP -249.946572  HP -46.784131   TA 0.915414 HA 0.819549
Update 591  TP -248.578831  HP -46.701342   TA 0.913534 HA 0.842105
Update 596  TP -243.959416  HP -46.540302   TA 0.914474 HA 0.842105
Update 601  TP -242.676215  HP -44.364231   TA 0.906955 HA 0.842105
Update 606  TP -241.827717  HP -44.299548   TA 0.908835 HA 0.842105
Update 611  TP -239.532871  HP -43.791678   TA 0.910714 HA 0.842105
Update 616  TP -229.517861  HP -43.702759   TA 0.921992 HA 0.857143
Update 621  TP -225.474249  HP -43.319282   TA 0.925752 HA 0.857143
Update 626  TP -229.062185  HP -44.131819   TA 0.927632 HA 0.864662
Update 631  TP -226.635879  HP -43.013458   TA 0.925752 HA 0.864662
Update 636  TP -225.437236  HP -42.699302   TA 0.925752 HA 0.864662
Update 641  TP -225.904292  HP -43.031701   TA 0.927632 HA 0.864662
Update 646  TP -223.246820  HP -42.559244   TA 0.925752 HA 0.864662
Update 651  TP -222.700526  HP -42.439148   TA 0.928571 HA 0.864662
Update 656  TP -222.722059  HP -42.583771   TA 0.928571 HA 0.864662
Update 661  TP -281.322162  HP -43.377656   TA 0.904135 HA 0.804511
Update 666  TP -365.101072  HP -54.040243   TA 0.860902 HA 0.789474
Update 671  TP -218.123627  HP -39.663130   TA 0.921053 HA 0.857143
Update 676  TP -209.704211  HP -37.760275   TA 0.921992 HA 0.879699
Update 681  TP -201.668429  HP -37.163618   TA 0.929511 HA 0.887218
Update 686  TP -199.254202  HP -36.934058   TA 0.930451 HA 0.887218
Update 691  TP -198.658361  HP -36.835035   TA 0.931391 HA 0.894737
Update 696  TP -199.669053  HP -36.859867   TA 0.931391 HA 0.887218
Update 701  TP -200.746204  HP -37.067692   TA 0.930451 HA 0.879699
Update 706  TP -201.525502  HP -37.179001   TA 0.931391 HA 0.879699
Update 711  TP -201.673805  HP -37.216659   TA 0.929511 HA 0.879699
Update 716  TP -199.445188  HP -37.105272   TA 0.929511 HA 0.879699
Update 721  TP -199.256234  HP -37.170147   TA 0.929511 HA 0.879699
Update 726  TP -211.605289  HP -38.013420   TA 0.926692 HA 0.864662
Update 731  TP -222.191596  HP -36.993143   TA 0.917293 HA 0.864662
Update 736  TP -221.537604  HP -36.748665   TA 0.918233 HA 0.864662
Update 741  TP -246.398766  HP -39.083169   TA 0.904135 HA 0.834586
Update 746  TP -189.339091  HP -39.232028   TA 0.930451 HA 0.872180
Update 751  TP -187.309716  HP -39.190439   TA 0.933271 HA 0.872180
Update 756  TP -183.072416  HP -39.562462   TA 0.933271 HA 0.872180
Update 761  TP -182.831653  HP -39.745906   TA 0.932331 HA 0.872180
Update 766  TP -178.452533  HP -42.148127   TA 0.938910 HA 0.887218
Update 771  TP -177.241145  HP -41.667510   TA 0.938910 HA 0.887218
Update 776  TP -174.779804  HP -41.234422   TA 0.944549 HA 0.887218
Update 781  TP -176.277105  HP -41.512446   TA 0.940789 HA 0.887218
Update 786  TP -179.732178  HP -42.471562   TA 0.939850 HA 0.894737
Update 791  TP -175.962642  HP -41.516582   TA 0.945489 HA 0.909774
Update 796  TP -173.308043  HP -40.777019   TA 0.944549 HA 0.917293
Update 801  TP -173.995732  HP -41.054263   TA 0.944549 HA 0.917293
Update 806  TP -179.777250  HP -44.067683   TA 0.939850 HA 0.902256
Update 811  TP -172.531646  HP -42.413536   TA 0.941729 HA 0.917293
Update 816  TP -169.641926  HP -41.807964   TA 0.945489 HA 0.917293
Update 821  TP -173.993326  HP -42.071138   TA 0.943609 HA 0.917293
Update 826  TP -187.497428  HP -44.028831   TA 0.936090 HA 0.902256
Update 831  TP -184.617046  HP -43.242932   TA 0.940789 HA 0.902256
Update 836  TP -197.764769  HP -45.849594   TA 0.931391 HA 0.887218
Update 841  TP -204.799995  HP -47.834826   TA 0.937030 HA 0.879699
Update 846  TP -204.946643  HP -47.864765   TA 0.937030 HA 0.879699
Update 851  TP -202.062023  HP -47.165404   TA 0.936090 HA 0.879699
Update 856  TP -169.105768  HP -41.970383   TA 0.946429 HA 0.902256
Update 861  TP -168.595586  HP -40.046166   TA 0.946429 HA 0.872180
Update 866  TP -164.762256  HP -39.626914   TA 0.948308 HA 0.887218
Update 871  TP -160.769793  HP -39.285828   TA 0.953008 HA 0.894737
Update 876  TP -160.049262  HP -39.644025   TA 0.952068 HA 0.894737
Update 881  TP -159.624532  HP -39.651528   TA 0.951128 HA 0.894737
Update 886  TP -159.130907  HP -39.529600   TA 0.952068 HA 0.894737
Update 891  TP -159.120370  HP -38.868996   TA 0.951128 HA 0.887218
Update 896  TP -153.208052  HP -37.467234   TA 0.951128 HA 0.894737
Update 901  TP -153.418686  HP -37.207869   TA 0.952068 HA 0.902256
Update 906  TP -150.251963  HP -35.433819   TA 0.954887 HA 0.909774
Update 911  TP -157.828842  HP -36.863874   TA 0.952068 HA 0.924812
Update 916  TP -152.206975  HP -35.730176   TA 0.953947 HA 0.917293
Update 921  TP -151.730390  HP -35.486676   TA 0.953008 HA 0.924812
Update 926  TP -151.060222  HP -35.336081   TA 0.953008 HA 0.917293
Update 931  TP -148.612508  HP -35.166795   TA 0.953947 HA 0.909774
Update 936  TP -141.432263  HP -34.092393   TA 0.958647 HA 0.894737
Update 941  TP -137.427662  HP -35.658593   TA 0.957707 HA 0.909774
Update 946  TP -136.479051  HP -32.396565   TA 0.961466 HA 0.909774
Update 951  TP -146.192443  HP -32.909057   TA 0.957707 HA 0.894737
Update 956  TP -141.011705  HP -32.751713   TA 0.962406 HA 0.894737
Update 961  TP -143.155927  HP -32.281370   TA 0.957707 HA 0.894737
Update 966  TP -149.693322  HP -32.370375   TA 0.957707 HA 0.894737
Update 971  TP -234.299127  HP -41.093451   TA 0.913534 HA 0.819549
Update 976  TP -235.926118  HP -41.248726   TA 0.911654 HA 0.819549
Update 981  TP -234.098253  HP -41.121300   TA 0.913534 HA 0.819549
Update 986  TP -190.096212  HP -35.731700   TA 0.932331 HA 0.857143
Update 991  TP -125.908772  HP -29.593233   TA 0.964286 HA 0.917293
Update 996  TP -129.455382  HP -29.481803   TA 0.961466 HA 0.917293
Update 1001 TP -125.818356  HP -29.248682   TA 0.966165 HA 0.917293
Update 1006 TP -125.828875  HP -29.308350   TA 0.966165 HA 0.917293
Update 1011 TP -123.280222  HP -29.637264   TA 0.966165 HA 0.917293
Update 1016 TP -117.074925  HP -30.060078   TA 0.966165 HA 0.924812
Update 1021 TP -116.003785  HP -30.190768   TA 0.967105 HA 0.924812
Update 1026 TP -114.255184  HP -31.214400   TA 0.969925 HA 0.924812
Update 1031 TP -114.343308  HP -31.085326   TA 0.969925 HA 0.924812
Update 1036 TP -114.395224  HP -30.827217   TA 0.969925 HA 0.924812
Update 1041 TP -114.558548  HP -30.790052   TA 0.970865 HA 0.924812
Update 1046 TP -114.015824  HP -31.287454   TA 0.970865 HA 0.924812
Update 1051 TP -114.308296  HP -31.041163   TA 0.969925 HA 0.924812
Update 1056 TP -115.552797  HP -30.647346   TA 0.967105 HA 0.917293
Update 1061 TP -113.656177  HP -30.890384   TA 0.970865 HA 0.924812

```

Hints
-

1.  As with the previous assignment, make sure that you debug on small
    datasets first (I've provided _toy text_ in the data directory to get you started).
1.  Certainly make sure that you do the unregularized version first
    and get it to work well.
1.  Use numpy functions whenever you can to make the computation faster.


