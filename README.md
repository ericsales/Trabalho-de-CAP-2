//Trabalho de CAP 2

/*
Input:
Output:
*/

/*
Variaveis:
    variaveis x e y usadas 
    -   X1 = primeiro ponto do poligono
    -   Y1 = primeiro ponto do poligono
    -   X  = ponto i-1 da somatoria
    -   Y  = ponto i-1 da somatoria
    -   Xi = ponto atual da somatoria
    -   Yi = ponto atual da somatoria

    resultadda das contas
    -   somatoria = somatoria dos pontos x e Y
    -   s = resultado da somatoria mais o ultimo ponto e do primeiro
    -   a = area do poligono

    contadores de laço
    -   i = contador de laço
    -   j = contador de laço

    variaveis auxiares
    -   quantPoligonos = variavel auxiliar
    -   quantPontos = variavel auxiliar
*/

//Bibliotecas
#include <stdio.h>
#include <math.h>

int main(){
  
  //Inicializacoes
  double X1, Y1, X, Y, Xi, Yi, somatoria = 0, s, a;
  int i, j, quantPoligonos, quantPontos;
 
  //Entra de quantidade de poligonos a serem a digitada
  printf("Digite a quantidade de poligonos: ");
  scanf("%d", &quantPoligonos);

  //Inicio do laço  
  for(i = 1; i <= quantPoligonos; i++)
  {
        //Entra da quantidade de pontos
        printf("Digite a quantidade de pontos: ");
        scanf("%d", &quantPontos);
          
        printf("\n");
 
        //Primeiro ponto
        printf("Digite a primeira coordenada X: ");
        scanf("%lf", &X1);
        printf("Digite a primeira coordenada Y: ");
        scanf("%lf", &Y1);

        printf("\n");                           //Quebra de linha
 
        X = X1;                                 //Ponto auxiliar que funcionara como a coordenada anterior
        Y = Y1;
 
        //Inicio do laço
        for(j = 1; j < quantPontos; j++)
        {
            //Entra dos demais pontos
            printf("Digite a coordenada X: ");
            scanf("%lf", &Xi);
            printf("Digite a coordenada Y: ");
            scanf("%lf", &Yi);

            //Quebra de linha
            printf("\n");
 
            somatoria = somatoria + ((Xi * Y) - (Yi * X));      //Conta da somatoria sendo Xi o ponto atual e Y o ponto anterios
 
            X = Xi;                                             //A variavel X recebe Xi, agora Xi pode receber o novo ponto
            Y = Yi;
        }
 
        s = ((X1 * Y) - (Y1 * X)) + somatoria;                  //Soma dos ultimo com o primeiro ponto
          
        a = s/2;                                                //Calculo da area

        //Saida do resultado 

        printf("\nArea do poligono = %.2lf", a);
  }

}
