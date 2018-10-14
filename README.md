计算2*2  结果放在ax中
程序代码 
assume cs:code
code segment
  mov ax,2
  add ax,ax
  mov ax,4c00h
  int 21h
code ends
end

编程计算 2^3 
程序代码
assume cs:code
  code segment
    mov ax,2
    add ax,ax
    add ax,ax
    mov ax,4c00h
    int 21h
    code ends
    end
编程计算 2^12
程序代码 可以用loop来简化 循环
assume cs:code
code segment
  mov ax,2
  mov cx,11
s:add ax,ax
  loop s
  mov ax,4c00h
  int 21h
  code ends
  end
编程计算 2^12
程序代码 可以用loop来简化 循环
assume cs:code
code segment

start:mov ax,2
  mov cx,11
s:  add ax,ax
    loop s
    mov ax,4c00h
    int 21h
code ends
end start


用加法计算 123*136的值  
assume cs:code
code segment
  mov ax,0
  mov cx,236
s:add ax,123
  loop s
  mov ax,4c00h
  int 21h
code ends
end
改进上一个程序的计算速度
assume cs:code
  code segment
    mov ax,0
    mov cx,123
  s:add ax,236
    loop s
    mov ax,4c00h
    int 21h
  code ends
end
考虑问题  计算ffff：0006单元中的数乘以3  结果存储在dx中  是否会超出dx所能存储的范围？要估算的值 是否超标
可以用累加法 实现乘法  赋值 就是让值相等  如何赋值 
当 ffff：0006单元和  和ax为不同时 可以赋值
例如
assume cs:code
code segment
  mov ax,0ffffh
  mov ds,ax
  mov bx,6
  mov al,[bx]
  mov ah,0
  mov dx,0
  mov cx,3
s:add dx,ax
  loop s
  mov ax,4c00h
  int 21h
code ends
end
 汇编的源程序 中不允许字符开头的地址
 


assume cs:code
code segment
  mov bx,0
  mov cx,12
s:mov ax,0ffffh
  mov ds,ax
  mov dl,[bx];
  mov ax,0020h
  mov da,ax
  mov [bx],dl
  inc bx
  loop s
  mov ax,4c00h
  int 21h
code ends
end


另外一种写法

assume cs:code
code segment
  mov ax,0ffffh
  mov ds,ax
  mov ax,0020h
  mov es,ax
  mov bx,0
  mov cx,12
s:mov dl,[bx]
  mov es:[bx],dl
  inc bx
  loop s
  mov ax,4c00h
  int 21h
code ends
end


在代码段中使用数据举例  dw   就是 字型数据的意思 difine word  d b   define byte


assume cs:code
code segment
  dw 0123H,0456H,0789H,0abcH,0fedH,0cbaH,0987H
  mov bx,0
  mov ax,0
  mov cx,8
s：add ax,cs:[bx]
  add bx,2
  loop s
  mov ax,4c00h
  int 21
code ends
end





assume cs:code
code segment
  dw 0123H,0456H,0789H,0abcH,0fedH,0cbaH,0987H
start mov bx,0
  mov ax,0
  mov cx,8
s：add ax,cs:[bx]
  add bx,2
  loop s
  mov ax,4c00h
  int 21
code ends
end


codesg segment
    dw 0123H,0456H,0789H
    
    
    

转换 字母大小写
  assume cs:codesg,ds:

