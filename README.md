# EXP 1 A : COMPUTATION OF DFT USING DIRECT AND FFT

# AIM: 

# To Obtain DFT and FFT of a given sequence in SCILAB. 

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
// DISCRETE FOURIER TRANSFORM 
~~~
clc;
clear;
close;

// Input sequence
xn = [1 2 3 4 3 2 1];
n1 = 0:1:length(xn)-1;

// -------- Plot input sequence --------
subplot(3,1,1);
plot2d3(n1, xn);
xlabel('Time n');
ylabel('Amplitude x[n]');
title('Input Sequence');

// -------- DFT Calculation (Direct Method) --------
j = %i;             // imaginary unit in Scilab
N = length(xn);
Xk = zeros(1, N);

for k = 0:N-1
    for n = 0:N-1
        Xk(k+1) = Xk(k+1) + xn(n+1) * exp((-j*2*%pi*k*n)/N);
    end
end

disp(Xk, "DFT of x[n] = ");

// -------- Magnitude Spectrum --------
K1 = 0:1:length(Xk)-1;
magnitude = abs(Xk);

subplot(3,1,2);
plot2d3(K1, magnitude);
xlabel('Frequency (Hz)');
ylabel('Magnitude (gain)');
title('Magnitude Spectrum');

// -------- Phase Spectrum --------
angle = atan(imag(Xk), real(Xk));   // phase in radians

subplot(3,1,3);
plot2d3(K1, angle);
xlabel('Frequency (Hz)');
ylabel('Phase (radians)');
title('Phase Spectrum');

~~~
# OUTPUT: 

<img width="761" height="713" alt="image" src="https://github.com/user-attachments/assets/10e05543-6e36-41ba-ac0b-99fe217418b5" />

# RESULT: 
 Thus, the Discrete Fourier Transform and Fast Fourier Transform of the given sequence were
 obtained and its magnitude andphasespectrum were plotted
