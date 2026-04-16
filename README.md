<img src="imgs/UNIFOR_logo1b.png" width="400">

# T4 - Problema do Caixeiro Viajante (TSP) com Heurísticas de Inserção

Trabalho Prático 4 da disciplina de Resolução de Problemas com Grafos (UNIFOR).

Implementação em Java das heurísticas de inserção **nearest insertion** e **smallest insertion** para o Traveling Salesman Problem (TSP).

---

## Heurísticas implementadas

### Nearest Insertion

A cada passo, o ponto `p` é inserido imediatamente após o nó do circuito atual que está mais próximo de `p` (menor distância euclidiana). A inserção ocorre na posição que causa o menor aumento possível no comprimento total do percurso.

### Smallest Insertion (Cheapest Insertion)

A cada passo, o ponto `p` é inserido entre os dois nós consecutivos `(i, j)` do circuito atual cuja inserção gera o menor aumento no comprimento total. O aumento de custo para cada aresta é calculado como:

```
custo = dist(i, p) + dist(p, j) - dist(i, j)
```

---

## Estrutura do projeto

```text
Projeto4/
├── README.md
├── T4.md
├── dados/
│   ├── tsp10.txt           (instância de depuração, 10 cidades)
│   ├── tsp10-nearest.txt   (referência passo a passo — nearest)
│   ├── tsp10-smallest.txt  (referência passo a passo — smallest)
│   ├── tsp10-optimal.txt   (solução ótima da instância de 10 cidades)
│   └── usa13509.txt        (instância de execução final, 13.509 cidades)
└── src/
    ├── Main.java
    ├── Point.java
    ├── Tour.java
    ├── TSPVisualizer.java
    ├── In.java
    ├── StdIn.java
    ├── StdOut.java
    └── StdDraw.java
```

---

## Compilação e execução

No diretório `src`, execute:

```bash
javac *.java
java Main ../dados/tsp10.txt
```

Para a instância final:

```bash
java Main ../dados/usa13509.txt
```

---

## Visualização

O programa exibe os dois circuitos sobrepostos:

- **Vermelho** — Nearest Insertion
- **Azul** — Smallest Insertion
- **Preto** — pontos das cidades

Os comprimentos de cada circuito são exibidos na legenda da janela.

---

## Resultados obtidos

| Instância | Nearest Insertion | Smallest Insertion |
|-----------|------------------:|-------------------:|
| tsp10     | 1566.1363         | 1655.7462          |

[Assista à apresentação do projeto aqui]("https://www.youtube.com/watch?v=ppAPmURW3DQ")
