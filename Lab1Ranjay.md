Laboratory Activity 1: To Find DFT/IDFT of given DT Signal


Name: Ranjay E. Pauya
     
  
  Jercy Baldoza

      
Course and Year : BSCpE - 3

I. OBJECTIVES: 
In this laboratory exercise, the students are expected to: 
    find Discrete Fourier Transform and Inverse Discrete Fourier Transform of given digital signal..

II. MATERIALS: 
   Software: MATLAB 

III. PROCEDURE: 
THEORY: Basic equation to find the DFT of a sequence is given below. 


![image](https://github.com/user-attachments/assets/6a4a34dc-5312-42ec-8155-d890ed6a1abd)

Basic equation to find the IDFT of a sequence is given below. 


![image](https://github.com/user-attachments/assets/b5a77ac3-d7d7-4dc0-8077-dca334633506)

Algorithm:  
Step I: Get the input sequence. 
Step II: Find the DFT of the input sequence using direct equation of DFT.  
Step III: Find the IDFT using the direct equation.  
Step IV: Plot DFT and IDFT of the given sequence using matlab command stem. 
Step V: Display the above outputs. 

Flow chart:


![image](https://github.com/user-attachments/assets/8e8be4e0-9873-4310-a479-f51249235c13)

PROGRAM: 


clc;  
close all;  
clear all;  
xn=input('Enter the sequence x(n)'); %Get the sequence from user  
ln=length(xn); %find the length of the sequence  
xk=zeros(1,ln); %initialize an array of same size as that of input sequence  
ixk=zeros(1,ln); %initialize an array of same size as that of input sequence  
%DFT of the sequence  
%-----------------------------------------------------  
for k=0:ln-1  
for n=0:ln-1  
xk(k+1)=xk(k+1)+(xn(n+1)*exp((i)*2*pi*k*n/ln));  
end  
end  
%------------------------------------------------------  
%Plotting input sequence  
%-----------------------------------------------------  
t=0:ln-1;  
subplot(221);  
stem(t,xn);  
ylabel ('Amplitude');  
xlabel ('Time Index');  
title('Input Sequence');  
%--------------------------------------------------------------- 
magnitude=abs(xk); % Find the magnitudes of individual DFT points  
% plot the magnitude response  
%------------------------------------------------------------  
t=0:ln-1;  
8 
subplot(222);  
stem(t,magnitude);  
ylabel ('Amplitude');  
xlabel ('K');  
title('Magnitude Response');  
%------------------------------------------------------------  
phase=angle(xk); % Find the phases of individual DFT points % plot the magnitude  
sequence  
%------------------------------------------------------------  
t=0:ln-1;  
subplot(223);  
stem(t,phase);  
ylabel ('Phase');  
xlabel ('K');  
title ('Phase Response');  
%------------------------------------------------------------  
%IDFT of the sequence  
%------------------------------------------------------------  
for n=0:ln-1  
for k=0:ln-1  
ixk(n+1)=ixk(n+1)+(xk(k+1)*exp(i*2*pi*k*n/ln));  
end  
end  
ixk=ixk./ln;  
%------------------------------------------------------------  
%code block to plot the input sequence  
%------------------------------------------------------------  
t=0:ln-1;  
subplot(224);  
stem(t,ixk);  
ylabel ('Amplitude');  
xlabel ('Time Index');  
title ('IDFT sequence');  
%------------------------------------------------------  


Output:  


Xn=[1 2 3 4 5]  
Xk = 15,-2.50+3.44i,-2.50+0.81i,-2.49-0.81i,-2.49-3.44i

Output Waveforms:


![image](https://github.com/user-attachments/assets/0030f0a1-4e3d-44c2-8f62-880249efeb72)


Result:


![image](https://github.com/user-attachments/assets/3c1839e6-7683-47eb-ab4f-75b1f7d49ba5)

VIVA QUESTIONS:


1. Define signal, Give Examples for 1-D, 2-D, 3-D signals.


ANSWER:
•	Signal: A signal is a time-varying or space-varying quantity that carries information. It can be represented as a function of one or more independent variables.
o	1-D Signal: A signal that is a function of a single independent variable. For example, a sound wave, where the signal is represented as a function of time, i.e., x(t)x(t)x(t).
o	2-D Signal: A signal that is a function of two independent variables. For example, an image, where the signal is a function of spatial coordinates xxx and yyy, i.e., f(x,y)f(x, y)f(x,y).
o	3-D Signal: A signal that is a function of three independent variables. For example, a video sequence, where the signal is a function of space and time, i.e., f(x,y,t)f(x, y, t)f(x,y,t).

2. Define transform. What is the need for transform?


ANSWER:
•	Transform: A transform is a mathematical operation that converts a signal from one domain to another (e.g., from time domain to frequency domain). This is done to extract useful information about the signal that is easier to analyze or manipulate.
•	Need for Transform: The primary reasons for using transforms are:
o	Simplifying the analysis and processing of signals.
o	Converting signals into a form where specific properties (like frequency content) are more evident.
o	Making it easier to apply filters and perform operations like convolution.

3. Differentiate Fourier transform and discrete Fourier transform.


ANSWER:
•	Fourier Transform (FT):
o	Converts a continuous-time signal (usually aperiodic) into a continuous frequency spectrum.
o	The output is a continuous function of frequency.
o	Applicable to signals defined over continuous time.
•	Discrete Fourier Transform (DFT):
o	Converts a discrete-time signal (usually periodic) into a discrete frequency spectrum.
o	The output is a sequence of complex numbers corresponding to the frequencies present in the signal.
o	Applicable to signals defined at discrete time intervals (sampled signals).

4. Differentiate DFT and DTFT.


ANSWER:
•	Discrete Fourier Transform (DFT):
o	Defined for discrete-time signals with a finite length.
o	Produces a finite number of frequency components.
o	Computed over a finite interval and provides a periodic frequency spectrum.
•	Discrete-Time Fourier Transform (DTFT):
o	Defined for discrete-time signals that can be of infinite length.
o	Produces a continuous frequency spectrum.
o	The DTFT gives a continuous representation of the frequency content of the signal, unlike the DFT which gives a discrete set of frequency bins.

5. Explain the mathematical formula for calculation of DFT.


ANSWER:
The Discrete Fourier Transform (DFT) of a sequence x(n)x(n)x(n) of length NNN is given by:
X(k)=∑n=0N−1x(n)⋅e−j2πNknX(k) = \sum_{n=0}^{N-1} x(n) \cdot e^{-j \frac{2\pi}{N} kn}X(k)=n=0∑N−1x(n)⋅e−jN2πkn 
where:
•	X(k)X(k)X(k) is the DFT of x(n)x(n)x(n) at frequency index kkk.
•	x(n)x(n)x(n) is the input sequence.
•	NNN is the length of the input sequence.
•	e−j2πNkne^{-j \frac{2\pi}{N} kn}e−jN2πkn represents the complex exponential function that provides the frequency components.

6. Explain the mathematical formula for calculation of IDFT.


ANSWER:
The Inverse Discrete Fourier Transform (IDFT) is used to reconstruct the original sequence from its frequency-domain representation. The formula for IDFT is:
x(n)=1N∑k=0N−1X(k)⋅ej2πNknx(n) = \frac{1}{N} \sum_{k=0}^{N-1} X(k) \cdot e^{j \frac{2\pi}{N} kn}x(n)=N1k=0∑N−1X(k)⋅ejN2πkn 
where:
•	x(n)x(n)x(n) is the original sequence.
•	X(k)X(k)X(k) is the DFT of the sequence.
•	NNN is the length of the sequence.
•	ej2πNkne^{j \frac{2\pi}{N} kn}ejN2πkn is the complex exponential function used for the transformation.

7. How to calculate FT for 1-D signal?


ANSWER:
The Fourier Transform (FT) for a 1-D signal x(t)x(t)x(t) is calculated using the following formula:
X(f)=∫−∞∞x(t)⋅e−j2πftdtX(f) = \int_{-\infty}^{\infty} x(t) \cdot e^{-j 2\pi f t} dtX(f)=∫−∞∞x(t)⋅e−j2πftdt 
where:
•	X(f)X(f)X(f) is the frequency-domain representation of the signal.
•	x(t)x(t)x(t) is the time-domain signal.
•	fff is the frequency.
•	The integral is taken over all time values.
For practical purposes, the signal may be sampled, and the FT is approximated using numerical methods.

8. What is meant by magnitude plot, phase plot, power spectrum?


ANSWER:
•	Magnitude Plot: It represents the magnitude of the frequency components of the signal. In the context of the Fourier Transform, it shows how much of each frequency is present in the signal.
Magnitude=∣X(f)∣\text{Magnitude} = |X(f)|Magnitude=∣X(f)∣ 
•	Phase Plot: It shows the phase angle of the frequency components of the signal. It provides information about the shift of each frequency component.
Phase=arg⁡(X(f))\text{Phase} = \arg(X(f))Phase=arg(X(f)) 
•	Power Spectrum: The power spectrum represents the distribution of power (or energy) of a signal with respect to frequency. It is typically the square of the magnitude of the Fourier transform:
P(f)=∣X(f)∣2P(f) = |X(f)|^2P(f)=∣X(f)∣2 

9. Explain the applications of DFT.


ANSWER:
The Discrete Fourier Transform (DFT) has numerous applications, including:
•	Signal Processing: Used to analyze and manipulate signals in various fields like audio, speech, and image processing.
•	Compression: Used in image and audio compression algorithms (e.g., JPEG, MP3).
•	Spectral Analysis: Used to analyze the frequency content of signals.
•	Filtering: Enables efficient filtering of signals by manipulating their frequency components.
•	Pattern Recognition: Used in computer vision and other fields for feature extraction.

10. What are separable transforms?


ANSWER:
•	Separable Transforms: These are transforms that can be broken down into simpler, one-dimensional transforms applied independently along each dimension of a multi-dimensional signal.
o	In 2-D signal processing (e.g., image processing), separable transforms allow you to apply the transform row-by-row and then column-by-column, making computation more efficient.
o	Example: The 2-D Discrete Fourier Transform (DFT) is separable, meaning it can be computed by first taking the 1-D DFT of each row of the image and then taking the 1-D DFT of each column.
