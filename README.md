# algoritmos ordenação


1. INTRODUÇÃO


No mundo da computação é essencial entregar um código limpo, bem estruturado e com um processo de compilação em um menor e armazenamento possível (mas é praticamente impossível obter todos esses resultados ao mesmo tempo). Portanto, para obter um código eficiente e otimizado (afim de alcançar bons resultado citados anteriormente, deve-se analisar os algoritmos específicos de cada área e comparar cada um, sendo definido por busca, ordenação e outros.
É importante salientar que para se ter um resultado plausível, em relação ao processo de compilação e armazenamento, analisa-se a quantidade de termos presentes no algoritmo, pois, um algoritmo de tamanho 5 seria sempre menor que 1000. Outro fato seria a junção da quantidade de termos com a complexidade, notação BigOnotation, do algoritmo, seja para um caso médio ou bom.
Nesse caso, afunilando mais o assunto, tem-se os algoritmos de ordenação: Quick Sort, Merge Sort, Selection Sort, Bubble Sort e Insertion Sort, sendo os 2 primeiros sando recursividade e os 3 últimos usando apenas vetores.

2. MÉTODO

Antes de inicializar a implementação do algoritmo, foi explicada a matéria de Algoritmos de Ordenação pelo professor Elder. Após isso, foi passado aos discentes um trabalho sobre os algoritmos de ordenação, pedindo para comparar com 4 vetores de diferentes tamanhos.
Logo depois, foi implementado o código com o auxílio do CodeBlocks e DevC++ -pois em alguns casos o CodeBlocks dava erros – e com o auxílio da biblioteca Time.H foi medido o tempo de execução de cada algoritmo. Foi realizado uma quantidade de 5 interações, mas nesse caso, o usuário estaria disposto a fazer o tanto que quisesse. Também, foi utilizado 2 vetores, um original e outro cópia. A cópia sempre seria parte da ordenação, já a original apenas serviria para fazer a cópia. Nesse caso, se não colocasse um vetor cópia, o vetor sempre estaria ordenado, afetando outros algoritmos, pois suas ações sempre teriam tempo 0.

SEGUE O CÓDIGO EM ANEXO E NA LINGUAGUEM C.


3. RESULTADOS E DISCUSSÕES

Portanto, por meio do código acima, após inúmeras iterações (5, nesse caso) e com os tamanhos dos vetores de 10000, 30000, 60000, 90000, como também, uma quantidade máxima de elementos até 100000, obtém-se o seguinte resultado das compilações referentes aos algoritmos de ordenação.

Tabela 1: Algoritmos Ordenação para 10000 elementos 10000 
BUBBLESORT INSER.SORT SELECT.SORT MERGESORT QUICKSORT

1ºIteração
0.317
0.093
0.162
0.003
0.001 

2ºIteração
0.317
0.089 
0.171 
0.002 
0.002

3ºIteração
0.323
0.092
0.168
0.002
0.001 

4ºIteração 
0.318
0.09 
0.163 
0.002
0.002

5ºIteração
0.332
0.089
0.171
0.003
0.002 

Média 
0.3214 
0.0906 
0.167
0.0024
0.0016



Tabela 2:
Algoritmos Ordenação para 30000 elementos 30000 BUBBLESORT 
INSER.SORT SELECT.SORT MERGESORT QUICKSORT

1ºIteração
3.25
0.788
1.45
0.01
0.005 

2ºIteração 
3.24
0.802
1.459
0.011 
0.005

3ºIteração
3.24
0.797
1.447
0.013
0.005

4ºIteração 
3.365
0.777 
1.491
0.013
0.005

5ºIteração
3.2
0.789
1.488
0.012
0.005 

Média
3.2832 
0.7906
1.4576
0.0124
0.005

Tabela 3 : Algoritmos Ordenação para 60000 elementos 60000 
BUBBLESORT INSER.SORT SELECT.SORT MERGESORT QUICKSORT

1ºIteração
13.543
3.509
5.843
0.038
0.011 

2ºIteração
14.015 
3.442 
6.08
0.038
0.01

3ºIteração
14.479
3. 384
6.089
0.044
0.012

4ºIteração 
14.151
3.363 
6.218 
0.042
0.011

5ºIteração
14.465
3.266
6.146
0.039
0.011 

Média 
14.1306
3.3928
6.0752 
0.0402
0.011

Tabela 4 : Algoritmos Ordenação para 90000 elementos 90000 
BUBBLESORT INSER.SORT SELECT.SORT MERGESORT QUICKSORT

1ºIteração
30.891
7.169
13.148
0.099
0.019 

2ºIteração
31.076
7.161 
13.117 
0.096
0.017

3ºIteração
33.458
8.032
14.254
0.098
0.017

4ºIteração
31.857
7.1 
13.013 
0.099
0.018

5ºIteração
35.963
13.721
16.496
0.097
0.018 

Média 
32.649
8.6366
14.0056
0.0978
0.0178


Segue em anexo o template do trabalho, tendo assim a plotagem do gráfico no Excell e algoritmos na notação BigOnotation
