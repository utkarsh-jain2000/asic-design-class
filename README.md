Lab O1 Write the C code in a file in ubuntu terminal and save it as vsdlab1.c (source code) Next, compile the source code using gcc compiler, this will generate the executable code. Now, run the executable code to see the output.

Write an code leafpad vsdlab1.c
to create c file name vsdlab1

![lab 1_step 1](https://github.com/user-attachments/assets/a5484cf1-491f-4973-a143-0f3cdb78b1ef)

Now write an c code of an sum of number from 1 to n
![lab 1_step 2](https://github.com/user-attachments/assets/ae76c7b8-0ab7-418f-8284-3dd36a3b4515)

and Then compile it with gcc.filename.c
THEN RUN IT BY ./a.out

![lab 1 _step 3](https://github.com/user-attachments/assets/2cff22a0-ccc4-4f80-b8e0-567e4cae3cd2)



Lab 1B Compiling a C program with RISCV gcc compiler, execute it, generate the output Now, compile the vsdlab1.c using RISCV gcc compiler, also see the assembly code for C program.



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

now lets modify code with slight change let change o1 with fast in an above code and then run it 

![lab 2_6](https://github.com/user-attachments/assets/5b924a16-9a31-4aa2-af12-1c91d623aef6)

now to check (100E0 - 100b0)/4 we get C

![lab 2_7](https://github.com/user-attachments/assets/61979cb0-ca79-454c-ab3a-524e6527abe8)
