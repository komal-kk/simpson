# simpson
Simpson 3/8 rule for integration in 3D
import matplotlib.pyplot as plt
import scipy
import scipy.integrate as integrate
import numpy as np
import math
import cmath 
import types
import scipy.stats
import scipy.special as special
from scipy.stats import norm
import matplotlib.mlab as mlab
import scipy.sparse as sp
import scipy.linalg as la



x0=-1
xn=1

y0=-1
yn=1

z0=-1
zn=1

n=10000

h=(abs(xn-x0))/(float)(n);
#print(h)


def fun():
	def fx(x):
		return math.cos(x)

	sx=0

	for i in range(1,n):
		x=x0+i*h
		if(i%3==0):
			sx=sx+2*fx(x)
		else:
			sx=sx+3*fx(x)
		#print(s)
	ax=((3*h/8)*(fx(x0)+fx(xn)+sx))
	print(ax)
	def fxy(y):
		return math.cos(y)*ax
	sy=0

	for i in range(1,n):
		y=y0+i*h
		if(i%3==0):
			sy=sy+2*fxy(y)
		else:
			sy=sy+3*fxy(y)
		#print(s)
	ay=((3*h/8)*(fxy(y0)+fxy(yn)+sy))
	def fxyz(z):
		return math.cos(z)*ay
	sz=0
	print(ay)
	for i in range(1,n):
		z=z0+i*h
		if(i%3==0):
			sz=sz+2*fxyz(z)
		else:
			sz=sz+3*fxyz(z)
		#print(s)
	return((3*h/8)*(fxyz(z0)+fxyz(zn)+sz))

print(fun())
