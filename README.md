
🏦 Sistema Bancário Simples (Refatoração Funcional)

Este projeto implementa um sistema bancário básico com operações de Depósito, Saque e Extrato, seguindo a estrutura de desenvolvimento inicial, mas evoluído para uma arquitetura **modular** baseada em **Funções**.

O principal objetivo desta refatoração foi organizar o código, migrando a lógica de fluxo para funções dedicadas, conforme solicitado pelo desafio, garantindo clareza e manutenibilidade.

## ✨ Destaques da Refatoração

A arquitetura do código foi aprimorada com a aplicação dos seguintes conceitos:

* **Modularidade:** Todo o sistema foi dividido em funções específicas para cada tarefa (operacional e cadastral).
* **Parâmetros Específicos:** Uso de Argumentos Apenas por Posição (`/`) e Argumentos Apenas por Nome (`*`) para aumentar a clareza e segurança na chamada das funções.
* **Separação de Responsabilidades:** Criação de funções dedicadas para o gerenciamento de **usuários** e **contas bancárias**, utilizando listas e dicionários.

## ⚙️ Funcionalidades Implementadas

O sistema oferece as seguintes operações:

| Comando | Descrição |
| :---: | :--- |
| `[d]` | **Depositar:** Adiciona valor ao saldo. |
| `[s]` | **Sacar:** Retira valor, respeitando o limite diário de R$ 500,00 e o máximo de 3 saques por dia. |
| `[e]` | **Extrato:** Exibe o histórico de movimentações e o saldo atual. |
| `[nu]` | **Novo Usuário:** Cadastra um novo usuário, garantindo a unicidade do CPF. |
| `[nc]` | **Nova Conta:** Cria uma conta bancária, vinculada a um usuário existente (agência fixa: `0001`). |
| `[lc]` | **Listar Contas:** Exibe todas as contas cadastradas. |
| `[q]` | **Sair:** Encerra a aplicação. |

## 📐 Estrutura do Código

| Nome da Função | Responsabilidade | Tipo de Argumento |
| :--- | :--- | :--- |
| `main()` | Gerencia o loop principal, o menu e as variáveis de estado. | N/A |
| `depositar()` | Executa o depósito. | **Posicional (`/`)** |
| `sacar()` | Executa o saque, checando todas as regras (saldo, limite, saques). | **Nomeado (`*`)** |
| `exibir_extrato()` | Exibe o extrato e o saldo. | **Posicional (`/`)** |
| `filtrar_usuario()` | Busca um usuário na lista pelo CPF. | Padrão |
| `criar_usuario()` | Coleta dados e adiciona um novo usuário. | Padrão |
| `criar_conta()` | Cria um número de conta e o vincula ao usuário. | Padrão |

### Exemplo da Função `sacar()`

A função `sacar` utiliza **Argumentos Apenas por Nome** (`*`) para forçar o uso explícito dos nomes dos parâmetros na chamada. Isso melhora a legibilidade e previne a inversão acidental de valores críticos como `saldo` e `limite`.

```python
# Chamada na função main() para garantir clareza
saldo, extrato, numero_saques = sacar(
    saldo=saldo,
    valor=valor,
    extrato=extrato,
    limite=limite,
    # ... demais parâmetros
)
🚀 Como Executar o Projeto
Pré-requisitos: Certifique-se de ter o Python instalado.

Clone o Repositório:
git clone [https://github.com/BrunaDev9/sistema-bancario-python.git](https://github.com/BrunaDev9/sistema-bancario-python.git)
cd sistema-bancario-python
Execute o Arquivo:
python sistema-bancario-python.py
🧑‍💻 Autor
Bruna Veras
