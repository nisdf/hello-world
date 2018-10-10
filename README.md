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

