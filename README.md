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

- ##### Output shown as below:
![op](https://github.com/user-attachments/assets/b0d6a723-366c-4103-b19c-30619712e1f3)
![output](https://github.com/user-attachments/assets/709666dd-fa55-4d23-84a6-82a8445e404a)
![output2](https://github.com/user-attachments/assets/b9992a69-52c0-44aa-87f3-c908102a7ddd)


  </details>
