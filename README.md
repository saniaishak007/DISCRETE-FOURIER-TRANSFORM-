# EXP 1 A : COMPUTATION OF DFT USING DIRECT AND FFT

# AIM: 

To Obtain DFT and FFT of a given sequence in SCILAB. 

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
// DISCRETE FOURIER TRANSFORM 
```
clc;
clear;
xn=[1 2 3 4 4 3 2 1];
n1=0:1:length(xn)-1;
subplot(3,1,1);
plot2d3(n1,xn);
xlabel('Time n');
ylabel('Amplitude xn');
title('Input Sequence');
j=sqrt(-1);
N=length(xn);
Xk=zeros(1,N);
for k=0:N-1
for n=0:N-1
Xk(k+1)=Xk(k+1)+xn(n+1)*exp((-j*2*%pi*k*n)/N);
end
end
disp(Xk)
K1=0:1:length(Xk)-1;
magnitude=abs(Xk)
subplot(3,1,2);
plot2d3(K1,magnitude);
xlabel('frequency(Hz)');
ylabel('magnitude(gain)');
title('magnitude spectrum');
angle = atan(imag(Xk),real(Xk))
subplot(3,1,3);
plot2d3(K1,angle);
xlabel('frequency(Hz)');
ylabel('Phase');
title('Phase spectrum');
```
# CALCULATION:
```
x = 1. 2. 3. 4. 4. 3. 2. 1.
FFT of x(n) is X(k)= 20. - 5.8284271 - 2.4142136i 1.546D-17 - 2.220D-16i - 0.1715729 -
0.4142136i - 2.449D-16i - 0.1715729 + 0.4142136i - 6.708D-15 - 2.220D-16i - 5.8284271 +
2.4142136i
magnitude of X(k)
magnitude = 20. 6.3086441 2.226D-16 0.4483415 2.449D-16 0.4483415
6.711D-15 6.3086441
Angle of X(k)
angle = 0. - 2.7488936 - 1.5012702 - 1.9634954 - 1.5707963 1.9634954 -
3.1085019 2.7488936
```
//DFT USING FFT
```
clear;
clc;
close;
xn = [1 2 3 4 4 3 2 1]
n1=0:1:length(xn)-1;
subplot(2,2,1);
plot2d3(n1,xn);
xlabel('Time n');
ylabel('Amplitude');
title('Input Sequence');
Xk = fft(xn);
K1=0:1:length(Xk)-1;
magnitude=abs(Xk)
subplot(2,2,2);
plot2d3(K1,magnitude);
xlabel('frequency(Hz)');
ylabel('magnitude(gain)');
title('magnitude spectrum');
angle = atan(imag(Xk),real(Xk))
subplot(2,2,3);
plot2d3(K1,angle);
xlabel('frequency(Hz)');
ylabel('Phase');
title('Phase spectrum')
y= ifft(Xk)
n2=0:1:length(y)-1;
subplot(2,2,4)
plot2d3(n2,y)
xlabel('Time n');
ylabel('Amplitude');
title('Inverse FFT OF X(K)');
```
# CALCULATION:
```
xn = 1. 2. 3. 4. 4. 3. 2. 1.
magnitude = 20. 6.3086441 0. 0.4483415 0. 0.4483415 0. 6.3086441
angle = 0. - 2.7488936 0. - 1.9634954 0. 1.9634954 0. 2.7488936
y = 1. 2. 3. 4. 4. 3. 2. 1.
```

# OUTPUT: 

<img width="692" height="464" alt="image" src="https://github.com/user-attachments/assets/32c32b3f-0d12-40cd-bc09-d07aac098c64" />

<img width="475" height="331" alt="image" src="https://github.com/user-attachments/assets/ff437018-5f3e-4c2b-84ca-4d2f6839810b" />


# RESULT: 
Thus, the Discrete Fourier Transform of the given sequence was
obtained and its magnitude and phase spectrum were plotted.
