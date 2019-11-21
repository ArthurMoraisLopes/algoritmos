# algoritmos

#include <stdlib.h>
#include <locale.h>
#include <conio.h>
#include <time.h>
#include <math.h>



void copia ( int vetormagico [], int vetormalabarista [], int tamanho)
{
    for (int conttransferencia = 0; conttransferencia<tamanho; conttransferencia++)
    {
        vetormalabarista [conttransferencia] = vetormagico [conttransferencia];
    }
}




void tempomedio(double tempos[], double med, int iteraor, char tipo[])
{
    int con;

    printf("\nTempo médio gasto para o ordenador %s: ", tipo);

    for(con=0; con<iteraor; con++)
    {
        med = med + tempos[con];
    }
    printf("%lf\n", med/iteraor);
}





void BubbleSort(int vetormagico[], int tamanho)
{
    int i, j, temporario;
    for (i=0; i<tamanho-1; i++)
    {
        for (j=0; j<tamanho-1-i ; j++)
        {
            if (vetormagico[j+1]<vetormagico[j])
            {

                temporario = vetormagico[j+1];
                vetormagico[j+1] = vetormagico [j];
                vetormagico[j] = temporario;
            }
        }
    }
}





void InsertionSort(int vetormagico[], int tamanho)
{
    int i, j, temporario;
    for (i=1; i<tamanho; i++)
    {
        temporario = vetormagico[i];
        j = i-1;
        while ((temporario <  vetormagico[j]) && (j>=0))
        {
            vetormagico[j+1] = vetormagico[j];
            j--;
        }
        vetormagico[j+1] = temporario;
    }
}




int SMALLEST (int vetormagico[], int tamanho, int movimento)
{
    int elemento = vetormagico[movimento], i;
    for (i=(movimento+1); i<tamanho; i++)
    {
        if (vetormagico[i]<elemento)
        {
            elemento = vetormagico[i];
            movimento = i;
        }
    }

    return movimento;
}

void SelectionSort(int vetormagico[], int tamanho)
{
    int movimento, posicao, temporario;
    for (movimento=0; movimento<tamanho; movimento++)
    {
        posicao = SMALLEST(vetormagico, tamanho, movimento);
        temporario = vetormagico[movimento];
        vetormagico[movimento] = vetormagico [posicao];
        vetormagico [posicao] = temporario;
    }
}




void MergeFazTudo (int vetormagico [], int beg, int meio, int end, int tamanho)
{
    int i = beg, j = meio+1, index = beg, temp[tamanho], k;
    while ((i<=meio)&& (j<=end))
    {
        if (vetormagico[i]< vetormagico[j])
            temp [index++] = vetormagico [i++];
        else
            temp [index++] = vetormagico [j++];
    }
    if (i>meio)
    {
        while (j<=end)
            temp [index++] = vetormagico [j++];
    }
    else
    {
        while (i<=meio)
            temp [index++] = vetormagico [i++];
    }
    for (k=beg; k<index; k++)
        vetormagico[k] = temp[k];
}


void MergeSort(int vetormagico [], int beg, int end, int tamanho)
{
    int meio;
    if (beg<end)
    {
        meio = floor ((beg+end)/2);
        MergeSort(vetormagico, beg, meio, tamanho);
        MergeSort(vetormagico, meio+1, end, tamanho);
        MergeFazTudo (vetormagico, beg, meio, end, tamanho);
    }
}





int PARTITION (int vetormagico [], int beg, int end)
{
    int esquerda = beg;
    int direita = end;
    int posicaorepartevetor = beg;
    int elemento = vetormagico[posicaorepartevetor];
    int temporario;
    while (esquerda < direita)
    {
        while (vetormagico[esquerda]<=elemento)
            esquerda ++;
        while (vetormagico[direita]>elemento)
            direita --;
        if (esquerda <direita)
        {
            temporario = vetormagico[esquerda];
            vetormagico[esquerda] = vetormagico[direita];
            vetormagico[direita] = temporario;
        }
    }
    vetormagico [beg] = vetormagico[direita];
    vetormagico [direita] = elemento;
    return direita;
}


void QuickSort(int vetormagico[], int beg, int end)
{
    int posicaorepartevetor;
    if (beg<end)
    {
        posicaorepartevetor = PARTITION (vetormagico, beg, end);
        QuickSort (vetormagico, beg,posicaorepartevetor-1);
        QuickSort (vetormagico,posicaorepartevetor+1, end);
    }
}





void main()
{

    srand(time(NULL));
    clock_t comeco;
    clock_t termino;
    double tempogasto, tempogasto2, tempogasto3, tempogasto4, tempogasto5;
    double med = 0;
    setlocale(LC_ALL, "");
    int tamanho;
    int iteraor;
    int elementomax;
    int k, contadoritera;


    printf ("Qual o tamanho do seu vetor ? ");
    

 TAMANHO:
    
    scanf ("%d", &tamanho);
    if(tamanho<1)
    {
        printf("COMO SE QUER ORDENAR VETOR VAZIO OUU NEGATIVO ? TÁ DOIDO ??:\n");
        goto TAMANHO;
    }
    puts ("\n\n");



    printf ("Quantas interações cada algoritmo de ordenação tem que ter ? ");
    
    
ITERACAO:

    scanf ("%d", &iteraor);
    if(iteraor<1)
    {
        printf("COMO SE QUER INTERAGIR COM NÚMERO NEGATIVO? TÁ DOIDO ??:\n");
        goto ITERACAO;
    }
    puts ("\n\n");



    printf ("Qual o tamanho máximo de cada elemento do vetor?:");
    
    
ELEMENTOMAX:

    scanf ("%d", &elementomax);
    if(elementomax<1)
    {
        printf("SÓ POSITIVO FERA !!\n");
        goto ELEMENTOMAX;
    }



    //TEMPOS DOS ALGORITMOS
    double tempos[iteraor];
    double tempos2[iteraor];
    double tempos3[iteraor];
    double tempos4[iteraor];
    double tempos5[iteraor];


    //VETORES CRIADOS
    int vetormagico[tamanho];
    int vetormalabarista [tamanho];


    for (k=0; k<tamanho; k++)
    {
        vetormagico [k] = (rand()%elementomax);
    }


    for (contadoritera=0; contadoritera< iteraor; contadoritera++)
    {
        puts ("\n");



        //BUBBLE SORT
        comeco = 0, termino = 0;
        copia(vetormagico, vetormalabarista, tamanho);
        comeco = clock();
        BubbleSort(vetormalabarista, tamanho);
        termino = clock();
        copia(vetormagico, vetormalabarista, tamanho);
        tempogasto = (double)(termino-comeco)/CLOCKS_PER_SEC;
        tempos[contadoritera] = tempogasto;
        puts ("\n");
        printf("Tempo gasto para iteração a %dº Iteração com BubbleSort: ", contadoritera+1);
        printf("%lf", tempogasto);
        tempogasto = 0;



        //INSERTION SORT
        comeco = 0, termino = 0;
        comeco = clock();
        InsertionSort(vetormalabarista, tamanho);
        termino = clock();
        copia(vetormagico, vetormalabarista, tamanho);
        tempogasto2 = (double)(termino-comeco)/CLOCKS_PER_SEC;
        tempos2[contadoritera] = tempogasto2;
        puts ("\n");
        printf("Tempo gasto para iteração a %dº Iteração com InsertionSort: ", contadoritera+1);
        printf("%lf", tempogasto2);
        tempogasto = 0;



        //SELECTION SORT
        comeco = 0, termino= 0;
        comeco = clock();
        SelectionSort(vetormalabarista, tamanho);
        termino = clock();
        copia(vetormagico, vetormalabarista, tamanho);
        tempogasto3 = (double)(termino-comeco)/CLOCKS_PER_SEC;
        tempos3[contadoritera] = tempogasto3;
        puts ("\n");
        printf("Tempo gasto para iteração a %dº Iteração com Selection Sort:  ", contadoritera+1);
        printf("%lf", tempogasto3);
        tempogasto = 0;



        //QUICK SORT
        int beg = 0, end = tamanho-1;
        comeco = clock();
        QuickSort(vetormalabarista, beg, end);
        termino = clock();
        copia(vetormagico, vetormalabarista, tamanho);
        tempogasto5 = (double)(termino-comeco)/CLOCKS_PER_SEC;
        tempos5[contadoritera] = tempogasto5;
        puts ("\n");
        printf("Tempo gasto para iteração a %dº Iteração com Quick Sort:  ", contadoritera+1);
        printf("%lf", tempogasto5);
        tempogasto = 0;



        //MERGE SORT
        beg = 0, end = tamanho-1;
        comeco = clock();
        MergeSort(vetormalabarista, beg, end, tamanho);
        termino = clock();
        copia(vetormagico, vetormalabarista, tamanho);
        tempogasto4 = (double)(termino-comeco)/CLOCKS_PER_SEC;
        tempos4[contadoritera] = tempogasto4;
        puts ("\n");
        printf("Tempo gasto para iteração a %dº Iteração com Merge Sort:  ", contadoritera+1);
        printf("%lf", tempogasto4);
        tempogasto = 0;
        getchar ();
    }


    puts ("\n");

    tempomedio(tempos, med, iteraor, "BubbleSort");
    med = 0;
    tempomedio(tempos2, med, iteraor, "InsertionSort");
    med = 0;
    tempomedio(tempos3, med, iteraor, "SelectionSort");
    med = 0;
    tempomedio(tempos4, med, iteraor, "MergeSort");
    med = 0;
    tempomedio(tempos5, med, iteraor, "QuickSort");
    med = 0;

    getchar ();
}
