# Experiment-08- Encoders-and-decoders 
### AIM: To implement 8 to 3 Encoder and  3to8 Decoder using verilog and validate its outputs
### HARDWARE REQUIRED:  – PC, Cyclone II , USB flasher
### SOFTWARE REQUIRED:   Quartus prime
### THEORY 

## Encoders
Binary code of N digits can be used to store 2N distinct elements of coded information. This is what encoders and decoders are used for. Encoders convert 2N lines of input into a code of N bits and Decoders decode the N bits into 2N lines.

1. Encoders –
An encoder is a combinational circuit that converts binary information in the form of a 2N input lines into N output lines, which represent N bit code for the input. For simple encoders, it is assumed that only one input line is active at a time.

As an example, let’s consider Octal to Binary encoder. As shown in the following figure, an octal-to-binary encoder takes 8 input lines and generates 3 output lines.

![image](https://user-images.githubusercontent.com/36288975/171543588-bc0746df-a173-4b35-989e-5fb7d385fe8a.png)
## Figure -01 3 to 8 Encoder 


Implementation –

X = D4 + D5 + D6 + D7
Y = D2 +D3 + D6 + D7
Z = D1 + D3 + D5 + D7 
Hence, the encoder can be realised with OR gates as follows:


![image](https://user-images.githubusercontent.com/36288975/171543740-68403b82-aa93-4c98-9343-f32b14885a2e.png)
## Figure -02 3 to 8 Encoder implenentation 

 ### Decoders 
A decoder does the opposite job of an encoder. It is a combinational circuit that converts n lines of input into 2n lines of output.

Let’s take an example of 3-to-8 line decoder.
Implementation –
D0 is high when X = 0, Y = 0 and Z = 0. Hence,

D0 = X’ Y’ Z’ 
Similarly,

D1 = X’ Y’ Z
D2 = X’ Y Z’
D3 = X’ Y Z
D4 = X Y’ Z’
D5 = X Y’ Z
D6 = X Y Z’
D7 = X Y Z 


![image](https://user-images.githubusercontent.com/36288975/171543978-ee2d0671-2846-40a1-8705-507fd6287a49.png)
## Figure -03 8 to 3 Decoder 



![image](https://user-images.githubusercontent.com/36288975/171543866-5a6eace6-8683-49d7-9c4f-a7cb30ec3035.png)
## Figure -04 8 to 3 Decoder implementation 

### Procedure
/* write all the steps invloved */



### PROGRAM 
/*
Program for Endocers and Decoders  and verify its truth table in quartus using Verilog programming.
Developed by: KAVINESH M
RegisterNumber:  212222230064
*/
i]Encoder
```
module encoder(a,b,c,d0,d1,d2,d3,d4,d5,d6,d7);
output a,b,c;
input d0,d1,d2,d3,d4,d5,d6,d7;
or(a,d4,d5,d6,d7);
or(b,d2,d3,d6,d7);
or(c,d1,d3,d5,d7);
endmodule
```
ii]Decoder
```
module decoder(d0,d1,d2,d3,d4,d5,d6,d7,a,b,c);
output d0,d1,d2,d3,d4,d5,d6,d7;
input a,b,c;
assign d0 = (~a&~b&~c);
assign d1 = (~a&~b&c);
assign d2 = (~a&b&~c);
assign d3 = (~a&b&c);
assign d4 = (a&~b&~c);
assign d5 = (a&~b&c);
assign d6 = (a&b&~c);
assign d7 = (a&b&c);
endmodule
```



### RTL LOGIC  
### Encoder

![244270331-163324cc-5635-4298-855c-daa0b8992f55](https://github.com/kavinesh8476/Experiment-08-Encoders-and-decoders-/assets/118466561/512d79ed-dfb8-4ed9-aac2-3d0912e32c1b)
### Decoder

![244273355-3a63ac44-9b51-4447-aa13-942cb3ae2af2](https://github.com/kavinesh8476/Experiment-08-Encoders-and-decoders-/assets/118466561/706e8e56-dc00-4eed-8661-27c39efa1a45)




### TIMING DIGRAMS  
### Encoder
![244272176-af233e4b-f409-4ab1-abb3-638af9cab952](https://github.com/kavinesh8476/Experiment-08-Encoders-and-decoders-/assets/118466561/7f914f6c-0b1d-4144-9d47-0e3b8da3c8bb)

### Decoder
![244274050-07b1d303-ff53-41c6-9c1e-861546cb6cc8](https://github.com/kavinesh8476/Experiment-08-Encoders-and-decoders-/assets/118466561/3d852a5d-0b0f-497a-bdea-79491dab802e)



### TRUTH TABLE 

### Encoder
![244272667-c8fca45d-bfda-42f0-a3e3-a879e7425812](https://github.com/kavinesh8476/Experiment-08-Encoders-and-decoders-/assets/118466561/3aac1c6d-a31a-4e13-8b9c-524cf05d4798)


### Decoder
![244274125-65dc08a0-5bcd-4ff2-ba4e-1a4a6a2384be](https://github.com/kavinesh8476/Experiment-08-Encoders-and-decoders-/assets/118466561/18945ed4-3df2-40a5-9cdb-406844e2c56a)

### RESULTS 
Thus the program to desing encoder and decoder is done.
