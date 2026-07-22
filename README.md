Análise Comparativa: Árvores AVL vs. Rubro-Negra na Indexação de CPFs

Estudo experimental e comparativo entre as estruturas de dados AVL e Rubro-Negra (ambas implementadas manualmente em C++), avaliando o desempenho em operações de inserção, busca e remoção sob diferentes padrões de entrada (aleatória e ordenada) com até 5 milhões de registros sintéticos de CPF.

Principais Destaques & Conclusões
Sem Vencedor Universal:

Inserção Aleatória: A árvore Rubro-Negra é ~4–10% mais rápida (devido a menos rotações/rebalancing).

Remoção Aleatória: A AVL é ~10–16% mais rápida.

Busca: Ambas empatam na média de comparações, embora a AVL garanta uma altura máxima ~2× menor no pior caso de entrada ordenada (23 vs 42 em 5M).

Estrutura do CPF & Sharding:

Índice Particionado: Dividir os dados em 10 árvores pelo 9º dígito (região fiscal) acelerou a consulta regional em ~5×.

Árvores vs. Tabela Hash (unordered_set): A Hash vence em buscas pontuais, mas as árvores balanceadas são >150× mais rápidas em consultas por intervalo/range e ordens sequenciais.

Complexidade & Manutenibilidade: A AVL apresentou implementação consideravelmente mais simples do que a Rubro-Negra (cujo fixup de remoção é propenso a erros).

Linguagem: C++11 / C++17 (G++ 11.4 -O3)

Dados Sintéticos: CPFs gerados via algoritmo Mersenne Twister (semente fixa, dígitos verificadores válidos e distribuição populacional por região fiscal — em conformidade com a LGPD).

Ambiente: Ubuntu 22.04 LTS (4 vCPU, 3.8 GiB RAM).

Métricas Avaliadas: Tempo de execução (ms), altura máxima da árvore, comprimento médio de caminho e falhas de validação.
