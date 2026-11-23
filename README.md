# Sistema de Gerenciamento de Filas (Atendimento Prioritário)

Sistema desenvolvido em **C** para controle de filas de atendimento com triagem automatizada de prioridades. O programa organiza senhas em três níveis (Urgente, Preferencial e Normal).

## Funcionalidades

- **Triagem e Geração de Senhas:** Classifica o usuário automaticamente com base em idade, gênero e condições especiais, gerando senhas sequenciais formatadas (`U001`, `P001`, `N001`).
- **Ordem de Chamada por Prioridade:** Respeita a hierarquia **Urgente > Preferencial > Normal**, mantendo a ordem de chegada (FIFO) dentro de cada categoria.
- **Consulta da Próxima Senha:** Permite visualizar qual será a próxima senha chamada sem removê-la da fila.
- **Controle de Atendimento Ativo:** Impede que uma nova senha seja chamada enquanto houver um atendimento em andamento.
- **Painel em Tempo Real:** Exibe a senha em atendimento no momento, a quantidade de pessoas aguardando e todas as senhas pendentes por categoria.

## Regras de classificação

Durante o cadastro, o sistema avalia os dados informados na seguinte ordem de precedência:

| **Urgente** | `U` | Idade superior a 80 anos. |

| **Preferencial** | `P` | Gestantes ou lactantes (feminino, entre 10 e 60 anos), pessoas com necessidades especiais, pessoas com obesidade, mulheres com 60 anos ou mais, ou homens com 65 anos ou mais. |

| **Normal** | `N` | Demais usuários que não se enquadram nos critérios anteriores. |

## Estrutura e Funcionamento Técnico

- **Armazenamento:** Utiliza três matrizes estáticas (`filaU`, `filaP` e `filaN`) com capacidade para até **50 senhas por categoria**, gerenciadas por índices de início (`iU`, `iP`, `iN`) e fim (`fU`, `fP`, `fN`).
- **Validação de Entrada:** Conta com limpeza de buffer (`limpa()`) e loops de verificação para evitar falhas de leitura em campos de gênero, idade (`0` a `130`) e respostas binárias (`S/N`).
- **Dependências:** Utiliza apenas bibliotecas padrão da linguagem C (`stdio.h` e `ctype.h`), sem necessidade de bibliotecas externas.

## Como Compilar e Executar

### Pré-requisitos
- Compilador C instalado ou compilador no navegador (online gdb)

### Passo a passo

1.Copie o código fonte

2. cole no compilador

3. execute o código
