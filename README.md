# L-gica-proposicional-e-grafos
atividade ponderada

# Matemática – Atividade Ponderada

**Aluno:** Henrique Rodrigues Diniz  
**Turma:** T15  
**Data:** 14/05/2025



## ITEM 1 – LÓGICA PROPOSICIONAL

**a)**  
O usuário está autenticado e possui perfil de administrador, ou então o usuário está autenticado e possui matrícula ativa, mas **não possui perfil de administrador**.  
Ou seja, o acesso ao sistema será concedido se ele for administrador autenticado, ou aluno ativo autenticado sem ser administrador.



**b)**  
Fórmula original:  
```
a = (p ∧ q) ∨ (p ∧ r ∧ ¬q)
```

Fórmula com conectivos ¬ e ∨, aplicando De Morgan:  
```
a = ¬(¬p ∨ ¬q) ∨ ¬(¬p ∨ ¬r ∨ q)
```



**c)** Tabela Verdade:

| p | q | r | ¬q | p∧q | p∧r∧¬q | a = (p∧q) ∨ (p∧r∧¬q) |
|---|---|---|----|------|----------|-----------------------|
| 0 | 0 | 0 |  1 |   0  |     0    |           0           |
| 0 | 0 | 1 |  1 |   0  |     0    |           0           |
| 0 | 1 | 0 |  0 |   0  |     0    |           0           |
| 0 | 1 | 1 |  0 |   0  |     0    |           0           |
| 1 | 0 | 0 |  1 |   0  |     0    |           0           |
| 1 | 0 | 1 |  1 |   0  |     1    |           1           |
| 1 | 1 | 0 |  0 |   1  |     0    |           1           |
| 1 | 1 | 1 |  0 |   1  |     0    |           1           |



**d)**  
A fórmula `a` é uma **contingência**, pois apresenta valor lógico verdadeiro em alguns casos e falso em outros, como demonstrado na tabela acima.



## ITEM 2 – GRAFO DE NAVEGAÇÃO ENTRE PÁGINAS

**a)** Matriz de Adjacência (ordem: C, D, I, O, P):

|     | C | D | I | O | P |
|-----|---|---|---|---|---|
| C   | 0 | 0 | 0 | 1 | 0 |
| D   | 1 | 0 | 0 | 0 | 1 |
| I   | 0 | 1 | 0 | 0 | 0 |
| O   | 0 | 0 | 1 | 0 | 0 |
| P   | 1 | 0 | 0 | 0 | 0 |



**b)**  
O grafo possui 2 ciclos:
- Ciclo 1: D → P → D  
- Ciclo 2: I → D → C → O → I



**c)**  
O grafo não é fortemente conexo, pois não existe caminho entre todos os pares de vértices.  
Por exemplo: de C até I não existe nenhum caminho, o que viola a definição de conectividade forte.



## ITEM 3 – GRAFO DE PERMISSÕES COM REGRAS LÓGICAS

a) Caminhos de A até E e condições:

1. A → B → C → D → E  
   Condição: `p ∧ q ∧ r ∧ ¬p` → contradição (inviável)

2. A → C → D → E  
   Condição: `q ∧ r ∧ ¬p` → **válido**, se o usuário foi contratado, participa das tarefas, e não possui bons resultados acadêmicos



**b)**  
Se o usuário satisfaz `p ∧ q ∧ ¬r`, então:

- Ele **tem bons resultados acadêmicos**
- Ele **foi contratado**
- Mas **não participa das tarefas**

Nesse caso, nenhum caminho até o vértice E é possível, pois ambos exigem a proposição `r` (participação nas tarefas).


**c)**  
Para permitir o acesso via caminho A → B → C → D → E, propomos alterar a condição da aresta (D → E):

- De: `¬p`  
- Para: `(¬p ∨ q)` → **contingência**

Agora, a nova condição lógica do caminho é:  
`p ∧ q ∧ r ∧ (¬p ∨ q)` → o que pode ser **verdadeiro** dependendo dos valores de `p` e `q`.


