### Installing dedalus on Ubuntu 18.04

dedalus is a nifty Python package for numerically solving PDE's.
It saves a lot of coding time, and enables you to vary the problem setup without doing a total rewrite.
This comes at the price of a lot of dependancies. Here are the steps I had to take to get dedalus installed on Ubuntu 18.04.

```bash
$ sudo apt install libopenmpi2
$ sudo apt install libopenmpi-dev
$ pip install mpi4py
$ sudo apt install libhdf5-openmpi-dev
$ pip install h5py
```

Then you'll need to install fttw3. If building from source, be sure to use the --enable-mpi option with ./configure, as dedalus depends on it.
Also, in order for the library to compile properly, you need the --enable-shared option with configure, and you need to do
```
sudo make CFLAGS=-fPIC
```
