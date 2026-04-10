data segment

Duml db Obh, 05h, 07h, Oah, 01h

result db 1 dup (0)

carry db Oh

data ends

ey to create

code segment

press Enter

start assume cs code,ds data

mov dx, data

mov ds,dx.

mov c1,05h

mov si.offset mum1

upimov al,lsil

add resulta Lianswer:a1:22h

jnc next

inc carry

next: inc.si

lopp up.

mov ax1c001

int, 21h

code ends

end start.
