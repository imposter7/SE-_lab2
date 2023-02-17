# SE-_lab2
Git basics
global add
section .text
add:
    cmp rdx, $0; if size of matrix is 0x0, return
    je finish;
    mov r9, rdi; have A* pointer in r9 (because we'll be modifying rdi)
    mov r8, rdx; store n in r8
    mov rax, rdx;
    imul r8;
    mov r8, rax
    mov rdx, rax; rdx and r8 hold n^2
loop:
    mov rax, [rdi]
    add rax, [rsi]
    mov [rdi], rax; store A[i] = A[i] + B[i]
    add rdi, $8;
    add rsi, $8; i++
    dec r8;
    cmp r8, 0;
    jg loop;
finish:
    mov rax, r9; return pointer to modified A matrix
    ret
