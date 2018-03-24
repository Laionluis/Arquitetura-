Intruções de teste: carregar, no instruction memory do monociclo e pipeline e na memoria no multiciclo,
o arquivo teste_instrucoes_mono_mult, as instruções são as seguintes:

Para a instrução jump register:

	00e00008  => jr $7   
	01000008  => jr $8
	01200008  => jr $9

Para a instrução exclusive or:

	00222026  => xor $4,$1,$2
	00232826  => xor $5,$1,$3
	00433026  => xor $6,$2,$3

Para a instrução Load upper immediate:

	3c010001  => lui $1, 0x0001
	3c0200f0  => lui $2, 0x00f0
	3c03000f  => lui $3, 0x000f

#para teste do jump register colocar no registrador 7 (no bank registers) o valor hex 10,
no registrador 8 o valor 50 e no 9 deixar 0. No "programinha" de teste ele começa com uma
instrução jr que pula para o valor que ta no registrador, que no caso vai para um endereço
que contem a sequencia de 3 intruções de lui e mais uma intrução jr que vai para um endereço
que tem a sequencia de 3 intruções do xor e mais uma instrução jr que volta para o enreço 0.
O lui pega o imediato, extende para 32 bits e faz left 16 nele para ficar com os 16 bits baixos
com zeros. O xor fizemos com os registradores resultantes do lui.
Para testar com outros valores precisa modificar os registradores no bank register.

