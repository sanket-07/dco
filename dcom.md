AIM = To study simulation of different line codes using matlab

clear all;
close all;
% Unipolar NRZ
c = input("enter the required data");
bitrate = 1;
T = length(c)/bitrate; 
m = 200;
M = m*length(c);
dt = T/M;
t = 0:dt:T;
x = zeros(1,length(t));
for i = 0:length(c)-1
  if c(i+1) == 1
    x(i*m+1:(i+1)*m) = 1;
  else
    x(i*m+1:(i+1)*m) = 0;
  end
end
figure;
plot(t,x);
axis([0 t(end) -0.1 1.1])
grid on;
title(['Unipolar NRZ: [' num2str(c) ']']);






Aim: Vertical redundancy Check (VRC) code generation and error detection
clc;
close all;
%transmitter
b= 0;
a= input('Enter the sender 7 bit data')
for i=1:7
    if(a(i)==1)
       b=b+1;
    end
end
    if rem(b,2)==1
        a(8)=1;
    else a(8)=0;
    end
disp('Data for transmission with even parity')    
disp(a);    

%receiver
r=input('Enter 8 bit received data')
s=0;
for i=1:8
    if(r(i)==1)
        s=s+1;
    end
end

    if rem(s,2)==1
disp('Received data is in error')         
         
     end
     
disp(' No error')     
   a(8)=[ ];
disp('Received data %a')
disp(a)


