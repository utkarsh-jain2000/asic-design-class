# Task 1

## Lab O1 Write the C code in a file in ubuntu terminal and save it as vsdlab1.c 
(source code)Next, compile the source code using gcc compiler, this will generate the executable code. Now, run the executable code to see the output.

Write an code leafpad vsdlab1.c
to create c file name vsdlab1

![lab 1_step 1](https://github.com/user-attachments/assets/a5484cf1-491f-4973-a143-0f3cdb78b1ef)

Now write an c code of an sum of number from 1 to n
![lab 1_step 2](https://github.com/user-attachments/assets/ae76c7b8-0ab7-418f-8284-3dd36a3b4515)

and Then compile it with gcc.filename.c
THEN RUN IT BY ./a.out

![lab 1 _step 3](https://github.com/user-attachments/assets/2cff22a0-ccc4-4f80-b8e0-567e4cae3cd2)




# Task 2 



## Lab 1B. Compiling a C program with RISCV gcc compiler, execute it, generate the output Now, compile the vsdlab1.c using RISCV gcc compiler, also see the assembly code for C program.



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

### now lets modify code with slight change let change o1 with fast in an above code and then run it 

![lab 2_8](https://github.com/user-attachments/assets/e52ce094-b7e3-4340-ba69-33882cd75551)

![lab 2_6](https://github.com/user-attachments/assets/5b924a16-9a31-4aa2-af12-1c91d623aef6)

now to check (100E0 - 100b0)/4 we get C

![lab 2_7](https://github.com/user-attachments/assets/61979cb0-ca79-454c-ab3a-524e6527abe8)




# Task 3


## Labo3 To Execute of the output file of RISCv compiler in spike simulator

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

## Same thing for o1 as well

### until pc 0 10184

![lab3_11](https://github.com/user-attachments/assets/68a87b4f-3aff-465f-9e8a-162e09a0a257)

![lab3_12](https://github.com/user-attachments/assets/c230b11f-49e5-4e5c-a7f8-75dd0b3b32bd)





# Task 4

## To sort and organise a set of given instructions into their respective format type:

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

# RISC-V Instructions and Their Hexadecimal Representation

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


