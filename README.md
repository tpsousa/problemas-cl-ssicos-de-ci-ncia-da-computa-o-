# 🏰 Torres de Hanói 

Este repositório traz uma solução **simples e elegante** para o clássico problema das **Torres de Hanói**, usando **Python** e um pouquinho de **recursão**. Bora entender como funciona?

---

## O que é o problema?

O desafio das **Torres de Hanói** é assim: você tem **3 hastes** e um monte de **discos empilhados** na primeira haste (a origem). O objetivo é mover todos os discos para outra haste (o destino), respeitando estas regras:

1. Só dá pra **mover um disco por vez**.
2. Você **não pode colocar um disco maior sobre um menor**.
3. Pode usar uma terceira haste (a auxiliar) pra ajudar na bagunça.

Parece simples, mas a coisa complica quando os discos aumentam!

---

## Como resolvemos isso?

Aqui a mágica é usar **recursão**, que é basicamente uma função chamando a si mesma pra resolver subproblemas menores até chegar num ponto tão simples que dá pra resolver direto (o famoso caso base).

A ideia é:
1. Mover os `n-1` discos da origem para a haste auxiliar.
2. Mover o maior disco direto para o destino.
3. Mover os `n-1` discos da auxiliar para o destino.

---

## Código da Solução

Aqui está a solução em Python:

```python
def hanoi(n, origem, destino, auxiliar):
    if n == 1:
        print(f"Mova o disco 1 de {origem} para {destino}")
        return
    hanoi(n - 1, origem, auxiliar, destino)
    print(f"Mova o disco {n} de {origem} para {destino}")
    hanoi(n - 1, auxiliar, destino, origem)

# Exemplo: Resolver o problema com 3 discos
hanoi(3, 'A', 'C', 'B')
Exemplo de saída (3 discos):
css
Copiar código
Mova o disco 1 de A para C
Mova o disco 2 de A para B
Mova o disco 1 de C para B
Mova o disco 3 de A para C
Mova o disco 1 de B para A
Mova o disco 2 de B para C
Mova o disco 1 de A para C
Como funciona a lógica?
A recursão funciona assim:

Se n == 1, é moleza: movemos o único disco direto para o destino.
Caso contrário:
Chamamos a função pra mover os n-1 discos pra auxiliar.
Movemos o disco maior pra o destino.
Chamamos de novo pra levar os discos da auxiliar pro destino.
Basicamente, dividimos o problema em partes menores até resolver tudo!

Por que essa solução é legal?
Compacta: Poucas linhas e resolve um problema super famoso.
Fácil de entender: A lógica é clara e segue um fluxo natural.
Recursiva: Quem não gosta de uma boa recursão, né?
🤝 Contribua!
Curtiu a solução? Tem ideias pra melhorar ou quer adicionar algo novo? Bora colaborar!
