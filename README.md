

# DESAFIO DIO.

Projeto realizado para desafiar e fixar os conhecimentos adquiridos no Bootcamp da Dio em parceria com a Vivo.
Durante o desafio, tivemos a chance de aplicar conhecimentos em programação Python e criar um sistema funcional que simule as operações bancárias.

## ⚠️ Projeto/Desafio ⚠️

Neste projeto, foi solicitado a criação de um Sistema Bancário em Python. O objetivo é implementar três operações essenciais: depósito, saque e extrato. O sistema será desenvolvido para um banco que busca monetizar suas operações. 

Linguagem utilizada:

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)

## Estrutura do Código:

menu = """

[d] Depositar
[s] Sacar
[e] Extrato
[q] Sair

=> """

saldo = 0
limite = 500
extrato = ""
numero_saques = 0
LIMITE_SAQUES = 3

while True:

    opcao = input(menu)

    if opcao == "d":
        valor = float(input("Informe o valor do depósito: "))

        if valor > 0:
            saldo += valor
            extrato += f"Depósito: R$ {valor:.2f}\n"

        else:
            print("Operação falhou! O valor informado é inválido.")

    elif opcao == "s":
        valor = float(input("Informe o valor do saque:"))
    
        excedeu_saldo = valor > saldo
    
        excedeu_limite = valor > limite
    
        excedeu_saques = numero_saques >= LIMITE_SAQUES
    
        if excedeu_saldo:
            print("Operação falhou, Você não tem saldo suficiente.")

        elif excedeu_limite:
            print("Operação falhou! O valor do saque excedeu o limite.")

        elif excedeu_saques:
            print("Operação falhou! Número máximo de saques excedido.")

        elif valor > 0:
            saldo -= valor
            extrato += f"Saque: R$ {valor:.2f}\n"
            numero_saques += 1

        else:
            print("Operação falhou! O valor informado é inválido.")

    elif opcao == "e":
        print("\n=============== EXTRATO ==================")
        print("Não foram realizados movimentações." if not extrato else extrato)
        print(f"\nSaldo: R$ {saldo:.2f}")
        print("============================================")

    elif opcao == "q":
        break

    else:
        print("Operação inválida, por favor selecione novamente a operação desejada.")


## Pré-visualização do Sistema:

[d] Depositar

[s] Sacar

[e] Extrato

[q] Sair

=> e  

============== EXTRATO =============


Não foram realizadas movimentações.

Saldo: R$ 0.00

==================================


---------------------------------------------------------------------------------------------------------------------------------------------------------

## Esboço da segunda parte do desafio.

Neste 2° desafio iremos atualizar a implementação do sistema bancário, para armazenar os dados de clientes e contas bancárias em objetos ao invés de dicionários.
Todo o passo a passo da implementação esta descrita na imagem abaixo.


![Trilha Python - desafio](https://github.com/Sidnei247/Desafio-sistema-bancario-Python/assets/166535833/9dbdd1ba-5b9a-43b9-b0dc-9a3fd0a1000b)
