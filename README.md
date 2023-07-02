# desafio_basico_py

**menu = """
==========   MENU  ==========
    [d] - Depositar
    [s] - Sacar
    [e] - Extrato
    [q] - Sair
==============================
"""

saldo = 0
limite = 500
extrato = ""
numero_saques = 0
LIMITE_SAQUES = 3

while True:
    opcao  = input(menu)

    if opcao == "d":
        valor = float(input("Informe o depositado: "))

        if valor > 0:
            print(f"Deposito foi realizado com sucesso! R$ {valor:.2f}\n")
            saldo += valor
            extrato += f"Depósito realizado: {valor:.2f}\n"

        else:
            print("Operação falhou: O valor é inválido")
    
    elif opcao == "s":

        valor = float(input("Qual o valor de saque: "))

        excedeu_saldo = valor > limite
        excedeu_limite = valor > limite
        excedeu_saques = numero_saques >= LIMITE_SAQUES

        if excedeu_saldo:
            print("Operação falhou! Você não tem saldo.")

        elif excedeu_limite:
            print("Falha! O valor do saque excede o limite.")

        elif excedeu_saques:
            print("Falha! O numero maximo de saques atingido.")

        elif valor > 0:
            print(f"Saque feito com sucesso! R$ {valor:.2f}\n")
            saldo -= valor
            extrato += f"Saque realizado: {valor:.2f}\n"

        else:
            print("Falha: O valor informado é inválido.")

    elif opcao == "e":
        print("============================== EXTRATO ==============================")
        print("Não foram realizadas movimentações na conta." if not extrato else extrato)
        print(f"\nSaldo: R$ {saldo:.2f}")
        print("=====================================================================")

    elif opcao == "q":
        break
    
    else:
        print("Inválida, por favor selecione um comando válido.")**
