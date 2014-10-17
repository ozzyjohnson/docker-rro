docker-rro
==========

I threw this together to try out [Revolution R](http://mran.revolutionanalytics.com/).

The thing that jumped out at me is [Multithreaded Performance](http://mran.revolutionanalytics.com/documents/rro/open/#intelmkl1). I've fooled with *apply, parallel and segue in the past and anything which promises an innate boost is interesting.

A quick run of the linked [R-benchmark 2.5](http://r.research.att.com/benchmarks/R-benchmark-25.R) pretty cleanly demonstrates the benefits.

Running on my i7 960 desktop.

### R version 3.1.1 (2014-07-10) -- "Sock it to Me":
   R Benchmark 2.5
   ===============
Number of times each test is run__________________________:  3

   I. Matrix calculation
   ---------------------
Creation, transp., deformation of a 2500x2500 matrix (sec):  1.04566666666667 
2400x2400 normal distributed random matrix ^1000____ (sec):  1.27666666666667 
Sorting of 7,000,000 random values__________________ (sec):  0.870999999999999 
2800x2800 cross-product matrix (b = a' * a)_________ (sec):  12.6506666666667 
Linear regr. over a 3000x3000 matrix (c = a \ b')___ (sec):  5.53366666666667 
                      --------------------------------------------
                 Trimmed geom. mean (2 extremes eliminated):  1.94757680093039 

   II. Matrix functions
   --------------------
FFT over 2,400,000 random values____________________ (sec):  0.435000000000007 
Eigenvalues of a 640x640 random matrix______________ (sec):  1.02266666666667 
Determinant of a 2500x2500 random matrix____________ (sec):  4.94333333333333 
Cholesky decomposition of a 3000x3000 matrix________ (sec):  4.35366666666667 
Inverse of a 1600x1600 random matrix________________ (sec):  4.64800000000001 
                      --------------------------------------------
                Trimmed geom. mean (2 extremes eliminated):  2.74548114131991 

   III. Programmation
   ------------------
3,500,000 Fibonacci numbers calculation (vector calc)(sec):  0.708666666666668 
Creation of a 3000x3000 Hilbert matrix (matrix calc) (sec):  0.23199999999999 
Grand common divisors of 400,000 pairs (recursion)__ (sec):  0.98333333333333 
Creation of a 500x500 Toeplitz matrix (loops)_______ (sec):  0.419666666666662 
Escoufier's method on a 45x45 matrix (mixed)________ (sec):  0.5 
                      --------------------------------------------
                Trimmed geom. mean (2 extremes eliminated):  0.529792120787922 


Total time for all 15 tests_________________________ (sec):  39.624 
Overall mean (sum of I, II and III trimmed means/3)_ (sec):  1.41494486551293 
                      --- End of test ---

### Revolution R Open 8.0 beta:
   R Benchmark 2.5
   ===============
Number of times each test is run__________________________:  3

   I. Matrix calculation
   ---------------------
Creation, transp., deformation of a 2500x2500 matrix (sec):  0.993666666666666 
2400x2400 normal distributed random matrix ^1000____ (sec):  1.359 
Sorting of 7,000,000 random values__________________ (sec):  0.840666666666666 
2800x2800 cross-product matrix (b = a' * a)_________ (sec):  0.975666666666668 
Linear regr. over a 3000x3000 matrix (c = a \ b')___ (sec):  0.543666666666667 
                      --------------------------------------------
                 Trimmed geom. mean (2 extremes eliminated):  0.934089891303611 

   II. Matrix functions
   --------------------
FFT over 2,400,000 random values____________________ (sec):  0.397333333333333 
Eigenvalues of a 640x640 random matrix______________ (sec):  0.461666666666666 
Determinant of a 2500x2500 random matrix____________ (sec):  0.327666666666666 
Cholesky decomposition of a 3000x3000 matrix________ (sec):  0.342999999999996 
Inverse of a 1600x1600 random matrix________________ (sec):  0.444000000000003 
                      --------------------------------------------
                Trimmed geom. mean (2 extremes eliminated):  0.392594336527815 

   III. Programmation
   ------------------
3,500,000 Fibonacci numbers calculation (vector calc)(sec):  0.683 
Creation of a 3000x3000 Hilbert matrix (matrix calc) (sec):  0.203666666666668 
Grand common divisors of 400,000 pairs (recursion)__ (sec):  0.941999999999998 
Creation of a 500x500 Toeplitz matrix (loops)_______ (sec):  0.390000000000001 
Escoufier's method on a 45x45 matrix (mixed)________ (sec):  0.400999999999996 
                      --------------------------------------------
                Trimmed geom. mean (2 extremes eliminated):  0.474471241719301 


Total time for all 15 tests_________________________ (sec):  9.30599999999999 
Overall mean (sum of I, II and III trimmed means/3)_ (sec):  0.558274167101361 
                      --- End of test ---
