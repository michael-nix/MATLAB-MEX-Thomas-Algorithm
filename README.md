# General MEX Implementation of Thomas' Algorithm

MLDIVIDE has a great tridiagonal matrix solver for sparse matrices, and there are other implementations of Thomas' algorithm out there (see below), but I needed a faster way to solve tridiagonal systems for complex data; this seems to do the trick. On my system (and R2018b), this is about four times faster than MLDIVIDE or a straight up implementation in MATLAB.

This does use interleaved complex numbers with AVX instructions for complex operations, so to compile for use just put it on your path, type "mex -R2018a 'CFLAGS=-mavx' tdma.c" and it should work.
