# hackin-breakin-risc-v

This repository is a hacking playground for my RISC-V exploration. 

We will learn about the many elements in an assembly language program. Among these elements, we have directives, labels, mnemonics, operands, immediates, instructions, and pseudo instructions.
Major focus on:

    Describe the RISC-V assembly language syntax and features.
    Identify the many elements of a RISC-V assembly program, like directives, labels, mnemonics, and operands.
    Identify the pseudoinstructions in a RISC-V assembly program.
    Explain how Control and Status Registers are managed in the RISC-V assembly code.
    Use immediate values properly in a RISC-V assembly program.

## ARCHITECTURE

32 bit

64 bit

128 bit

## REGISTERS

33 registers including $pc, 32 general use

x0-x32 + pc

- 6 special purpose( stack pointer, frame pointer, program counter, etc)

- 7 temporary(t0-t6) (non-persistent)

- 12 saved(s0-s11) (non-volatile)

- 8 arguments(a0-a7) 

## RISC V instruction set

 Three register instruction structure
 
```
<operation> <dst>,<src1>,<src2>
```

- addi a2,x0,64

```
$a2= $zero +64

$a2= 64
```

- la a1, helloworld

```
a1= <address of helloworld label>
```
[https://riscv.org/wp-content/uploads/2017/05/riscv-spec-v2.2.pdf](https://riscv.org/wp-content/uploads/2017/05/riscv-spec-v2.2.pdf)

## RISC-V SYSCALL table

- Linux syscall defines how to interact with the kernel
      - specifies functions we can call, syscall numbers, arguments required, etc

Unix implementation syscall table: [https://github.com/westerndigitalcorporation/RISC-V-Linux/blob/13cb16d5e8e11ebca490cad50cc5abbd222839a1/linux/include/uapi/asm-generic/unistd.h](https://github.com/westerndigitalcorporation/RISC-V-Linux/blob/13cb16d5e8e11ebca490cad50cc5abbd222839a1/linux/include/uapi/asm-generic/unistd.h)


- `exit` syscall is 93, `write` syscall is 64

- to implement a syscall:
  
      - set a7 to the syscall number
  
      - set a0 to the arguments for that syscall
  
      - invoke the ecall instruction to call the kernel
  
- No risc chips ? use qemu riscv for testing













