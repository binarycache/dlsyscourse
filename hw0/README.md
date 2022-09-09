# Homework 0
Public repository and stub/testing code for Homework 0 of 10-714.

# Personal Notes

#### The IDX file format is a simple format for vectors and multidimensional matrices of various numerical types.
Long version:  http://yann.lecun.com/exdb/mnist/
Short version: 

The basic format according to is: big-endian

magic number (4 bytes, with first two bytes always 0)
size in dimension 1, 4 bytes
size in dimension 2, 4 bytes
size in dimension 3, 4 bytes
....
size in dimension N, 4 bytes
data


The third byte of magic number codes the type of the data:

0x08: unsigned byte
0x09: signed byte
0x0B: short (2 bytes)
0x0C: int (4 bytes)
0x0D: float (4 bytes)
0x0E: double (8 bytes)

The fouth byte codes the number of dimensions of the vector/matrix: 1 for vectors, 2 for matrices....


Behaviour
If the storage format indicates that there are more than 2 dimensions, the resulting Matrix accumulates dimensions 2 and higher in the columns. For example, with three dimensions of size n1, n2 and n3, respectively, the resulting Matrix object will have n1 rows and n2×n3 columns.

Reading the uncompressed file train-images-idx3-ubyte available at http://yann.lecun.com/exdb/mnist/ with 60000 images of 28×28 pixel data, will result in a new Matrix object with 60000 rows and 784 (=28×28) columns. Each cell will contain a number in the interval from 0 to 255.

Reading the uncompressed file train-labels-idx1-ubyte with 60000 labels will result in a new Matrix object with 1 row and 60000 columns. Each cell will contain a number in the interval from 0 to 9.
