#electronics #analog


## Chopper
A particular variant of opamp with very low offset voltage.

![[Opper_Chopper.png]]

During phase 1 (pictured), $B$ opamp measures its own offset voltage and stores it onto capacitor $C_1$ which is then fed back and offsets that opamp. 
During phase 2 (switches in alternate state), $B$ opamp measures offset voltage of $A$ and stores its value onto $C_2$ (its own offset has been removed in previous stage). 

## Videos
- [EEVblog 24 - Chopper Operational Amplifiers](https://www.youtube.com/watch?v=oibJUt6QkwI)

%% 
## TODO
- verify opamp, the description seems odds