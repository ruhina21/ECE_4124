![image](https://github.com/ruhina21/ECE_4124/assets/108121106/8f5b9c2f-9087-4f4b-8b50-7e0f9b328a2f)


# Lab Report-04

## Course no. ECE 4124
## Course Title:  Digital Signal Processing Sessional




## Submitted by:
Name: Ruhina Tabasshum Prome
Roll: 1810005                                               
Department: Electrical and Computer Engineering


## Submitted by:
### Name: Ruhina Tabasshum Prome
### Roll: 1810005                                               
### Department: Electrical and Computer Engineering



### Date of Submission: 22/05/2023

---------------------------------------------------------------------------------------------------------------------------------------------------


# Experimennt No. 04
## Theory
The Z-transform (ZT) is a mathematical tool which is used to convert the difference equations in time domain into the algebraic equations in z-domain.

The Z-transform is a very useful tool in the analysis of a linear shift invariant (LSI) system. An LSI discrete time system is represented by difference equations. To solve these difference equations which are in time domain, they are converted first into algebraic equations in z-domain using the Z-transform, then the algebraic equations are manipulated in z-domain and the result obtained is converted back into time domain using the inverse Z-transform.

The set of points in the z-plane, for which the Z-transform of a discrete-time sequence x(n) converges is called the region of convergence (ROC) of the Z-transform X(z).

The Z-transform will have the below structure, based on Rational Functions : X(z)=P(z)/Q(z)
 
The two polynomials,  P(z) and  Q(z), allow us to find the poles and zeros of the Z-Transform.

Zeros are the values for z where P(z)=0 i.e. the complex frequencies that make the overall gain of the filter transfer function zero.
poles are the value(s) for  z where  Q(z)=0 i.e. the complex frequencies that make the overall gain of the filter transfer function infinite.


### Finding delay in auto-correlation of a function
```m
clc;
close all;
t=0:0.1:40;
x=sin(t);
y=sin(t-5);
h=square(x);
g=square(y);
k=xcorr(x,y);
[val,idx]=max(abs(k));
delay=(idx-1-length(x)+1)/10;
lag=-length(h)+1:length(g)-1;

subplot(3,1,1);
plot(t,h);
title('signal');

subplot(3,1,2);
plot(t,g);
title('delayed signal');

subplot(3,1,3);
plot(lag/10,k);
title('correlated signal');
```
### Finding Z transform of a signal

```m
clc;
x=[1 2 3 4];
y=[1 2 3];
l=length(x);
X=0;
z=sym('z');
for i=0:l-1
X=X+x(i+1)*z^(-i);
end
disp (X)
```

### Mapping zeros and ones in Z-plane 
```m
x=[1 2 3 4];
l=length(x);
X=0;
z=sym('z');
for i=0:l-1
X=X+x(i+1)*z^(-i);
end
disp (X)

a=tf(x,-1);
pzmap(a);
grid on;
```

## Conclusion
Thus we have successfully implemented all the signals in MATLAB. The output was found same as per theory.
