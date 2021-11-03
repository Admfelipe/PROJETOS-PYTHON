# Gerador de QrCode usando  python

from time import sleep
import qrcode as qrcode

newpath = r'C:\QrGerados'
import os
if not os.path.exists(newpath):
    os.makedirs(newpath)

print('=='*25)
print("                 Bem vindo!")
print("        Gerador de QRCode Centrofarma")
print("=="*25)

while True:
    data = (input('Cole seu Link aqui: '))  # entrada de link
    nomedoarquivo = input('Nome do Arquivo: ')
    filename = (f'C:\QrGerados\{nomedoarquivo}.png')  # nomear o arquivo
    img = qrcode.make(data)  # gerar o qr code
    img.save(filename)  # salvar a imagem

    print("\nSeu QRcode Foi salvo na pasta C:\QrGerados")

    sair = input("\nDeseja gerar um novo QrCode? s/n: ")

    convert = sair.lower()

    if convert == ('n'):
        break
print("=="*25)
print("Obrigado por utilizar o Gerador de QrCode!!!")

sleep(1)
print("=="*25)

print("\n"+"**"*25+"\nEncerrando...")
print("**"*25)
sleep(3)

path = "C:\QrGerados"
path = os.path.realpath(path)
os.startfile(path)
