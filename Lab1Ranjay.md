clc;
close all;
clear all;

xn = input('Enter the sequence x(n): '); % Get the sequence from user
ln = length(xn); % Find the length of the sequence
xk = zeros(1, ln); % Initialize an array of the same size as that of the input sequence
ixk = zeros(1, ln); % Initialize an array of the same size as that of the input sequence

% DFT of the sequence
for k = 0:ln-1
    for n = 0:ln-1
        xk(k+1) = xk(k+1) + (xn(n+1) * exp(1i * 2 * pi * k * n / ln)); % Use 1i for imaginary unit
    end
end

% Plotting input sequence
t = 0:ln-1;
subplot(2, 2, 1);
stem(t, xn);
ylabel('Amplitude');
xlabel('Time Index');
title('Input Sequence');

% Find the magnitudes of individual DFT points
magnitude = abs(xk); 

% Plot the magnitude response
subplot(2, 2, 2);
stem(t, magnitude);
ylabel('Amplitude');
xlabel('K');
title('Magnitude Response');

% Find the phases of individual DFT points
phase = angle(xk);

% Plot the phase response
subplot(2, 2, 3);
stem(t, phase);
ylabel('Phase');
xlabel('K');
title('Phase Response');

% IDFT of the sequence
for n = 0:ln-1
    for k = 0:ln-1
        ixk(n+1) = ixk(n+1) + (xk(k+1) * exp(1i * 2 * pi * k * n / ln)); % Use 1i for imaginary unit
    end
end
ixk = ixk / ln; % Normalize the inverse DFT

% Plot the IDFT sequence
subplot(2, 2, 4);
stem(t, ixk);
ylabel('Amplitude');
xlabel('Time Index');
title('IDFT Sequence');
