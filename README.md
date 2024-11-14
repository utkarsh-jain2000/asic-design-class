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
![Screenshot 2024-10-24 015458](https://github.com/user-attachments/assets/6eb8b37e-cddc-43b2-92d3-28d5c665286f)


After Synthesis

![s16](https://github.com/user-attachments/assets/c9a479d4-4bfa-4531-9ed0-be5233107df2)
![s18](https://github.com/user-attachments/assets/d16d4319-73d7-4636-b13d-0e2630b84c7c)
![s17](https://github.com/user-attachments/assets/737aa68e-dd6e-45f4-8fe0-1319071fe288)


</details>

## Static Timing Analysis for Synthesized Risc-V Core using OpenSTA 
<details>
  <summary> LAB - Timing Analysis of VSDBabySOC using OpenSTA </summary>

 #### STA:
 
Static Timing Analysis (STA) is essential in ASIC design for ensuring that the digital circuit meets the required timing constraints without requiring dynamic simulation of actual data. The focus of STA is to validate that all timing paths within the design meet specific constraints, which ensures the circuit will function correctly across all operational conditions.

- Timing Paths: In STA, timing paths are analyzed to ensure data can travel from one point to another within a defined time. The main types are:

- Setup Paths: Ensure data arrives at the next stage before the clock edge.

- Hold Paths: Ensure data is stable for a certain period after the clock edge.

- Clock Domains: STA divides the design into different clock domains to verify timing between elements synchronized to the same or different clocks. For multiple clocks, STA verifies the timing paths between each clock domain, focusing on:

- Synchronous Domains: Where clocks are related and can be analyzed for setup and hold constraints.

- Asynchronous Domains: Where clocks are unrelated, requiring special handling, often with synchronizers or FIFO buffers. Clock Skew and Jitter:

- Clock Skew: The difference in arrival times of a clock signal at different flip-flops. STA checks skew impact since it affects timing paths and data setup/hold requirements.

- Clock Jitter: Variation in clock edge timing due to noise or other factors. STA incorporates jitter in timing analysis to ensure that jitter doesn’t cause timing violations.

#### Timing Checks:
- Setup Check: Ensures data arrives before the clock edge, allowing sufficient time for stabilization.
- Hold Check: Ensures data remains stable long enough after the clock edge.

#### Timing Margins and Slack:
- Slack: The difference between the required time and the actual arrival time of signals. Positive slack means timing constraints are met, while negative slack indicates a timing violation.
Setup Slack: Time margin for setup constraints.
- Hold Slack: Time margin for hold constraints.
- Static Timing Tools: STA tools, like Synopsys PrimeTime and Cadence Tempus, perform analysis by creating and traversing timing graphs that represent all paths in the design. These tools provide reports on slack, critical paths, and timing violations.
Process, Voltage, and Temperature (PVT) Corners: STA includes PVT analysis to account for variations in manufacturing, operational voltages, and temperature ranges. STA ensures that timing constraints are met across worst-case PVT corners.

#### Optimization Techniques:
- Buffer Insertion: Adds buffers to reduce delay in long paths.
- Gate Sizing: Resizes gates to improve timing on critical paths.
- Clock Tree Optimization (CTO): Minimizes skew and jitter in the clock distribution network. By ensuring that timing analysis is thorough and covers all potential scenarios, STA plays a crucial role in achieving reliable and high-performance ASIC designs.

##### reg2reg Path:
A reg2reg path (register-to-register path) refers to a timing path in a digital circuit that connects two sequential elements, specifically flip-flops or registers. This path is crucial in the context of Static Timing Analysis (STA) because it represents the flow of data from one register to another through combinational logic.

Reg2reg paths are essential for ensuring proper data flow and synchronization in digital circuits, especially in designs with pipelining or sequential operations. Analyzing these paths helps in verifying that the data processing occurs correctly across clock cycles, thereby ensuring the overall functionality and reliability of the circuit.

##### clk2reg Path:
A clk2reg path (clock-to-register path) refers to a timing path in a digital circuit that connects the clock signal to a register (flip-flop). This path is crucial for ensuring that the register operates correctly in response to clock events.

The following commands were run to get the max-min report of the VSDbabysoc design:
```
read_liberty /mnt/sky130_fd_sc_hd__tt_025C_1v80.lib
read_verilog /mnt/vsdbabysoc.synth.v  
link_design rvmyth

create_clock -name CLK -period 9.1 [get_ports CLK]
set_clock_uncertainty [expr 0.05 * 9.1] -setup [get_clocks CLK]
set_clock_uncertainty [expr 0.08 * 9.1] -hold [get_clocks CLK]
set_clock_transition [expr 0.05 * 9.1] [get_clocks CLK]
set_input_transition [expr 0.08 * 9.1] [all_inputs]

report_checks -path_delay max
report_checks -path_delay min
```

Timing configurations:
```
Clock period: 9.1 nanoseconds
Setup uncertainty: 5% of clock period
Clock transition: 5% of clock period
Hold uncertainty: 8% of clock period
Input transition: 8% of clock period
```
Terminal output :
![a1](https://github.com/user-attachments/assets/e5168c7b-a0bf-4540-a33b-84f3c5434f3e)
![a2](https://github.com/user-attachments/assets/5dfa4272-02c3-4234-b404-7b605efb4db1)

Reg2Reg max path:
![a3](https://github.com/user-attachments/assets/434483f6-f079-4217-8b77-21fb0604fa68)

Reg2Reg min path:
![a4](https://github.com/user-attachments/assets/0b076f54-2b6c-4dcf-a4d3-a4ceabc9c309)

The max path report indicates Setup Slack while the min path report shows Hold Slack measurements.
</details>

## Lab 15 : PVT Corner Analysis for Synthesized VSDBabySoC using OpenSTA
<details>
  <summary> Perform Static Timing Analysis on the synthesized RISC-V netlist from Laboratory 14, using different PVT files. </summary>

  The STA checks are performed across all the corners to confirm the design meets the target timing requirements.

The worst max path (Setup-critical) corners in the sub-40nm process nodes are usually: ss_LowTemp_LowVolt, ss_HighTemp_LowVolt (Slowest corners) The worst min path (Hold-critical) corners being: ff_LowTemp_HighVolt,ff_HighTemp_HighVolt (Fastest corners).

The SDC file used for generating clock and data constraints is given below:

```
set_units -time ns
set PERIOD 9.1
create_clock [get_pins {pll/CLK}] -name clk -period $PERIOD
set_clock_uncertainty [expr 0.05 * $PERIOD] -setup [get_clocks clk]
set_clock_uncertainty [expr 0.08 * $PERIOD] -hold [get_clocks clk]
set_clock_transition [expr 0.05 * $PERIOD] [get_clocks clk]


set_input_transition [expr $PERIOD * 0.08] [get_ports ENB_CP]
set_input_transition [expr $PERIOD * 0.08] [get_ports ENB_VCO]
set_input_transition [expr $PERIOD * 0.08] [get_ports REF]
set_input_transition [expr $PERIOD * 0.08] [get_ports VCO_IN]
set_input_transition [expr $PERIOD * 0.08] [get_ports VREFH]
```
The below tcl script sta_pvt.tcl can be run to performt the STA across the PVT corners for which the sky130 lib files are available:
```
set list_of_lib_files(1) "sky130_fd_sc_hd__tt_025C_1v80.lib"
set list_of_lib_files(2) "sky130_fd_sc_hd__tt_100C_1v80.lib"
set list_of_lib_files(3) "sky130_fd_sc_hd__ff_100C_1v65.lib"
set list_of_lib_files(4) "sky130_fd_sc_hd__ff_100C_1v95.lib"
set list_of_lib_files(5) "sky130_fd_sc_hd__ff_n40C_1v56.lib"
set list_of_lib_files(6) "sky130_fd_sc_hd__ff_n40C_1v65.lib"
set list_of_lib_files(7) "sky130_fd_sc_hd__ff_n40C_1v76.lib"
set list_of_lib_files(8) "sky130_fd_sc_hd__ff_n40C_1v95.lib"
set list_of_lib_files(9) "sky130_fd_sc_hd__ss_100C_1v40.lib"
set list_of_lib_files(10) "sky130_fd_sc_hd__ss_100C_1v60.lib"
set list_of_lib_files(11) "sky130_fd_sc_hd__ss_n40C_1v28.lib"
set list_of_lib_files(12) "sky130_fd_sc_hd__ss_n40C_1v35.lib"
set list_of_lib_files(13) "sky130_fd_sc_hd__ss_n40C_1v40.lib"
set list_of_lib_files(14) "sky130_fd_sc_hd__ss_n40C_1v44.lib"
set list_of_lib_files(15) "sky130_fd_sc_hd__ss_n40C_1v60.lib"
set list_of_lib_files(16) "sky130_fd_sc_hd__ss_n40C_1v76.lib"

for {set i 1} {$i <= [array size list_of_lib_files]} {incr i} {
read_liberty /mnt/$list_of_lib_files($i)
read_liberty -min /mnt/avsdpll.lib
read_liberty -max /mnt/avsdpll.lib
read_liberty -min /mnt/avsddac.lib
read_liberty -max /mnt/avsddac.lib
read_verilog /mnt/vsdbabysoc.synth.v
link_design rvmyth
read_sdc /mnt/vsdbabysoc_synthesis.sdc
check_setup -verbose
report_checks -path_delay min_max -fields {nets cap slew input_pins fanout} -digits {4} > /mnt/sta_output/min_max_$list_of_lib_files($i).txt

exec echo "$list_of_lib_files($i)" >> /mnt/sta_output/sta_worst_max_slack.txt
report_worst_slack -max -digits {4} >> /mnt/sta_output/sta_worst_max_slack.txt

exec echo "$list_of_lib_files($i)" >> /mnt/sta_output/sta_worst_min_slack.txt
report_worst_slack -min -digits {4} >> /mnt/sta_output/sta_worst_min_slack.txt

exec echo "$list_of_lib_files($i)" >> /mnt/sta_output/sta_tns.txt
report_tns -digits {4} >> /mnt/sta_output/sta_tns.txt

exec echo "$list_of_lib_files($i)" >> /mnt/sta_output/sta_wns.txt
report_wns -digits {4} >> /mnt/sta_output/sta_wns.txt
}


```
Now, to execute the tickle script, follow the below commands
```
sta
source scripts/sta_pvt.tcl
```
![s1](https://github.com/user-attachments/assets/9aa16204-76a0-4afb-95f7-b81b6b5cff6c)

Below table shows the output for different library files,

![excel](https://github.com/user-attachments/assets/50679de5-879e-4163-a68b-f5fc066767f4)


Following graph shows the worst setup slack measured for different library files,
![wss](https://github.com/user-attachments/assets/49b73ae9-97a4-4cca-80c2-06a038a71762)

Following graph shows the worst hold slack measured for different library files,
![worst hold slack](https://github.com/user-attachments/assets/e0f7be1b-2b30-4e5b-b31d-69506731579e)


Following graph shows the worst negative slack measured for different library files,
![wns](https://github.com/user-attachments/assets/60066fd6-acda-4230-bb7f-4eb69873b69f)


Following graph shows the total negative slack measured for different library files,

![tns](https://github.com/user-attachments/assets/aeb2a280-7921-4867-ba72-e82f1690e678)

Observation:

1: Worst setup slack - sky130_fd_sc_hd__ss_n40C_1v28 PVT Corner library file

2: Worst hold slack - sky130_fd_sc_hd__ff_n40C_1v95 PVT Corner library file

</details>


## Lab 16 : Advanced Physical Design Using Openlane/Sky130 Wokshop
<details>
  <summary> Advanced Physical Design Using Openlane/Sky130 Wokshop </summary>

  
<details>
  <summary> day 1 </summary>
Tasks:

Run 'picorv32a' design synthesis using OpenLANE flow and generate necessary outputs.

Calculate the flop ratio.

The Flop ratio can be calculated as follows:
```
Flop Ratio = Number of D Flip-Flops/ Total Number of Cells
	Percentage of Flip Flops = Flop Ratio * 100
```

1. Run 'picorv32a' design floorplan using OpenLANE flow and generate necessary outputs
Commands to invoke the OpenLANE flow and perform floorplan -
```
# Change directory to openlane flow directory
cd Desktop/work/tools/openlane_working_dir/openlane

# alias docker='docker run -it -v $(pwd):/openLANE_flow -v $PDK_ROOT:$PDK_ROOT -e PDK_ROOT=$PDK_ROOT -u $(id -u $USER):$(id -g $USER) efabless/openlane:v0.21'
# Since we have aliased the long command to 'docker' we can invoke the OpenLANE flow docker sub-system by just running this command
docker
# Now that we have entered the OpenLANE flow contained docker sub-system we can invoke the OpenLANE flow in the Interactive mode using the following command
./flow.tcl -interactive

# Now that OpenLANE flow is open we have to input the required packages for proper functionality of the OpenLANE flow
package require openlane 0.9

# Now the OpenLANE flow is ready to run any design and initially we have to prep the design creating some necessary files and directories for running a specific design which in our case is 'picorv32a'
prep -design picorv32a

# Now that the design is prepped and ready, we can run synthesis using following command
run_synthesis

# Now we can run floorplan
run_floorplan
```

Screenshots of running each commands -
  ![s1](https://github.com/user-attachments/assets/c4d582ff-92c7-4913-b732-63c248d77eb1)
![s2](https://github.com/user-attachments/assets/b4d25b49-f492-492d-8b2b-ac0e47922aee)
![s3](https://github.com/user-attachments/assets/0ef3a087-031a-401d-b187-e2d89e4b418f)
![s4](https://github.com/user-attachments/assets/879f947a-a03a-4f29-91f7-a6bd2fe09918)
![s5](https://github.com/user-attachments/assets/8319a754-a646-406d-bda8-330c48777a2b)
![s6](https://github.com/user-attachments/assets/5945ba08-b012-4f5a-8f88-69e7393cf74e)
![s7](https://github.com/user-attachments/assets/2a5d68dc-a830-4457-9c3b-2319976adc61)
![s8](https://github.com/user-attachments/assets/4a2782a3-83c3-4753-97b8-10ad76c04da4)
![s9](https://github.com/user-attachments/assets/19c911ab-f801-43e9-a5eb-29a2454c397c)
![s10](https://github.com/user-attachments/assets/3474cb31-521f-4490-8d36-5fd97a040a65)
![s11](https://github.com/user-attachments/assets/28650c0b-9071-443a-92ec-5ee043243243)
![s12](https://github.com/user-attachments/assets/fdf01c9a-107b-457a-819d-188e59d97b68)
![s13](https://github.com/user-attachments/assets/222c4a99-0837-4e34-aecc-4a2a2c1ff171)
![s14](https://github.com/user-attachments/assets/cc307187-445c-43cf-aea4-d0720a1fcfed)


###### 2. Calculate the Flop ratio:


![s15](https://github.com/user-attachments/assets/125fcb2b-0dae-40e5-a16e-bc1945678aab)

![s16](https://github.com/user-attachments/assets/0e17b11c-dda3-4891-ad04-6954553cfdbc)
![s17](https://github.com/user-attachments/assets/b1aa9ad7-d43f-4679-835d-31f9bbfb2a99)

![s18](https://github.com/user-attachments/assets/40df3b16-ce2d-4bbc-aab5-d1c1a52311f2)



Calculation of Flop Ratio and DFF % from synthesis statistics report file
```
Flop Ratio = 1613/14876 = 0.108429685
    Percentage of Flip Flops = 0.108429685 ∗ 100 = 10.84296854%
```

</details>
<details>
  <summary> day 2 </summary>

 
####  Good floorplan vs bad floorplan and introduction to library cells
Tasks:

1. Run 'picorv32a' design floorplan using OpenLANE flow and generate necessary outputs.
2. Calculate the die area in microns from the values in floorplan def.
3. Load generated floorplan def in magic tool and explore the floorplan.
4. Run 'picorv32a' design congestion aware placement using OpenLANE flow and generate necessary outputs.
5. Load generated placement def in magic tool and explore the placement. Area of Die in microns = Die width in microns ∗ Die height in microns

- 1. Run 'picorv32a' design floorplan using OpenLANE flow and generate necessary outputs

Commands to invoke the OpenLANE flow and perform floorplan
```
# Change directory to openlane flow directory
cd Desktop/work/tools/openlane_working_dir/openlane

# alias docker='docker run -it -v $(pwd):/openLANE_flow -v $PDK_ROOT:$PDK_ROOT -e PDK_ROOT=$PDK_ROOT -u $(id -u $USER):$(id -g $USER) efabless/openlane:v0.21'
# Since we have aliased the long command to 'docker' we can invoke the OpenLANE flow docker sub-system by just running this command
docker
# Now that we have entered the OpenLANE flow contained docker sub-system we can invoke the OpenLANE flow in the Interactive mode using the following command
./flow.tcl -interactive

# Now that OpenLANE flow is open we have to input the required packages for proper functionality of the OpenLANE flow
package require openlane 0.9

# Now the OpenLANE flow is ready to run any design and initially we have to prep the design creating some necessary files and directories for running a specific design which in our case is 'picorv32a'
prep -design picorv32a

# Now that the design is prepped and ready, we can run synthesis using following command
run_synthesis

# Now we can run floorplan
run_floorplan
```
Screenshot of floorplan run
![s23](https://github.com/user-attachments/assets/ae3fd647-7cd2-4336-aabe-b9575d03326f)

2. Calculate the die area in microns from the values in floorplan def.

  ![s19](https://github.com/user-attachments/assets/fb2885dd-466e-44e3-9c97-649d87838301) 
  ![s20](https://github.com/user-attachments/assets/cfef0ad5-c775-4ef4-91ff-f640a9e5018f)
![s21](https://github.com/user-attachments/assets/c588399c-1b7e-4b44-9790-1ec1f5522fcb)

![s22](https://github.com/user-attachments/assets/f06d037c-6f79-43f4-a82b-ae62ebd755d2)

![s24](https://github.com/user-attachments/assets/97f0145e-a150-496b-9eeb-37ef291c9657)

![s25](https://github.com/user-attachments/assets/c2a32dc1-c3e4-4c35-b5c4-6f8475800fdd)

![s26](https://github.com/user-attachments/assets/95ce3bca-8af2-4702-8cb7-baefbfc71440)

![s27](https://github.com/user-attachments/assets/9d35360c-b30c-4900-b3e2-d648f1fe6744)

![s28](https://github.com/user-attachments/assets/8ec3bbc6-022c-4bd1-b733-89e5e5f9ff84)

![s29](https://github.com/user-attachments/assets/225817f9-2a35-482e-ab89-a58b48e8f6ff)
![30](https://github.com/user-attachments/assets/98ba34df-bf11-41d2-ba4c-715ad6d0394b)

![s31](https://github.com/user-attachments/assets/3713d508-c6c0-41cc-ad28-0047e7d742f0)

![s32](https://github.com/user-attachments/assets/ab3c10a1-ec46-46df-8f75-316643630347)

![s33](https://github.com/user-attachments/assets/8d66415f-6839-465b-b03d-99a043ebd7fc)

#### Floorplan DEF Analysis

According to the floorplan DEF:

- 1000 Unit Distance: 1 Micron
- Die Width in Unit Distance: (660685 - 0 = 660685)
- Die Height in Unit Distance: (671405 - 0 = 671405)
- Distance in Microns: Value in Unit Distance / 1000
Calculated Die Dimensions in Microns:
- Die Width: (660685/1000 = 660.685) Microns
- Die Height: (671405/1000 = 671.405) Microns
- Area of Die in Square Microns: [ 660.685 * 671.405 = 443587.212425 Square Microns ]
- 
Load generated floorplan def in magic tool and explore the floorplan.

Commands to load floorplan def in magic in another terminal
```
# Change directory to path containing generated floorplan def
cd Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/12-11_17-31/results/floorplan/

# Command to load the floorplan def in magic tool
magic -T /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.floorplan.def &

```
![s34](https://github.com/user-attachments/assets/c388554d-5065-4c66-b5cb-ce5151dd10cb)

![s35](https://github.com/user-attachments/assets/6be78aea-47ce-4e40-8665-3c158773eb4d)
![s36](https://github.com/user-attachments/assets/419380ea-1791-4f2d-b843-0ef8e02a757a)
![s37](https://github.com/user-attachments/assets/bca261bd-5893-49c6-8ea6-d52efc11bbf5)
![s38](https://github.com/user-attachments/assets/4dabe00c-6554-42a9-bc91-01b35edfba88)

4. Run 'picorv32a' design congestion aware placement using OpenLANE flow and generate necessary outputs. Command to run placement
```
# Congestion aware placement by default
run_placement
```

![s39](https://github.com/user-attachments/assets/d413867d-3d05-4124-9526-d13e1ae73ae9)

5. Load generated placement def in magic tool and explore the placement. Commands to load placement def in magic in another terminal
```
# Change directory to path containing generated placement def
cd Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/12-11_17-31/results/placement/

# Command to load the placement def in magic tool
magic -T /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.placement.def &
```

![s40](https://github.com/user-attachments/assets/b5aefd08-aa28-4c87-b6b3-620a5c9e8576)
![s41](https://github.com/user-attachments/assets/42b2d59d-9f0a-423f-a0ae-d307cf243c9b)
![s42](https://github.com/user-attachments/assets/0cb590c1-3044-4e0b-9a91-12b00c14083a)

![s43](https://github.com/user-attachments/assets/f8f41c32-9fad-40c8-8f01-53cc516fe247)

</details>
<details>
  <summary> day 3 </summary>
	
### Design Library Cell Using Magic Layout and Cell characterization:

Tasks:

1.Clone custom inverter standard cell design from github repository: Standard cell design and characterization using OpenLANE flow. 2.Load the custom inverter layout in magic and explore. 3.Spice extraction of inverter in magic. 4.Editing the spice model file for analysis through simulation. 5.Post-layout ngspice simulations. 6.Find problem in the DRC section of the old magic tech file for the skywater process and fix them.

##### 1. Clone custom inverter standard cell design from github repository
```
# Change directory to openlane
cd Desktop/work/tools/openlane_working_dir/openlane

# Clone the repository with custom inverter design
git clone https://github.com/nickson-jose/vsdstdcelldesign

# Change into repository directory
cd vsdstdcelldesign

# Copy magic tech file to the repo directory for easy access
cp /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech .

# Check contents whether everything is present
ls

# Command to open custom inverter layout in magic
magic -T sky130A.tech sky130_inv.mag &
```

![d1](https://github.com/user-attachments/assets/e8eef71f-8248-442c-b1b7-5e0d2b224be9)

2.Load the custom inverter layout in magic and explore.

- Screenshot of custom inverter layout in magic

![d2](https://github.com/user-attachments/assets/a471acbb-a336-4952-9085-89896bb96785)



- NMOS and PMOS identified
pmos:
![d3](https://github.com/user-attachments/assets/7b840bbb-a4b0-4df5-ba2b-90933731968f)

nmos :
![d4](https://github.com/user-attachments/assets/5ec17532-57be-4938-9a4d-9ad11f781139)



- Output Y connectivity to PMOS and NMOS drain verified

![d7](https://github.com/user-attachments/assets/a09f9275-6442-407e-acd0-fd8fd7395872)


- NMOS source connectivity to VSS (here VGND) verified
![d6](https://github.com/user-attachments/assets/8911348d-3074-44a0-8883-6daf76e37c04)

- PMOS source connectivity to VPWR (here VPWR) verified
![d5](https://github.com/user-attachments/assets/481091cc-d48b-460e-bad1-16d8349cb9d2)

  
- Deleting necessary layout part to see DRC error
![d8](https://github.com/user-attachments/assets/54f67257-b1a1-467e-be49-37e7913ec1ab)

  ![d9](https://github.com/user-attachments/assets/0ce7db39-83e2-4e1c-aa96-ed66b898a0e9)


3.Spice extraction of inverter in magic.

Commands for spice extraction of the custom inverter layout to be used in tkcon window of magic
```
# Check current directory
pwd

# Extraction command to extract to .ext format
extract all

# Before converting ext to spice this command enable the parasitic extraction also
ext2spice cthresh 0 rthresh 0

# Converting to ext to spice
ext2spice
```

Screenshot of tkcon window after running above commands

![a8](https://github.com/user-attachments/assets/c6ad02ee-d1a4-4650-af52-923989198ea0)


![a9](https://github.com/user-attachments/assets/b95908a4-a3a9-416e-9076-5f775b66ebfb)

![a10](https://github.com/user-attachments/assets/a7794c64-ae51-4ce6-9570-45238a453316)


4. Editing the spice model file for analysis through simulation.

Measuring unit distance in layout grid

![a11](https://github.com/user-attachments/assets/6e95f79e-3fa6-4cc3-af76-69f82237335d)


Final edited spice file ready for ngspice simulation

![a12](https://github.com/user-attachments/assets/68a808b4-853b-44a2-bd94-8cc43808f9b9)


5.Post-layout ngspice simulations.

Commands for ngspice simulation
```
# Command to directly load spice file for simulation to ngspice
ngspice sky130_inv.spice

# Now that we have entered ngspice with the simulation spice file loaded we just have to load the plot
plot y vs time a

```
Screenshots of ngspice run

![a13](https://github.com/user-attachments/assets/c510d4f0-8b3b-4d39-9f01-ff301b471ae5)


![a14](https://github.com/user-attachments/assets/4aa103b0-9745-44aa-b703-7dac0a3305f5)


Rise transition time calculation Rise Transition Time = Time taken for output to rise to 80% − Time taken for output to rise to 20% 20% of output (3.3V) = 0.66V 20% of output (3.3V) = 2.64V

20% Screenshots


![a16](https://github.com/user-attachments/assets/7dc8fcdc-ddae-4e9e-a2cb-6bceddb946c5)

80% Screenshots


![a17](https://github.com/user-attachments/assets/af2c90b9-9077-4866-9027-c15f599df4f8)

```
Rise Transition Time = 2.2394 - 2.1803 = 0.05639 ns = 56.39 ps
```
Fall Transition Time = Time taken for output to fall to 80% − Time taken for output to fall to 20% 20% of output (3.3V) = 0.66V 20% of output (3.3V) = 2.64V

20% Screenshots


![a18](https://github.com/user-attachments/assets/441b8d06-6f20-4703-bfe2-5eb7146b6c2a)
80% Screenshots

![a19](https://github.com/user-attachments/assets/30ffbc36-a655-434e-bd7c-352f78c112be)
```
Fall Transition Time = 4.09266 - 4.05061 = 0.04205 ns = 42.05 ps
```


Rise Cell Delay Calculation Rise cell delay = Time taken by output to rise to 50% − Time taken by input to fall to 50% 50 % of 3.3V = 1.65V

50% Screenshots


![a20](https://github.com/user-attachments/assets/fe74ea8a-5e40-493a-a66b-38392a837186)

```
Rise cell delay = 2.20667 - 2.15061 = 0.05599 ns = 55.99 ps
```
Fall Cell Delay Calculation Fall cell delay = Time taken by output to fall to 50% − Time taken by input to rise to 50% 50 % of 3.3V = 1.65V

50% Screenshots


![a21](https://github.com/user-attachments/assets/a8a0f886-9e23-4fcc-a8f2-e94b73ad112c)


![a22](https://github.com/user-attachments/assets/704aa7c2-7978-434f-abe7-576b0890c4a8)

```
Fall cell delay = 4.07494 - 4.04966 = 0.02528 ns = 25.28 ps

```

6. Find problem in the DRC section of the old magic tech file for the skywater process and fix them.

Link to Sky130 Periphery rules: https://skywater-pdk.readthedocs.io/en/main/rules/periphery.html

Commands to download and view the corrupted skywater process magic tech file and associated files to perform drc corrections
```
# Change to home directory
cd

# Command to download the lab files
wget http://opencircuitdesign.com/open_pdks/archive/drc_tests.tgz

# Since lab file is compressed command to extract it
tar xfz drc_tests.tgz

# Change directory into the lab folder
cd drc_tests

# List all files and directories present in the current directory
ls -al

# Command to view .magicrc file
gvim .magicrc

# Command to open magic tool in better graphics
magic -d XR &

```

Screenshots of commands run


![a23](https://github.com/user-attachments/assets/ad473ff8-0303-43c3-ad7c-a753deea4042)

Screenshot of .magicrc file

![a24](https://github.com/user-attachments/assets/a513487b-c774-4b4f-b5a1-bdf3266d6a19)

Incorrectly implemented poly.9 simple rule correction

Screenshot of poly rule


![a25](https://github.com/user-attachments/assets/115af544-0632-48f3-b3cb-47c2789039ac)


Incorrectly implemented poly.9 rule no drc violation even though spacing < 0.48u


![a26](https://github.com/user-attachments/assets/bf67b847-cc19-40e0-8897-1e3dff47d2d3)


![a27](https://github.com/user-attachments/assets/b214c4b0-3e6c-425f-801f-ef0164eb5737)


![a28](https://github.com/user-attachments/assets/ef69d850-8965-49b8-ae96-8558d5cce8e1)

![image](https://github.com/user-attachments/assets/0b54c188-12cd-4065-b993-8954dc88a846)



New commands inserted in sky130A.tech file to update drc

![a29](https://github.com/user-attachments/assets/487a1092-33ca-4918-8379-9128882d3e42)

![a30](https://github.com/user-attachments/assets/efd0ea35-f0d0-4cd2-8247-8c4aaf62b25b)

![a33](https://github.com/user-attachments/assets/ef37a674-a85a-4e9b-b528-8c462e17edf6)


Commands to run in tkcon window
```
# Loading updated tech file
tech load sky130A.tech

# Must re-run drc check to see updated drc errors
drc check

# Selecting region displaying the new errors and getting the error messages 
drc why
Screenshot of magic window with rule implemented
```

![a31](https://github.com/user-attachments/assets/9d021b96-b539-4ef2-9262-0e8d66855d9d)


![a32](https://github.com/user-attachments/assets/668db95d-82a4-44a3-9038-99e9af7c436d)

![image](https://github.com/user-attachments/assets/ad47ea71-d607-433f-9530-4732beddb8d3)








</details>
<details>
  <summary> day 4 </summary>
  
##### Section 4 - Pre-layout timing analysis and importance of good clock tree 

Theory
Implementation
Section 4 tasks:-
- Fix up small DRC errors and verify the design is ready to be inserted into our flow.
- Save the finalized layout with custom name and open it.
- Generate lef from the layout.
- Copy the newly generated lef and associated required lib files to 'picorv32a' design 'src' directory.
- Edit 'config.tcl' to change lib file and add the new extra lef into the openlane flow.
- Run openlane flow synthesis with newly inserted custom inverter cell.
- Remove/reduce the newly introduced violations with the introduction of custom inverter cell by modifying design parameters.
- Once synthesis has accepted our custom inverter we can now run floorplan and placement and verify the cell is accepted in PnR flow.
- Do Post-Synthesis timing analysis with OpenSTA tool.
- Make timing ECO fixes to remove all violations.
- Replace the old netlist with the new netlist generated after timing ECO fix and implement the floorplan, placement and cts.
- Post-CTS OpenROAD timing analysis.
- Explore post-CTS OpenROAD timing analysis by removing 'sky130_fd_sc_hd__clkbuf_1' cell from - -- clock buffer list variable 'CTS_CLK_BUFFER_LIST'.
	
![s1](https://github.com/user-attachments/assets/28663ae5-7e4b-4a58-854a-212e0951a35a)

Commands for tkcon window to set grid as tracks of locali layer
```
# Get syntax for grid command
help grid

# Set grid values accordingly
grid 0.46um 0.34um 0.23um 0.17um

```
Screenshot of commands run
![s1](https://github.com/user-attachments/assets/2d702b33-ec76-4456-9c29-c45d7b278725)


Condition 1 verified

![s2](https://github.com/user-attachments/assets/a4eaad1b-d7ee-4405-84f1-ea1f6937cf41)


Condition 2 verified

HORIZONTAL TRACK PITCH = 0.46um
    
![s3](https://github.com/user-attachments/assets/e7c22ff5-24a6-4edf-95ba-d6e5d21ff82c)


WIDTH OF STANDARD CELL = 1.38um =3*0.46



Condition 3 verified
 VERTICAL PITCH = 0.34um

 ![s4](https://github.com/user-attachments/assets/eda2a1a9-e638-448c-90b8-f25237786ca2)


HEIGHT OF STANDARD CELL = 2.72um = 0.34*8

2. Save the finalized layout with custom name and open it.
Command for tkcon window to save the layout with custom name
```
# Command to save as
save sky130_utkinv.mag
Command to open the newly saved layout

# Command to open custom inverter layout in magic
magic -T sky130A.tech sky130_utkinv.mag &
```
Screenshot of newly saved layout

![s6](https://github.com/user-attachments/assets/933986f5-c6c3-490e-9d48-6c9e055f8e6d)


![s7](https://github.com/user-attachments/assets/b5cb91fa-5983-4146-bbdd-af4af225773c)

3. Generate lef from the layout.
Command for tkcon window to write lef
```
# lef command
lef write
```
Screenshot of command run

![s9](https://github.com/user-attachments/assets/c98c22eb-8d62-46ec-8628-f646fd2fa4e4)


Screenshot of newly created lef file

![s8](https://github.com/user-attachments/assets/4eb90304-b7a8-47a3-a61b-1b93123afd32)

4. Copy the newly generated lef and associated required lib files to 'picorv32a' design 'src' directory.
Commands to copy necessary files to 'picorv32a' design 'src' directory
```
# Copy lef file
cp sky130_vsdinv.lef ~/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/src/

# List and check whether it's copied
ls ~/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/src/

# Copy lib files
cp libs/sky130_fd_sc_hd__* ~/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/src/

# List and check whether it's copied
ls ~/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/src/

```

Screenshot of commands run

![s10](https://github.com/user-attachments/assets/141b4be9-51f9-4136-b2a0-037998988713)

5. Edit 'config.tcl' to change lib file and add the new extra lef into the openlane flow.
Commands to be added to config.tcl to include our custom cell in the openlane flow
```
set ::env(LIB_SYNTH) "$::env(OPENLANE_ROOT)/designs/picorv32a/src/sky130_fd_sc_hd__typical.lib"
set ::env(LIB_FASTEST) "$::env(OPENLANE_ROOT)/designs/picorv32a/src/sky130_fd_sc_hd__fast.lib"
set ::env(LIB_SLOWEST) "$::env(OPENLANE_ROOT)/designs/picorv32a/src/sky130_fd_sc_hd__slow.lib"
set ::env(LIB_TYPICAL) "$::env(OPENLANE_ROOT)/designs/picorv32a/src/sky130_fd_sc_hd__typical.lib"

set ::env(EXTRA_LEFS) [glob $::env(OPENLANE_ROOT)/designs/$::env(DESIGN_NAME)/src/*.lef]
```

Edited config.tcl to include the added lef and change library to ones we added in src directory

![s11](https://github.com/user-attachments/assets/42bf9f32-74cb-4fc2-b60d-bc26b174d8f4)


6. Run openlane flow synthesis with newly inserted custom inverter cell.
   
Commands to invoke the OpenLANE flow include new lef and perform synthesis
```
# Change directory to openlane flow directory
cd Desktop/work/tools/openlane_working_dir/openlane

# alias docker='docker run -it -v $(pwd):/openLANE_flow -v $PDK_ROOT:$PDK_ROOT -e PDK_ROOT=$PDK_ROOT -u $(id -u $USER):$(id -g $USER) efabless/openlane:v0.21'
# Since we have aliased the long command to 'docker' we can invoke the OpenLANE flow docker sub-system by just running this command
docker
# Now that we have entered the OpenLANE flow contained docker sub-system we can invoke the OpenLANE flow in the Interactive mode using the following command
./flow.tcl -interactive

# Now that OpenLANE flow is open we have to input the required packages for proper functionality of the OpenLANE flow
package require openlane 0.9

# Now the OpenLANE flow is ready to run any design and initially we have to prep the design creating some necessary files and directories for running a specific design which in our case is 'picorv32a'
prep -design picorv32a

# Adiitional commands to include newly added lef to openlane flow
set lefs [glob $::env(DESIGN_DIR)/src/*.lef]
add_lefs -src $lefs

# Now that the design is prepped and ready, we can run synthesis using following command
run_synthesis
```
Screenshots of commands run

![s12](https://github.com/user-attachments/assets/6fe854e6-2f3e-4a3a-93ec-749589e950f6)
![s13](https://github.com/user-attachments/assets/63f690a9-462e-4276-8375-635aec68cbcb)
![s14](https://github.com/user-attachments/assets/bb035b87-1654-4d2e-a0bb-97633dacecc8)
![s15](https://github.com/user-attachments/assets/bffa4c5c-42ac-46b6-9108-282201ae5420)
![s16](https://github.com/user-attachments/assets/a0fa4ab0-2d60-4598-80c0-4a15898179e4)

Commands to view and change parameters to improve timing and run synthesis
```
# Now once again we have to prep design so as to update variables
prep -design picorv32a -tag 13-11_15-18 -overwrite

# Addiitional commands to include newly added lef to openlane flow merged.lef
set lefs [glob $::env(DESIGN_DIR)/src/*.lef]
add_lefs -src $lefs

# Command to display current value of variable SYNTH_STRATEGY
echo $::env(SYNTH_STRATEGY)

# Command to set new value for SYNTH_STRATEGY
set ::env(SYNTH_STRATEGY) "DELAY 3"

# Command to display current value of variable SYNTH_BUFFERING to check whether it's enabled
echo $::env(SYNTH_BUFFERING)

# Command to display current value of variable SYNTH_SIZING
echo $::env(SYNTH_SIZING)

# Command to set new value for SYNTH_SIZING
set ::env(SYNTH_SIZING) 1

# Command to display current value of variable SYNTH_DRIVING_CELL to check whether it's the proper cell or not
echo $::env(SYNTH_DRIVING_CELL)

# Now that the design is prepped and ready, we can run synthesis using following command
run_synthesis

```
Screenshot of merged.lef in tmp directory with our custom inverter as macro

![s17](https://github.com/user-attachments/assets/0f02501f-0402-4c5f-82da-c9a0b32c8b27)
![s18](https://github.com/user-attachments/assets/55bce239-dde8-43e9-a9a1-3a0998a693f6)

Screenshots of commands run

![s19](https://github.com/user-attachments/assets/bc8e9ecf-4af6-4353-a52d-0334c641f75e)
![s20](https://github.com/user-attachments/assets/641041d4-f02d-4778-82b5-1f04b533dd20)
![s21](https://github.com/user-attachments/assets/27db5f81-b540-4472-850a-47c03e4ef0e1)
![s22](https://github.com/user-attachments/assets/9ca10d8e-e2b0-4abe-9497-9486776153b8)

8. Once synthesis has accepted our custom inverter we can now run floorplan and placement and verify the cell is accepted in PnR flow.
Now that our custom inverter is properly accepted in synthesis we can now run floorplan using following command
```
# Now we can run floorplan
run_floorplan
```
Screenshots of command run

![s23](https://github.com/user-attachments/assets/e6e8a76d-17ec-4ec6-b950-9d0cab9805c9)

![s24](https://github.com/user-attachments/assets/6f4cbe58-4635-4648-a51c-d418943a8967)

Since we are facing unexpected un-explainable error while using run_floorplan command, we can instead use the following set of commands available based on information from Desktop/work/tools/openlane_working_dir/openlane/scripts/tcl_commands/floorplan.tcl and also based on Floorplan Commands section in Desktop/work/tools/openlane_working_dir/openlane/docs/source/OpenLANE_commands.md
```
# Follwing commands are alltogather sourced in "run_floorplan" command
init_floorplan
place_io
tap_decap_or
```
Screenshots of commands run

![s25](https://github.com/user-attachments/assets/17ed4a33-8a46-44f6-ac6a-2a3c4ec475ff)

![s26](https://github.com/user-attachments/assets/565851fe-cdd7-45ff-ac46-2c79334bb65b)
![s27](https://github.com/user-attachments/assets/6cbe7b41-3276-4b76-a1d2-daad71b8fbe3)

Commands to load placement def in magic in another terminal

```
# Change directory to path containing generated placement def
cd Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/24-03_10-03/results/placement/

# Command to load the placement def in magic tool
magic -T /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.placement.def &
```
Screenshot of placement def in magic
![s28](https://github.com/user-attachments/assets/efa450c1-0a69-4dab-994d-5953f8979114)
![s29](https://github.com/user-attachments/assets/255652b1-7e35-4b05-9619-0142b72d84d5)
![s30](https://github.com/user-attachments/assets/22cd9e9a-5967-4f0e-980d-0e4317820236)

9. Do Post-Synthesis timing analysis with OpenSTA tool.
    
Since we are having 0 wns after improved timing run we are going to do timing analysis on initial run of synthesis which has lots of violations and no parameters were added to improve timing

Commands to invoke the OpenLANE flow include new lef and perform synthesis
```
# Change directory to openlane flow directory
cd Desktop/work/tools/openlane_working_dir/openlane

# alias docker='docker run -it -v $(pwd):/openLANE_flow -v $PDK_ROOT:$PDK_ROOT -e PDK_ROOT=$PDK_ROOT -u $(id -u $USER):$(id -g $USER) efabless/openlane:v0.21'
# Since we have aliased the long command to 'docker' we can invoke the OpenLANE flow docker sub-system by just running this command
docker
# Now that we have entered the OpenLANE flow contained docker sub-system we can invoke the OpenLANE flow in the Interactive mode using the following command
./flow.tcl -interactive

# Now that OpenLANE flow is open we have to input the required packages for proper functionality of the OpenLANE flow
package require openlane 0.9

# Now the OpenLANE flow is ready to run any design and initially we have to prep the design creating some necessary files and directories for running a specific design which in our case is 'picorv32a'
prep -design picorv32a

# Adiitional commands to include newly added lef to openlane flow
set lefs [glob $::env(DESIGN_DIR)/src/*.lef]
add_lefs -src $lefs

# Command to set new value for SYNTH_SIZING
set ::env(SYNTH_SIZING) 1

# Now that the design is prepped and ready, we can run synthesis using following command
run_synthesis
```

Commands run final screenshot
![s31](https://github.com/user-attachments/assets/474baea2-9e1c-4eac-99b8-f5f4aaddd55d)
![s32](https://github.com/user-attachments/assets/761dc8b3-f0bc-4923-9c97-9c7a05d32589)

![s33](https://github.com/user-attachments/assets/a05ccb8d-8e6a-459f-b3b8-309c6f39b4eb)

![s34](https://github.com/user-attachments/assets/d40f2b72-dda6-4b75-80f5-d3a03b2e8066)

Newly created pre_sta.conf for STA analysis in openlane directory

![s36](https://github.com/user-attachments/assets/6266a580-f611-4e9f-947e-521639035581)

Newly created my_base.sdc for STA analysis in openlane/designs/picorv32a/src directory based on the file openlane/scripts/base.sdc

![s35](https://github.com/user-attachments/assets/9bc6a306-0e48-4407-860f-8bdc125320c2)

Commands to run STA in another terminal
```
# Change directory to openlane
cd Desktop/work/tools/openlane_working_dir/openlane

# Command to invoke OpenSTA tool with script
sta pre_sta.conf

```
Screenshots of commands run
![s37](https://github.com/user-attachments/assets/1af4d9c4-5a68-4795-aff4-e847542d07d2)

![s38](https://github.com/user-attachments/assets/94d46ce2-c486-40b7-b20c-c4484522beb8)

![s39](https://github.com/user-attachments/assets/6235d0ed-bdd7-45b8-bdcc-a99168fb8eea)


Since more fanout is causing more delay we can add parameter to reduce fanout and do synthesis again

Commands to include new lef and perform synthesis

# Now the OpenLANE flow is ready to run any design and initially we have to prep the design creating some necessary files and directories for running a specific design which in our case is 'picorv32a'
prep -design picorv32a -tag 13-11_17-18 -overwrite

# Adiitional commands to include newly added lef to openlane flow
set lefs [glob $::env(DESIGN_DIR)/src/*.lef]
add_lefs -src $lefs

# Command to set new value for SYNTH_SIZING
set ::env(SYNTH_SIZING) 1

# Command to set new value for SYNTH_MAX_FANOUT
set ::env(SYNTH_MAX_FANOUT) 4

# Command to display current value of variable SYNTH_DRIVING_CELL to check whether it's the proper cell or not
echo $::env(SYNTH_DRIVING_CELL)

# Now that the design is prepped and ready, we can run synthesis using following command
run_synthesis
Commands run final screenshot

![s40](https://github.com/user-attachments/assets/47bbee33-e8e9-43a1-903c-8ff942ba85b8)


![s41](https://github.com/user-attachments/assets/71cc93e1-6134-4b4e-b11f-725a964e5511)
![s42](https://github.com/user-attachments/assets/1230020c-4e02-4b51-becd-86ed8b4b70a6)



Commands to run STA in another terminal
```
# Change directory to openlane
cd Desktop/work/tools/openlane_working_dir/openlane

# Command to invoke OpenSTA tool with script
sta pre_sta.conf
```
Screenshots of commands run
![s43](https://github.com/user-attachments/assets/f1f68a12-81ce-4fb5-9e9e-63bb65c1df8f)



![s45](https://github.com/user-attachments/assets/3d075d6b-9a64-46c8-b53a-ab007c558364)

10. Make timing ECO fixes to remove all violations.
OR gate of drive strength 2 is driving 4 fanouts

![s44](https://github.com/user-attachments/assets/ae69b54e-106c-44a2-a49b-5848caebe577)

Commands to perform analysis and optimize timing by replacing with OR gate of drive strength 4
```
# Reports all the connections to a net
report_net -connections _11672_

# Checking command syntax
help replace_cell

# Replacing cell
replace_cell _14510_ sky130_fd_sc_hd__or3_4

# Generating custom timing report
report_checks -fields {net cap slew input_pins} -digits 4
Result - slack reduced
```
![s46](https://github.com/user-attachments/assets/e0151ad0-a03f-46b3-aebd-2e3e5cc7ecbc)

![s47](https://github.com/user-attachments/assets/0a50c03f-f66a-4238-a5ea-2f1faae0e38b)

![s48](https://github.com/user-attachments/assets/1e9f612b-3af0-48fa-bdd1-e41912660b96)


OR gate of drive strength 2 is driving 4 fanouts
![s49](https://github.com/user-attachments/assets/07d4c018-5a97-4454-ab0d-071ceafb7be6)

Commands to perform analysis and optimize timing by replacing with OR gate of drive strength 4
```
# Reports all the connections to a net
report_net -connections _11675_

# Replacing cell
replace_cell _14514_ sky130_fd_sc_hd__or3_4

# Generating custom timing report
report_checks -fields {net cap slew input_pins} -digits 4
Result - slack reduced
```

![s50](https://github.com/user-attachments/assets/dd8712d9-099f-4926-92f2-396c0113ce5f)

![s51](https://github.com/user-attachments/assets/a601d0ea-89f7-47be-97bd-8a91b2f604ee)

![s52](https://github.com/user-attachments/assets/48c02440-3fc8-4b38-9c9b-22f5f7e76395)

OR gate of drive strength 2 driving OA gate has more delay

![s53](https://github.com/user-attachments/assets/8bbe285a-b5ca-481e-8e3f-4616f1dfa91e)

Commands to perform analysis and optimize timing by replacing with OR gate of drive strength 4
```
# Reports all the connections to a net
report_net -connections _11643_

# Replacing cell
replace_cell _14481_ sky130_fd_sc_hd__or4_4

# Generating custom timing report
report_checks -fields {net cap slew input_pins} -digits 4
Result - slack reduced
```
![s54](https://github.com/user-attachments/assets/150bd928-6496-4477-ae44-3ec6658762d9)

![s55](https://github.com/user-attachments/assets/65349741-b431-44b8-9921-38edc2566f62)


OR gate of drive strength 2 driving OA gate has more delay

![s56](https://github.com/user-attachments/assets/bdf6713e-c8e3-4d76-b8c5-1a3e05147d62)

Commands to perform analysis and optimize timing by replacing with OR gate of drive strength 4
```
# Reports all the connections to a net
report_net -connections _11668_

# Replacing cell
replace_cell _14506_ sky130_fd_sc_hd__or4_4

# Generating custom timing report
report_checks -fields {net cap slew input_pins} -digits 4
Result - slack reduced
````

![s57](https://github.com/user-attachments/assets/6eb553e7-9293-4f92-9707-19d3c85668c9)

![s58](https://github.com/user-attachments/assets/8824241e-9ad6-4706-87c0-bdda1cd56733)

Commands to verify instance _14506_ is replaced with sky130_fd_sc_hd__or4_4
```
# Generating custom timing report
report_checks -from _29043_ -to _30440_ -through _14506_

```
Screenshot of replaced instance

![s59](https://github.com/user-attachments/assets/1e8f1acd-843b-46af-8a9e-55587473f325)

We started ECO fixes at wns -23.9000 and now we stand at wns -22.6173 we reduced around 1.2827 ns of violation

11. Replace the old netlist with the new netlist generated after timing ECO fix and implement the floorplan, placement and cts.
Now to insert this updated netlist to PnR flow and we can use write_verilog and overwrite the synthesis netlist but before that we are going to make a copy of the old old netlist

Commands to make copy of netlist
```
# Change from home directory to synthesis results directory
cd Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/25-03_18-52/results/synthesis/

# List contents of the directory
ls

# Copy and rename the netlist
cp picorv32a.synthesis.v picorv32a.synthesis_old.v

# List contents of the directory
ls
```
Screenshot of commands run

![s60](https://github.com/user-attachments/assets/225e06a0-affc-4f3d-ae71-05cc0af183f6)

Commands to write verilog
```
# Check syntax
help write_verilog

# Overwriting current synthesis netlist
write_verilog /home/vsduser/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/25-03_18-52/results/synthesis/picorv32a.synthesis.v

# Exit from OpenSTA since timing analysis is done
exit
```
Screenshot of commands run


![s61](https://github.com/user-attachments/assets/b8815a54-a7be-4afd-a9a2-b96b9c72047e)


Verified that the netlist is overwritten by checking that instance _14506_ is replaced with ```sky130_fd_sc_hd__or4_4			```

![s62](https://github.com/user-attachments/assets/380a0b63-e6cc-49c3-99c8-36ce09c1fb83)

Since we confirmed that netlist is replaced and will be loaded in PnR but since we want to follow up on the earlier 0 violation design we are continuing with the clean design to further stages

Commands load the design and run necessary stages
```
# Now once again we have to prep design so as to update variables
prep -design picorv32a -tag 24-03_10-03 -overwrite

# Addiitional commands to include newly added lef to openlane flow merged.lef
set lefs [glob $::env(DESIGN_DIR)/src/*.lef]
add_lefs -src $lefs

# Command to set new value for SYNTH_STRATEGY
set ::env(SYNTH_STRATEGY) "DELAY 3"

# Command to set new value for SYNTH_SIZING
set ::env(SYNTH_SIZING) 1

# Now that the design is prepped and ready, we can run synthesis using following command
run_synthesis

# Follwing commands are alltogather sourced in "run_floorplan" command
init_floorplan
place_io
tap_decap_or

# Now we are ready to run placement
run_placement

# Incase getting error
unset ::env(LIB_CTS)

# With placement done we are now ready to run CTS
run_cts
```
Screenshots of commands run
![s63](https://github.com/user-attachments/assets/f166d1a6-bea1-4124-b0f8-26ac70ab63b2)
![s64](https://github.com/user-attachments/assets/a21d0fff-1757-4dd7-a547-d002ccfb8f33)
![s65](https://github.com/user-attachments/assets/0a6fc2f8-8969-404a-af91-a3fb1971732f)
![s66](https://github.com/user-attachments/assets/becc04ff-989e-4062-a896-c7e2e8579b1c)
![s67](https://github.com/user-attachments/assets/32c2056e-9e1a-4d45-9d44-cd3b49d1d66e)
![s68](https://github.com/user-attachments/assets/7e0f56f8-b256-4370-ad37-125f24d84a10)
![s69](https://github.com/user-attachments/assets/6afdd220-2bd7-4677-8894-3f998952c39c)
![s70](https://github.com/user-attachments/assets/edfa96b3-5b23-40c8-97f7-16bc52f9430a)


12. Post-CTS OpenROAD timing analysis.
Commands to be run in OpenLANE flow to do OpenROAD timing analysis with integrated OpenSTA in

```
OpenROAD

# Command to run OpenROAD tool
openroad

# Reading lef file
read_lef /openLANE_flow/designs/picorv32a/runs/13-11_17-18/tmp/merged.lef

# Reading def file
read_def /openLANE_flow/designs/picorv32a/runs/13-11_17-18/results/cts/picorv32a.cts.def

# Creating an OpenROAD database to work with
write_db pico_cts.db

# Loading the created database in OpenROAD
read_db pico_cts.db

# Read netlist post CTS
read_verilog /openLANE_flow/designs/picorv32a/runs/13-11_17-18/results/synthesis/picorv32a.synthesis_cts.v

# Read library for design
read_liberty $::env(LIB_SYNTH_COMPLETE)

# Link design and library
link_design picorv32a

# Read in the custom sdc we created
read_sdc /openLANE_flow/designs/picorv32a/src/my_base.sdc

# Setting all cloks as propagated clocks
set_propagated_clock [all_clocks]

# Check syntax of 'report_checks' command
help report_checks

# Generating custom timing report
report_checks -path_delay min_max -fields {slew trans net cap input_pins} -format full_clock_expanded -digits 4

# Exit to OpenLANE flow
exit
```
Screenshots of commands run and timing report generated
![s71](https://github.com/user-attachments/assets/e46c2605-089a-45b9-800f-200c47853ac0)
![s72](https://github.com/user-attachments/assets/67ef0a33-b92c-46df-8f43-b53a5a70f79b)
![s73](https://github.com/user-attachments/assets/00077e5a-d343-45cb-9aae-01d51ab294cc)

13. Explore post-CTS OpenROAD timing analysis by removing 'sky130_fd_sc_hd__clkbuf_1' cell from clock buffer list variable 'CTS_CLK_BUFFER_LIST'.

Commands to be run in OpenLANE flow to do OpenROAD timing analysis after changing 

```
CTS_CLK_BUFFER_LIST

# Checking current value of 'CTS_CLK_BUFFER_LIST'
echo $::env(CTS_CLK_BUFFER_LIST)

# Removing 'sky130_fd_sc_hd__clkbuf_1' from the list
set ::env(CTS_CLK_BUFFER_LIST) [lreplace $::env(CTS_CLK_BUFFER_LIST) 0 0]

# Checking current value of 'CTS_CLK_BUFFER_LIST'
echo $::env(CTS_CLK_BUFFER_LIST)

# Checking current value of 'CURRENT_DEF'
echo $::env(CURRENT_DEF)

# Setting def as placement def
set ::env(CURRENT_DEF) /openLANE_flow/designs/picorv32a/runs/24-03_10-03/results/placement/picorv32a.placement.def

# Run CTS again
run_cts

# Checking current value of 'CTS_CLK_BUFFER_LIST'
echo $::env(CTS_CLK_BUFFER_LIST)

# Command to run OpenROAD tool
openroad

# Reading lef file
read_lef /openLANE_flow/designs/picorv32a/runs/13-11_17-18/tmp/merged.lef

# Reading def file
read_def /openLANE_flow/designs/picorv32a/runs/13-11_17-18/results/cts/picorv32a.cts.def

# Creating an OpenROAD database to work with
write_db pico_cts1.db

# Loading the created database in OpenROAD
read_db pico_cts.db

# Read netlist post CTS
read_verilog /openLANE_flow/designs/picorv32a/runs/13-11_17-18/results/synthesis/picorv32a.synthesis_cts.v

# Read library for design
read_liberty $::env(LIB_SYNTH_COMPLETE)

# Link design and library
link_design picorv32a

# Read in the custom sdc we created
read_sdc /openLANE_flow/designs/picorv32a/src/my_base.sdc

# Setting all cloks as propagated clocks
set_propagated_clock [all_clocks]

# Generating custom timing report
report_checks -path_delay min_max -fields {slew trans net cap input_pins} -format full_clock_expanded -digits 4

# Report hold skew
report_clock_skew -hold

# Report setup skew
report_clock_skew -setup

# Exit to OpenLANE flow
exit

# Checking current value of 'CTS_CLK_BUFFER_LIST'
echo $::env(CTS_CLK_BUFFER_LIST)

# Inserting 'sky130_fd_sc_hd__clkbuf_1' to first index of list
set ::env(CTS_CLK_BUFFER_LIST) [linsert $::env(CTS_CLK_BUFFER_LIST) 0 sky130_fd_sc_hd__clkbuf_1]

# Checking current value of 'CTS_CLK_BUFFER_LIST'
echo $::env(CTS_CLK_BUFFER_LIST)
```
Screenshots of commands run and timing report generated

![s74](https://github.com/user-attachments/assets/b8382bbb-d733-4b6d-a0ce-c1fed147531a)


![s75](https://github.com/user-attachments/assets/ba8fea30-dd38-4213-a537-6b31b9b2d978)

![s76](https://github.com/user-attachments/assets/81575cbe-41bb-4e44-951a-998524822608)

![s77](https://github.com/user-attachments/assets/9258d19b-ef5b-4133-b1ac-160360e56e53)






</details>

<details>
  <summary> day 5 </summary>

  ##### Final steps for RTL2GDS using tritonRoute and openSTA

  Theory
Implementation
Section 5 tasks:-
Perform generation of Power Distribution Network (PDN) and explore the PDN layout.
Perfrom detailed routing using TritonRoute.
Post-Route parasitic extraction using SPEF extractor.
Post-Route OpenSTA timing analysis with the extracted parasitics of the route.
All section 5 logs, reports and results can be found in following run folder:



1. Perform generation of Power Distribution Network (PDN) and explore the PDN layout.
Commands to perform all necessary stages up until now
```

# Change directory to openlane flow directory
cd Desktop/work/tools/openlane_working_dir/openlane

# alias docker='docker run -it -v $(pwd):/openLANE_flow -v $PDK_ROOT:$PDK_ROOT -e PDK_ROOT=$PDK_ROOT -u $(id -u $USER):$(id -g $USER) efabless/openlane:v0.21'
# Since we have aliased the long command to 'docker' we can invoke the OpenLANE flow docker sub-system by just running this command
docker
# Now that we have entered the OpenLANE flow contained docker sub-system we can invoke the OpenLANE flow in the Interactive mode using the following command
./flow.tcl -interactive

# Now that OpenLANE flow is open we have to input the required packages for proper functionality of the OpenLANE flow
package require openlane 0.9

# Now the OpenLANE flow is ready to run any design and initially we have to prep the design creating some necessary files and directories for running a specific design which in our case is 'picorv32a'
prep -design picorv32a

# Addiitional commands to include newly added lef to openlane flow merged.lef
set lefs [glob $::env(DESIGN_DIR)/src/*.lef]
add_lefs -src $lefs

# Command to set new value for SYNTH_STRATEGY
set ::env(SYNTH_STRATEGY) "DELAY 3"

# Command to set new value for SYNTH_SIZING
set ::env(SYNTH_SIZING) 1

# Now that the design is prepped and ready, we can run synthesis using following command
run_synthesis

# Following commands are alltogather sourced in "run_floorplan" command
init_floorplan
place_io
tap_decap_or

# Now we are ready to run placement
run_placement

# Incase getting error
unset ::env(LIB_CTS)

# With placement done we are now ready to run CTS
run_cts

# Now that CTS is done we can do power distribution network
gen_pdn

```
Screenshots of power distribution network run
![b1](https://github.com/user-attachments/assets/4729756c-b995-4a15-852b-7fe160f2b252)

![b2](https://github.com/user-attachments/assets/14dc9073-d921-4298-95d0-5b8aeb18b5e9)
![b3](https://github.com/user-attachments/assets/5d1c48ad-cc01-4e3f-af73-b1f62dbf940e)
![b4](https://github.com/user-attachments/assets/64179fc6-90d6-4877-99b7-5f694813748f)
![b5](https://github.com/user-attachments/assets/1cc5c47d-39f9-4998-b6ec-fc509aeae6c2)
![b6](https://github.com/user-attachments/assets/de3cf92b-b3f0-4ffc-8b2a-079819e6ae81)
![b7](https://github.com/user-attachments/assets/3f2dee4e-fe3b-4e93-a367-9e3f3e280c46)
![b8](https://github.com/user-attachments/assets/da3f98f0-2ae1-464a-a2b3-f576c7d73f08)
![b9](https://github.com/user-attachments/assets/737fc379-13b9-4cb9-94f1-2f83d7626785)
![b10](https://github.com/user-attachments/assets/eb833c97-c80b-41c0-8afa-b3cfb94f2054)
![b11](https://github.com/user-attachments/assets/4ad7d6c9-438c-41d3-8e96-e326d0ae85a2)



Commands to load PDN def in magic in another terminal
```
# Change directory to path containing generated PDN def
cd Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/13-11_20-08/tmp/floorplan/

# Command to load the PDN def in magic tool
magic -T /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read 14-pdn.def &
```

Screenshots of PDN def

![b12](https://github.com/user-attachments/assets/dbd0af34-8e0d-4761-9eea-fc850adcb302)
![b13](https://github.com/user-attachments/assets/b998c21a-4281-4d78-80d4-a8f5d13cf3a6)
![b14](https://github.com/user-attachments/assets/96528634-8487-4419-acb6-13c9eebe28d3)
![b15](https://github.com/user-attachments/assets/4e725e36-6495-4b80-bf15-be95de511bb3)
![b16](https://github.com/user-attachments/assets/0d93dd96-d4d9-4730-9f71-649187056c0f)

2. Perfrom detailed routing using TritonRoute and explore the routed layout.
Command to perform routing
```
# Check value of 'CURRENT_DEF'
echo $::env(CURRENT_DEF)

# Check value of 'ROUTING_STRATEGY'
echo $::env(ROUTING_STRATEGY)

# Command for detailed route using TritonRoute
run_routing

```

Screenshots of routing run

![b17](https://github.com/user-attachments/assets/3b38cd05-cc08-4ea1-aacf-cb8032edca06)
![b18](https://github.com/user-attachments/assets/b54e2f3f-823b-4852-8c09-0ad71498c8ae)

Commands to load routed def in magic in another terminal
```
# Change directory to path containing routed def
cd Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/13-11_20-08/results/routing/

# Command to load the routed def in magic tool
magic -T /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.def &
```

Screenshots of routed def

![b19](https://github.com/user-attachments/assets/2184fbad-ba58-46a6-b739-a8695576163f)

![b20](https://github.com/user-attachments/assets/ae976da4-88ab-44e5-a29c-ff7c83a75d49)
![b21](https://github.com/user-attachments/assets/e30706fd-733d-4475-959b-de7ea7197635)
![b22](https://github.com/user-attachments/assets/3852f1a4-405a-4985-a98c-ad63821a39cc)
![b23](https://github.com/user-attachments/assets/e53a19c2-cfb2-435c-ad2a-373042691b9d)
![b24](https://github.com/user-attachments/assets/8b35b30a-5d82-40f2-8fa7-9939b4d0ad92)

Screenshot of fast route guide present in openlane/designs/picorv32a/runs/13-11_20-08/tmp/routing directory



![b25](https://github.com/user-attachments/assets/0cb1cdc6-a3a6-42be-b05c-7cf757c4f77e)

3. Post-Route parasitic extraction using SPEF extractor.
Commands for SPEF extraction using external tool
```
# Change directory
cd Desktop/work/tools/SPEF_EXTRACTOR

# Command extract spef
python3 main.py /home/vsduser/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/13-11_20-08/tmp/merged.lef /home/vsduser/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/13-11_20-08/results/routing/picorv32a.def
4. Post-Route OpenSTA timing analysis with the extracted parasitics of the route.
Commands to be run in OpenLANE flow to do OpenROAD timing analysis with integrated OpenSTA in OpenROAD

# Command to run OpenROAD tool
openroad

# Reading lef file
read_lef /openLANE_flow/designs/picorv32a/runs/13-11_20-08/tmp/merged.lef

# Reading def file
read_def /openLANE_flow/designs/picorv32a/runs/13-11_20-08/results/routing/picorv32a.def

# Creating an OpenROAD database to work with
write_db pico_route.db

# Loading the created database in OpenROAD
read_db pico_route.db

# Read netlist post CTS
read_verilog /openLANE_flow/designs/picorv32a/runs/13-11_20-08/results/synthesis/picorv32a.synthesis_preroute.v

# Read library for design
read_liberty $::env(LIB_SYNTH_COMPLETE)

# Link design and library
link_design picorv32a

# Read in the custom sdc we created
read_sdc /openLANE_flow/designs/picorv32a/src/my_base.sdc

# Setting all cloks as propagated clocks
set_propagated_clock [all_clocks]

# Read SPEF
read_spef /openLANE_flow/designs/picorv32a/runs/13-11_20-08/results/routing/picorv32a.spef

# Generating custom timing report
report_checks -path_delay min_max -fields {slew trans net cap input_pins} -format full_clock_expanded -digits 4

# Exit to OpenLANE flow
exit
```

Screenshots of commands run and timing report generated
![b26](https://github.com/user-attachments/assets/40136464-a2ee-4173-bd46-5581eb9cc056)
![b27](https://github.com/user-attachments/assets/a020cd4a-6300-4841-9fff-f35ba8f696c2)
![b28](https://github.com/user-attachments/assets/7acc6949-c091-47e1-a914-f29d4fed8f72)
![b29](https://github.com/user-attachments/assets/65f7ea42-f573-49f1-9afe-5e2ae0873e53)



</details>
