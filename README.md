# FIR-FILTER-DESIGN
# EXP 4 d: Design-of-FIR-Digital-Filter-using-Blackman-Window

## AIM 1:  To perform Design-of-LOWPASS FIR-Digital-Filter-using-Blackman-Window using SCILAB.

## APPARATUS REQUIRED: 
PC installed with SCILAB. 

## PROGRAM:
```
clc ; 
close ; 
M=input('Enter the Odd Filter Length ='); 
Wc=input('Enter the Digital Cut off frequency ='); 
alpha= (M -1)/2 // Center Value 
for n = 1:M 
if (n ==alpha+1) 
hd(n) = Wc/ %pi ; else 
hd(n) = sin(Wc *((n -1)-alpha)) /(((n -1)-alpha)*%pi); 
end 
end 
// Blackman Window 
for n = 1:M 
W(n) = 0.42-(0.5*cos((2*%pi*(n-1))/(M-1)))+(0.08*cos((4*%pi*(n-1))/(M-1))); 
end 
//Windowing filter coefficients 
h = hd.*W; 
disp(h,'Filter Coefficients are') 
[hzm,fr]= frmag (h,256) ; 
subplot(2 ,1 ,1) 
plot(2*fr, hzm) 
xlabel( ' Normalized Digital Frequency w'); 
ylabel( 'Magnitude '); 
title( ' Frequency Response of FIR LPF using Blackman Window ') 
hzm_dB = 20* log10 (hzm); 
subplot (2 ,1 ,2); 
plot(2*fr , hzm_dB); 
xlabel( ' Normalized Digital Frequency W' ); 
ylabel( 'Magnitude in dB'); 
title('Frequency Response of FIR LPF using Blackman Window');
```
## CALCULATION:


<img width="1600" height="1099" alt="image" src="https://github.com/user-attachments/assets/fdd335fa-7b44-4863-9f7c-ceab72005731" />
<img width="1555" height="698" alt="image" src="https://github.com/user-attachments/assets/eba75f27-c1dd-4d19-be87-79d105fef9ed" />

## OUTPUT: 
<img width="491" height="457" alt="image" src="https://github.com/user-attachments/assets/fe2f6af7-8e45-4a0b-afde-95f61d044e96" />
<img width="759" height="719" alt="image" src="https://github.com/user-attachments/assets/dd71ddfd-8654-4801-acb8-49a2f1364fa7" />


## RESULT: 

Thus design of low pass FIR digital filter using-Blackman-Window waveforms were plotted and output was verified.

## AIM 2: 
To perform DESIGN OF HIGH PASS FIR DIGITAL FILTERS using SCILAB.

## APPARATUS REQUIRED: 
PC installed with SCILAB. 

## PROGRAM: 
```
clc ; 
close ; 
M=input('Enter the Odd Filter Length ='); 
Wc=input('Enter the Digital Cut off frequency ='); 
alpha= (M -1)/2 // Center Value 
for n = 1:M 
if (n ==alpha+1) 
hd(n) = 1-Wc/ %pi ; 
else 
hd(n) = -sin(Wc *((n -1)-alpha)) /(((n -1)-alpha)*%pi); 
end 
end 
// Blackman Window 
for n = 1:M 
W(n) = 0.42-(0.5*cos((2*%pi*(n-1))/(M-1)))+(0.08*cos((4*%pi*(n-1))/(M-1))); 
end
//Windowing filter coefficients 
h = hd.*W; 
disp(h,'Filter Coefficients are') 
[hzm,fr]= frmag (h,256) ; 
subplot(2 ,1 ,1) 
plot(2*fr, hzm) 
xlabel( ' Normalized Digital Frequency w'); 
ylabel( 'Magnitude '); 
title( ' Frequency Response of FIR HPF using Blackman Window ') 
hzm_dB = 20* log10 (hzm); 
subplot (2 ,1 ,2); 
plot(2*fr , hzm_dB); 
xlabel( ' Normalized Digital Frequency W' ); 
ylabel( 'Magnitude in dB'); 
title('Frequency Response of FIR HPF using Blackman Window');
```
## CALCULATION:
<img width="1361" height="1033" alt="image" src="https://github.com/user-attachments/assets/7365af8f-4251-4c24-9e62-29126ad1016a" />



## OUTPUT: 

<img width="451" height="479" alt="image" src="https://github.com/user-attachments/assets/8aa0463f-277d-4c08-b249-a58579a8a423" />
<img width="756" height="718" alt="image" src="https://github.com/user-attachments/assets/ca7c4148-d965-44e6-98fe-1d6d87f15af0" />

## RESULT: 
Thus design of HIGH pass FIR digital filter using-Blackman-Window waveforms were plotted and output was verified.

## AIM 3: 
To perform DESIGN OF BAND PASS FIR DIGITAL FILTERS using SCILAB.

## APPARATUS REQUIRED: 
PC installed with SCILAB. 

## PROGRAM: 
```
clc ; 
close ; 
M=input('Enter the Odd Filter Length ='); 
Wc=input('Enter the Digital Cut off frequency ='); 
Wc2=Wc(2); 
Wc1=Wc(1); 
alpha= (M -1)/2 // Center Value 
for n = 1:M 
if (n ==alpha+1) 
hd(n) =(Wc2-Wc1)/%pi ; 
else 
hd(n) =((sin(Wc2 *((n -1)-alpha)))-(sin(Wc1 *((n -1)-alpha))))/(((n -1)-alpha)*%pi); 
end 
end 
// Blackman Window 
for n = 1:M 
W(n) = 0.42-(0.5*cos((2*%pi*(n-1))/(M-1)))+(0.08*cos((4*%pi*(n-1))/(M-1))); 
end 
//Windowing filter coefficients 
h = hd.*W; 
disp(h,'Filter Coefficients are') 
[hzm,fr]= frmag (h,256) ; 
subplot(2 ,1 ,1) 
plot(2*fr, hzm) 
xlabel( ' Normalized Digital Frequency w'); 
ylabel( 'Magnitude '); 
title( ' Frequency Response of FIR BPF using Blackman Window ') 
hzm_dB = 20* log10 (hzm); 
subplot (2 ,1 ,2); 
plot(2*fr , hzm_dB);  
xlabel( ' Normalized Digital Frequency W' ); 
ylabel( 'Magnitude in dB'); 
title('Frequency Response of FIR BPF using Blackman Window');
```
## CALCULATION:
<img width="1600" height="1445" alt="image" src="https://github.com/user-attachments/assets/42f5ba84-125e-45de-ba3a-3e477c4d01ab" />


## OUTPUT: 
<img width="556" height="458" alt="image" src="https://github.com/user-attachments/assets/1e5d480a-214d-4381-897e-bb47de346295" />

<img width="771" height="715" alt="image" src="https://github.com/user-attachments/assets/4e6f578e-6c0a-4203-9cd1-3be10fcb60e4" />

## RESULT: 
Thus design of BAND pass FIR digital filter using-Blackman-Window waveforms were plotted and output was verified.

## AIM 4:
To perform DESIGN OF BAND STOP FIR DIGITAL FILTER using SCILAB.

## APPARATUS REQUIRED: 
PC installed with SCILAB. 

## PROGRAM: 
```
clc ; 
close ; 
M=input('Enter the Odd Filter Length ='); 
Wc=input('Enter the Digital Cut off frequency ='); 
Wc2=Wc(2); 
Wc1=Wc(1); 
alpha= (M -1)/2 // Center Value 
for n = 1:M 
if (n ==alpha+1) 
hd(n) =1-((Wc2-Wc1)/%pi); 
else 
hd(n) =((sin(Wc1 *((n -1)-alpha)))-(sin(Wc2 *((n -1)-alpha))))/(((n -1)-alpha)*%pi); 
end 
end 
// Blackman Window 
for n = 1:M 
W(n) = 0.42-(0.5*cos((2*%pi*(n-1))/(M-1)))-(0.08*cos((4*%pi*(n-1))/(M-1))); 
end 
//Windowing filter coefficients 
h = hd.*W; 
disp(h,'Filter Coefficients are') 
[hzm,fr]= frmag (h,256) ; 
subplot(2 ,1 ,1) 
plot(2*fr, hzm) 
xlabel( ' Normalized Digital Frequency w'); 
ylabel( 'Magnitude '); 
title( ' Frequency Response of FIR BSF using Blackman Window ') 
hzm_dB = 20* log10 (hzm); 
subplot (2 ,1 ,2); 
plot(2*fr , hzm_dB); 
xlabel( ' Normalized Digital Frequency W' ); 
ylabel( 'Magnitude in dB'); 
title('Frequency Response of FIR BSF using Blackman Window');
```
## CALCULATION:

<img width="1438" height="1105" alt="image" src="https://github.com/user-attachments/assets/69145dd3-c68d-424d-b1f7-9feceb495f39" />

## OUTPUT: 
<img width="582" height="512" alt="image" src="https://github.com/user-attachments/assets/3e1b38e3-bcb9-4694-8310-b7aa8a6991df" />

0<img width="759" height="723" alt="image" src="https://github.com/user-attachments/assets/fa05308b-ec56-4e59-b119-cc6f579cfea2" />

## RESULT: 
Thus design of BAND STOP FIR digital filter using-Blackman-Window waveforms were plotted and output was verified.
