# Tópicos de Big Data em Python
Código para trabalho de extensão:

```
import csv

# Função para adicionar uma nova pessoa ao cadastro
def adicionar_pessoa(cadastro):
    nome = input("Digite o nome: ")
    bairro = input("Digite o bairro onde morou: ")
    problema = input("Digite o tipo de problema que levou à situação de rua: ")

    pessoa = {
        'Nome': nome,
        'Bairro': bairro,
        'Problema': problema
    }

    cadastro.append(pessoa)
    print("Pessoa cadastrada com sucesso!")

# Função para salvar o cadastro em um arquivo CSV
def salvar_cadastro(cadastro):
    with open('cadastro_pessoas.csv', 'w', newline='') as csvfile:
        fieldnames = ['Nome', 'Bairro', 'Problema']
        writer = csv.DictWriter(csvfile, fieldnames=fieldnames)

        writer.writeheader()
        for pessoa in cadastro:
            writer.writerow(pessoa)

# Função principal
def main():
    cadastro = []

    while True:
        print("\nMenu:")
        print("1. Adicionar nova pessoa")
        print("2. Salvar e sair")
        escolha = input("Escolha uma opção: ")

        if escolha == '1':
            adicionar_pessoa(cadastro)
        elif escolha == '2':
            salvar_cadastro(cadastro)
            break
        else:
            print("Opção inválida. Tente novamente.")

if __name__ == "__main__":
    main()
```
