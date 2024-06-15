# Fresnel-and-Fourier-holograms-in-digital-holography-
Recording and reconstruction of images using computational based methods 
CODE 1

>> clear all

close all

>> A=" C:\Users\Madam Abigail\Desktop\DHH.bmp"

>> I=imread(A);

>> M=512;

>> I= imresize(1*I, [M M]);

>> I=double(1*I(:, :, 1));

>> figure; imshow(mat2gray(abs(1*I)));

>> title('Object pattern');

>> axis off

>> r=1:M;

>> c=1:M;

>> [C, R]=meshgrid(c,r);

>> O=fftshift(ifft2(fftshift(1*I)));

>> R=ones(512,512);

>> R=R*max(max(abs(O)));

>> R=R.*exp(2*i*pi.*C/4);

>> H=abs(O+R).^2;

>> figure; imshow(mat2gray(abs(H)));

>> U=fftshift(ifft2(fftshift(H)));

>> figure; imshow(900.*mat2gray(abs(U)));

>> title('Reconstructed image');

>> axis off



CODE 2

>> N=500;

A=imread('C:\Users\Madam Abigail\Desktop\DH.png','png');

A=double(A);

A=A(1:N,1:N);

A=imresize(A,[N,N]);

B=zeros(N,N);

B(250,250)=100;

A1=fftshift(fft2(A));

>> 'clear (A)';

>> I1=abs(A1).*abs(A1);

>> B1=fftshift(fft2(B));

>> I2=abs(B1).*abs(B1);

>> D1=A1+B1;

>> I3=abs(D1).*abs(D1);

>> I4=(I3-I1);

>> D2=fftshift(fft2(I4));

>> I5=abs(D2).*abs(D2);

>> figure;

>> imshow(mat2gray(abs(A)))

>> title('Object pattern')

>> axis off

>> figure

>> imshow(mat2gray(abs(I5)))

>> title('reconstructed image')

>> axis off

>> figure;

>> imshow(mat2gray(abs(I2)))

>> title('Fourier hologram')

>> axis off

>> title('reconstructed image')



FOR FOURIER HOLOGRAM, LOAD THE OBJECT AND CREATE THE OBJECT AND REFERENCE MATRICES.

N=500; % This defines the size of the matrix

>> A=imread('C:\Users\Madam Abigail\Desktop\DHH.bmp','bmp');  % this is loading the image. The image needs to be accessed on the computer storage for recording and reconstruction using the matlab imread function

>> A=double(A); 

>> A=A(1:N,1:N);

>> A=imresize(A,[N,N]);

>> B=zeros(N,N); % this is the dirac delta function 

>> B(250,250)=100;

%To calculate the far field diffraction pattern for the object and reference beam

>> A1=fftshift(fft2(A)); % this is to calculate the diffraction pattern for the object

>> A1=fftshift(fft2(A));

>> I1=abs(A1).*abs(A1);

>> figure;

>> imshow(mat2gray(abs(A)))

>> title('Object pattern')

>> axis off

>> I1=abs(A1).*abs(A1);

>> B1=fftshift(fft2(B)); %this is to calculate the diffraction pattern for the reference

>>  I2=abs(B1).*abs(B1);

% now the hologram can be created by interfering the diffracted of both the object and the reference

Filtering can be done as 

>> I4=(I3-I1); %filtering autocorrelation  term

% after filtering has been done, hologram is reconstructed as

>> D2=fSSSftshift(fft2(I4));

>> I5=abs(D2).*abs(D2);

>> figure;

>> imshow(mat2gray(abs(I2)))

>> title('Fourier hologram')

>> axis off

>> figure

>> imshow(mat2gray(abs(I5)))

>> title('reconstructed image')

>> axis off

WELL RUN AND TRUSTED CODES FINAL 

A=imread('C:\Users\Madam Abigail\Desktop\DH.png','png');

A=double(A);

>> A=A(1:N,1:N);

% after running the above code (line 3 and this kind of error appears, apply the image resize to resize the source image.

A=imresize(A,[N,N]);

>> B=zeros(N,N);

B(250,250)=100;

A1=fftshift(fft2(A));

I1=abs(A1).*abs(A1);

B1=fftshift(fft2(B));

I2=abs(B1).*abs(B1);

D1=A1+B1;

I3=abs(D1).*abs(D1);

I4=(I3-I1);

D2=fftshift(fft2(I4));

I5=abs(D2).*abs(D2);

figure;

imshow(mat2gray(abs(A)))

title('Object pattern')

axis off

figure

imshow(mat2gray(abs(I5)))

title('reconstructed image')

axis off

figure;

imshow(mat2gray(abs(I2)))



CODE THREE (3)

%Fraunhoffer Hologram 

%Defining the size of the object   

clc;

 clear all;

N=256; 

%Loading the image 

A=imread('C:\Users\Madam Abigail\Desktop\New folder\me.jpg','jpg');% should be suitably modified by the user

 A=A(1:N,1:N); 

A=double(A);

 %Dirac delta function 

B=zeros(N,N); 

B(129,129)=100; 

%To generate the diffraction pattern for the object and reference 

A1=fftshift(fft2(A));

 I1=abs(A1).*abs(A1); 

B1=fftshift(fft2(B)); 

I2=abs(B1).*abs(B1); 

%Hologram construction and Filtering 

D1=A1+B1; 

I3=abs(D1).*abs(D1); 

I4=(I3‐I1); 

imwrite(I4,'C:\Users\Madam Abigail\Desktop\New folder\me.jpg');%Hologram reconstruction 

D2=fftshift(fft2(I4)); 

I5=abs(D2).*abs(D2); 

imwrite(I5,'C:\Users\Madam Abigail\Desktop\New folder\me.jpg');

%To see the object, reference, hologram and reconstruction 

colormap(prism);

subplot(3,3,1); 

image(A); 

subplot(3,3,2); 

image(B); 

subplot(3,3,3); 

imagesc(I1); 

subplot(3,3,4); 

imagesc(I2); 

subplot(3,3,5); 

imagesc(I4); 

subplot(3,3,6); 

imagesc(I5); 

returnsubplot(3,3,4); 

imagesc(I2);



