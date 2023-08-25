# Sistema_Bancario
menu = """[1]- Deposito
[2] - Saque 
[3] - Extrato
[4] - Sair 
"""
limite_diario = 3
saldo = 0
limite_saque = 500
extrato = ""
cont = 0
while True:
    menus = input(menu)

    if menus == "1":
        valor = float(input("Qual valor a ser depositado? "))
        saldo += valor
        extrato +=f"Depósito de R$ {valor:.2f}\n"

    if menus == "2":
        saque = float(input("Valor do saque? "))
        cont += 1
        if saldo < saque:
            print("Saldo insuficiente")
        if saque > limite_saque:
            print("Esse valor ultrapassa o limite diário")
        if limite_diario == cont:
            print("Você atingiu o limite de saque diário")
        if saque > 0 and saque < 500:
            saldo -= saque
            extrato+=f"Saque de R$ {saque:.2f}\n"

    if menus == "3":

        print("="*10)
        print("""Extrato""")
        print(extrato)
        print(f"Seu saldo é R${saldo}")
        print("="*10)
    if menus == "4":
        break
