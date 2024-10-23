# ASIC Design Class
### This GitHub repository belongs to Utkarsh Jain, MT2024538, and is intended for the ASIC Design class spanning August 2024 to December 2024. The repository contains the following:

- ####  Detailed documentation for each laboratory experiment conducted
- #### Visual snapshots illustrating the step-by-step procedure of the experiments
- #### Source code files related to each experiment
## Assignment

<details>
  <summary>Assignment 1 : Write the C code in a file in ubuntu terminal and save it as vsdlab1.c </summary>



compile the source code using gcc compiler, this will generate the executable code. Now, run the executable code to see the output.

Write an code leafpad vsdlab1.c
to create c file name vsdlab1

![lab 1_step 1](https://github.com/user-attachments/assets/a5484cf1-491f-4973-a143-0f3cdb78b1ef)

Now write an c code of an sum of number from 1 to n
![lab 1_step 2](https://github.com/user-attachments/assets/ae76c7b8-0ab7-418f-8284-3dd36a3b4515)

and Then compile it with gcc.filename.c
THEN RUN IT BY ./a.out

![lab 1 _step 3](https://github.com/user-attachments/assets/2cff22a0-ccc4-4f80-b8e0-567e4cae3cd2)


</details>

<details>
  <summary>Assignment 2 : Compiling a C program with RISCV gcc compiler, execute it, generate the output Now, compile the vsdlab1.c using RISCV gcc compiler, also see the assembly code for C program.</summary>

Compiling a C program with RISCV gcc compiler, execute it, generate the output Now, compile the vsdlab1.c using RISCV gcc compiler, also see the assembly code for C program.



![lab 2_1](https://github.com/user-attachments/assets/2a71c904-6834-4b9f-ac05-ffe7046342d4)

To run an program by an riscv64 type riscv64-unknown-elf-gcc-O1-mabi=l p64-march=rv64i-a filename.o filename.c

![lab 2_2](https://github.com/user-attachments/assets/5dcf9e52-e1ee-44d6-b39b-1c73192442d9)

To run an assembly code for c program write: riscv-unknown-elf-objdump-d filename.o
it will give an branch of codes

![lab 2_3](https://github.com/user-attachments/assets/263d0844-1ce9-415e-8f94-bccb5b992623)

we want our main program code now write: riscv-unknown-elf-objdump-d filename.o | less
(we will get our main assembly code)

![lab 2_4](https://github.com/user-attachments/assets/4b2dfa02-c700-4301-b296-3e57c9f08ce8)

now to check add 101BC + 4 we get 101c0 now subtract (101C0-10184)/4 we get f 

![lab 2_5](https://github.com/user-attachments/assets/df0e4717-d970-4d6b-9dcb-6319ff6c3f36)

- - ### now lets modify code with slight change let change o1 with fast in an above code and then run it 

![lab 2_8](https://github.com/user-attachments/assets/e52ce094-b7e3-4340-ba69-33882cd75551)

![lab 2_6](https://github.com/user-attachments/assets/5b924a16-9a31-4aa2-af12-1c91d623aef6)

now to check (100E0 - 100b0)/4 we get C

![lab 2_7](https://github.com/user-attachments/assets/61979cb0-ca79-454c-ab3a-524e6527abe8)

</details>


  <details>
    
  <summary>Assignment 3 : To Execute of the output file of RISCv compiler in spike simulator</summary>


To decode it write : spike pk filename.o

![lab3_1](https://github.com/user-attachments/assets/396c8fd4-7b0f-4ec3-acb5-eb37d445025a)

Open an new Terminal and write : riscv-unknown-elf-objdump-d filename.o | less

![lab3_2](https://github.com/user-attachments/assets/f18e8c88-6fe2-421c-b45f-bd39fe732389)

Go to previous terminal and write : spike -d pk filename.o
 and then type : until pc 0 100b0
 then type : reg 0 a2 ( Inst LUI is executed) (LUI : load upper immediate).
 
 ![lab3_3](https://github.com/user-attachments/assets/800e8e5f-5a37-456f-99cb-a7c355b13f82)
 
 ![lab3_4](https://github.com/user-attachments/assets/223bfe53-feca-48e3-bea7-726f58c01a78)

![lab3_5](https://github.com/user-attachments/assets/120f18ae-20d1-4c0a-86c5-870e15f6fe94)

press enter for next inst
type : reg 0 a2 (after modifying content of a2)

press enter for next inst

type : reg 0 a0

press enter

![lab3_6](https://github.com/user-attachments/assets/11a5d815-483a-4611-8034-196940fe5c79)

type reg 0 sp
(go back)
type: q
tyep: spike -d pk filename.o
until pc 0 100b8
reg 0 sp

![lab3_7](https://github.com/user-attachments/assets/20bec14b-af3d-407e-9df0-c768011a4198)

Go to calc and type 3ffffffb50 in hexa and subtract 16 in dec you get 10 at hexa decimal.


![lab3_8](https://github.com/user-attachments/assets/79c6a105-14bf-433a-a236-6e1e5bdb1f25)

![lab3_9](https://github.com/user-attachments/assets/c1dee427-9aec-4cd0-8c20-fda01d4f77be)

- - ## Same thing for o1 as well

### until pc 0 10184

![lab3_11](https://github.com/user-attachments/assets/68a87b4f-3aff-465f-9e8a-162e09a0a257)

![lab3_12](https://github.com/user-attachments/assets/c230b11f-49e5-4e5c-a7f8-75dd0b3b32bd)

</details>



<details>
  <summary>Assignment 4 : To sort and organise a set of given instructions into their respective format type:</summary>

  

## 1. ADD r4, r4, r4
      Type: R
      Format:
      
      funct7 | rs2 | rs1 | funct3 | rd | opcode
      0000000 | 00100 | 00100 | 000 | 00100 | 0110011

## 2. SUB r4, r4, r4
     Type: R
     Format:

    funct7 | rs2 | rs1 | funct3 | rd | opcode
    0100000 | 00100 | 00100 | 000 | 00100 | 0110011

## 3. AND r4, r4, r4
    Type: R
    Format:

    funct7 | rs2 | rs1 | funct3 | rd | opcode
    0000000 | 00100 | 00100 | 111 | 00100 | 0110011

## 4. OR r8, r4, r5
    Type: R
    Format:

      funct7 | rs2 | rs1 | funct3 | rd | opcode
      0000000 | 00101 | 00100 | 110 | 01000 | 0110011

## 5. XOR r8, r4, r4
    Type: R
    Format:

    funct7 | rs2 | rs1 | funct3 | rd | opcode
    0000000 | 00100 | 00100 | 100 | 01000 | 0110011


## 6. SLT r00, r1, r4
    Type: R
    Format:

    funct7 | rs2 | rs1 | funct3 | rd | opcode
    0000000 | 00100 | 00001 | 010 | 00000 | 0110011


## 7. ADDI r02, r2, 5
    Type: I
    Format:


    imm[11:0] | rs1 | funct3 | rd | opcode
    000000000101 | 00010 | 000 | 00010 | 0010011


## 8. SW r2, r0, 4
    Type: S
    Format:

    imm[11:5] | rs2 | rs1 | funct3 | imm[4:0] | opcode
    0000000 | 00010 | 00000 | 010 | 00100 | 0100011


## 9. SRL r06, r01, r1
    Type: R
    Format:

    funct7 | rs2 | rs1 | funct3 | rd | opcode
    0000000 | 00001 | 00001 | 101 | 00110 | 0110011
    

## 10. BNE r0, r0, 20
    Type: B
    Format:


    imm[12] | imm[10:5] | rs2 | rs1 | funct3 | imm[4:1] | imm[11] | opcode
    0 | 000000 | 00000 | 00000 | 001 | 0100 | 0 | 1100011

## 11. BEQ r0, r0, 15
    Type: B
    Format:

    imm[12] | imm[10:5] | rs2 | rs1 | funct3 | imm[4:1] | imm[11] | opcode
    0 | 000000 | 00000 | 00000 | 000 | 1111 | 0 | 1100011

## 12. LW r03, r01, 2
    Type: I
    Format:
 
    imm[11:0] | rs1 | funct3 | rd | opcode
    000000000010 | 00001 | 010 | 00011 | 0000011


## 13. SLL r05, r01, r1
    Type: R
    Format:


    funct7 | rs2 | rs1 | funct3 | rd | opcode
    0000000 | 00001 | 00001 | 001 | 00101 | 0110011

- # RISC-V Instructions and Their Hexadecimal Representation

| Instruction | Assembly Code | Hexadecimal Representation |
|-------------|---------------|---------------------|
| ADD         | `ADD r4, r4, r4` | `0x00024233`        |
| SUB         | `SUB r4, r4, r4` | `0x40024233`        |
| AND         | `AND r4, r4, r4` | `0x000242b3`        |
| OR          | `OR r8, r4, r5`  | `0x000422b3`        |
| XOR         | `XOR r8, r4, r4` | `0x000421b3`        |
| SLT         | `SLT r00, r1, r4`| `0x00012133`        |
| ADDI        | `ADDI r02, r2, 5`| `0x00028213`        |
| SW          | `SW r2, r0, 4`   | `0x00012023`        |
| SRL         | `SRL r06, r01, r1`| `0x000301b3`        |
| BNE         | `BNE r0, r0, 20` | `0x00100013`        |
| BEQ         | `BEQ r0, r0, 15` | `0x000f0013`        |
| LW          | `LW r03, r01, 2` | `0x00212083`        |
| SLL         | `SLL r05, r01, r1`| `0x00030133`        |

- # RISC-V and Hardcoded ISA Instructions Comparison

## Table 1: Instructions Comparison

| Operation | Standard RISC-V ISA (Hex) | Standard RISC-V ISA (Binary)                              | Hardcoded ISA (Hex) | Hardcoded ISA (Binary)                                |
|-----------|---------------------------|------------------------------------------------------------|---------------------|--------------------------------------------------------|
| ADD       | 32'h00024233                | 000000000000 00100 000 00100 0110011                     | 32'h02208300      | 000000100010 00000 100 00000 01100000                  |
| SUB       | 32'h40024233                | 010000000000 00100 000 00100 0110011                     | 32'h02209380      | 000000100010 01000 100 10000 01100000                  |
| AND       | 32'h000242b3                | 000000000000 00100 111 00100 0110011                     | 32'h0230a400      | 000000100011 01000 101 00100 01100000                  |
| OR        | 32'h000422b3                | 000000000000 00100 110 01000 0110011                     | 32'h02513480      | 000000100101 00010 110 10100 01100000                  |
| XOR       | 32'h000421b3                | 000000000000 00100 100 01000 0110011                     | 32'h0240c500      | 000000100100 00000 100 11000 01100000                  |
| SLT       | 32'h00012133                | 000000000000 00001 010 00000 0110011                     | 32'h02415580      | 000000100100 00010 101 01010 01100000                  |
| ADDI      | 32'h00028213                | 000000000000 00010 010 00010 0010011                     | 32'h00520600      | 000000100100 00010 010 00010 01100000                  |
| SW        | 32'h00012023                | 000000000000 00000 010 00010 0100011                     | 32'h00209181      | 000000100010 00000 010 00001 01100000                  |
| SRL       | 32'h000301b3                | 000000000000 00001 101 00110 0110011                     | 32'h00271803      | 000000100010 00000 011 00110 011000001                 |
| BNE       | 32'h00100013                | 000000000001 00000 001 00000 1100011                     | N/A               | N/A                                                    |
| BEQ       | 32'h000f0013                | 000000000000 00000 000 00000 1100011                     | 32'h00f00002      | 000000000000 00000 000 00000 11000000                  |
| LW        | 32'h00212083                | 000000000010 00001 010 00011 0000011                     | 32'h00208681      | 000000100010 00000 010 01100 01100000                  |
| SLL       | 32'h00030133                | 000000000000 00001 000 00101 0110011                     | 32'h00208783      | 000000100010 00000 111 01111 01100000                  |


</details>

<details>
  <summary>Assignment 5 : Use Above RISC-V Core Verilog netlist and testbench for functional simulation experiment. Upload waveform snapshots for the commands on your GitHub. Reference GitHub repo is here. </summary>



## Here we will try to execute verilog code by modifying operation setting with those of our operation
### We run these code with help of gtkwave and icarur 

## Identifying Instruction Types
### A.The given hardcoded instructions are:
![a13](https://github.com/user-attachments/assets/354b4c8a-2a2e-43cc-81c8-7e6fc6852d3b)

## 1. ADD R6, R2, R1

### This is the waveform of the given hardcoded verilog program:

![a2](https://github.com/user-attachments/assets/30bc4f7b-accd-4e1b-beca-c98e8cd7473a)

## 2. SUB R7, R1, R2

### This is the waveform of the given hardcoded verilog program:

![a3](https://github.com/user-attachments/assets/f983286b-4031-49a1-8ab9-1b95586fa9dc)


## 3. AND R8, R1, R3

### This is the waveform of the given hardcoded verilog program:

![a4](https://github.com/user-attachments/assets/f43c53c4-2764-498f-9f2b-6ba3a1937cd3)


## 4. OR R9, R2, R5

### This is the waveform of the given hardcoded verilog program:

![a5](https://github.com/user-attachments/assets/31bfef57-d9bf-46e3-bc3c-bce0246d242c)


## 5. XOR r10, r1, r4

### This is the waveform of the given hardcoded verilog program:

![a7](https://github.com/user-attachments/assets/3e41f82d-080f-4b96-8640-8a47c7b29530)


## 6. SLT r1, r2, r4 

### This is the waveform of the given hardcoded verilog program:

![a8](https://github.com/user-attachments/assets/2695f089-8d6e-42cb-a97e-3700ca952aba)


## 7. ADDI r12, r4, 5 

### This is the waveform of the given hardcoded verilog program:

![a9](https://github.com/user-attachments/assets/2237192c-4d2f-4c1a-a40f-892d3e964102)


## 8. SW r3, r1, 2

### This is the waveform of the given hardcoded verilog program:

![a10](https://github.com/user-attachments/assets/10328064-81ee-4896-8892-55b86b9d93cc)


## 9. LW r13, r01, 2

### This is the waveform of the given hardcoded verilog program:

![a11](https://github.com/user-attachments/assets/86d06b97-6a64-40ed-8650-5749f1fba050)


## 10. BEQ r0, r0, 15

### This is the waveform of the given hardcoded verilog program:

![a12](https://github.com/user-attachments/assets/e5e8e8bf-b17a-4220-905c-5f7118328ad2)



- ## This is the waveform of our verilog program:

### B.The given custom instructions are:

![a1](https://github.com/user-attachments/assets/9f9034ca-0612-4c17-a00f-ab38260c67c4)

## 1. ADD r4, r4, r4
### Operation : 32'h00024233

### This is the waveform of the given hardcoded verilog program:

![r1](https://github.com/user-attachments/assets/f3d714d5-621b-427e-b257-e0917971cc8f)

## 2. SUB r4, r4, r4
### Operation : 32'h00024233

### This is the waveform of the given hardcoded verilog program:

![r2](https://github.com/user-attachments/assets/c44636c6-68aa-4162-aade-70ae61351e1e)

## 3. AND r4, r4, r4
### Operation : 32'h000242b3

### This is the waveform of the given hardcoded verilog program:

![r3](https://github.com/user-attachments/assets/cfe80f8e-4374-434a-a89a-e49d41c14719)


## 4. OR r8, r4, r5
### Operation : 32'h000422b3

### This is the waveform of the given hardcoded verilog program:

![r4](https://github.com/user-attachments/assets/22fe76fb-5385-4ecb-b5b8-7148ea23c1ee)


## 5. XOR r8, r4, r4
### Operation : 32'h000421b3

### This is the waveform of the given hardcoded verilog program:


![r5](https://github.com/user-attachments/assets/c7cf73a8-2ebb-4958-94fb-474058d29f8d)

## 6. SLT r00, r1, r4
### Operation : 32'h00012133

### This is the waveform of the given hardcoded verilog program:

![r6](https://github.com/user-attachments/assets/47aba7f7-f7f6-4ac3-95fd-bf1df92b4620)



## 7. ADDI r02, r2, 5
### Operation : 32'h00028213`

### This is the waveform of the given hardcoded verilog program:

![r7](https://github.com/user-attachments/assets/2cc5a625-e43c-4f4f-9e00-c9328b2e5373)


## 8. SW r2, r0, 4
### Operation : 32'h00012023


### This is the waveform of the given hardcoded verilog program:

![r8](https://github.com/user-attachments/assets/39725e9f-5a56-4546-a8c9-6bc9d48c6a13)


## 9. SRL r06, r01, r1
### Operation : 32'h000301b3


### This is the waveform of the given hardcoded verilog program:

![r9](https://github.com/user-attachments/assets/c8ff0ed3-f31c-4c69-a042-bd8f5f7220b0)


## 10. BNE r0, r0, 20
### Operation : 32'h00100013


### This is the waveform of the given hardcoded verilog program:

![r10](https://github.com/user-attachments/assets/c3364a51-be42-4d60-b967-0fae66126287)



## 11. BEQ r0, r0, 15
### Operation : 32'h000f0013


### This is the waveform of the given hardcoded verilog program:

![r11](https://github.com/user-attachments/assets/749e3094-f2fe-42e0-9478-6d7f45294ab9)



## 12. LW r03, r01, 2
### Operation : 32'h00212083


### This is the waveform of the given hardcoded verilog program:

![r12](https://github.com/user-attachments/assets/0e74a588-ab6a-474d-8a19-3d7ca5cdf0c0)



## 13. SLL r05, r01, r1
### Operation : 32'h00030133


### This is the waveform of the given hardcoded verilog program:

![r13](https://github.com/user-attachments/assets/2b58652b-e66a-4185-bc9b-58263e7c4cc0)

</details>

- ## Compile  Low Pass Filter application with GCC and RISC-V GCC

<details>
  <summary>Assignment 6 : Compile C application with GCC and RISC-V GCC</summary>



### Application Name - Low Pass Filter

### 1.code

![s5](https://github.com/user-attachments/assets/b6b460e0-3ed1-476f-afdc-63ea402a70af)

### 2.Compile program with gcc compiler as shown below:

![s4](https://github.com/user-attachments/assets/64154fad-7140-4a40-962c-42fe9f2267ac)

### 3.Compiled with Risc-V gcc and run using "Spike command " as shown below: 

![s11](https://github.com/user-attachments/assets/19a60506-d116-4e5c-a110-80653e61b494)

### 4.Creating Objdump File

![s7](https://github.com/user-attachments/assets/decdcf75-eb38-4004-ac63-dde8df63866c)

![s8](https://github.com/user-attachments/assets/337908c8-fe72-4793-ae9a-2ffd3ebf124a)


</details>

- ## RISCV-Processor-Using-TLV
<details>
  <summary>Assignment 7 : Digital Logic with TL-Verilog and Makerchip </summary>

-  ## Logic Gates
  
Logic gates are fundamental building blocks of digital electronic circuits. They are responsible for performing logical operations on input signals and producing output signals based on predefined logic rules. These gates are the foundation of digital computation and are used to design and construct more complex digital systems like processors, memory units, and controllers. Logic gates manipulate binary signals, which are typically represented as "0" and "1".

## 2:1 Multiplexer

Multiplexer, also known as a data selector, is a device that selects between several analog or digital input signals and forwards the selected input to a single output line.

The TL-Verilog code is shown below :

    $out = $sel? $in1 : $in2;
    
  ![l3_mux](https://github.com/user-attachments/assets/cd928d46-402e-48e8-9418-994961e2921f)

## 2:1 Vector Multiplexer
The TL-Verilog code is shown below :

    $out[7:0] = $sel ? $in1[7:0] : $in2[7:0];
    
  ![vector mux](https://github.com/user-attachments/assets/1dee7db8-c43d-4120-98a8-1f3d4d3152fd)

## And Gate on IDE MAKERCHIP
The AND gate is a basic digital logic gate that implements logical conjunction (&) from mathematical logic

The TL-Verilog code is shown below :
          
    $out[4:0] = $in1[3:0] & $in2[3:0];
  
  ![Understanding Usage Of Vector](https://github.com/user-attachments/assets/1fc3433f-b9cd-435a-bb58-504590678d98)

## MUX CALCULATOR ON IDE MAKERCHIP

The TL-Verilog code is shown below :

    $clk_utkarsh = *clk;
    $reset = *reset;
   
    $val1[31:0] = $rand1[3:0];
    $val2[31:0] = $rand2[3:0];
    $op[1:0] = $rand3[1:0];
    $sum[31:0] = $val1[31:0] + $val2[31:0];
    $diff[31:0] = $val1[31:0] - $val2[31:0];
    $prod[31:0] = $val1[31:0] * $val2[31:0];
    $quot[31:0] = $val1[31:0] / $val2[31:0];
    $out[31:0] =
         ($op == 0)
           ? $sum[31:0] :
         ($op == 1)
           ? $diff[31:0] :
         ($op == 2)
           ? $prod[31:0] :
         ($op == 3)
           ? $quot[31:0] :
         //default
           32'b0;
           
![Mux on Makerchip IDE](https://github.com/user-attachments/assets/06e34e3e-2787-444c-bee5-715c8019b0aa)

## COUNTER
Counter is a device which stores the number of times a particular event or process has occurred, often in relationship to a clock

The TL-Verilog code is shown below :

     $count[3:0] = reset ? 1: (>>1$count[3:0] + 1); 

  ![counter](https://github.com/user-attachments/assets/9a1a454b-1709-437d-b1b8-567d6fe400fd)
  
- ## Pipelining
Pipelining is a technique used in computer architecture and digital system design to enhance the efficiency of processing by dividing a complex task into smaller, sequential stages. Each stage performs a specific operation on the data, and these stages are arranged in a pipeline. Pipelining enables multiple instructions or tasks to be executed concurrently, with different stages of different instructions being processed simultaneously. In a pipelined architecture, the processing of an instruction is divided into several stages. This allows for overlapping the execution of multiple instructions, reducing the overall time needed to complete a sequence of tasks.

- - ### PYTHAGOREAN THEORUM
Pythagorean theorem or Pythagoras' theorem is a fundamental relation in Euclidean geometry between the three sides of a right triangle. It states that the area of the square whose side is the hypotenuse is equal to the sum of the areas of the squares on the other two sides.

The TL-Verilog code is shown below :

       \m5_TLV_version 1d: tl-x.org
    \m5
   
     // =================================================
     // Welcome!  New to Makerchip? Try the "Learn" menu.
     // =================================================
   
     //use(m5-1.0)   /// uncomment to use M5 macro library.
    \SV
      // Macro providing required top-level module definition, random
     // stimulus support, and Verilator config.
    m5_makerchip_module   // (Expanded in Nav-TLV pane.)
   
    `include "sqrt32.v"
    \TLV
     $reset = *reset;
     $aa = $rand1[3:0];
     $bb = $rand2[3:0];
    |calc
       @1
         $aa_sq[31:0] = $aa * $aa;
      @2
         $bb_sq[31:0] = $bb * $bb;
      @3
         $cc_sq[31:0] = $aa_sq + $bb_sq;
      @4
         $out[31:0] = sqrt($cc_sq);
   
     // Assert these to end simulation (before Makerchip cycle limit).
     *passed = *cyc_cnt > 40;
     *failed = 1'b0;
    \SV
     endmodule
     
![pythagorean](https://github.com/user-attachments/assets/7cc7f299-dcb2-416f-9986-606e00ec0549)

### Error Detection 



    |comp
    @1 
      $err1 = $bad_input || $illegal_op;
  
    @3
      $err2 = $err1 || $over_flow;
  
    @6
      $err3 = $err2 || $div_by_zero;


![Error Conditions Within Computation Pipeline](https://github.com/user-attachments/assets/79ca844d-2135-4529-aa95-29a21d0fdcfb)


### Lab on 2 Counter and Calculator


The TL-Verilog code is given below :

      |calc
      @0
         $clk_utkarsh = *clk;
         $reset = *reset;
         
      @1
         $val1[31:0] = >>1$out[31:0];
         $val2[31:0] = $rand2[3:0];
         $sum[31:0] = $val1 + $val2;
         $diff[31:0] = $val1 - $val2;
         $prod[31:0] = $val1 * $val2;
         $quot[31:0] = $val1 / $val2;

         $out[31:0] = $reset ? 0 
                                 : ($op[1] ? ($op[0] ? $div : $prod)
                                                                    :($op[0] ? $diff : $sum));
         
         $cnt[31:0] = $reset ? 0 : >>1$cnt + 1;

  ![Lab On 2-Counter and Calculator in pipeline](https://github.com/user-attachments/assets/ec5612e6-87c6-4af0-aba3-ff1fd1e5d80a)      

  ### 2 cycle calculator 

  The TL-Verilog code is given below :
  
          $clk_utkarsh = *clk;
          $reset = *reset;
          $op[1:0] = $random[1:0];
          $val2[31:0] = $rand2[3:0];
         |calc
      @1
         $val1[31:0] = >>2$out;
         $sum[31:0] = $val1+$val2;
         $diff[31:0] = $val1-$val2;
         $prod[31:0] = $val1*$val2;
         $div[31:0] = $val1/$val2;
         $valid = $reset ? 0 : (>>1$valid + 1);
      @2
         $out[31:0] = ($reset | ~($valid))  ? 32'h0 : ($op[1] ? ($op[0] ? $div : $prod):($op[0] ? $diff : $sum));

  ![Lab On 2-CycleCalculator](https://github.com/user-attachments/assets/e1d43cc9-07ce-4f0d-8190-caf3a54192cd)

  
- ## Validity

In Transaction-Level Verilog (TL-Verilog), validity is a concept used to track the state and timing of transactions within a design description. In TL-Verilog, transactions are used to represent higher-level actions or events that occur in a design. A transaction typically consists of a set of signals that represent the data and control information associated with that action. Validity, refers to whether a transaction is considered "valid" or "invalid" based on the state of its.

### Distance Accumulator

The TL-Verilog code is given below :

      |calc
      @1
         $reset = *reset;
      ?$valid
         @1
            $aa_sq[31:0] = $aa[3:0] * $aa;
            $bb_sq[31:0] = $bb[3:0] * $bb;
         @2
            $cc_sq[31:0] = $aa_sq + $bb_sq;
         @3
            $out[31:0] = sqrt($cc_sq);
      @4
         $tot_dist[31:0] = $reset ? '0 : ($valid ? (>>1$tot_dist + $out) : $RETAIN);


![Lab On Distance Accumulator with Pythagoran's theorem](https://github.com/user-attachments/assets/611d025b-266c-43e3-8543-5a2d0b63cb2a)

### 2 Cycle Calculator with Validity

  The TL-Verilog code is given below :

     $clk_utkarsh = *clk;
     $reset = *reset;
    |calc
      @1
        $clk_utkarsh = *clk;
        $reset = *reset;
      @1
         $valid = $reset ? 0 : >>1$valid+1;
         $valid_or_reset = $valid || $reset;
      ?$valid_or_reset
         @1
            $val1[31:0] = >>2$out;
            $sum[31:0] = $val1+$val2;
            $diff[31:0] = $val1-$val2;
            $prod[31:0] = $val1*$val2;
            $div[31:0] = $val1/$val2;
            $valid = $reset ? 0 : (>>1$valid + 1);
         @2
            $out[31:0] = $reset  ? 32'h0 : ($op[1] ? ($op[0] ? $div : $prod):($op[0] ? $diff : $sum));

![Lab on cycle Calculator with validity](https://github.com/user-attachments/assets/e1b35bc3-7367-4934-84b0-19fedc4cb724)

   

 ### Lab Calculator with Single Value Memory
 
   The TL-Verilog code is given below :
   
          |calc
      @0 
         $clk_utkarsh = *clk;
         $reset = *reset;
         
      @1
         $val1 [31:0] = >>2$out;
         $val2 [31:0] = $rand2[3:0];
         
         $valid = $reset ? 1'b0 : >>1$valid + 1'b1 ;
         $valid_or_reset = $valid || $reset;
         
      ?$vaild_or_reset
         @1   
            $sum [31:0] = $val1 + $val2;
            $diff[31:0] = $val1 - $val2;
            $prod[31:0] = $val1 * $val2;
            $div[31:0] = $val1 / $val2;
            
         @2   
            $mem[31:0] = $reset ? 32'b0 :
                         ($op[2:0] == 3'b101) ? $val1 : >>2$mem ;
            
            $out [31:0] = $reset ? 32'b0 :
                          ($op[2:0] == 3'b000) ? $sum :
                          ($op[2:0] == 3'b001) ? $diff :
                          ($op[2:0] == 3'b010) ? $prod :
                          ($op[2:0] == 3'b011) ? $quot :
                          ($op[2:0] == 3'b100) ? >>2$mem : >>2$out ;
         
 ![Lab on Calculator Single Value memory Lab](https://github.com/user-attachments/assets/552cd478-1127-4150-b24f-9657f444f357)


</details>

<details>
  <summary>Assignment 8 : Building a RISC-V CPU core Micro-architecture </summary>

<details>
   <summary>Fetch and Decode </summary>

  
  ### Lab on Program Counter:

   The code is given below :
     
    \m4_TLV_version 1d: tl-x.org
    \SV
    // This code can be found in: https://github.com/stevehoover/RISC-V_MYTH_Workshop
   
    m4_include_lib(['https://raw.githubusercontent.com/BalaDhinesh/RISC-V_MYTH_Workshop/master/tlv_lib/risc-v_shell_lib.tlv'])

    \SV
    m4_makerchip_module   // (Expanded in Nav-TLV pane.)
    \TLV

    // /====================\
    // | Sum 1 to 9 Program |
    // \====================/
    //
    // Program for MYTH Workshop to test RV32I
    // Add 1,2,3,...,9 (in that order).
    //
    // Regs:
    //  r10 (a0): In: 0, Out: final sum
    //  r12 (a2): 10
    //  r13 (a3): 1..10
    //  r14 (a4): Sum
    // 
    // External to function:
    m4_asm(ADD, r10, r0, r0)             // Initialize r10 (a0) to 0.
    // Function:
    m4_asm(ADD, r14, r10, r0)            // Initialize sum register a4 with 0x0
    m4_asm(ADDI, r12, r10, 1010)         // Store count of 10 in register a2.
    m4_asm(ADD, r13, r10, r0)            // Initialize intermediate sum register a3 with 0
    // Loop:
    m4_asm(ADD, r14, r13, r14)           // Incremental addition
    m4_asm(ADDI, r13, r13, 1)            // Increment intermediate register by 1
    m4_asm(BLT, r13, r12, 1111111111000) // If a3 is less than a2, branch to label named <loop>
    m4_asm(ADD, r10, r14, r0)            // Store final result to register a0 so that it can be read by main program
   
    // Optional:
    // m4_asm(JAL, r7, 00000000000000000000) // Done. Jump to itself (infinite loop). (Up to 20-bit signed immediate plus implicit 0 bit (unlike JALR) provides byte address; last immediate bit should also be 0)
    m4_define_hier(['M4_IMEM'], M4_NUM_INSTRS)

    |cpu
      @0 
         $$clk_utkarsh = *clk;
         $reset = *reset;



      // YOUR CODE HERE
      // ...
      @0
         $pc[31:0] = >>1$reset ? 32'd0 : (>>1$pc+32'd4);
      // Note: Because of the magic we are using for visualisation, if visualisation is enabled below,
      //       be sure to avoid having unassigned signals (which you might be using for random inputs)
      //       other than those specifically expected in the labs. You'll get strange errors for these.

   
    // Assert these to end simulation (before Makerchip cycle limit).
    *passed = *cyc_cnt > 40;
    *failed = 1'b0;
   
    // Macro instantiations for:
    //  o instruction memory
    //  o register file
    //  o data memory
    //  o CPU visualization
    |cpu
      //m4+imem(@1)    // Args: (read stage)
      //m4+rf(@1, @1)  // Args: (read stage, write stage) - if equal, no register bypass is required
      //m4+dmem(@4)    // Args: (read/write stage)
      //m4+myth_fpga(@0)  // Uncomment to run on fpga

    //m4+cpu_viz(@4)    // For visualisation, argument should be at least equal to the last stage of CPU logic. @4 would work for all labs.
    \SV
    endmodule
    
![LAB FOR PC](https://github.com/user-attachments/assets/485b1ea7-c2f8-4af3-a207-39315037318e)

### Instruction Fetch

  The code is given below :
                  
        \m4_TLV_version 1d: tl-x.org
         \SV
         // This code can be found in: https://github.com/stevehoover/RISC-V_MYTH_Workshop
   
         m4_include_lib(['https://raw.githubusercontent.com/BalaDhinesh/RISC-V_MYTH_Workshop/master/tlv_lib/risc-v_shell_lib.tlv'])
  
    \SV
    m4_makerchip_module   // (Expanded in Nav-TLV pane.)
    \TLV

    // /====================\
    // | Sum 1 to 9 Program |
    // \====================/
    //
    // Program for MYTH Workshop to test RV32I
    // Add 1,2,3,...,9 (in that order).
    //
    // Regs:
    //  r10 (a0): In: 0, Out: final sum
    //  r12 (a2): 10
    //  r13 (a3): 1..10
    //  r14 (a4): Sum
    // 
    // External to function:
    m4_asm(ADD, r10, r0, r0)             // Initialize r10 (a0) to 0.
    // Function:
    m4_asm(ADD, r14, r10, r0)            // Initialize sum register a4 with 0x0
    m4_asm(ADDI, r12, r10, 1010)         // Store count of 10 in register a2.
    m4_asm(ADD, r13, r10, r0)            // Initialize intermediate sum register a3 with 0
    // Loop:
    m4_asm(ADD, r14, r13, r14)           // Incremental addition
    m4_asm(ADDI, r13, r13, 1)            // Increment intermediate register by 1
    m4_asm(BLT, r13, r12, 1111111111000) // If a3 is less than a2, branch to label named <loop>
    m4_asm(ADD, r10, r14, r0)            // Store final result to register a0 so that it can be read by main program
   
    // Optional:
    // m4_asm(JAL, r7, 00000000000000000000) // Done. Jump to itself (infinite loop). (Up to 20-bit signed immediate plus implicit 0 bit (unlike JALR) provides byte address; last immediate bit should also be 0)
    m4_define_hier(['M4_IMEM'], M4_NUM_INSTRS)

    |cpu
      @0 
         $clk_utkarsh = *clk;
         $reset = *reset;



      // YOUR CODE HERE
      // ...
      @0
         $pc[31:0] = >>1$reset ? 32'd0 : (>>1$pc+32'd4);
      @1
         $imem_rd_en = !$reset;
         $imem_rd_addr[M4_IMEM_INDEX_CNT-1:0] = $pc[M4_IMEM_INDEX_CNT+1:2];
         $instr[31:0] = $imem_rd_data[31:0];
      ?$imem_rd_en
         @1
            $imem_rd_data[31:0] = /imem[$imem_rd_addr]$instr;
      // Note: Because of the magic we are using for visualisation, if visualisation is enabled below,
      //       be sure to avoid having unassigned signals (which you might be using for random inputs)
      //       other than those specifically expected in the labs. You'll get strange errors for these.

   
    // Assert these to end simulation (before Makerchip cycle limit).
    *passed = *cyc_cnt > 40;
    *failed = 1'b0;
   
    // Macro instantiations for:
    //  o instruction memory
    //  o register file
    //  o data memory
    //  o CPU visualization
    |cpu
      m4+imem(@1)    // Args: (read stage)
      //m4+rf(@1, @1)  // Args: (read stage, write stage) - if equal, no register bypass is required
      //m4+dmem(@4)    // Args: (read/write stage)
      //m4+myth_fpga(@0)  // Uncomment to run on fpga

    m4+cpu_viz(@4)    // For visualisation, argument should be at least equal to the last stage of CPU logic. @4 would work for all labs.
    \SV
    endmodule
  
![PROGRAM COUNTER](https://github.com/user-attachments/assets/2130cf51-4af0-46b8-a081-a9fb77d1f785)

### Lab For RV Instruction Types IRSBJU Decode Logic

The code is given below :

      @0
         $pc[31:0] = >>1$reset ? 32'd0 : (>>1$pc+32'd4);
      @1
         //Instruction Fetch
         $imem_rd_en = !$reset;
         $imem_rd_addr[M4_IMEM_INDEX_CNT-1:0] = $pc[M4_IMEM_INDEX_CNT+1:2];
         $instr[31:0] = $imem_rd_data[31:0];
      ?$imem_rd_en
         @1
            $imem_rd_data[31:0] = /imem[$imem_rd_addr]$instr;
      @1
         //Instruction Decode
         $is_i_instr = $instr[6:2] ==? 5'b0000x ||
                       $instr[6:2] ==? 5'b001x0 ||
                       $instr[6:2] ==? 5'b11001 ||
                       $instr[6:2] ==? 5'b11100;
         
         $is_u_instr = $instr[6:2] ==? 5'b0x101;
         
         $is_r_instr = $instr[6:2] ==? 5'b01011 ||
                       $instr[6:2] ==? 5'b011x0 ||
                       $instr[6:2] ==? 5'b10100;
         
         $is_b_instr = $instr[6:2] ==? 5'b11000;
         
         $is_j_instr = $instr[6:2] ==? 5'b11011;
         
         $is_s_instr = $instr[6:2] ==? 5'b0100x;
         
![LAB ON INSTRUCTION IMMEDIATE DECODE](https://github.com/user-attachments/assets/b4e450a0-c978-4898-9c87-9dad33e4fca8)

###  Instruction Immidiate Decode

 The code is given below :

       $imm[31:0] = $is_i_instr ? {{21{$instr[31]}}, $instr[30:20]} :
                    $is_s_instr ? {{21{$instr[31]}}, $instr[30:25], $instr[11:7]} :
                    $is_b_instr ? {{20{$instr[31]}}, $instr[7], $instr[30:25], $instr[11:8], 1'b0} :
                    $is_u_instr ? {$instr[31:12], 12'b0} :
                    $is_j_instr ? {{12{$instr[31]}}, $instr[19:12], $instr[20], $instr[30:21], 1'b0} :
                                    32'b0;
         $rs2[4:0] = $instr[24:20];
         $rs1[4:0] = $instr[19:15];
         $rd[4:0]  = $instr[11:7];
         $opcode[6:0] = $instr[6:0];
         $func7[6:0] = $instr[31:25];
         $func3[2:0] = $instr[14:12];



![LAB ON INSTRUCTION DECODE](https://github.com/user-attachments/assets/6dac67b9-9563-4776-a5cc-38ca21e3cbe5)

### Lab To Decode Instruction Field Based

 The code is given below :
 
         $rs2_valid = $is_r_instr || $is_s_instr || $is_b_instr;
         ?$rs2_valid
            $rs2[4:0] = $instr[24:20];
            
         $rs1_valid = $is_r_instr || $is_i_instr || $is_s_instr || $is_b_instr;
         ?$rs1_valid
            $rs1[4:0] = $instr[19:15];
         
         $funct3_valid = $is_r_instr || $is_i_instr || $is_s_instr || $is_b_instr;
         ?$funct3_valid
            $funct3[2:0] = $instr[14:12];
            
         $funct7_valid = $is_r_instr ;
         ?$funct7_valid
            $funct7[6:0] = $instr[31:25];
            
         $rd_valid = $is_r_instr || $is_i_instr || $is_u_instr || $is_j_instr;
         ?$rd_valid
            $rd[4:0] = $instr[11:7];


![Lab To Decode Instruction Field Based](https://github.com/user-attachments/assets/4f08da1d-ad6d-4585-9abb-a87701553740)


### LAB ON Individual Instruction Decode

 The code is given below :

         $dec_bits [10:0] = {$funct7[5], $funct3, $opcode};
         $is_beq = $dec_bits ==? 11'bx_000_1100011;
         $is_bne = $dec_bits ==? 11'bx_001_1100011;
         $is_blt = $dec_bits ==? 11'bx_100_1100011;
         $is_bge = $dec_bits ==? 11'bx_101_1100011;
         $is_bltu = $dec_bits ==? 11'bx_110_1100011;
         $is_bgeu = $dec_bits ==? 11'bx_111_1100011;
         $is_addi = $dec_bits ==? 11'bx_000_0010011;
         $is_add = $dec_bits ==? 11'b0_000_0110011;            

![LAB ON Individual Instruction Decode](https://github.com/user-attachments/assets/976e47e5-e6a9-4528-96d7-82c3492fa269)

</details>
<details>
  <summary>Risc-V Control Logic </summary>

### Lab For Register File Read Part1 

The code is given below :

              
         $rf_wr_en = 1'b0;
         $rf_wr_index[4:0] = 5'b0;
         $rf_wr_data[31:0] = 32'b0;
         
         $rf_rd_en1 = $rs1_valid;
         $rf_rd_index1[4:0] = $rs1;
         
         $rf_rd_en2 = $rs2_valid;
         $rf_rd_index2[4:0] = $rs2;
        
 
 ![Lab For Register File Read Part1](https://github.com/user-attachments/assets/20fcb6c4-b4de-46d7-a70e-c53be5d2ad74).

 
 ### Lab For Register File Read Part-2
 
 The code is given below :

        $src1_value[31:0] = $rf_rd_data1;
        $src2_value[31:0] = $rf_rd_data2;

 
 ![Lab For Register File Read Part-2](https://github.com/user-attachments/assets/2b78000b-0ab8-4cd1-bcfa-e2e0e8dfe2a7)


### Lab For ALU Operations For add/add

The code is given below :

       $result[31:0] = $is_addi ? $src1_value + $imm :
                         $is_add ? $src1_value + $src2_value :
                         32'bx ;

![Lab For ALU Operations For add](https://github.com/user-attachments/assets/fc83eaf2-bd84-4b36-b8ef-afca0ac01c1d)

### Lab For Register File Write

The code is given below :
       
         $rf_wr_en = $rd_valid && $rd != 5'b0;
         $rf_wr_index[4:0] = $rd;
         $rf_wr_data[31:0] = $result;

![LAB FOR REGISTER FILE WRITE](https://github.com/user-attachments/assets/72cd1255-432e-48db-9723-490ea363a111)


### Lab For Implementing Branch Instructions

The code is given below :

        $taken_branch = $is_beq ? ($src1_value == $src2_value):
                         $is_bne ? ($src1_value != $src2_value):
                         $is_blt ? (($src1_value < $src2_value) ^ ($src1_value[31] != $src2_value[31])):
                         $is_bge ? (($src1_value >= $src2_value) ^ ($src1_value[31] != $src2_value[31])):
                         $is_bltu ? ($src1_value < $src2_value):
                         $is_bgeu ? ($src1_value >= $src2_value):
                                    1'b0;
         `BOGUS_USE($taken_branch)
         $br_tgt_pc[31:0] = $pc + $imm;

![LAB ON BRANCH INSTRUCTION](https://github.com/user-attachments/assets/156521b7-76ab-40a0-8293-3c5207903a37)

### Lab To Create Simple Testbench

The code is given below :

             *passed = |cpu/xreg[10]>>5$value == (1+2+3+4+5+6+7+8+9) ;


![LAB ON TESTBENCH](https://github.com/user-attachments/assets/84b0fbdd-d814-4bc8-a098-43d06cb3cfb8)
![test_bench](https://github.com/user-attachments/assets/830563df-25ff-4f77-b49d-64e15195bd8f)

</details>

</details>

<details>
  <summary>Assignment 9 : Complete Pipelined RiscV CPU Micro-architecture
 </summary>
<details>
  <summary>Pipelining the CPU</summary>
  
### Lab To Create 3-Cycle Valid Signal

The code is given below : 

         $start = >>1$reset && !$reset;
         $valid = $reset ? 1'b0 : ($start || >>3$valid);
         
To Take Care Of Invalid Cycles use code

         $valid_taken_br = $valid && $taken_branch;

To Distribute Logic

        always @* begin
    if (reset) begin
        pc = 32'b0;  // or simply 'pc = 0;' depending on your style
    end else if (valid_taken_branch) begin
        pc = br_tgt_pc;
    end else begin
        pc = pc + 32'd4;
    end
    end


</details>

<details>
  <summary>Solution to Pipeline hazard</summary>

  ### Code For Lab For Register File Bypass To Address Rd-After-Wr Hazard

  Use code

        //Register file bypass logic - data forwarding from ALU to resolve RAW dependence
         $src1_value[31:0] = ((>>1$rf_wr_en) && (>>1$rd == $rs1 )) ? (>>1$result): $rf_rd_data1; 
	 $src2_value[31:0] = ((>>1$rf_wr_en) && (>>1$rd == $rs2 )) ? (>>1$result) : $rf_rd_data2;

  ### Code For Branches To Correct The Branch Target Path
  
  Use code

        
         $valid = ~(>>1$valid_taken_br || >>2$valid_taken_br || >>1$is_load || >>2$is_load || >>2$jump_valid 	|| >>1$jump_valid);
        
         $valid_taken_br = $valid && $taken_br;
        
         $valid_load = $valid && $is_load;
        
         $jump_valid = $valid && $is_jump;
         $jal_valid  = $valid && $is_jal;
         $jalr_valid = $valid && $is_jalr;

	 $pc[31:0] = (>>1$reset) ? 32'b0 : (>>3$valid_taken_br) ? (>>3$br_tgt_pc) :  (>>3$int_pc)  ;
         //$valid = $reset ? 1'b0 : ($start) ? 1'b1 : (>>3$valid) ; no need for this

  
### Lab To Complete Instruction Decode Except Fence, Ecall, Ebreak

The code is given below : 
        
         $dec_bits[10:0] = {$func7[5], $func3, $opcode} ;
         
         $is_beq = $dec_bits ==? 11'bx_000_1100011 ;
         $is_bne = $dec_bits ==? 11'bx_001_1100011 ;
         $is_blt = $dec_bits ==? 11'bx_100_1100011 ;
         $is_bge = $dec_bits ==? 11'bx_101_1100011 ;           
         $is_bltu = $dec_bits ==? 11'bx_110_1100011 ;
         $is_bgeu = $dec_bits ==? 11'bx_111_1100011 ;  
         $is_addi = $dec_bits ==? 11'bx_000_0010011 ;
         $is_add = $dec_bits ==? 11'b0_000_0110011 ;
         $is_load = $dec_bits ==? 11'bx_xxx_0000011 ;
         $is_jump = $is_jal || $is_jalr ;
         
         `BOGUS_USE($is_beq $is_bne $is_blt $is_bge $is_bltu $is_bgeu $is_addi $is_add) 

### Lab To Code Complete ALU

The code is given below : 

        $result[31:0] = $is_addi  ? $src1_value +  $imm :
                         $is_add   ? $src1_value +  $src2_value :
                         $is_andi  ? $src1_value &  $imm :
                         $is_ori   ? $src1_value |  $imm :
                         $is_xori  ? $src1_value ^  $imm :
                         $is_slli  ? $src1_value << $imm[5:0]:
                         $is_srli  ? $src1_value >> $imm[5:0]:
                         $is_and   ? $src1_value &  $src2_value:
                         $is_or    ? $src1_value |  $src2_value:
                         $is_xor   ? $src1_value ^  $src2_value:
                         $is_sub   ? $src1_value -  $src2_value:
                         $is_sll   ? $src1_value << $src2_value:
                         $is_srl   ? $src1_value >> $src2_value:
                         $is_sltu  ? $sltu_rslt[31:0]:
                         $is_sltiu ? $sltiu_rslt[31:0]:
                         $is_lui   ? {$imm[31:12], 12'b0}:
                         $is_auipc ? $pc + $imm:
                         $is_jal   ? $pc + 4:
                         $is_jalr  ? $pc + 4:
                         $is_srai  ? ({ {32{$src1_value[31]}} , $src1_value} >> $imm[4:0]) :
                         $is_slt   ? (($src1_value[31] == $src2_value[31]) ? $sltu_rslt : {31'b0, $src1_value[31]}):
                         $is_slti  ? (($src1_value[31] == $imm[31]) ? $sltiu_rslt : {31'b0, $src1_value[31]}) :
                         $is_sra   ? ({ {32{$src1_value[31]}}, $src1_value} >> $src2_value[4:0]) :
                         $is_load  ? $src1_value +  $imm :
                         $is_s_instr ? $src1_value + $imm :
                                    32'bx;


</details>

<details>
  <summary>Load/Store Instructions and Completing RISC-V CPU
</summary>
  
### Lab To Redirect Loads

The code is given below : 

         $rf_rd_en1 = $rs1_valid && >>2$result ;
         $rf_rd_index1[4:0] = $rs1 ;
         $rf_rd_en2 = $rs2_valid && >>2$result;
         $rf_rd_index2[4:0] = $rs2 ;

### Lab To Instantiate Data Memory To The CPU

 The code is given below : 
        uncomment on MACROS

     |cpu
      m4+imem(@1)    // Args: (read stage)
      m4+rf(@2, @3)  // Args: (read stage, write stage) - if equal, no register bypass is required
      m4+dmem(@4)    // Args: (read/write stage)

    m4+cpu_viz(@4)    // For visualisation, argument should be at least equal to the last stage of CPU logic. @4 would work for all labs.

         $dmem_wr_en = $is_s_instr && $valid ;
         $dmem_addr[3:0] = $result[5:2] ;
         $dmem_wr_data[31:0] = $src2_value ;
         $dmem_rd_en = $is_load ;

### Lab To Add Stores And Loads To The Test Program

Add the code given below in loop :

          m4_asm(SW, r0, r10, 100)
          m4_asm(LW, r15, r0, 100)

### Add Control Logic For Jump Instructions
The code is given below : 

         $jalr_tgt_pc[31:0] = $imm[31:0] + $src1_value[31:0]; 

## Final Stage Pipelined Logic         

  The code is given below : 

```
\m4_TLV_version 1d: tl-x.org
\SV
   // Template code can be found in: https://github.com/stevehoover/RISC-V_MYTH_Workshop
   
   m4_include_lib(['https://raw.githubusercontent.com/BalaDhinesh/RISC-V_MYTH_Workshop/master/tlv_lib/risc-v_shell_lib.tlv'])

\SV
   m4_makerchip_module   // (Expanded in Nav-TLV pane.)
\TLV

   // /====================\
   // | Sum 1 to 9 Program |
   // \====================/
   //
   // Add 1,2,3,...,9 (in that order).
   //
   // Regs:
   //  r10 (a0): In: 0, Out: final sum
   //  r12 (a2): 10
   //  r13 (a3): 1..10
   //  r14 (a4): Sum
   // 
   // External to function:
   m4_asm(ADD, r10, r0, r0)             // Initialize r10 (a0) to 0.
   // Function:
   m4_asm(ADD, r14, r10, r0)            // Initialize sum register a4 with 0x0
   m4_asm(ADDI, r12, r10, 1010)         // Store count of 10 in register a2.
   m4_asm(ADD, r13, r10, r0)            // Initialize intermediate sum register a3 with 0
   // Loop:
   m4_asm(ADD, r14, r13, r14)           // Incremental addition
   m4_asm(ADDI, r13, r13, 1)            // Increment intermediate register by 1
   m4_asm(BLT, r13, r12, 1111111111000) // If a3 is less than a2, branch to label named <loop>
   m4_asm(ADD, r10, r14, r0)            // Store final result to register a0 so that it can be read by main program
   m4_asm(SW, r0, r10, 10000)           // Store r10 result in dmem
   m4_asm(LW, r17, r0, 10000)           // Load contents of dmem to r17
   m4_asm(JAL, r7, 00000000000000000000) // Done. Jump to itself (infinite loop). (Up to 20-bit signed immediate plus implicit 0 bit (unlike JALR) provides byte address; last immediate bit should also be 0)
   m4_define_hier(['M4_IMEM'], M4_NUM_INSTRS)

   |cpu
      @0
         $clk_utkars = *clk;
         $reset = *reset;
         
         //PC fetch - branch, jumps and loads introduce 2 cycle bubbles in this pipeline
         $pc[31:0] = >>1$reset ? '0 : (>>3$valid_taken_br ? >>3$br_tgt_pc :
                                       >>3$valid_load     ? >>3$inc_pc[31:0] :
                                       >>3$jal_valid      ? >>3$br_tgt_pc :
                                       >>3$jalr_valid     ? >>3$jalr_tgt_pc :
                                                     (>>1$inc_pc[31:0]));
         // Access instruction memory using PC
         $imem_rd_en = ~ $reset;
         $imem_rd_addr[M4_IMEM_INDEX_CNT-1:0] = $pc[M4_IMEM_INDEX_CNT+1:2];
         
         
      @1
         //Getting instruction from IMem
         $instr[31:0] = $imem_rd_data[31:0];
         
         //Increment PC
         $inc_pc[31:0] = $pc[31:0] + 32'h4;
         
         //Decoding I,R,S,U,B,J type of instructions based on opcode [6:0]
         //Only [6:2] is used here because this implementation is for RV64I which does not use [1:0]
         $is_i_instr = $instr[6:2] ==? 5'b0000x ||
                       $instr[6:2] ==? 5'b001x0 ||
                       $instr[6:2] == 5'b11001;
         
         $is_r_instr = $instr[6:2] == 5'b01011 ||
                       $instr[6:2] ==? 5'b011x0 ||
                       $instr[6:2] == 5'b10100;
         
         $is_s_instr = $instr[6:2] ==? 5'b0100x;
         
         $is_u_instr = $instr[6:2] ==? 5'b0x101;
         
         $is_b_instr = $instr[6:2] == 5'b11000;
         
         $is_j_instr = $instr[6:2] == 5'b11011;
         
         //Immediate value decode
         $imm[31:0] = $is_i_instr ? { {21{$instr[31]}} , $instr[30:20]} :
                      $is_s_instr ? { {21{$instr[31]}} , $instr[30:25] , $instr[11:8] , $instr[7]} :
                      $is_b_instr ? { {20{$instr[31]}} , $instr[7] , $instr[30:25] , $instr[11:8] , 1'b0} :
                      $is_u_instr ? { $instr[31] , $instr[30:12] , { 12{1'b0}} } :
                      $is_j_instr ? { {12{$instr[31]}} , $instr[19:12] , $instr[20] , $instr[30:21] , 1'b0} :
                      >>1$imm[31:0];
         
         //Generate valid signals for each instruction fields
         $rs1_or_funct3_valid    = $is_r_instr || $is_i_instr || $is_s_instr || $is_b_instr;
         $rs2_valid              = $is_r_instr || $is_s_instr || $is_b_instr;
         $rd_valid               = $is_r_instr || $is_i_instr || $is_u_instr || $is_j_instr;
         $funct7_valid           = $is_r_instr;
         
         //Decode other fields of instruction - source and destination registers, funct, opcode
         ?$rs1_or_funct3_valid
            $rs1[4:0]    = $instr[19:15];
            $funct3[2:0] = $instr[14:12];
         
         ?$rs2_valid
            $rs2[4:0]    = $instr[24:20];
         
         ?$rd_valid
            $rd[4:0]     = $instr[11:7];
         
         ?$funct7_valid
            $funct7[6:0] = $instr[31:25];
         
         $opcode[6:0] = $instr[6:0];
         
         //Decode instruction in subset of base instruction set based on RISC-V 32I
         $dec_bits[10:0] = {$funct7[5],$funct3,$opcode};
         
         //Branch instructions
         $is_beq   = $dec_bits ==? 11'bx_000_1100011;
         $is_bne   = $dec_bits ==? 11'bx_001_1100011;
         $is_blt   = $dec_bits ==? 11'bx_100_1100011;
         $is_bge   = $dec_bits ==? 11'bx_101_1100011;
         $is_bltu  = $dec_bits ==? 11'bx_110_1100011;
         $is_bgeu  = $dec_bits ==? 11'bx_111_1100011;
         
         //Jump instructions
         $is_auipc = $dec_bits ==? 11'bx_xxx_0010111;
         $is_jal   = $dec_bits ==? 11'bx_xxx_1101111;
         $is_jalr  = $dec_bits ==? 11'bx_000_1100111;
         
         //Arithmetic instructions
         $is_addi  = $dec_bits ==? 11'bx_000_0010011;
         $is_add   = $dec_bits ==  11'b0_000_0110011;
         $is_lui   = $dec_bits ==? 11'bx_xxx_0110111;
         $is_slti  = $dec_bits ==? 11'bx_010_0010011;
         $is_sltiu = $dec_bits ==? 11'bx_011_0010011;
         $is_xori  = $dec_bits ==? 11'bx_100_0010011;
         $is_ori   = $dec_bits ==? 11'bx_110_0010011;
         $is_andi  = $dec_bits ==? 11'bx_111_0010011;
         $is_slli  = $dec_bits ==? 11'b0_001_0010011;
         $is_srli  = $dec_bits ==? 11'b0_101_0010011;
         $is_srai  = $dec_bits ==? 11'b1_101_0010011;
         $is_sub   = $dec_bits ==? 11'b1_000_0110011;
         $is_sll   = $dec_bits ==? 11'b0_001_0110011;
         $is_slt   = $dec_bits ==? 11'b0_010_0110011;
         $is_sltu  = $dec_bits ==? 11'b0_011_0110011;
         $is_xor   = $dec_bits ==? 11'b0_100_0110011;
         $is_srl   = $dec_bits ==? 11'b0_101_0110011;
         $is_sra   = $dec_bits ==? 11'b1_101_0110011;
         $is_or    = $dec_bits ==? 11'b0_110_0110011;
         $is_and   = $dec_bits ==? 11'b0_111_0110011;
         
         //Store instructions
         $is_sb    = $dec_bits ==? 11'bx_000_0100011;
         $is_sh    = $dec_bits ==? 11'bx_001_0100011;
         $is_sw    = $dec_bits ==? 11'bx_010_0100011;
         
         //Load instructions - support only 4 byte load
         $is_load  = $dec_bits ==? 11'bx_xxx_0000011;
         
         $is_jump = $is_jal || $is_jalr;
         
      @2
         //Get Source register values from reg file
         $rf_rd_en1 = $rs1_or_funct3_valid;
         $rf_rd_en2 = $rs2_valid;
         
         $rf_rd_index1[4:0] = $rs1[4:0];
         $rf_rd_index2[4:0] = $rs2[4:0];
         
         //Register file bypass logic - data forwarding from ALU to resolve RAW dependence
         $src1_value[31:0] = $rs1_bypass ? >>1$result[31:0] : $rf_rd_data1[31:0];
         $src2_value[31:0] = $rs2_bypass ? >>1$result[31:0] : $rf_rd_data2[31:0];
         
         //Branch target PC computation for branches and JAL
         $br_tgt_pc[31:0] = $imm[31:0] + $pc[31:0];
         
         //RAW dependence check for ALU data forwarding
         //If previous instruction was writing to reg file, and current instruction is reading from same register
         $rs1_bypass = >>1$rf_wr_en && (>>1$rd == $rs1);
         $rs2_bypass = >>1$rf_wr_en && (>>1$rd == $rs2);
         
      @3
         //ALU
         $result[31:0] = $is_addi  ? $src1_value +  $imm :
                         $is_add   ? $src1_value +  $src2_value :
                         $is_andi  ? $src1_value &  $imm :
                         $is_ori   ? $src1_value |  $imm :
                         $is_xori  ? $src1_value ^  $imm :
                         $is_slli  ? $src1_value << $imm[5:0]:
                         $is_srli  ? $src1_value >> $imm[5:0]:
                         $is_and   ? $src1_value &  $src2_value:
                         $is_or    ? $src1_value |  $src2_value:
                         $is_xor   ? $src1_value ^  $src2_value:
                         $is_sub   ? $src1_value -  $src2_value:
                         $is_sll   ? $src1_value << $src2_value:
                         $is_srl   ? $src1_value >> $src2_value:
                         $is_sltu  ? $sltu_rslt[31:0]:
                         $is_sltiu ? $sltiu_rslt[31:0]:
                         $is_lui   ? {$imm[31:12], 12'b0}:
                         $is_auipc ? $pc + $imm:
                         $is_jal   ? $pc + 4:
                         $is_jalr  ? $pc + 4:
                         $is_srai  ? ({ {32{$src1_value[31]}} , $src1_value} >> $imm[4:0]) :
                         $is_slt   ? (($src1_value[31] == $src2_value[31]) ? $sltu_rslt : {31'b0, $src1_value[31]}):
                         $is_slti  ? (($src1_value[31] == $imm[31]) ? $sltiu_rslt : {31'b0, $src1_value[31]}) :
                         $is_sra   ? ({ {32{$src1_value[31]}}, $src1_value} >> $src2_value[4:0]) :
                         $is_load  ? $src1_value +  $imm :
                         $is_s_instr ? $src1_value + $imm :
                                    32'bx;
         
         $sltu_rslt[31:0]  = $src1_value <  $src2_value;
         $sltiu_rslt[31:0] = $src1_value <  $imm;
         
         //Jump instruction target PC computation
         $jalr_tgt_pc[31:0] = $imm[31:0] + $src1_value[31:0]; 
         
         //Branch resolution
         $taken_br = $is_beq ? ($src1_value == $src2_value) :
                     $is_bne ? ($src1_value != $src2_value) :
                     $is_blt ? (($src1_value < $src2_value) ^ ($src1_value[31] != $src2_value[31])) :
                     $is_bge ? (($src1_value >= $src2_value) ^ ($src1_value[31] != $src2_value[31])) :
                     $is_bltu ? ($src1_value < $src2_value) :
                     $is_bgeu ? ($src1_value >= $src2_value) :
                     1'b0;
         
         //Current instruction is valid if one of the previous 2 instructions were not (taken_branch or load or jump)
         $valid = ~(>>1$valid_taken_br || >>2$valid_taken_br || >>1$is_load || >>2$is_load || >>2$jump_valid || >>1$jump_valid);
         
         //Current instruction is valid & is a taken branch
         $valid_taken_br = $valid && $taken_br;
         
         //Current instruction is valid & is a load
         $valid_load = $valid && $is_load;
         
         //Current instruction is valid & is jump
         $jump_valid = $valid && $is_jump;
         $jal_valid  = $valid && $is_jal;
         $jalr_valid = $valid && $is_jalr;
         
         //Destination register update - ALU result or load result depending on instruction
         $rf_wr_en = (($rd != '0) && $rd_valid && $valid) || >>2$valid_load;
         $rf_wr_index[4:0] = $valid ? $rd[4:0] : >>2$rd[4:0];
         $rf_wr_data[31:0] = $valid ? $result[31:0] : >>2$ld_data[31:0];
         
      @4
         //Data memory access for load, store
         $dmem_addr[3:0]     =  $result[5:2];
         $dmem_wr_en         =  $valid && $is_s_instr;
         $dmem_wr_data[31:0] =  $src2_value[31:0];
         $dmem_rd_en         =  $valid_load;
         
      
         //Write back data read from load instruction to register
         $ld_data[31:0]      =  $dmem_rd_data[31:0];
         
      
      

      // Note: Because of the magic we are using for visualisation, if visualisation is enabled below,
      //       be sure to avoid having unassigned signals (which you might be using for random inputs)
      //       other than those specifically expected in the labs. You'll get strange errors for these.

   
   // Assert these to end simulation (before Makerchip cycle limit).
   //Checks if sum of numbers from 1 to 9 is obtained in reg[17] and runs 10 cycles extra after this is met
   *passed = |cpu/xreg[17]>>10$value == (1+2+3+4+5+6+7+8+9);
   //Run for 200 cycles without any checks
   //*passed = *cyc_cnt > 200;
   *failed = 1'b0;
   
   // Macro instantiations for:
   //  o instruction memory
   //  o register file
   //  o data memory
   //  o CPU visualization
   |cpu
      m4+imem(@1)    // Args: (read stage)
      m4+rf(@2, @3)  // Args: (read stage, write stage) - if equal, no register bypass is required
      m4+dmem(@4)    // Args: (read/write stage)
   
   m4+cpu_viz(@4)    // For visualisation, argument should be at least equal to the last stage of CPU logic
                       // @4 would work for all labs
\SV
   endmodule
```

![final wave1](https://github.com/user-attachments/assets/0267f49d-48f9-41b8-8fba-8933057e1b62)


 ##### The following image shows the clock signal which contains my name clk_utkarsh
 ![clk](https://github.com/user-attachments/assets/83e08dc2-b045-437e-b25a-a1c7d00685f5)
 ##### The following image shows the reset signal
 ![reset](https://github.com/user-attachments/assets/b0dc59a4-67ac-4d13-83b3-98a967af5f7f)
 ##### The following image shows the gradual addition of the in the r14 register
 ![final wave](https://github.com/user-attachments/assets/11e1a445-236f-4a31-90dd-f31f5215c4aa)

 
 #### Final RISCV Diagram
 ![final riscv](https://github.com/user-attachments/assets/9ea6938a-c7b6-489e-8c25-aeb49ef9ab20)
 ![riscv final](https://github.com/user-attachments/assets/76429877-8e4c-4480-b440-5c2349da5be2)

</details>


</details>

## The Sandpiper-SaaS compiler will be used to convert TLV (Target Level Verilog) into Verilog. After this conversion, pre-synthesis simulations will be performed using the GTKWave simulator to validate the design.
<details>
  <summary>Assignment 10 : The Sandpiper-SaaS compiler will convert TLV to Verilog, and then GTKWave will be used for pre-synthesis simulation to verify the design. </summary>
	
### Step-by-Step Procedure:

- #### Install Required Packages: Begin by installing the necessary packages using pip:
```
python3-pip git iverilog gtkwave

cd ~

sudo apt-get install python3-venv

python3 -m venv .venv

source ~/.venv/bin/activate

pip3 install pyyaml click sandpiper-saas

```
- #### Clone the github repo: clone this repo containing VSDBabySoC design files and testbench. Move into the VSDBabySoc directory
```
git clone https://github.com/manili/VSDBabySoC.git
cd VSDBabySoc

```
- #### Replace the rvmyth.tlv file in the VSDBabySoC Directory: replace in src/module with the rvmth.tlv.

- #### Convert .tlv to .v using converter:
```
sandpiper-saas -i ./src/module/*.tlv -o rvmyth.v --bestsv --noline -p verilog --outdir ./src/module/
```
![im](https://github.com/user-attachments/assets/cd2a6d05-a0c8-4bfd-9065-ef8c81e52277)

- #### Make the pre_synth_sim.vcd: We will create the pre_synth_sim.vcd by running the following command
```
make pre_synth_sim
```
![a3](https://github.com/user-attachments/assets/4dc1a0a4-52e7-42ff-9c08-a004b9d0abd4)

The result of the simulation i.e the pre_synth_sim.vcd will be stored in the output/pre_synth_sim directory

- #### Now to compile and simulate RISC-V design run the following code: To compile and simulate vsdbabysoc design.

```
iverilog -o output/pre_synth_sim.out -DPRE_SYNTH_SIM src/module/testbench.v -I src/include -I src/module
```
```
cd output
./pre_synth_sim.out
```
![a2](https://github.com/user-attachments/assets/05a78a11-85a8-4c55-bf80-5e4a4e43d531)

To generate pre_synth_sim.vcd file,which is our simulation waveform file.

- #### To open the Simulation file in gtkwave tool: To do so run the follwowing command
```
gtkwave pre_synth_sim.vcd
```
![a1](https://github.com/user-attachments/assets/c929ed52-cb5c-4ec2-9b64-4aaa4a4f5d88)

- #### The following diagram contains:-
- clk_utkarsh: This is the clock input to the RISC-V core.
- reset: This is the input reset signal to the RISC-V core.
- OUT[9:0]: This is the 10-bit output [9:0] OUT port of the RISC-V core. This port comes from the RISC-V register #14, originally.
  
- ##### Clk(clk_utkarsh) shown as below:
![clk](https://github.com/user-attachments/assets/bc7dca9c-1877-41f6-954e-41d6847936b6)

- ##### Reset shown as below:
![rset](https://github.com/user-attachments/assets/4fb228fa-3e12-429e-8601-09a2f629d2b5)

- ##### Sum output of 1+2+3+4+5+6+7+8+9
![op](https://github.com/user-attachments/assets/b0d6a723-366c-4103-b19c-30619712e1f3)
![output](https://github.com/user-attachments/assets/709666dd-fa55-4d23-84a6-82a8445e404a)
![output2](https://github.com/user-attachments/assets/b9992a69-52c0-44aa-87f3-c908102a7ddd)

###### Makerchip IDE simulation results for comparison
 ![final wave](https://github.com/user-attachments/assets/9bf791d2-3879-4b6a-8c5d-a6fd4d3d245e)


  </details>

## Addition of Peripherals to convert the Digital output to analog output using DAC and PLL

<details>
  <summary>Assignment 11 : </summary>

In this assignment we are adding two peripherals to convert the digital output to the analog output namely PLL and DAC.

- Phase locked loop:- The crystal oscillator present on the board is capable of giving a clock of frequency between 12 - 20 MHZ. The processor operates at frequency near 100MHZ and thus we need an IP/Peripheral to convert this low frequency clock to a high frequency clock. Here the PLL comes into picture. The input to the PLL is the crystal oscillator clock and returns a high frequency clock to our risc v core. This clock is then appended by my name CPU_clk_utk_a0.
- Digital to Analog Converter:- The processor works with digital input but we transmit or receive signals in analog form. So in order to convert the digital signal in our risc v core to analog signal we are using the digital to analog converter IP.
Commands used to run the rvmyth.v file
```
iverilog -o ./pre_synth_sim.out -DPRE_SYNTH_SIM src/module/testbench.v -I src/include -I src/module/
```
After this we dump the ./pre_synth_sim.out file to create the .vcd file using the following command
```
./pre_synth_sim.out
```
We then run this .vcd file on gtkwave to observe the output
```
gtkwave pre_synth_sim.vcd
```
The above process has been executed by me in the following way

 ![asic2](https://github.com/user-attachments/assets/c7ad1f1c-d870-47d4-bb7f-22b4839b6aa8)

The output of the above code is as follows:-

![asic4](https://github.com/user-attachments/assets/63831f41-abff-4ac9-bf7e-f6ed46e96dfe)
![asic5](https://github.com/user-attachments/assets/186433c5-4916-4e90-a369-1eeb9d1fe282)

- Yosys installation for next lab.
  ![asic yosys](https://github.com/user-attachments/assets/6472d5ad-fc24-4c48-9fb0-2c0cb6e55031)

  </details>

 ## RTL design using Verilog with SKY130 Technology
<details>
  <summary>Assignment 12  </summary>

#### A simulator is utilized to verify if a design meets its intended specifications by simulating the associated code. The simulator monitors input signal changes, and when an input change occurs, it re-evaluates the corresponding output. RTL (Register Transfer Level) design refers to the Verilog code that models the behavior of a digital circuit. To validate this design, a testbench is developed, which is then simulated using Icarus Verilog. During the simulation, a VCD (Value Change Dump) file is created. This file is analyzed with GTKWave, a tool that allows users to load, inspect, and visualize waveforms generated during the simulation. By viewing these waveforms, users can examine signal interactions, verify timing relationships, and ensure that the circuit operates as intended.

#### This flow leverages Icarus Verilog for simulation and GTKWave for debugging and waveform analysis.
![Screenshot 2024-10-16 181840](https://github.com/user-attachments/assets/3c6ac45e-f7a9-4675-9d30-946af1de9dc9)

![Screenshot 2024-10-16 175423](https://github.com/user-attachments/assets/28f296d7-f8a6-4786-9808-a9d4134c4fdf)

<details>
  <summary> DAY : 1 </summary>
	
#### Initial step shown :

##### Enter the following commands in the Ubuntu terminal as depicted in the screenshot
```
sudo -i
sudo apt-get install git
ls
cd /home

git clone https://github.com/kunalg123/sky130RTLDesignAndSynthesisWorkshop.git
cd sky130RTLDesignAndSynthesisWorkshop/verilog_files
ls
```
![Screenshot 2024-10-16 162418](https://github.com/user-attachments/assets/7523ed1d-8913-407d-884e-22481890439b)

##### We can observe the list of files present in the directory.
![directory](https://github.com/user-attachments/assets/d4867166-6f4b-4dc9-a5f8-7f14771686c9)

##### Introduction to iverilog and GTKWave: This tutorial involved learning about how to simulate the design and testbench for a 2x1 multiplexer, using iverilog, and displaying the waveform on GTKWave.
![Screenshot 2024-10-16 164046](https://github.com/user-attachments/assets/609603da-f7b1-4d49-ba43-40fe4cef21f3)
![Screenshot 2024-10-16 164303](https://github.com/user-attachments/assets/77381fef-b936-4434-a147-71b4b54043c7)

##### //Design 
```
module good_mux (input i0, input i1, input sel, output reg y);
    always@(*)
    begin
    	if(sel)
  		y<=i1;
  	else
  		y<=i0;
    end
endmodule
//Testbench
module tb_good_mux;
  reg i0,i1,sel;
  wire y;

   	good_mux uut(.sel(sel),.i0(i0),.i1(i1),.y(y));

  initial begin
  	$dumpfile("tb_good_mux.vcd");
  	$dumpvars(0,tb_good_mux);
  	sel=0;
  	i0=0;
  	i1=0;
  	#300 $finish;
  end
  always #75 sel = ~sel;
  always #10 i0 = ~i0;
  always #55 i1 = ~i1;
endmodule
```
- ##### Introduction to Yosys: This tutorial involved the use of Yosys for synthesising the design we created in Verilog, viewing its netlists and the cells that are generated for the purpose of creating the circuit. The following commands are used:

  ```
  1. yosys
  2. read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
  3. read_verilog good_mux.v
  4. synth -top good_mux
  5. abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
  6. show
  7. write_verilog -noattr good_mux_netlist.v
  8. gvim good_mux_netlist.v
  ```
1. Opens Yosys Tool
2. Reads the technology library file (Liberty format) required for synthesis using the specified path.
3. Loads the Verilog file good_mux.v for synthesis.
4. Performs synthesis on the design, with good_mux as the top module.
5. Optimizes the synthesized design using the ABC tool and the specified technology library.
6. Displays the synthesized design as a schematic.
7. Writes the synthesized netlist to the file good_mux_netlist.v without attributes.
8. Opens the netlist file good_mux_netlist.v in the gvim text editor.
![y1](https://github.com/user-attachments/assets/090a4183-d355-416d-8ecf-59f1487236e9)
![y2](https://github.com/user-attachments/assets/509b1983-f53c-4866-a73f-57e0f965523b)
![y3](https://github.com/user-attachments/assets/1f70d5de-b2a1-4de6-bd87-ee101c803dd6)
![y4](https://github.com/user-attachments/assets/284a7408-3a55-4cd2-8e84-3bc1c40a26a8)
![y5](https://github.com/user-attachments/assets/15567dd8-db47-4819-a0f6-e1a97a7e6351)
![y6](https://github.com/user-attachments/assets/7c5f4f34-5678-41bc-a0e2-8ba2416d1d95)
![y7](https://github.com/user-attachments/assets/777c1880-bffb-4892-bd22-a49fef1d620a)
![y8](https://github.com/user-attachments/assets/ffd112cc-06c6-4e88-9909-83137dc80cec)
![y9](https://github.com/user-attachments/assets/e36f9129-0cbc-43c9-8783-687f4ad29a6b)

</details>

<details>
  <summary> DAY : 2 </summary>

 - #### Yosys Synthesis for Multiple Modules: This tutorial involved the synthesis of a design file that has more than one module.

```
//Design

module sub_module2 (input a, input b, output y);
	assign y = a | b;
endmodule

module sub_module1 (input a, input b, output y);
	assign y = a&b;
endmodule

module multiple_modules (input a, input b, input c, output y);
	wire net1;
	sub_module1 u1(.a(a),.b(b),.y(net1)); //net1 = a&b
	sub_module2 u2(.a(net1),.b(c),.y(y)); //y = netic,ie y = a&b + c;
endmodule
```
```
1. yosys
2. read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
3. read_verilog multiple_modules.v
4. synth -top multiple_modules
5. abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
6. show
7. write_verilog -noattr multiple_modules_netlist.v
8. gvim multiple_modules_netlist.v
```
```
//Generated Netlist
module multiple_modules (a, b, c, y);
	input a; wire a;
	input b; wire b;
	input c; wire c;
	wire net1;
	output y; wire y;

	sub_modulel ul (.a(a),.b(b),.y(net1));
	sub_module2 u2 (.a(net1),.b(c),.y (y));
endmodule

module sub_modulel (a, b, y);
	wire _0_;
	wire _1_;
	wire _2_;
	input a; wire a;
	input b; wire b;
	output y; wire y;
	
	sky130_fd_sc_hd_and2_0_3_(.A(_1_),.B(_0_),.X(_2_));
	
	assign _1_ = b;
	assign _0_ = a;
	assign y = _2_;
endmodule

module sub_module2 (a, b, y);
	wire _0_;
	wire _1_;
	wire _2_;
	input a; wire a;
	input b; wire b;
	output y;wire y;

	sky130_fd_sc_hd_or2_0_3_ (A(_1_), .B( 0 ), .X( 2 ));
	assign _1_ = b;
	assign _0_ = a;
	assign y = _2_;
endmodule
```
![y10](https://github.com/user-attachments/assets/eae38cd0-52c5-498f-8cd1-3130a5a4fb93)
![y11](https://github.com/user-attachments/assets/2bfb3a25-2d5e-4829-a8f5-2af00f8cfdd6)
![y12](https://github.com/user-attachments/assets/4dc80f51-8b4e-41e5-acab-a52f5d616f9e)
![y13](https://github.com/user-attachments/assets/2e0c7a01-186c-4c0f-badf-2708944ae050)
![y14](https://github.com/user-attachments/assets/da0670b3-5897-4b30-814c-b321cad11db3)
![y15](https://github.com/user-attachments/assets/e6e826c3-b160-4852-8489-15d4239f178a)

Use of Flattening: Merges all hierarchical modules in the design into a single module to create a flat netlist. 
```
   1. yosys 
   2. read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
3. read_verilog multiple_modules.v
4. synth -top multiple_modules
5. abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
6. flatten
7. show
8. write_verilog -noattr multiple_modules_netlist.v 9. gvim multiple_modules_netlist.v
```
 ```
//Generated Netlist
module multiple_modules (a, b, c, y);
	wire _0_; wire _1_;
	wire _2_; wire _3_;
	wire _4_; wire _5_;
	input a; wire a;
	input b; wire b;
	input c; wire c;
	wire net1;
	wire \ul.a;
	wire \ul.b;
	wire \ul.y;
	wire \u2.a;
	wire \u2.b;
	wire \u2.y;
	output y; wire y;
	
	sky130_fd_sc_hd_and2_0 _6_ (.A(1),.B(0),.X(_2_));
	sky130_fd_sc_hd_or2_0 _7_(.A(4),.B(_3_),.X(5));

	assign 4 = \u2.b ;
	assign 3 = \u2.a ;
	assign \u2.y = _5_;
	assign \u2.a = net1;
	assign \u2.b = c;
	assign y = \u2.y;
	assign 1 = \u1.b;
	assign 0 = \ul.a ;
	assign \ul.y = _2_;
	assign \ul.a = a;
	assign \u1.b = b;
	assign net1 = \u1.y;
endmodule
```
![y16](https://github.com/user-attachments/assets/d84a1d22-1614-41aa-82c4-08ada769a52d)
![y17](https://github.com/user-attachments/assets/7d70bae6-45a2-4a34-9fed-f4e3c5ee3edb)
![y18](https://github.com/user-attachments/assets/867411d2-e61a-4463-a19e-70fabb140612)
![y19](https://github.com/user-attachments/assets/3ef0d11e-c194-462c-9e2d-8829d9660831)
![y20](https://github.com/user-attachments/assets/bc4f0b09-133c-4bcc-ac39-ee0acf7a8a21)
![y21](https://github.com/user-attachments/assets/f6c2b9f5-4d51-47b2-b87b-5977fd6334fa)
![y22](https://github.com/user-attachments/assets/b050f3ac-7cca-47aa-adf3-89193fe82e19)
![y23](https://github.com/user-attachments/assets/bc6168e4-1d2d-46df-9f29-4421eb9d751b)

```
   1. yosys 
   2. read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
3. read_verilog multiple_modules.v
4. synth -top multiple_modules
5. abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

6. show
7. write_verilog -noattr multiple_modules_netlist.v 9. gvim multiple_modules_netlist.v
```

![y24](https://github.com/user-attachments/assets/42bd8c4f-2b88-429c-aea2-06c8ec13edb7)
![y25](https://github.com/user-attachments/assets/3b056f4b-587a-43f3-b3a8-7a9f03ce1a4e)
![y26](https://github.com/user-attachments/assets/918ca932-5f1e-477f-975e-457881e50c02)
![y27](https://github.com/user-attachments/assets/b26a10fc-8e69-4469-ab20-9302e517f8c7)

Simulation of D-Flipflop using Iverilog and GTKWave: Performed simulations for 3 types of D-Flipflops - Asynchronous Reset, Asynchronous Set and Synchronous Reset.
Asynchronous Reset

```
iverilog dff_asyncres.v tb_dff_asyncres.v
./a.out
gtkwave tb_dff_asyncres.vcd
```
```
//Design
module dff_asyncres(input clk, input async_reset, input d, output reg q);
	always@(posedge clk, posedge async_reset)
	begin
		if(async_reset)
			q <= 1'b0;
		else
			q <= d;
	end
endmodule
```
```
//Testbench
module tb_dff_asyncres; 
	reg clk, async_reset, d;
	wire q;
	dff_asyncres uut (.clk(clk),.async_reset (async_reset),.d(d),.q(q));

	initial begin
		$dumpfile("tb_dff_asyncres.vcd");
		$dumpvars(0,tb_dff_asyncres);
		// Initialize Inputs
		clk = 0;
		async_reset = 1;
		d = 0;
		#3000 $finish;
	end
		
	always #10 clk = ~clk;
	always #23 d = ~d;
	always #547 async_reset=~async_reset; 
endmodule
```
![y28](https://github.com/user-attachments/assets/71de149a-74d7-4ddd-95c1-adacb5e3bf18)
![y29](https://github.com/user-attachments/assets/fc2d890e-a8df-426e-81b4-d69ac37e85ea)

Asynchronous Set

```
iverilog dff_async_set.v tb_dff_async_set.v
./a.out
gtkwave tb_dff_async_set.vcd
```
```
//Design
module dff_async_set(input clk, input async_set, input d, output reg q);
	always@(posedge clk, posedge async_set)
	begin
		if(async_set)
			q <= 1'b1;
		else
			q <= d;
	end
endmodule
```
```
//Testbench
module tb_dff_async_set; 
	reg clk, async_set, d;
	wire q;
	dff_async_set uut (.clk(clk),.async_set (async_set),.d(d),.q(q));

	initial begin
		$dumpfile("tb_dff_async_set.vcd");
		$dumpvars(0,tb_dff_async_set);
		// Initialize Inputs
		clk = 0;
		async_set = 1;
		d = 0;
		#3000 $finish;
	end
		
	always #10 clk = ~clk;
	always #23 d = ~d;
	always #547 async_set=~async_set; 
endmodule
```
![y30](https://github.com/user-attachments/assets/a9097603-8ef9-4edb-9427-3c8723c59e0e)
![y31](https://github.com/user-attachments/assets/efac233e-9eae-4a21-8cc9-fa175fd4a73d)

From the waveform, it can be observed that the Q output changes to one when the asynchronous set is set high, independent of the positive/negative clock edge.

Synchronous Reset
```
iverilog dff_syncres.v tb_dff_syncres.v
./a.out
gtkwave tb_dff_syncres.vcd
```
```
//Design
module dff_syncres(input clk, input sync_reset, input d, output reg q);
	always@(posedge clk)
	begin
		if(sync_reset)
			q <= 1'b0;
		else
			q <= d;
	end
endmodule
```
```
//Testbench
module tb_dff_syncres; 
	reg clk, syncres, d;
	wire q;
	dff_asyncres uut (.clk(clk),.sync_reset (sync_reset),.d(d),.q(q));

	initial begin
		$dumpfile("tb_dff_syncres.vcd");
		$dumpvars(0,tb_dff_syncres);
		// Initialize Inputs
		clk = 0;
		sync_reset = 1;
		d = 0;
		#3000 $finish;
	end
		
	always #10 clk = ~clk;
	always #23 d = ~d;
	always #547 sync_reset=~async_reset; 
endmodule
```
![y32](https://github.com/user-attachments/assets/cd1ded0a-6d6f-4679-be7b-a1c723384b8d)
![y33](https://github.com/user-attachments/assets/138daf09-9b96-4039-b59e-6d21435db322)

From the waveform, it can be observed that the Q output changes to zero when the synchronous reset is set high, only at the positive clock edge.

Synthesis of D-Flipflop using Yosys: Synthesized 3 types of D-Flipflops - Asynchronous Reset, Asynchronous Set and Synchronous Reset.
Asynchronous Reset
```
1. yosys
2. read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
3. read_verilog dff_asyncres.v
4. synth -top dff_asyncres
5. dfflibmap -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
7. show
8. write_verilog -noattr dff_asyncres_netlist.v
9. gvim dff_asyncres_netlist.v
```
```
//Generated Netlist   		
module dff_asyncres (clk, async_reset, d, q);
	wire _0_;
	wire _1_;
	wire _2_;
	input async_reset;
	input clk;
	input d;
	output q;
	
	sky130_fd_sc_hd__clkinv_1 _3_ (.A(_0_),.Y(_1_));
	sky130_fd_sc_hd__dfrtp_1 _4_ (.CLK(clk),.D(d),.RESET_B(_2_),.Q(q));
	assign _0_ = async_reset;
	assign _2_ = _1_;
endmodule
```
![y34](https://github.com/user-attachments/assets/3a3f2b4d-4553-4f09-8ba7-55e7755c37d2)
![y35](https://github.com/user-attachments/assets/2abefa3c-46a0-4fdc-9c4f-5b0ef6fdd8c4)
![y36](https://github.com/user-attachments/assets/65b2a639-2b6d-4c13-bfb0-6a8a6025dd65)
![y37](https://github.com/user-attachments/assets/caa3e046-74f3-4660-b1b3-a983880e6fc3)
![y38](https://github.com/user-attachments/assets/b73fb282-1cd1-4e67-9611-31ff76543b32)

Asynchronous Reset
```
1. yosys
2. read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
3. read_verilog dff_async_set.v
4. synth -top dff_async_set
5. dfflibmap -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
7. show
8. write_verilog -noattr dff_async_set_netlist.v
9. gvim dff_async_set_netlist.v
```
```
//Generated Netlist   		
module dff_async_set (clk, async_set, d, q);
	wire _0_;
	wire _1_;
	wire _2_;
	input async_set;
	input clk;
	input d;
	output q;
	
	sky130_fd_sc_hd__clkinv_1 _3_ (.A(_0_),.Y(_1_));
	sky130_fd_sc_hd__dfrtp_1 _4_ (.CLK(clk),.D(d),.RESET_B(_2_),.Q(q));
	assign _0_ = async_set;
	assign _2_ = _1_;
endmodule
```
![y39](https://github.com/user-attachments/assets/ebb42b40-c6fb-4eac-92c9-aec1dd7ee93f)
![y40](https://github.com/user-attachments/assets/4402894c-c988-4da3-a48b-e0e0fb5087f7)
![y41](https://github.com/user-attachments/assets/e11516c6-1f51-452e-902d-d42a04533542)
![y42](https://github.com/user-attachments/assets/5088c522-7bae-4b29-9f1d-55ae0783d1b9)

Synchronous Reset
```
1. yosys
2. read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
3. read_verilog dff_syncres.v
4. synth -top dff_syncres
5. dfflibmap -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
7. show
8. write_verilog -noattr dff_syncres_netlist.v
9. gvim dff_syncres_netlist.v
```
```
//Generated Netlist   		
module dff_syncres (clk, sync_reset, d, q);
	wire _0_;
	wire _1_;
	wire _2_;
	input sync_reset;
	input clk;
	input d;
	output q;
	
	sky130_fd_sc_hd__clkinv_1 _3_ (.A(_0_),.Y(_1_));
	sky130_fd_sc_hd__dfrtp_1 _4_ (.CLK(clk),.D(d),.RESET_B(_2_),.Q(q));
	assign _0_ = sync_reset;
	assign _2_ = _1_;
endmodule
```
![y43](https://github.com/user-attachments/assets/3692d40d-fa36-4b22-a53a-9607a4838b42)
![y44](https://github.com/user-attachments/assets/0b390733-1836-47e1-bea6-6559ddd24828)
![y45](https://github.com/user-attachments/assets/fbc2d006-8b2a-4ce9-8c86-6295ff35edf0)
![y46](https://github.com/user-attachments/assets/f6d52d3e-b039-487a-96dd-db7f557cb09f)
![y47](https://github.com/user-attachments/assets/2ab7c801-a39b-4814-8375-9e28bc8de835)

Multiplication by 2: This tutorial, we get to know that specific multiplier hardware is not required for multiplication of a number by 2. It can simply be achieved by concatenating the number itself with a zero in the LSB.
```
1. yosys
2. read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
3. read_verilog mult_2.v
4. synth -top mul2
5. abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
6. show
7. write_verilog -noattr mul2_net.v
8. gvim mul2_net.v
```
```
//Design
module mul2(input [2:0]a, output [3:0]y);
	assign y=a*2;
endmodule
```
```
//Generated Netlist
module mul2(a,y);
	input [2:0]a; wire [2:0]a;
	output [3:0]y; wire [3:0]y;

	assign y = {a,1'h0};
endmodule
```
![y48](https://github.com/user-attachments/assets/7101dc18-a3f7-43c0-b962-be36d94f4849)
![y49](https://github.com/user-attachments/assets/30c66a33-19c4-43c4-b30d-f8302fa3cf9d)
![y50](https://github.com/user-attachments/assets/a49694ad-7ebf-438d-afb0-8fa131b1a2b2)

Multiplication by 9: This tutorial, we get to know that specific multiplier hardware is not required for multiplication of a number by 9. It can simply be achieved by concatenating the number with itself.
```
1. yosys
2. read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
3. read_verilog mult_9.v
4. synth -top mult9
5. abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
6. show
7. write_verilog -noattr mul9_net.v
8. gvim mul9_net.v
```
```
//Design
module mul2(input [2:0]a, output [5:0]y);
	assign y=a*9;
endmodule
```
```
//Generated Netlist
module mul9(a,y);
	input [2:0]a; wire [2:0]a;
	output [5:0]y; wire [5:0]y;

	assign y = {a,a};
endmodule
```
![y51](https://github.com/user-attachments/assets/de5c6d3b-cc7d-4c7a-9efd-d837838df34c)
![y52](https://github.com/user-attachments/assets/143b7cb1-4de0-45a7-91ea-54481ba32e6b)
![y53](https://github.com/user-attachments/assets/bf928afe-4c3c-4beb-9837-5f0548c724e2)
![y54](https://github.com/user-attachments/assets/6555e8f1-0a52-4e64-ab52-b615540a11f2)
![y55](https://github.com/user-attachments/assets/a5d63a35-c7d9-4c6b-bba7-9c52a0ce25ea)
![y56](https://github.com/user-attachments/assets/67cd977e-b7ca-488e-b175-f168300d2e79)
![y57](https://github.com/user-attachments/assets/5a87cbd7-b94c-455b-847e-b683fd342d70)








</details>
<details>
  <summary> DAY : 3 </summary>

 Optimization of Various Designs
Design infers 2 input AND Gate:
```1. yosys
2. read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
3. read_verilog opt_check.v
4. synth -top opt_check
5. abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
6. opt_clean -purge
7. show
```
Removes unused or redundant logic in the design and purges any dangling wires or gates.
//Design
```
module opt_check(input a, input b, output y);
	assign y = a?b:0;
endmodule
```
![y1](https://github.com/user-attachments/assets/65fc4992-8213-41ba-a916-649046d43c93)
![y2](https://github.com/user-attachments/assets/e7bae3f0-2fca-4b4b-8f1d-ee38db102cfe)
![y3](https://github.com/user-attachments/assets/4c44bd0d-ef89-4a35-b3b4-338ec353ec71)
![y4](https://github.com/user-attachments/assets/d3ed4489-8a5a-4a71-89bf-74222e8aba96)
Design infers 2 input OR Gate:
```
1. yosys
2. read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
3. read_verilog opt_check2.v
4. synth -top opt_check2
5. abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
6. opt_clean -purge
7. show
```
```
//Design
module opt_check2(input a, input b, output y);
	assign y = a?1:b;
endmodule
```
![y5](https://github.com/user-attachments/assets/30435f6c-d413-4d2d-ab07-27c930b1c6db)
![y6](https://github.com/user-attachments/assets/edf85eef-63c4-4bd7-9f07-b70a78192f07)
![y7](https://github.com/user-attachments/assets/8b097f84-e950-445f-9998-a647fa930d9b)
![y8](https://github.com/user-attachments/assets/7af57395-d9f6-40f5-86c3-e576f0c1fc28)
Design infers 3 input AND Gate:
```
1. yosys
2. read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
3. read_verilog opt_check3.v
4. synth -top opt_check3
5. abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
6. opt_clean -purge
7. show
```
```
//Design
module opt_check2(input a, input b, input c, output y);
	assign y = a?(b?c:0):0;
endmodule
```
![y9](https://github.com/user-attachments/assets/b96a9928-2c7e-44af-83dc-3101b24519f3)
![y10](https://github.com/user-attachments/assets/411b3c1b-961e-47e5-af26-16595149e061)
![y11](https://github.com/user-attachments/assets/f70557d0-18d6-409b-8d8e-653dcff955ce)

Design infers 2 input XNOR Gate (3 input Boolean Logic)
```
1. yosys
2. read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
3. read_verilog opt_check4.v
4. synth -top opt_check4
5. abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
6. opt_clean -purge
7. show
```
```
//Design
module opt_check2(input a, input b, input c, output y);
	assign y = a ? (b ? ~c : c) : ~c;
endmodule
```
![y12](https://github.com/user-attachments/assets/e6a891b7-0d01-42c2-a31e-78bda8700ab2)
![y13](https://github.com/user-attachments/assets/9077b438-d4e7-4b8b-a261-99828b2143d3)
![y14](https://github.com/user-attachments/assets/f815ac8e-141b-4228-a96f-7d4a0f7da20d)
![y15](https://github.com/user-attachments/assets/d52cfdd5-6b52-42f4-b518-a19e16d93f57)

D-Flipflop Constant 1 with Asynchronous Reset (active low)
```
iverilog dff_const1.v tb_dff_const1.v
./a.out
gtkwave tb_dff_const1.vcd
```

![y16](https://github.com/user-attachments/assets/834c8f04-f755-4506-9f6d-82255f9d96e4)
![y17](https://github.com/user-attachments/assets/e3041327-cb81-4266-b77f-5518b38191aa)
```
//Design
module dff_const1(input clk, input reset, output reg q); 
always @(posedge clk, posedge reset)
begin
	if(reset)
		q <= 1'b0;
	else
		q <= 1'b1;
end
endmodule
//Testbench
module tb_dff_const1; 
	reg clk, reset;
	wire q;

	dff_const1 uut (.clk(clk),.reset(reset),.q(q));

	initial begin
		$dumpfile("tb_dff_const1.vcd");
		$dumpvars(0,tb_dff_const1);
		// Initialize Inputs
		clk = 0;
		reset = 1;
		#3000 $finish;
	end

	always #10 clk = ~clk;
	always #1547 reset=~reset;
endmodule
```

![y22](https://github.com/user-attachments/assets/03b1d4d5-2051-4f64-9cef-4d304bb305f6)
![y23](https://github.com/user-attachments/assets/56c711b7-ea95-4448-a570-cb55626b9d19)
![y24](https://github.com/user-attachments/assets/df0fd0ed-8d4e-4b93-a810-51108f46f5a8)
![y25](https://github.com/user-attachments/assets/7234d971-5a0a-425c-93c0-b1e85212ac61)

D-Flipflop Constant 2 with Asynchronous Reset (active high)
```
iverilog dff_const2.v tb_dff_const2.v
./a.out
gtkwave tb_dff_const2.vcd
```
```
//Design
module dff_const2(input clk, input reset, output reg q); 
always @(posedge clk, posedge reset)
begin
	if(reset)
		q <= 1'b1;
	else
		q <= 1'b1;
end
endmodule
//Testbench
module tb_dff_const2; 
	reg clk, reset;
	wire q;

	dff_const2 uut (.clk(clk),.reset(reset),.q(q));

	initial begin
		$dumpfile("tb_dff_const1.vcd");
		$dumpvars(0,tb_dff_const1);
		// Initialize Inputs
		clk = 0;
		reset = 1;
		#3000 $finish;
	end

	always #10 clk = ~clk;
	always #1547 reset=~reset;
endmodule
```
![y18](https://github.com/user-attachments/assets/7b7dfbe5-dec7-4582-8ce1-ed3e2cce973f)
![y19](https://github.com/user-attachments/assets/57ec1a1d-444c-44b7-846b-3fc6bbc2e44e)


From the waveform, it can be observed that the Q output is always high irrespective of reset.
```
1. yosys
2. read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
3. read_verilog dff_const2.v
4. synth -top dff_const2
5. dfflibmap -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
7. show
```

![y26](https://github.com/user-attachments/assets/304c6cb0-669e-4162-ae07-e68d543b5417)
![y27](https://github.com/user-attachments/assets/99cb07a3-ff05-4d1c-ba0a-af7d41d3249c)
![y27_2](https://github.com/user-attachments/assets/6858503f-718e-4dc3-87fc-697e969fd1b7)

D-Flipflop Constant 3 with Asynchronous Reset (active low)
```
//Design
module dff_const3(input clk, input reset, output reg q); 
	reg q1;

	always @(posedge clk, posedge reset)
	begin
		if(reset)
		begin
			q <= 1'b1;
			q1 <= 1'b0;
		end
		else
		begin	
			q1 <= 1'b1;
			q <= q1;
		end
	end
endmodule
```
```
iverilog dff_const3.v tb_dff_const3.v
./a.out
gtkwave tb_dff_const3.vcd
```
![y20](https://github.com/user-attachments/assets/f3c1e600-c328-4f2b-8b6c-89b1f133a00b)
![y21](https://github.com/user-attachments/assets/fbcdca1f-ac83-4bc4-ba0c-c23bd41accd3)

```
1. yosys
2. read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
3. read_verilog dff_const2.v
4. synth -top dff_const2
5. dfflibmap -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
7. show
```

![y28](https://github.com/user-attachments/assets/6b5db99b-d4d5-43b7-841f-35cb881f395a)
![y29](https://github.com/user-attachments/assets/971c931b-cd41-473c-b965-a982aad3380c)
![y30](https://github.com/user-attachments/assets/647edaba-8319-42ef-99b7-5b900b52ead3)
![y31](https://github.com/user-attachments/assets/931327ea-1ba2-424f-8e97-aed0fd079ebc)


![y32](https://github.com/user-attachments/assets/58abf051-ad18-4d23-8382-bbcd388dae8a)
![y33](https://github.com/user-attachments/assets/00a1f5ac-2ddc-4b5c-9ae9-b610ca72a06f)

This module defines a D flip-flop, for a positive edge of reset, q is set to 1 and q1 is set to 0. On each clock cycle, q1 is set to 1, and q is updated with the value of q1.

When synthesized, the design will result in a flip-flop where q becomes 1 after the first clock cycle post-reset and stays 1 afterward.

D-Flipflop Constant 4 with Asynchronous Reset (active high)
```
//Design
module dff_const4(input clk, input reset, output reg q); 
	reg q1;

	always @(posedge clk, posedge reset)
	begin
		if(reset)
		begin
			q <= 1'b1;
			q1 <= 1'b1;
		end
		else
		begin	
			q1 <= 1'b1;
			q <= q1;
		end
	end
endmodule
```
```
1. yosys
2. read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
3. read_verilog dff_const4.v
4. synth -top dff_const4
5. dfflibmap -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
7. show
```
![y34](https://github.com/user-attachments/assets/d67a733a-beac-4159-bc83-3a21af0f56fa)

![y35](https://github.com/user-attachments/assets/3cd1cd35-5ae9-4670-804c-1d885c901158)
![y36](https://github.com/user-attachments/assets/19d02132-c94b-4033-8d0b-86837798ae2e)
This module defines a D flip-flop that sets both q and q1 to 1 on a positive edge of reset. On each clock cycle, q1 remains 1, and q is updated with the value of q1 (which is always 1).

When synthesized, the design will result in a flip-flop where q is always 1, regardless of the reset or clock state.

D-Flipflop Constant 5 with Asynchronous Reset
```
//Design
module dff_const5(input clk, input reset, output reg q); 
	reg q1;

	always @(posedge clk, posedge reset)
	begin
		if(reset)
		begin
			q <= 1'b0;
			q1 <= 1'b0;
		end
		else
		begin	
			q1 <= 1'b1;
			q <= q1;
		end
	end
endmodule
```
```
1. yosys
2. read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
3. read_verilog dff_const5.v
4. synth -top dff_const5
5. dfflibmap -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
7. show
```
![y37](https://github.com/user-attachments/assets/6ee30a43-3eac-4430-b9cc-b86471d83265)
![y38](https://github.com/user-attachments/assets/644dda0b-5d95-453a-85f6-1647f4a598f8)

![y39](https://github.com/user-attachments/assets/3f7cce5c-3acd-427d-870a-72b0657798bf)
![y40](https://github.com/user-attachments/assets/38be2226-db17-4ccb-95be-f5978796e2e6)

This module defines a D flip-flop that resets both q and q1 to 0 on a positive edge of reset. On each clock cycle, it sets q1 to 1 and then updates q with the value of q1 (which will always be 1 after the first cycle).

When synthesized, the design will result in a flip-flop where q is always 1 after the first clock cycle post-reset.

Counter Optimization 1:
```
//Design	
module counter_opt (input clk, input reset, output q);
	reg [2:0] count;
	assign q = count[0];
	
	always @(posedge clk,posedge reset)
	begin
		if(reset)
			count <= 3'b000;
		else
			count <= count + 1;
	end
endmodule
```
```
1. yosys
2. read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
3. read_verilog counter_opt.v
4. synth -top counter_opt
5. dfflibmap -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
7. show
```
![y41](https://github.com/user-attachments/assets/5562939f-6576-4d34-896c-e4900830a1c2)
![y42](https://github.com/user-attachments/assets/4380d222-fd53-4847-89df-64f0104f6fa1)

![y43](https://github.com/user-attachments/assets/84aa57fd-22c7-4584-97be-af7e4c00fe52)
![y44](https://github.com/user-attachments/assets/fcc72c4a-2685-449f-a22c-3f66428ef3dd)

Counter Optimization 2:
```
//Design	
module counter_opt2 (input clk, input reset, output q);
	reg [2:0] count;
	assign q = (count[2:0] == 3'b100);
	
	always @(posedge clk,posedge reset)
	begin
		if(reset)
			count <= 3'b000;
		else
			count <= count + 1;
	end
endmodule
```
```
1. yosys
2. read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
3. read_verilog counter_opt2.v
4. synth -top counter_opt2
5. dfflibmap -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
7. show
```
![y45](https://github.com/user-attachments/assets/d07e5d2a-70a4-49d3-bbff-e058a11ac556)
![y46](https://github.com/user-attachments/assets/0dd95f94-19df-4e4f-ae5c-5366ddc0c1d5)
![y47](https://github.com/user-attachments/assets/ec51ce2f-3e44-44d9-bcd0-df57651b43d9)
![y48](https://github.com/user-attachments/assets/aa88f368-f7f6-43b5-90da-667df049ea7d)








</details>

<details>
  <summary> DAY : 4 </summary>
	
- Design of 2x1 MUX using Ternary Operator:
//Design
```
module ternary_operator_mux(input i0, input i1, input sel, output y);
	assign y = sel?i1:i0;
endmodule
```
```
iverilog ternary_operator_mux.v tb_ternary_operator_mux.v
./a.out
gtkwave tb_ternary_operator_mux.vcd
```
These commands perform iverilog and GTKWave simulation.
![y1](https://github.com/user-attachments/assets/2849fd49-081d-40a6-b11a-ab7a48faf105)
![y2](https://github.com/user-attachments/assets/f0f5ff3a-7898-4bf2-9b8e-a354d2b296c7)
![y3](https://github.com/user-attachments/assets/aebe5aa4-ed0c-4867-83d6-6797fa76780d)
```
1. yosys
2. read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
3. read_verilog ternary_operator_mux.v
4. synth -top ternary_operator_mux
5. abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
6. opt_clean -purge
7. write_verilog -noattr ternary_operator_mux_net.v
8. !gvim ternary_operator_mux_net.v
9. show
```
```
//Generated Netlist
module ternary_operator_mux(i0, il, sel, y);
	wire _0_;
	wire _1_;
	wire _2_;
	wire _3_;
	input i0; wire i0;
	input il; wire il;
	input sel; wire sel;
	output y; wire y;
	
	sky130_fd_sc_hd_mux2_1 _4_ (.AO(_0_),.A1(_1_),.S(_2_),.X(_3_));

	assign _0_ = i0;
	assign _1_ = il;
	assign _2_ = sel;
	assign y = _3_;
endmodule
```
![y4](https://github.com/user-attachments/assets/60d23598-85ff-4325-a087-d30af723b83e)
![y5](https://github.com/user-attachments/assets/00feb4af-7323-4164-b2b5-c0e79c608416)
![y6](https://github.com/user-attachments/assets/0b23f96e-1adc-4f65-a814-8ff256767628)
![y7](https://github.com/user-attachments/assets/59aa72ed-4965-48ac-8b01-103fa31db04e)
```
iverilog ../my_lib/verilog_model/primitives.v ../my_lib/verilog_model/sky130_fd_sc_hd.v ternary_operator_mux.v tb_ternary_operator_mux.v
./a.out
gtkwave tb_ternary_operator_mux.vcd
```
![y8](https://github.com/user-attachments/assets/cbff7a12-6f66-410d-bcc7-38b403cc5723)
![y9](https://github.com/user-attachments/assets/9a25e732-6b57-4f8b-b665-4e5a794b1daf)
These waveforms correspond to the GATE LEVEL SYNTHESIS for the Ternary Operator MUX.

Design of a Bad 2x1 MUX:
//Design
```
module bad_mux(input i0, input i1, input sel, output reg y);
	always@(sel)
	begin
		if(sel)
			y <= i1;
		else
			y <= i0;
	end
endmodule
```
```
iverilog bad_mux.v tb_bad_mux.v
./a.out
gtkwave tb_bad_mux.vcd
```
![y10](https://github.com/user-attachments/assets/ef0a2b04-5641-41cf-87c8-253e09717a75)
![y11](https://github.com/user-attachments/assets/cfbcee49-c6d7-48a7-8ac7-684048ecd858)

From the waveform it can be observed that the output y changes only when there is a change in select line, completely ignoring the change in i0 and i1, which should also change the output y. Thus, this design is that of a bad MUX.

```
1. yosys
2. read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
3. read_verilog bad_mux.v
4. synth -top bad_mux
5. abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
6. opt_clean -purge
7. write_verilog -noattr bad_mux_net.v
8. !gvim bad_mux_net.v
9. show
```
//Generated Netlist
```
module bad_mux(i0, il, sel, y);
	wire _0_;
	wire _1_;
	wire _2_;
	wire _3_;
	input i0; wire i0;
	input il; wire il;
	input sel; wire sel;
	output y; wire y;
	
	sky130_fd_sc_hd_mux2_1 _4_ (.AO(_0_),.A1(_1_),.S(_2_),.X(_3_));

	assign _0_ = i0;
	assign _1_ = il;
	assign _2_ = sel;
	assign y = _3_;
endmodule
```
![y12](https://github.com/user-attachments/assets/eb9e4fbd-a1b2-44aa-b09c-4e1f009d3bcc)
![y13](https://github.com/user-attachments/assets/d0993ea3-3b43-424b-9619-f288aa5f1563)
![y14](https://github.com/user-attachments/assets/d223f4e4-8c58-462c-84dc-83544b0f3525)
```
iverilog ../my_lib/verilog_model/primitives.v ../my_lib/verilog_model/sky130_fd_sc_hd.v bad_mux.v tb_bad_mux.v
./a.out
gtkwave tb_bad_mux.vcd
```
![y15](https://github.com/user-attachments/assets/c87a3699-1f50-40c6-a8db-67dfdde29777)
![y16](https://github.com/user-attachments/assets/a72e1a06-940b-4d64-8207-6238c30ee89d)
These waveforms correspond to the GATE LEVEL SYNTHESIS for the Bad MUX.

Blocking Caveat:
```
//Design
module blocking_caveat(input a, input b, input c, output reg d);
	reg x;

	always@(*)
	begin
		d = x & c;
		x = a | b;
	end
endmodule
```
```
iverilog blocking_caveat.v tb_blocking_caveat.v
./a.out
gtkwave tb_blocking_caveat.vcd
```
![y17](https://github.com/user-attachments/assets/8fff35ea-e5aa-4784-9bf7-ee4a18289ba6)
![y18](https://github.com/user-attachments/assets/9121c436-c4a4-4442-bf29-50681554bbb1)
![y27](https://github.com/user-attachments/assets/8fca697b-0441-4654-90a7-77f045e3809c)

As depicted by the in the waveform, when A and B go zero, the OR gate output should be zero (X equal to zero), and the AND gate output should also be zero (same as D output). But, the AND gate input of X takes the previous value of A|B equal to one, based on the design created by the blocking statement, hence the discrepancy in the output.
```
1. yosys
2. read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
3. read_verilog blocking_caveat.v
4. synth -top blocking_caveat
5. abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
6. opt_clean -purge
7. write_verilog -noattr blocking_caveat_net.v
8. !gvim blocking_caveat_net.v
9. show
```
```
//Generated Netlist
module blocking_caveat(a,b,c,d);
	wire _0_;
	wire _1_;
	wire _2_;
	wire _3_;
	wire _4_;
	input a; wire a;
	input b; wire b;
	input c; wire c;
	input d; wire d;
	output d; wire d;
	
	sky130_fd_sc_hd__o21a_1 _5_ (.A1(_2_),.A2(_1_),.B1(_3_),.X(_4_));

	assign _2_ = b;
	assign _1_ = a;
	assign _3_ = c;
	assign d = _4_;
endmodule
```
![y19](https://github.com/user-attachments/assets/bf2e2ead-31d5-4c01-b9d9-7cd46a29d558)
![y20](https://github.com/user-attachments/assets/1456631e-b1fe-4787-8b52-1c09163454b0)
![y21](https://github.com/user-attachments/assets/795a9926-d6c7-4b16-9531-180dcd5cada1)
![y22](https://github.com/user-attachments/assets/5240c23d-0873-474c-b0b0-78507c9a1cd2)
```
iverilog ../my_lib/verilog_model/primitives.v ../my_lib/verilog_model/sky130_fd_sc_hd.v blocking_caveat.v tb_blocking_caveat.v
./a.out
gtkwave tb_blocking_caveat.vcd
```
![y23](https://github.com/user-attachments/assets/87f76479-113f-4230-b3e4-8d404819695e)
![y24](https://github.com/user-attachments/assets/df69a11e-2164-4797-8024-1f60f6f58825)
![y25](https://github.com/user-attachments/assets/dda95361-b5dd-4882-9c6d-d148c7642c00)
![y26](https://github.com/user-attachments/assets/f9924756-fd09-49b9-bd28-5b515f25034b)




 
</details>
</details>

## Synthesis of RISC-V using yosys and Post synthesis simulation of Babysoc using iverilog GTKwave
<details>
  <summary> Synthesis of RISC-V using yosys and Post synthesis simulation of Babysoc using iverilog GTKwave </summary>
	
	```
	1) Functionality vs Synthesized output waveform comparison. They should match. Plot atleast for top 20 cycles (20 ups and 20 downs)
        2) Synthesize output window CLEARLY showing standard cells in the gtkwave window along with your login name

	```

```
      Testbench
   `timescale 1ns / 1ps
   `ifdef PRE_SYNTH_SIM
    `include "vsdbabysoc.v"
    `include "avsddac.v"
    `include "avsdpll.v"
    //`include "rvmyth.v"
    `include "clk_gate.v"
    `elsif POST_SYNTH_SIM
    `include "rvmyth_netlist.v"
    `include "avsddac.v"
    `include "avsdpll.v"
    `include "primitives.v"
     `include "sky130_fd_sc_hd.v"
     `include "vsdbabysoc.v"
    `endif

    module vsdbabysoc_tb;
    reg       reset;
    reg       VCO_IN;
    reg       ENb_CP;
    reg       ENb_VCO;
    reg       REF;
    reg  real VREFL;
    reg  real VREFH;
    wire real OUT;

    vsdbabysoc uut (
      .OUT(OUT),
      .reset(reset),
      .VCO_IN(VCO_IN),
      .ENb_CP(ENb_CP),
      .ENb_VCO(ENb_VCO),
      .REF(REF),
      // .VREFL(VREFL),
      .VREFH(VREFH)
     );

      initial begin
      reset = 0;
        VREFL = 0.0;
         VREFH = 3.3;
        {REF, ENb_VCO} = 0;
        VCO_IN = 1'b0 ;
     
      #20 reset = 1;
      #100 reset = 0;
     end
   
     initial begin
      `ifdef PRE_SYNTH_SIM
      $dumpfile("pre_synth_sim.vcd");
      `elsif POST_SYNTH_SIM
      $dumpfile("post_synth_sim.vcd");
      `endif
       $dumpvars(0, vsdbabysoc_tb);
       end
  
     initial begin
      repeat(600) begin
         ENb_VCO = 1;
         #100 REF = ~REF;
         #(83.33/2) VCO_IN = ~VCO_IN;
      end
       $finish;
    end
   
     endmodule

```

//Generated Netlist

```

/* Generated by Yosys 0.44+60 (git sha1 0fc5812dc, g++ 11.4.0-1ubuntu1~22.04 -fPIC -O3) */

module clk_gate(gated_clk, free_clk, func_en, pwr_en, gating_override);
  input free_clk;
  wire free_clk;
  input func_en;
  wire func_en;
  output gated_clk;
  wire gated_clk;
  input gating_override;
  wire gating_override;
  input pwr_en;
  wire pwr_en;
  assign gated_clk = free_clk;
endmodule

module rvmyth(OUT, CLK, reset);

```
<details>
  <summary> Read more </summary>

```  
  wire _00000_;
  wire _00001_;
  wire _00002_;
  wire _00003_;
  wire _00004_;
  wire _00005_;
  wire _00006_;
  wire _00007_;
  wire _00008_;
  wire _00009_;
  wire _00010_;
  wire _00011_;
  wire _00012_;
  wire _00013_;
  wire _00014_;
  wire _00015_;
  wire _00016_;
  wire _00017_;
  wire _00018_;
  wire _00019_;
  wire _00020_;
  wire _00021_;
  wire _00022_;
  wire _00023_;
  wire _00024_;
  wire _00025_;
  wire _00026_;
  wire _00027_;
  wire _00028_;
  wire _00029_;
  wire _00030_;
  wire _00031_;
  wire _00032_;
  wire _00033_;
  wire _00034_;
  wire _00035_;
  wire _00036_;
  wire _00037_;
  wire _00038_;
  wire _00039_;
  wire _00040_;
  wire _00041_;
  wire _00042_;
  wire _00043_;
  wire _00044_;
  wire _00045_;
  wire _00046_;
  wire _00047_;
  wire _00048_;
  wire _00049_;
  wire _00050_;
  wire _00051_;
  wire _00052_;
  wire _00053_;
  wire _00054_;
  wire _00055_;
  wire _00056_;
  wire _00057_;
  wire _00058_;
  wire _00059_;
  wire _00060_;
  wire _00061_;
  wire _00062_;
  wire _00063_;
  wire _00064_;
  wire _00065_;
  wire _00066_;
  wire _00067_;
  wire _00068_;
  wire _00069_;
  wire _00070_;
  wire _00071_;
  wire _00072_;
  wire _00073_;
  wire _00074_;
  wire _00075_;
  wire _00076_;
  wire _00077_;
  wire _00078_;
  wire _00079_;
  wire _00080_;
  wire _00081_;
  wire _00082_;
  wire _00083_;
  wire _00084_;
  wire _00085_;
  wire _00086_;
  wire _00087_;
  wire _00088_;
  wire _00089_;
  wire _00090_;
  wire _00091_;
  wire _00092_;
  wire _00093_;
  wire _00094_;
  wire _00095_;
  wire _00096_;
  wire _00097_;
  wire _00098_;
  wire _00099_;
  wire _00100_;
  wire _00101_;
  wire _00102_;
  wire _00103_;
  wire _00104_;
  wire _00105_;
  wire _00106_;
  wire _00107_;
  wire _00108_;
  wire _00109_;
  wire _00110_;
  wire _00111_;
  wire _00112_;
  wire _00113_;
  wire _00114_;
  wire _00115_;
  wire _00116_;
  wire _00117_;
  wire _00118_;
  wire _00119_;
  wire _00120_;
  wire _00121_;
  wire _00122_;
  wire _00123_;
  wire _00124_;
  wire _00125_;
  wire _00126_;
  wire _00127_;
  wire _00128_;
  wire _00129_;
  wire _00130_;
  wire _00131_;
  wire _00132_;
  wire _00133_;
  wire _00134_;
  wire _00135_;
  wire _00136_;
  wire _00137_;
  wire _00138_;
  wire _00139_;
  wire _00140_;
  wire _00141_;
  wire _00142_;
  wire _00143_;
  wire _00144_;
  wire _00145_;
  wire _00146_;
  wire _00147_;
  wire _00148_;
  wire _00149_;
  wire _00150_;
  wire _00151_;
  wire _00152_;
  wire _00153_;
  wire _00154_;
  wire _00155_;
  wire _00156_;
  wire _00157_;
  wire _00158_;
  wire _00159_;
  wire _00160_;
  wire _00161_;
  wire _00162_;
  wire _00163_;
  wire _00164_;
  wire _00165_;
  wire _00166_;
  wire _00167_;
  wire _00168_;
  wire _00169_;
  wire _00170_;
  wire _00171_;
  wire _00172_;
  wire _00173_;
  wire _00174_;
  wire _00175_;
  wire _00176_;
  wire _00177_;
  wire _00178_;
  wire _00179_;
  wire _00180_;
  wire _00181_;
  wire _00182_;
  wire _00183_;
  wire _00184_;
  wire _00185_;
  wire _00186_;
  wire _00187_;
  wire _00188_;
  wire _00189_;
  wire _00190_;
  wire _00191_;
  wire _00192_;
  wire _00193_;
  wire _00194_;
  wire _00195_;
  wire _00196_;
  wire _00197_;
  wire _00198_;
  wire _00199_;
  wire _00200_;
  wire _00201_;
  wire _00202_;
  wire _00203_;
  wire _00204_;
  wire _00205_;
  wire _00206_;
  wire _00207_;
  wire _00208_;
  wire _00209_;
  wire _00210_;
  wire _00211_;
  wire _00212_;
  wire _00213_;
  wire _00214_;
  wire _00215_;
  wire _00216_;
  wire _00217_;
  wire _00218_;
  wire _00219_;
  wire _00220_;
  wire _00221_;
  wire _00222_;
  wire _00223_;
  wire _00224_;
  wire _00225_;
  wire _00226_;
  wire _00227_;
  wire _00228_;
  wire _00229_;
  wire _00230_;
  wire _00231_;
  wire _00232_;
  wire _00233_;
  wire _00234_;
  wire _00235_;
  wire _00236_;
  wire _00237_;
  wire _00238_;
  wire _00239_;
  wire _00240_;
  wire _00241_;
  wire _00242_;
  wire _00243_;
  wire _00244_;
  wire _00245_;
  wire _00246_;
  wire _00247_;
  wire _00248_;
  wire _00249_;
  wire _00250_;
  wire _00251_;
  wire _00252_;
  wire _00253_;
  wire _00254_;
  wire _00255_;
  wire _00256_;
  wire _00257_;
  wire _00258_;
  wire _00259_;
  wire _00260_;
  wire _00261_;
  wire _00262_;
  wire _00263_;
  wire _00264_;
  wire _00265_;
  wire _00266_;
  wire _00267_;
  wire _00268_;
  wire _00269_;
  wire _00270_;
  wire _00271_;
  wire _00272_;
  wire _00273_;
  wire _00274_;
  wire _00275_;
  wire _00276_;
  wire _00277_;
  wire _00278_;
  wire _00279_;
  wire _00280_;
  wire _00281_;
  wire _00282_;
  wire _00283_;
  wire _00284_;
  wire _00285_;
  wire _00286_;
  wire _00287_;
  wire _00288_;
  wire _00289_;
  wire _00290_;
  wire _00291_;
  wire _00292_;
  wire _00293_;
  wire _00294_;
  wire _00295_;
  wire _00296_;
  wire _00297_;
  wire _00298_;
  wire _00299_;
  wire _00300_;
  wire _00301_;
  wire _00302_;
  wire _00303_;
  wire _00304_;
  wire _00305_;
  wire _00306_;
  wire _00307_;
  wire _00308_;
  wire _00309_;
  wire _00310_;
  wire _00311_;
  wire _00312_;
  wire _00313_;
  wire _00314_;
  wire _00315_;
  wire _00316_;
  wire _00317_;
  wire _00318_;
  wire _00319_;
  wire _00320_;
  wire _00321_;
  wire _00322_;
  wire _00323_;
  wire _00324_;
  wire _00325_;
  wire _00326_;
  wire _00327_;
  wire _00328_;
  wire _00329_;
  wire _00330_;
  wire _00331_;
  wire _00332_;
  wire _00333_;
  wire _00334_;
  wire _00335_;
  wire _00336_;
  wire _00337_;
  wire _00338_;
  wire _00339_;
  wire _00340_;
  wire _00341_;
  wire _00342_;
  wire _00343_;
  wire _00344_;
  wire _00345_;
  wire _00346_;
  wire _00347_;
  wire _00348_;
  wire _00349_;
  wire _00350_;
  wire _00351_;
  wire _00352_;
  wire _00353_;
  wire _00354_;
  wire _00355_;
  wire _00356_;
  wire _00357_;
  wire _00358_;
  wire _00359_;
  wire _00360_;
  wire _00361_;
  wire _00362_;
  wire _00363_;
  wire _00364_;
  wire _00365_;
  wire _00366_;
  wire _00367_;
  wire _00368_;
  wire _00369_;
  wire _00370_;
  wire _00371_;
  wire _00372_;
  wire _00373_;
  wire _00374_;
  wire _00375_;
  wire _00376_;
  wire _00377_;
  wire _00378_;
  wire _00379_;
  wire _00380_;
  wire _00381_;
  wire _00382_;
  wire _00383_;
  wire _00384_;
  wire _00385_;
  wire _00386_;
  wire _00387_;
  wire _00388_;
  wire _00389_;
  wire _00390_;
  wire _00391_;
  wire _00392_;
  wire _00393_;
  wire _00394_;
  wire _00395_;
  wire _00396_;
  wire _00397_;
  wire _00398_;
  wire _00399_;
  wire _00400_;
  wire _00401_;
  wire _00402_;
  wire _00403_;
  wire _00404_;
  wire _00405_;
  wire _00406_;
  wire _00407_;
  wire _00408_;
  wire _00409_;
  wire _00410_;
  wire _00411_;
  wire _00412_;
  wire _00413_;
  wire _00414_;
  wire _00415_;
  wire _00416_;
  wire _00417_;
  wire _00418_;
  wire _00419_;
  wire _00420_;
  wire _00421_;
  wire _00422_;
  wire _00423_;
  wire _00424_;
  wire _00425_;
  wire _00426_;
  wire _00427_;
  wire _00428_;
  wire _00429_;
  wire _00430_;
  wire _00431_;
  wire _00432_;
  wire _00433_;
  wire _00434_;
  wire _00435_;
  wire _00436_;
  wire _00437_;
  wire _00438_;
  wire _00439_;
  wire _00440_;
  wire _00441_;
  wire _00442_;
  wire _00443_;
  wire _00444_;
  wire _00445_;
  wire _00446_;
  wire _00447_;
  wire _00448_;
  wire _00449_;
  wire _00450_;
  wire _00451_;
  wire _00452_;
  wire _00453_;
  wire _00454_;
  wire _00455_;
  wire _00456_;
  wire _00457_;
  wire _00458_;
  wire _00459_;
  wire _00460_;
  wire _00461_;
  wire _00462_;
  wire _00463_;
  wire _00464_;
  wire _00465_;
  wire _00466_;
  wire _00467_;
  wire _00468_;
  wire _00469_;
  wire _00470_;
  wire _00471_;
  wire _00472_;
  wire _00473_;
  wire _00474_;
  wire _00475_;
  wire _00476_;
  wire _00477_;
  wire _00478_;
  wire _00479_;
  wire _00480_;
  wire _00481_;
  wire _00482_;
  wire _00483_;
  wire _00484_;
  wire _00485_;
  wire _00486_;
  wire _00487_;
  wire _00488_;
  wire _00489_;
  wire _00490_;
  wire _00491_;
  wire _00492_;
  wire _00493_;
  wire _00494_;
  wire _00495_;
  wire _00496_;
  wire _00497_;
  wire _00498_;
  wire _00499_;
  wire _00500_;
  wire _00501_;
  wire _00502_;
  wire _00503_;
  wire _00504_;
  wire _00505_;
  wire _00506_;
  wire _00507_;
  wire _00508_;
  wire _00509_;
  wire _00510_;
  wire _00511_;
  wire _00512_;
  wire _00513_;
  wire _00514_;
  wire _00515_;
  wire _00516_;
  wire _00517_;
  wire _00518_;
  wire _00519_;
  wire _00520_;
  wire _00521_;
  wire _00522_;
  wire _00523_;
  wire _00524_;
  wire _00525_;
  wire _00526_;
  wire _00527_;
  wire _00528_;
  wire _00529_;
  wire _00530_;
  wire _00531_;
  wire _00532_;
  wire _00533_;
  wire _00534_;
  wire _00535_;
  wire _00536_;
  wire _00537_;
  wire _00538_;
  wire _00539_;
  wire _00540_;
  wire _00541_;
  wire _00542_;
  wire _00543_;
  wire _00544_;
  wire _00545_;
  wire _00546_;
  wire _00547_;
  wire _00548_;
  wire _00549_;
  wire _00550_;
  wire _00551_;
  wire _00552_;
  wire _00553_;
  wire _00554_;
  wire _00555_;
  wire _00556_;
  wire _00557_;
  wire _00558_;
  wire _00559_;
  wire _00560_;
  wire _00561_;
  wire _00562_;
  wire _00563_;
  wire _00564_;
  wire _00565_;
  wire _00566_;
  wire _00567_;
  wire _00568_;
  wire _00569_;
  wire _00570_;
  wire _00571_;
  wire _00572_;
  wire _00573_;
  wire _00574_;
  wire _00575_;
  wire _00576_;
  wire _00577_;
  wire _00578_;
  wire _00579_;
  wire _00580_;
  wire _00581_;
  wire _00582_;
  wire _00583_;
  wire _00584_;
  wire _00585_;
  wire _00586_;
  wire _00587_;
  wire _00588_;
  wire _00589_;
  wire _00590_;
  wire _00591_;
  wire _00592_;
  wire _00593_;
  wire _00594_;
  wire _00595_;
  wire _00596_;
  wire _00597_;
  wire _00598_;
  wire _00599_;
  wire _00600_;
  wire _00601_;
  wire _00602_;
  wire _00603_;
  wire _00604_;
  wire _00605_;
  wire _00606_;
  wire _00607_;
  wire _00608_;
  wire _00609_;
  wire _00610_;
  wire _00611_;
  wire _00612_;
  wire _00613_;
  wire _00614_;
  wire _00615_;
  wire _00616_;
  wire _00617_;
  wire _00618_;
  wire _00619_;
  wire _00620_;
  wire _00621_;
  wire _00622_;
  wire _00623_;
  wire _00624_;
  wire _00625_;
  wire _00626_;
  wire _00627_;
  wire _00628_;
  wire _00629_;
  wire _00630_;
  wire _00631_;
  wire _00632_;
  wire _00633_;
  wire _00634_;
  wire _00635_;
  wire _00636_;
  wire _00637_;
  wire _00638_;
  wire _00639_;
  wire _00640_;
  wire _00641_;
  wire _00642_;
  wire _00643_;
  wire _00644_;
  wire _00645_;
  wire _00646_;
  wire _00647_;
  wire _00648_;
  wire _00649_;
  wire _00650_;
  wire _00651_;
  wire _00652_;
  wire _00653_;
  wire _00654_;
  wire _00655_;
  wire _00656_;
  wire _00657_;
  wire _00658_;
  wire _00659_;
  wire _00660_;
  wire _00661_;
  wire _00662_;
  wire _00663_;
  wire _00664_;
  wire _00665_;
  wire _00666_;
  wire _00667_;
  wire _00668_;
  wire _00669_;
  wire _00670_;
  wire _00671_;
  wire _00672_;
  wire _00673_;
  wire _00674_;
  wire _00675_;
  wire _00676_;
  wire _00677_;
  wire _00678_;
  wire _00679_;
  wire _00680_;
  wire _00681_;
  wire _00682_;
  wire _00683_;
  wire _00684_;
  wire _00685_;
  wire _00686_;
  wire _00687_;
  wire _00688_;
  wire _00689_;
  wire _00690_;
  wire _00691_;
  wire _00692_;
  wire _00693_;
  wire _00694_;
  wire _00695_;
  wire _00696_;
  wire _00697_;
  wire _00698_;
  wire _00699_;
  wire _00700_;
  wire _00701_;
  wire _00702_;
  wire _00703_;
  wire _00704_;
  wire _00705_;
  wire _00706_;
  wire _00707_;
  wire _00708_;
  wire _00709_;
  wire _00710_;
  wire _00711_;
  wire _00712_;
  wire _00713_;
  wire _00714_;
  wire _00715_;
  wire _00716_;
  wire _00717_;
  wire _00718_;
  wire _00719_;
  wire _00720_;
  wire _00721_;
  wire _00722_;
  wire _00723_;
  wire _00724_;
  wire _00725_;
  wire _00726_;
  wire _00727_;
  wire _00728_;
  wire _00729_;
  wire _00730_;
  wire _00731_;
  wire _00732_;
  wire _00733_;
  wire _00734_;
  wire _00735_;
  wire _00736_;
  wire _00737_;
  wire _00738_;
  wire _00739_;
  wire _00740_;
  wire _00741_;
  wire _00742_;
  wire _00743_;
  wire _00744_;
  wire _00745_;
  wire _00746_;
  wire _00747_;
  wire _00748_;
  wire _00749_;
  wire _00750_;
  wire _00751_;
  wire _00752_;
  wire _00753_;
  wire _00754_;
  wire _00755_;
  wire _00756_;
  wire _00757_;
  wire _00758_;
  wire _00759_;
  wire _00760_;
  wire _00761_;
  wire _00762_;
  wire _00763_;
  wire _00764_;
  wire _00765_;
  wire _00766_;
  wire _00767_;
  wire _00768_;
  wire _00769_;
  wire _00770_;
  wire _00771_;
  wire _00772_;
  wire _00773_;
  wire _00774_;
  wire _00775_;
  wire _00776_;
  wire _00777_;
  wire _00778_;
  wire _00779_;
  wire _00780_;
  wire _00781_;
  wire _00782_;
  wire _00783_;
  wire _00784_;
  wire _00785_;
  wire _00786_;
  wire _00787_;
  wire _00788_;
  wire _00789_;
  wire _00790_;
  wire _00791_;
  wire _00792_;
  wire _00793_;
  wire _00794_;
  wire _00795_;
  wire _00796_;
  wire _00797_;
  wire _00798_;
  wire _00799_;
  wire _00800_;
  wire _00801_;
  wire _00802_;
  wire _00803_;
  wire _00804_;
  wire _00805_;
  wire _00806_;
  wire _00807_;
  wire _00808_;
  wire _00809_;
  wire _00810_;
  wire _00811_;
  wire _00812_;
  wire _00813_;
  wire _00814_;
  wire _00815_;
  wire _00816_;
  wire _00817_;
  wire _00818_;
  wire _00819_;
  wire _00820_;
  wire _00821_;
  wire _00822_;
  wire _00823_;
  wire _00824_;
  wire _00825_;
  wire _00826_;
  wire _00827_;
  wire _00828_;
  wire _00829_;
  wire _00830_;
  wire _00831_;
  wire _00832_;
  wire _00833_;
  wire _00834_;
  wire _00835_;
  wire _00836_;
  wire _00837_;
  wire _00838_;
  wire _00839_;
  wire _00840_;
  wire _00841_;
  wire _00842_;
  wire _00843_;
  wire _00844_;
  wire _00845_;
  wire _00846_;
  wire _00847_;
  wire _00848_;
  wire _00849_;
  wire _00850_;
  wire _00851_;
  wire _00852_;
  wire _00853_;
  wire _00854_;
  wire _00855_;
  wire _00856_;
  wire _00857_;
  wire _00858_;
  wire _00859_;
  wire _00860_;
  wire _00861_;
  wire _00862_;
  wire _00863_;
  wire _00864_;
  wire _00865_;
  wire _00866_;
  wire _00867_;
  wire _00868_;
  wire _00869_;
  wire _00870_;
  wire _00871_;
  wire _00872_;
  wire _00873_;
  wire _00874_;
  wire _00875_;
  wire _00876_;
  wire _00877_;
  wire _00878_;
  wire _00879_;
  wire _00880_;
  wire _00881_;
  wire _00882_;
  wire _00883_;
  wire _00884_;
  wire _00885_;
  wire _00886_;
  wire _00887_;
  wire _00888_;
  wire _00889_;
  wire _00890_;
  wire _00891_;
  wire _00892_;
  wire _00893_;
  wire _00894_;
  wire _00895_;
  wire _00896_;
  wire _00897_;
  wire _00898_;
  wire _00899_;
  wire _00900_;
  wire _00901_;
  wire _00902_;
  wire _00903_;
  wire _00904_;
  wire _00905_;
  wire _00906_;
  wire _00907_;
  wire _00908_;
  wire _00909_;
  wire _00910_;
  wire _00911_;
  wire _00912_;
  wire _00913_;
  wire _00914_;
  wire _00915_;
  wire _00916_;
  wire _00917_;
  wire _00918_;
  wire _00919_;
  wire _00920_;
  wire _00921_;
  wire _00922_;
  wire _00923_;
  wire _00924_;
  wire _00925_;
  wire _00926_;
  wire _00927_;
  wire _00928_;
  wire _00929_;
  wire _00930_;
  wire _00931_;
  wire _00932_;
  wire _00933_;
  wire _00934_;
  wire _00935_;
  wire _00936_;
  wire _00937_;
  wire _00938_;
  wire _00939_;
  wire _00940_;
  wire _00941_;
  wire _00942_;
  wire _00943_;
  wire _00944_;
  wire _00945_;
  wire _00946_;
  wire _00947_;
  wire _00948_;
  wire _00949_;
  wire _00950_;
  wire _00951_;
  wire _00952_;
  wire _00953_;
  wire _00954_;
  wire _00955_;
  wire _00956_;
  wire _00957_;
  wire _00958_;
  wire _00959_;
  wire _00960_;
  wire _00961_;
  wire _00962_;
  wire _00963_;
  wire _00964_;
  wire _00965_;
  wire _00966_;
  wire _00967_;
  wire _00968_;
  wire _00969_;
  wire _00970_;
  wire _00971_;
  wire _00972_;
  wire _00973_;
  wire _00974_;
  wire _00975_;
  wire _00976_;
  wire _00977_;
  wire _00978_;
  wire _00979_;
  wire _00980_;
  wire _00981_;
  wire _00982_;
  wire _00983_;
  wire _00984_;
  wire _00985_;
  wire _00986_;
  wire _00987_;
  wire _00988_;
  wire _00989_;
  wire _00990_;
  wire _00991_;
  wire _00992_;
  wire _00993_;
  wire _00994_;
  wire _00995_;
  wire _00996_;
  wire _00997_;
  wire _00998_;
  wire _00999_;
  wire _01000_;
  wire _01001_;
  wire _01002_;
  wire _01003_;
  wire _01004_;
  wire _01005_;
  wire _01006_;
  wire _01007_;
  wire _01008_;
  wire _01009_;
  wire _01010_;
  wire _01011_;
  wire _01012_;
  wire _01013_;
  wire _01014_;
  wire _01015_;
  wire _01016_;
  wire _01017_;
  wire _01018_;
  wire _01019_;
  wire _01020_;
  wire _01021_;
  wire _01022_;
  wire _01023_;
  wire _01024_;
  wire _01025_;
  wire _01026_;
  wire _01027_;
  wire _01028_;
  wire _01029_;
  wire _01030_;
  wire _01031_;
  wire _01032_;
  wire _01033_;
  wire _01034_;
  wire _01035_;
  wire _01036_;
  wire _01037_;
  wire _01038_;
  wire _01039_;
  wire _01040_;
  wire _01041_;
  wire _01042_;
  wire _01043_;
  wire _01044_;
  wire _01045_;
  wire _01046_;
  wire _01047_;
  wire _01048_;
  wire _01049_;
  wire _01050_;
  wire _01051_;
  wire _01052_;
  wire _01053_;
  wire _01054_;
  wire _01055_;
  wire _01056_;
  wire _01057_;
  wire _01058_;
  wire _01059_;
  wire _01060_;
  wire _01061_;
  wire _01062_;
  wire _01063_;
  wire _01064_;
  wire _01065_;
  wire _01066_;
  wire _01067_;
  wire _01068_;
  wire _01069_;
  wire _01070_;
  wire _01071_;
  wire _01072_;
  wire _01073_;
  wire _01074_;
  wire _01075_;
  wire _01076_;
  wire _01077_;
  wire _01078_;
  wire _01079_;
  wire _01080_;
  wire _01081_;
  wire _01082_;
  wire _01083_;
  wire _01084_;
  wire _01085_;
  wire _01086_;
  wire _01087_;
  wire _01088_;
  wire _01089_;
  wire _01090_;
  wire _01091_;
  wire _01092_;
  wire _01093_;
  wire _01094_;
  wire _01095_;
  wire _01096_;
  wire _01097_;
  wire _01098_;
  wire _01099_;
  wire _01100_;
  wire _01101_;
  wire _01102_;
  wire _01103_;
  wire _01104_;
  wire _01105_;
  wire _01106_;
  wire _01107_;
  wire _01108_;
  wire _01109_;
  wire _01110_;
  wire _01111_;
  wire _01112_;
  wire _01113_;
  wire _01114_;
  wire _01115_;
  wire _01116_;
  wire _01117_;
  wire _01118_;
  wire _01119_;
  wire _01120_;
  wire _01121_;
  wire _01122_;
  wire _01123_;
  wire _01124_;
  wire _01125_;
  wire _01126_;
  wire _01127_;
  wire _01128_;
  wire _01129_;
  wire _01130_;
  wire _01131_;
  wire _01132_;
  wire _01133_;
  wire _01134_;
  wire _01135_;
  wire _01136_;
  wire _01137_;
  wire _01138_;
  wire _01139_;
  wire _01140_;
  wire _01141_;
  wire _01142_;
  wire _01143_;
  wire _01144_;
  wire _01145_;
  wire _01146_;
  wire _01147_;
  wire _01148_;
  wire _01149_;
  wire _01150_;
  wire _01151_;
  wire _01152_;
  wire _01153_;
  wire _01154_;
  wire _01155_;
  wire _01156_;
  wire _01157_;
  wire _01158_;
  wire _01159_;
  wire _01160_;
  wire _01161_;
  wire _01162_;
  wire _01163_;
  wire _01164_;
  wire _01165_;
  wire _01166_;
  wire _01167_;
  wire _01168_;
  wire _01169_;
  wire _01170_;
  wire _01171_;
  wire _01172_;
  wire _01173_;
  wire _01174_;
  wire _01175_;
  wire _01176_;
  wire _01177_;
  wire _01178_;
  wire _01179_;
  wire _01180_;
  wire _01181_;
  wire _01182_;
  wire _01183_;
  wire _01184_;
  wire _01185_;
  wire _01186_;
  wire _01187_;
  wire _01188_;
  wire _01189_;
  wire _01190_;
  wire _01191_;
  wire _01192_;
  wire _01193_;
  wire _01194_;
  wire _01195_;
  wire _01196_;
  wire _01197_;
  wire _01198_;
  wire _01199_;
  wire _01200_;
  wire _01201_;
  wire _01202_;
  wire _01203_;
  wire _01204_;
  wire _01205_;
  wire _01206_;
  wire _01207_;
  wire _01208_;
  wire _01209_;
  wire _01210_;
  wire _01211_;
  wire _01212_;
  wire _01213_;
  wire _01214_;
  wire _01215_;
  wire _01216_;
  wire _01217_;
  wire _01218_;
  wire _01219_;
  wire _01220_;
  wire _01221_;
  wire _01222_;
  wire _01223_;
  wire _01224_;
  wire _01225_;
  wire _01226_;
  wire _01227_;
  wire _01228_;
  wire _01229_;
  wire _01230_;
  wire _01231_;
  wire _01232_;
  wire _01233_;
  wire _01234_;
  wire _01235_;
  wire _01236_;
  wire _01237_;
  wire _01238_;
  wire _01239_;
  wire _01240_;
  wire _01241_;
  wire _01242_;
  wire _01243_;
  wire _01244_;
  wire _01245_;
  wire _01246_;
  wire _01247_;
  wire _01248_;
  wire _01249_;
  wire _01250_;
  wire _01251_;
  wire _01252_;
  wire _01253_;
  wire _01254_;
  wire _01255_;
  wire _01256_;
  wire _01257_;
  wire _01258_;
  wire _01259_;
  wire _01260_;
  wire _01261_;
  wire _01262_;
  wire _01263_;
  wire _01264_;
  wire _01265_;
  wire _01266_;
  wire _01267_;
  wire _01268_;
  wire _01269_;
  wire _01270_;
  wire _01271_;
  wire _01272_;
  wire _01273_;
  wire _01274_;
  wire _01275_;
  wire _01276_;
  wire _01277_;
  wire _01278_;
  wire _01279_;
  wire _01280_;
  wire _01281_;
  wire _01282_;
  wire _01283_;
  wire _01284_;
  wire _01285_;
  wire _01286_;
  wire _01287_;
  wire _01288_;
  wire _01289_;
  wire _01290_;
  wire _01291_;
  wire _01292_;
  wire _01293_;
  wire _01294_;
  wire _01295_;
  wire _01296_;
  wire _01297_;
  wire _01298_;
  wire _01299_;
  wire _01300_;
  wire _01301_;
  wire _01302_;
  wire _01303_;
  wire _01304_;
  wire _01305_;
  wire _01306_;
  wire _01307_;
  wire _01308_;
  wire _01309_;
  wire _01310_;
  wire _01311_;
  wire _01312_;
  wire _01313_;
  wire _01314_;
  wire _01315_;
  wire _01316_;
  wire _01317_;
  wire _01318_;
  wire _01319_;
  wire _01320_;
  wire _01321_;
  wire _01322_;
  wire _01323_;
  wire _01324_;
  wire _01325_;
  wire _01326_;
  wire _01327_;
  wire _01328_;
  wire _01329_;
  wire _01330_;
  wire _01331_;
  wire _01332_;
  wire _01333_;
  wire _01334_;
  wire _01335_;
  wire _01336_;
  wire _01337_;
  wire _01338_;
  wire _01339_;
  wire _01340_;
  wire _01341_;
  wire _01342_;
  wire _01343_;
  wire _01344_;
  wire _01345_;
  wire _01346_;
  wire _01347_;
  wire _01348_;
  wire _01349_;
  wire _01350_;
  wire _01351_;
  wire _01352_;
  wire _01353_;
  wire _01354_;
  wire _01355_;
  wire _01356_;
  wire _01357_;
  wire _01358_;
  wire _01359_;
  wire _01360_;
  wire _01361_;
  wire _01362_;
  wire _01363_;
  wire _01364_;
  wire _01365_;
  wire _01366_;
  wire _01367_;
  wire _01368_;
  wire _01369_;
  wire _01370_;
  wire _01371_;
  wire _01372_;
  wire _01373_;
  wire _01374_;
  wire _01375_;
  wire _01376_;
  wire _01377_;
  wire _01378_;
  wire _01379_;
  wire _01380_;
  wire _01381_;
  wire _01382_;
  wire _01383_;
  wire _01384_;
  wire _01385_;
  wire _01386_;
  wire _01387_;
  wire _01388_;
  wire _01389_;
  wire _01390_;
  wire _01391_;
  wire _01392_;
  wire _01393_;
  wire _01394_;
  wire _01395_;
  wire _01396_;
  wire _01397_;
  wire _01398_;
  wire _01399_;
  wire _01400_;
  wire _01401_;
  wire _01402_;
  wire _01403_;
  wire _01404_;
  wire _01405_;
  wire _01406_;
  wire _01407_;
  wire _01408_;
  wire _01409_;
  wire _01410_;
  wire _01411_;
  wire _01412_;
  wire _01413_;
  wire _01414_;
  wire _01415_;
  wire _01416_;
  wire _01417_;
  wire _01418_;
  wire _01419_;
  wire _01420_;
  wire _01421_;
  wire _01422_;
  wire _01423_;
  wire _01424_;
  wire _01425_;
  wire _01426_;
  wire _01427_;
  wire _01428_;
  wire _01429_;
  wire _01430_;
  wire _01431_;
  wire _01432_;
  wire _01433_;
  wire _01434_;
  wire _01435_;
  wire _01436_;
  wire _01437_;
  wire _01438_;
  wire _01439_;
  wire _01440_;
  wire _01441_;
  wire _01442_;
  wire _01443_;
  wire _01444_;
  wire _01445_;
  wire _01446_;
  wire _01447_;
  wire _01448_;
  wire _01449_;
  wire _01450_;
  wire _01451_;
  wire _01452_;
  wire _01453_;
  wire _01454_;
  wire _01455_;
  wire _01456_;
  wire _01457_;
  wire _01458_;
  wire _01459_;
  wire _01460_;
  wire _01461_;
  wire _01462_;
  wire _01463_;
  wire _01464_;
  wire _01465_;
  wire _01466_;
  wire _01467_;
  wire _01468_;
  wire _01469_;
  wire _01470_;
  wire _01471_;
  wire _01472_;
  wire _01473_;
  wire _01474_;
  wire _01475_;
  wire _01476_;
  wire _01477_;
  wire _01478_;
  wire _01479_;
  wire _01480_;
  wire _01481_;
  wire _01482_;
  wire _01483_;
  wire _01484_;
  wire _01485_;
  wire _01486_;
  wire _01487_;
  wire _01488_;
  wire _01489_;
  wire _01490_;
  wire _01491_;
  wire _01492_;
  wire _01493_;
  wire _01494_;
  wire _01495_;
  wire _01496_;
  wire _01497_;
  wire _01498_;
  wire _01499_;
  wire _01500_;
  wire _01501_;
  wire _01502_;
  wire _01503_;
  wire _01504_;
  wire _01505_;
  wire _01506_;
  wire _01507_;
  wire _01508_;
  wire _01509_;
  wire _01510_;
  wire _01511_;
  wire _01512_;
  wire _01513_;
  wire _01514_;
  wire _01515_;
  wire _01516_;
  wire _01517_;
  wire _01518_;
  wire _01519_;
  wire _01520_;
  wire _01521_;
  wire _01522_;
  wire _01523_;
  wire _01524_;
  wire _01525_;
  wire _01526_;
  wire _01527_;
  wire _01528_;
  wire _01529_;
  wire _01530_;
  wire _01531_;
  wire _01532_;
  wire _01533_;
  wire _01534_;
  wire _01535_;
  wire _01536_;
  wire _01537_;
  wire _01538_;
  wire _01539_;
  wire _01540_;
  wire _01541_;
  wire _01542_;
  wire _01543_;
  wire _01544_;
  wire _01545_;
  wire _01546_;
  wire _01547_;
  wire _01548_;
  wire _01549_;
  wire _01550_;
  wire _01551_;
  wire _01552_;
  wire _01553_;
  wire _01554_;
  wire _01555_;
  wire _01556_;
  wire _01557_;
  wire _01558_;
  wire _01559_;
  wire _01560_;
  wire _01561_;
  wire _01562_;
  wire _01563_;
  wire _01564_;
  wire _01565_;
  wire _01566_;
  wire _01567_;
  wire _01568_;
  wire _01569_;
  wire _01570_;
  wire _01571_;
  wire _01572_;
  wire _01573_;
  wire _01574_;
  wire _01575_;
  wire _01576_;
  wire _01577_;
  wire _01578_;
  wire _01579_;
  wire _01580_;
  wire _01581_;
  wire _01582_;
  wire _01583_;
  wire _01584_;
  wire _01585_;
  wire _01586_;
  wire _01587_;
  wire _01588_;
  wire _01589_;
  wire _01590_;
  wire _01591_;
  wire _01592_;
  wire _01593_;
  wire _01594_;
  wire _01595_;
  wire _01596_;
  wire _01597_;
  wire _01598_;
  wire _01599_;
  wire _01600_;
  wire _01601_;
  wire _01602_;
  wire _01603_;
  wire _01604_;
  wire _01605_;
  wire _01606_;
  wire _01607_;
  wire _01608_;
  wire _01609_;
  wire _01610_;
  wire _01611_;
  wire _01612_;
  wire _01613_;
  wire _01614_;
  wire _01615_;
  wire _01616_;
  wire _01617_;
  wire _01618_;
  wire _01619_;
  wire _01620_;
  wire _01621_;
  wire _01622_;
  wire _01623_;
  wire _01624_;
  wire _01625_;
  wire _01626_;
  wire _01627_;
  wire _01628_;
  wire _01629_;
  wire _01630_;
  wire _01631_;
  wire _01632_;
  wire _01633_;
  wire _01634_;
  wire _01635_;
  wire _01636_;
  wire _01637_;
  wire _01638_;
  wire _01639_;
  wire _01640_;
  wire _01641_;
  wire _01642_;
  wire _01643_;
  wire _01644_;
  wire _01645_;
  wire _01646_;
  wire _01647_;
  wire _01648_;
  wire _01649_;
  wire _01650_;
  wire _01651_;
  wire _01652_;
  wire _01653_;
  wire _01654_;
  wire _01655_;
  wire _01656_;
  wire _01657_;
  wire _01658_;
  wire _01659_;
  wire _01660_;
  wire _01661_;
  wire _01662_;
  wire _01663_;
  wire _01664_;
  wire _01665_;
  wire _01666_;
  wire _01667_;
  wire _01668_;
  wire _01669_;
  wire _01670_;
  wire _01671_;
  wire _01672_;
  wire _01673_;
  wire _01674_;
  wire _01675_;
  wire _01676_;
  wire _01677_;
  wire _01678_;
  wire _01679_;
  wire _01680_;
  wire _01681_;
  wire _01682_;
  wire _01683_;
  wire _01684_;
  wire _01685_;
  wire _01686_;
  wire _01687_;
  wire _01688_;
  wire _01689_;
  wire _01690_;
  wire _01691_;
  wire _01692_;
  wire _01693_;
  wire _01694_;
  wire _01695_;
  wire _01696_;
  wire _01697_;
  wire _01698_;
  wire _01699_;
  wire _01700_;
  wire _01701_;
  wire _01702_;
  wire _01703_;
  wire _01704_;
  wire _01705_;
  wire _01706_;
  wire _01707_;
  wire _01708_;
  wire _01709_;
  wire _01710_;
  wire _01711_;
  wire _01712_;
  wire _01713_;
  wire _01714_;
  wire _01715_;
  wire _01716_;
  wire _01717_;
  wire _01718_;
  wire _01719_;
  wire _01720_;
  wire _01721_;
  wire _01722_;
  wire _01723_;
  wire _01724_;
  wire _01725_;
  wire _01726_;
  wire _01727_;
  wire _01728_;
  wire _01729_;
  wire _01730_;
  wire _01731_;
  wire _01732_;
  wire _01733_;
  wire _01734_;
  wire _01735_;
  wire _01736_;
  wire _01737_;
  wire _01738_;
  wire _01739_;
  wire _01740_;
  wire _01741_;
  wire _01742_;
  wire _01743_;
  wire _01744_;
  wire _01745_;
  wire _01746_;
  wire _01747_;
  wire _01748_;
  wire _01749_;
  wire _01750_;
  wire _01751_;
  wire _01752_;
  wire _01753_;
  wire _01754_;
  wire _01755_;
  wire _01756_;
  wire _01757_;
  wire _01758_;
  wire _01759_;
  wire _01760_;
  wire _01761_;
  wire _01762_;
  wire _01763_;
  wire _01764_;
  wire _01765_;
  wire _01766_;
  wire _01767_;
  wire _01768_;
  wire _01769_;
  wire _01770_;
  wire _01771_;
  wire _01772_;
  wire _01773_;
  wire _01774_;
  wire _01775_;
  wire _01776_;
  wire _01777_;
  wire _01778_;
  wire _01779_;
  wire _01780_;
  wire _01781_;
  wire _01782_;
  wire _01783_;
  wire _01784_;
  wire _01785_;
  wire _01786_;
  wire _01787_;
  wire _01788_;
  wire _01789_;
  wire _01790_;
  wire _01791_;
  wire _01792_;
  wire _01793_;
  wire _01794_;
  wire _01795_;
  wire _01796_;
  wire _01797_;
  wire _01798_;
  wire _01799_;
  wire _01800_;
  wire _01801_;
  wire _01802_;
  wire _01803_;
  wire _01804_;
  wire _01805_;
  wire _01806_;
  wire _01807_;
  wire _01808_;
  wire _01809_;
  wire _01810_;
  wire _01811_;
  wire _01812_;
  wire _01813_;
  wire _01814_;
  wire _01815_;
  wire _01816_;
  wire _01817_;
  wire _01818_;
  wire _01819_;
  wire _01820_;
  wire _01821_;
  wire _01822_;
  wire _01823_;
  wire _01824_;
  wire _01825_;
  wire _01826_;
  wire _01827_;
  wire _01828_;
  wire _01829_;
  wire _01830_;
  wire _01831_;
  wire _01832_;
  wire _01833_;
  wire _01834_;
  wire _01835_;
  wire _01836_;
  wire _01837_;
  wire _01838_;
  wire _01839_;
  wire _01840_;
  wire _01841_;
  wire _01842_;
  wire _01843_;
  wire _01844_;
  wire _01845_;
  wire _01846_;
  wire _01847_;
  wire _01848_;
  wire _01849_;
  wire _01850_;
  wire _01851_;
  wire _01852_;
  wire _01853_;
  wire _01854_;
  wire _01855_;
  wire _01856_;
  wire _01857_;
  wire _01858_;
  wire _01859_;
  wire _01860_;
  wire _01861_;
  wire _01862_;
  wire _01863_;
  wire _01864_;
  wire _01865_;
  wire _01866_;
  wire _01867_;
  wire _01868_;
  wire _01869_;
  wire _01870_;
  wire _01871_;
  wire _01872_;
  wire _01873_;
  wire _01874_;
  wire _01875_;
  wire _01876_;
  wire _01877_;
  wire _01878_;
  wire _01879_;
  wire _01880_;
  wire _01881_;
  wire _01882_;
  wire _01883_;
  wire _01884_;
  wire _01885_;
  wire _01886_;
  wire _01887_;
  wire _01888_;
  wire _01889_;
  wire _01890_;
  wire _01891_;
  wire _01892_;
  wire _01893_;
  wire _01894_;
  wire _01895_;
  wire _01896_;
  wire _01897_;
  wire _01898_;
  wire _01899_;
  wire _01900_;
  wire _01901_;
  wire _01902_;
  wire _01903_;
  wire _01904_;
  wire _01905_;
  wire _01906_;
  wire _01907_;
  wire _01908_;
  wire _01909_;
  wire _01910_;
  wire _01911_;
  wire _01912_;
  wire _01913_;
  wire _01914_;
  wire _01915_;
  wire _01916_;
  wire _01917_;
  wire _01918_;
  wire _01919_;
  wire _01920_;
  wire _01921_;
  wire _01922_;
  wire _01923_;
  wire _01924_;
  wire _01925_;
  wire _01926_;
  wire _01927_;
  wire _01928_;
  wire _01929_;
  wire _01930_;
  wire _01931_;
  wire _01932_;
  wire _01933_;
  wire _01934_;
  wire _01935_;
  wire _01936_;
  wire _01937_;
  wire _01938_;
  wire _01939_;
  wire _01940_;
  wire _01941_;
  wire _01942_;
  wire _01943_;
  wire _01944_;
  wire _01945_;
  wire _01946_;
  wire _01947_;
  wire _01948_;
  wire _01949_;
  wire _01950_;
  wire _01951_;
  wire _01952_;
  wire _01953_;
  wire _01954_;
  wire _01955_;
  wire _01956_;
  wire _01957_;
  wire _01958_;
  wire _01959_;
  wire _01960_;
  wire _01961_;
  wire _01962_;
  wire _01963_;
  wire _01964_;
  wire _01965_;
  wire _01966_;
  wire _01967_;
  wire _01968_;
  wire _01969_;
  wire _01970_;
  wire _01971_;
  wire _01972_;
  wire _01973_;
  wire _01974_;
  wire _01975_;
  wire _01976_;
  wire _01977_;
  wire _01978_;
  wire _01979_;
  wire _01980_;
  wire _01981_;
  wire _01982_;
  wire _01983_;
  wire _01984_;
  wire _01985_;
  wire _01986_;
  wire _01987_;
  wire _01988_;
  wire _01989_;
  wire _01990_;
  wire _01991_;
  wire _01992_;
  wire _01993_;
  wire _01994_;
  wire _01995_;
  wire _01996_;
  wire _01997_;
  wire _01998_;
  wire _01999_;
  wire _02000_;
  wire _02001_;
  wire _02002_;
  wire _02003_;
  wire _02004_;
  wire _02005_;
  wire _02006_;
  wire _02007_;
  wire _02008_;
  wire _02009_;
  wire _02010_;
  wire _02011_;
  wire _02012_;
  wire _02013_;
  wire _02014_;
  wire _02015_;
  wire _02016_;
  wire _02017_;
  wire _02018_;
  wire _02019_;
  wire _02020_;
  wire _02021_;
  wire _02022_;
  wire _02023_;
  wire _02024_;
  wire _02025_;
  wire _02026_;
  wire _02027_;
  wire _02028_;
  wire _02029_;
  wire _02030_;
  wire _02031_;
  wire _02032_;
  wire _02033_;
  wire _02034_;
  wire _02035_;
  wire _02036_;
  wire _02037_;
  wire _02038_;
  wire _02039_;
  wire _02040_;
  wire _02041_;
  wire _02042_;
  wire _02043_;
  wire _02044_;
  wire _02045_;
  wire _02046_;
  wire _02047_;
  wire _02048_;
  wire _02049_;
  wire _02050_;
  wire _02051_;
  wire _02052_;
  wire _02053_;
  wire _02054_;
  wire _02055_;
  wire _02056_;
  wire _02057_;
  wire _02058_;
  wire _02059_;
  wire _02060_;
  wire _02061_;
  wire _02062_;
  wire _02063_;
  wire _02064_;
  wire _02065_;
  wire _02066_;
  wire _02067_;
  wire _02068_;
  wire _02069_;
  wire _02070_;
  wire _02071_;
  wire _02072_;
  wire _02073_;
  wire _02074_;
  wire _02075_;
  wire _02076_;
  wire _02077_;
  wire _02078_;
  wire _02079_;
  wire _02080_;
  wire _02081_;
  wire _02082_;
  wire _02083_;
  wire _02084_;
  wire _02085_;
  wire _02086_;
  wire _02087_;
  wire _02088_;
  wire _02089_;
  wire _02090_;
  wire _02091_;
  wire _02092_;
  wire _02093_;
  wire _02094_;
  wire _02095_;
  wire _02096_;
  wire _02097_;
  wire _02098_;
  wire _02099_;
  wire _02100_;
  wire _02101_;
  wire _02102_;
  wire _02103_;
  wire _02104_;
  wire _02105_;
  wire _02106_;
  wire _02107_;
  wire _02108_;
  wire _02109_;
  wire _02110_;
  wire _02111_;
  wire _02112_;
  wire _02113_;
  wire _02114_;
  wire _02115_;
  wire _02116_;
  wire _02117_;
  wire _02118_;
  wire _02119_;
  wire _02120_;
  wire _02121_;
  wire _02122_;
  wire _02123_;
  wire _02124_;
  wire _02125_;
  wire _02126_;
  wire _02127_;
  wire _02128_;
  wire _02129_;
  wire _02130_;
  wire _02131_;
  wire _02132_;
  wire _02133_;
  wire _02134_;
  wire _02135_;
  wire _02136_;
  wire _02137_;
  wire _02138_;
  wire _02139_;
  wire _02140_;
  wire _02141_;
  wire _02142_;
  wire _02143_;
  wire _02144_;
  wire _02145_;
  wire _02146_;
  wire _02147_;
  wire _02148_;
  wire _02149_;
  wire _02150_;
  wire _02151_;
  wire _02152_;
  wire _02153_;
  wire _02154_;
  wire _02155_;
  wire _02156_;
  wire _02157_;
  wire _02158_;
  wire _02159_;
  wire _02160_;
  wire _02161_;
  wire _02162_;
  wire _02163_;
  wire _02164_;
  wire _02165_;
  wire _02166_;
  wire _02167_;
  wire _02168_;
  wire _02169_;
  wire _02170_;
  wire _02171_;
  wire _02172_;
  wire _02173_;
  wire _02174_;
  wire _02175_;
  wire _02176_;
  wire _02177_;
  wire _02178_;
  wire _02179_;
  wire _02180_;
  wire _02181_;
  wire _02182_;
  wire _02183_;
  wire _02184_;
  wire _02185_;
  wire _02186_;
  wire _02187_;
  wire _02188_;
  wire _02189_;
  wire _02190_;
  wire _02191_;
  wire _02192_;
  wire _02193_;
  wire _02194_;
  wire _02195_;
  wire _02196_;
  wire _02197_;
  wire _02198_;
  wire _02199_;
  wire _02200_;
  wire _02201_;
  wire _02202_;
  wire _02203_;
  wire _02204_;
  wire _02205_;
  wire _02206_;
  wire _02207_;
  wire _02208_;
  wire _02209_;
  wire _02210_;
  wire _02211_;
  wire _02212_;
  wire _02213_;
  wire _02214_;
  wire _02215_;
  wire _02216_;
  wire _02217_;
  wire _02218_;
  wire _02219_;
  wire _02220_;
  wire _02221_;
  wire _02222_;
  wire _02223_;
  wire _02224_;
  wire _02225_;
  wire _02226_;
  wire _02227_;
  wire _02228_;
  wire _02229_;
  wire _02230_;
  wire _02231_;
  wire _02232_;
  wire _02233_;
  wire _02234_;
  wire _02235_;
  wire _02236_;
  wire _02237_;
  wire _02238_;
  wire _02239_;
  wire _02240_;
  wire _02241_;
  wire _02242_;
  wire _02243_;
  wire _02244_;
  wire _02245_;
  wire _02246_;
  wire _02247_;
  wire _02248_;
  wire _02249_;
  wire _02250_;
  wire _02251_;
  wire _02252_;
  wire _02253_;
  wire _02254_;
  wire _02255_;
  wire _02256_;
  wire _02257_;
  wire _02258_;
  wire _02259_;
  wire _02260_;
  wire _02261_;
  wire _02262_;
  wire _02263_;
  wire _02264_;
  wire _02265_;
  wire _02266_;
  wire _02267_;
  wire _02268_;
  wire _02269_;
  wire _02270_;
  wire _02271_;
  wire _02272_;
  wire _02273_;
  wire _02274_;
  wire _02275_;
  wire _02276_;
  wire _02277_;
  wire _02278_;
  wire _02279_;
  wire _02280_;
  wire _02281_;
  wire _02282_;
  wire _02283_;
  wire _02284_;
  wire _02285_;
  wire _02286_;
  wire _02287_;
  wire _02288_;
  wire _02289_;
  wire _02290_;
  wire _02291_;
  wire _02292_;
  wire _02293_;
  wire _02294_;
  wire _02295_;
  wire _02296_;
  wire _02297_;
  wire _02298_;
  wire _02299_;
  wire _02300_;
  wire _02301_;
  wire _02302_;
  wire _02303_;
  wire _02304_;
  wire _02305_;
  wire _02306_;
  wire _02307_;
  wire _02308_;
  wire _02309_;
  wire _02310_;
  wire _02311_;
  wire _02312_;
  wire _02313_;
  wire _02314_;
  wire _02315_;
  wire _02316_;
  wire _02317_;
  wire _02318_;
  wire _02319_;
  wire _02320_;
  wire _02321_;
  wire _02322_;
  wire _02323_;
  wire _02324_;
  wire _02325_;
  wire _02326_;
  wire _02327_;
  wire _02328_;
  wire _02329_;
  wire _02330_;
  wire _02331_;
  wire _02332_;
  wire _02333_;
  wire _02334_;
  wire _02335_;
  wire _02336_;
  wire _02337_;
  wire _02338_;
  wire _02339_;
  wire _02340_;
  wire _02341_;
  wire _02342_;
  wire _02343_;
  wire _02344_;
  wire _02345_;
  wire _02346_;
  wire _02347_;
  wire _02348_;
  wire _02349_;
  wire _02350_;
  wire _02351_;
  wire _02352_;
  wire _02353_;
  wire _02354_;
  wire _02355_;
  wire _02356_;
  wire _02357_;
  wire _02358_;
  wire _02359_;
  wire _02360_;
  wire _02361_;
  wire _02362_;
  wire _02363_;
  wire _02364_;
  wire _02365_;
  wire _02366_;
  wire _02367_;
  wire _02368_;
  wire _02369_;
  wire _02370_;
  wire _02371_;
  wire _02372_;
  wire _02373_;
  wire _02374_;
  wire _02375_;
  wire _02376_;
  wire _02377_;
  wire _02378_;
  wire _02379_;
  wire _02380_;
  wire _02381_;
  wire _02382_;
  wire _02383_;
  wire _02384_;
  wire _02385_;
  wire _02386_;
  wire _02387_;
  wire _02388_;
  wire _02389_;
  wire _02390_;
  wire _02391_;
  wire _02392_;
  wire _02393_;
  wire _02394_;
  wire _02395_;
  wire _02396_;
  wire _02397_;
  wire _02398_;
  wire _02399_;
  wire _02400_;
  wire _02401_;
  wire _02402_;
  wire _02403_;
  wire _02404_;
  wire _02405_;
  wire _02406_;
  wire _02407_;
  wire _02408_;
  wire _02409_;
  wire _02410_;
  wire _02411_;
  wire _02412_;
  wire _02413_;
  wire _02414_;
  wire _02415_;
  wire _02416_;
  wire _02417_;
  wire _02418_;
  wire _02419_;
  wire _02420_;
  wire _02421_;
  wire _02422_;
  wire _02423_;
  wire _02424_;
  wire _02425_;
  wire _02426_;
  wire _02427_;
  wire _02428_;
  wire _02429_;
  wire _02430_;
  wire _02431_;
  wire _02432_;
  wire _02433_;
  wire _02434_;
  wire _02435_;
  wire _02436_;
  wire _02437_;
  wire _02438_;
  wire _02439_;
  wire _02440_;
  wire _02441_;
  wire _02442_;
  wire _02443_;
  wire _02444_;
  wire _02445_;
  wire _02446_;
  wire _02447_;
  wire _02448_;
  wire _02449_;
  wire _02450_;
  wire _02451_;
  wire _02452_;
  wire _02453_;
  wire _02454_;
  wire _02455_;
  wire _02456_;
  wire _02457_;
  wire _02458_;
  wire _02459_;
  wire _02460_;
  wire _02461_;
  wire _02462_;
  wire _02463_;
  wire _02464_;
  wire _02465_;
  wire _02466_;
  wire _02467_;
  wire _02468_;
  wire _02469_;
  wire _02470_;
  wire _02471_;
  wire _02472_;
  wire _02473_;
  wire _02474_;
  wire _02475_;
  wire _02476_;
  wire _02477_;
  wire _02478_;
  wire _02479_;
  wire _02480_;
  wire _02481_;
  wire _02482_;
  wire _02483_;
  wire _02484_;
  wire _02485_;
  wire _02486_;
  wire _02487_;
  wire _02488_;
  wire _02489_;
  wire _02490_;
  wire _02491_;
  wire _02492_;
  wire _02493_;
  wire _02494_;
  wire _02495_;
  wire _02496_;
  wire _02497_;
  wire _02498_;
  wire _02499_;
  wire _02500_;
  wire _02501_;
  wire _02502_;
  wire _02503_;
  wire _02504_;
  wire _02505_;
  wire _02506_;
  wire _02507_;
  wire _02508_;
  wire _02509_;
  wire _02510_;
  wire _02511_;
  wire _02512_;
  wire _02513_;
  wire _02514_;
  wire _02515_;
  wire _02516_;
  wire _02517_;
  wire _02518_;
  wire _02519_;
  wire _02520_;
  wire _02521_;
  wire _02522_;
  wire _02523_;
  wire _02524_;
  wire _02525_;
  wire _02526_;
  wire _02527_;
  wire _02528_;
  wire _02529_;
  wire _02530_;
  wire _02531_;
  wire _02532_;
  wire _02533_;
  wire _02534_;
  wire _02535_;
  wire _02536_;
  wire _02537_;
  wire _02538_;
  wire _02539_;
  wire _02540_;
  wire _02541_;
  wire _02542_;
  wire _02543_;
  wire _02544_;
  wire _02545_;
  wire _02546_;
  wire _02547_;
  wire _02548_;
  wire _02549_;
  wire _02550_;
  wire _02551_;
  wire _02552_;
  wire _02553_;
  wire _02554_;
  wire _02555_;
  wire _02556_;
  wire _02557_;
  wire _02558_;
  wire _02559_;
  wire _02560_;
  wire _02561_;
  wire _02562_;
  wire _02563_;
  wire _02564_;
  wire _02565_;
  wire _02566_;
  wire _02567_;
  wire _02568_;
  wire _02569_;
  wire _02570_;
  wire _02571_;
  wire _02572_;
  wire _02573_;
  wire _02574_;
  wire _02575_;
  wire _02576_;
  wire _02577_;
  wire _02578_;
  wire _02579_;
  wire _02580_;
  wire _02581_;
  wire _02582_;
  wire _02583_;
  wire _02584_;
  wire _02585_;
  wire _02586_;
  wire _02587_;
  wire _02588_;
  wire _02589_;
  wire _02590_;
  wire _02591_;
  wire _02592_;
  wire _02593_;
  wire _02594_;
  wire _02595_;
  wire _02596_;
  wire _02597_;
  wire _02598_;
  wire _02599_;
  wire _02600_;
  wire _02601_;
  wire _02602_;
  wire _02603_;
  wire _02604_;
  wire _02605_;
  wire _02606_;
  wire _02607_;
  wire _02608_;
  wire _02609_;
  wire _02610_;
  wire _02611_;
  wire _02612_;
  wire _02613_;
  wire _02614_;
  wire _02615_;
  wire _02616_;
  wire _02617_;
  wire _02618_;
  wire _02619_;
  wire _02620_;
  wire _02621_;
  wire _02622_;
  wire _02623_;
  wire _02624_;
  wire _02625_;
  wire _02626_;
  wire _02627_;
  wire _02628_;
  wire _02629_;
  wire _02630_;
  wire _02631_;
  wire _02632_;
  wire _02633_;
  wire _02634_;
  wire _02635_;
  wire _02636_;
  wire _02637_;
  wire _02638_;
  wire _02639_;
  wire _02640_;
  wire _02641_;
  wire _02642_;
  wire _02643_;
  wire _02644_;
  wire _02645_;
  wire _02646_;
  wire _02647_;
  wire _02648_;
  wire _02649_;
  wire _02650_;
  wire _02651_;
  wire _02652_;
  wire _02653_;
  wire _02654_;
  wire _02655_;
  wire _02656_;
  wire _02657_;
  wire _02658_;
  wire _02659_;
  wire _02660_;
  wire _02661_;
  wire _02662_;
  wire _02663_;
  wire _02664_;
  wire _02665_;
  wire _02666_;
  wire _02667_;
  wire _02668_;
  wire _02669_;
  wire _02670_;
  wire _02671_;
  wire _02672_;
  wire _02673_;
  wire _02674_;
  wire _02675_;
  wire _02676_;
  wire _02677_;
  wire _02678_;
  wire _02679_;
  wire _02680_;
  wire _02681_;
  wire _02682_;
  wire _02683_;
  wire _02684_;
  wire _02685_;
  wire _02686_;
  wire _02687_;
  wire _02688_;
  wire _02689_;
  wire _02690_;
  wire _02691_;
  wire _02692_;
  wire _02693_;
  wire _02694_;
  wire _02695_;
  wire _02696_;
  wire _02697_;
  wire _02698_;
  wire _02699_;
  wire _02700_;
  wire _02701_;
  wire _02702_;
  wire _02703_;
  wire _02704_;
  wire _02705_;
  wire _02706_;
  wire _02707_;
  wire _02708_;
  wire _02709_;
  wire _02710_;
  wire _02711_;
  wire _02712_;
  wire _02713_;
  wire _02714_;
  wire _02715_;
  wire _02716_;
  wire _02717_;
  wire _02718_;
  wire _02719_;
  wire _02720_;
  wire _02721_;
  wire _02722_;

module vsdbabysoc(OUT, reset, VCO_IN, ENb_CP, ENb_VCO, REF, VREFH);
  wire CLK;
  input ENb_CP;
  wire ENb_CP;
  input ENb_VCO;
  wire ENb_VCO;
  output OUT;
  wire OUT;
  input REF;
  wire REF;
  wire [9:0] RV_TO_DAC;
  input VCO_IN;
  wire VCO_IN;
  input VREFH;
  wire VREFH;
  input reset;
  wire reset;
  rvmyth core (
    .CLK(CLK),
    .OUT(RV_TO_DAC),
    .reset(reset)
  );
  avsddac dac (
    .D(RV_TO_DAC),
    .OUT(OUT),
    .VREFH(VREFH)
  );
  avsdpll pll (
    .CLK(CLK),
    .ENb_CP(ENb_CP),
    .ENb_VCO(ENb_VCO),
    .REF(REF),
    .VCO_IN(VCO_IN)
  );
endmodule



```
</details>
- Step 1: Perform iverilog compilation for rvmyth.v file generated from TL Verilog using Sandpiper tool, completed back in Laboratory 6

```
iverilog -o ./pre_synth_sim.out -DPRE_SYNTH_SIM src/module/testbench.v -I src/include -I src/module/
```
After this we dump the ./pre_synth_sim.out file to create the .vcd file using the following command
```
./pre_synth_sim.out
```
We then run this .vcd file on gtkwave to observe the output
```
gtkwave pre_synth_sim.vcd
```
The above process has been executed by me in the following way
![s15](https://github.com/user-attachments/assets/524e6943-d130-4a8e-a457-ba4140acc389)

![s1_1](https://github.com/user-attachments/assets/c66276d6-1eaa-4456-ab6a-258180ac409d)
![s1_2](https://github.com/user-attachments/assets/3b1e23c0-6ebd-4992-867a-853bb179e27a)

- Step 2: Perform synthesis using Yosys
![s6](https://github.com/user-attachments/assets/1b4c20ec-723c-4f2f-927a-823efd8565b4)
![s7](https://github.com/user-attachments/assets/4da4ec9c-da17-4228-b759-91b201b4ffb3)
![s8](https://github.com/user-attachments/assets/619b5abe-a03f-4047-83f0-85ec22f8e00f)
![s9](https://github.com/user-attachments/assets/fc3dc208-795c-42cc-9ad5-72352b3f4970)
![s10](https://github.com/user-attachments/assets/6d1b60ca-b885-4e4e-b55e-5d8e722630ca)
![s11](https://github.com/user-attachments/assets/765d8f06-0383-45e3-bf54-8208452a2310)
![s](https://github.com/user-attachments/assets/34d06c78-72b0-44d1-9562-dda03d390f88)

- Step 3: Use the netlist of rvmyth generated after synthesis (rvmyth_netlist.v) and run it along with the testbench.
  
![s12](https://github.com/user-attachments/assets/c079645c-5452-4906-952a-53998e9ba465)
![s16](https://github.com/user-attachments/assets/707e88cf-cff1-41f1-b50a-2d485ec19a22)
![s17](https://github.com/user-attachments/assets/737aa68e-dd6e-45f4-8fe0-1319071fe288)
![s18](https://github.com/user-attachments/assets/d1c80f37-ab74-4705-90a6-a498bcb0a177)

- Output Waveforms:

Before Synthesis

![s1_1](https://github.com/user-attachments/assets/c66276d6-1eaa-4456-ab6a-258180ac409d)


After Synthesis

![s16](https://github.com/user-attachments/assets/c9a479d4-4bfa-4531-9ed0-be5233107df2)
![s18](https://github.com/user-attachments/assets/d16d4319-73d7-4636-b13d-0e2630b84c7c)



</details>
