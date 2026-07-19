# comparativo-avl-rubronegra
Estudo comparativo de desempenho e estresse de inserção entre Árvore AVL e Árvore Rubro-Negra utilizando C++ e CPFs.

# Análise Comparativa de Estruturas de Dados Autocompensadoras sob Estresse de Ingestão

Este repositório contém a infraestrutura de testes em C++ desenvolvida para avaliar a eficiência computacional entre a **Árvore AVL** (implementação manual) e a **Árvore Rubro-Negra** (via `std::set`), focando estritamente na fase de carga, alocação de memória e rebalanceamento estrutural.

## Escopo da Pesquisa
O foco analítico deste estudo delimita-se especificamente à **Fase de Ingestão e Estruturação de Dados (Inserção Massiva)**. O objetivo é quantificar o custo computacional puro de rearranjo de ponteiros e rebalanceamento quando submetidos a lotes progressivos de dados em cenários realistas de alta escrita (como processos de *Bulk Loading* em bancos de dados).

## Estrutura do Projeto

* `main.cpp`: Código-fonte principal contendo a geração pseudoaleatória de chaves via Mersenne Twister, estruturas de dados e o pipeline de medição.
* Massa de Testes: Lotes de 500 mil, 1 milhão e 3 milhões de chaves de CPF exclusivas.

## Como Executar o Experimento

Para compilar e rodar o benchmark em sua máquina local, certifique-se de ter um compilador que suporte C++ 11 ou superior e execute:

```bash
g++ -O3 main.cpp -o benchmark
./benchmark

