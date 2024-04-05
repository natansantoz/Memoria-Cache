# Cache Direta

O objetivo do trabalho foi a implementação de uma cache que utilize mapeamento direto. 

**PS**: Os subcircuitos criados foram omitidos visando tornar o readme conciso.

<h2 align="center">Circuito Principal</h2>

![Circuito Principal](https://github.com/natansantoz/Memoria-Cache/blob/main/arquivos/circuito_principal.jpg)


<h2 align="center">Cache Direta</h2>

![Cache Direta](https://github.com/natansantoz/Memoria-Cache/blob/main/arquivos/cache.png)

<h2 align="center">Processador</h2>

![Processador](https://github.com/natansantoz/Memoria-Cache/blob/main/arquivos/processador.jpg)

<h2 align="center">Memória Principal</h2>

![Memória Principal](https://github.com/natansantoz/Memoria-Cache/blob/main/arquivos/memoria_principal.jpg)


<br>

<h2 align="center">Processador</h2>

O processador utilizado foi desenvolvido no trabalho de conclusão da disciplina de Arquitetura I. No entanto, foram realizadas adaptações como a adição de um novo registrador no banco, alterações no tamanho dos campos das instruções do conjunto de instruções, entre outras.


<br>

<h2 align="center">Cache Direta</h2>


A cache possui 8 linhas, cada uma composta de 4 palavras de 16 bits cada. Logo, o tamanho da cache é de 512 bits ou 64 bytes.


<br>

<h2 align="center">Política de Escrita</h2>

A política de escrita adotada foi a de escrita direta (write-through). 

Nesse sentido, as operações de escrita são realizadas na memória principal e na cache, de modo que ambas sempre estão atualizadas.


<br>

<h2 align="center">Memória Principal</h2>

Tendo em vista que o componente “Memória RAM” do Logisim possui apenas um barramento de saída e que a comunicação entre a memória principal e a cache é por blocos de quatro palavras, a criação de uma memória principal que possibilitasse tal comunicação foi necessária.

À luz das características supracitadas, combinamos quatro componentes “Memória RAM” do Logisim visando permitir a comunicação via bloco entre memória principal e cache.


<br>

<h2 align="center">Validando a Cache</h2>


Para validarmos a cache, utilizamos o [programa disponibilizado no documento do trabalho](https://github.com/natansantoz/Memoria-Cache/blob/main/arquivos/Enunciado%20ACII%20Trabalho%20I.pdf).


As memórias do Logisim armazenam as instruções em hexadecimal, por conseguinte, era necessária a conversão das instruções para tal formato.

Diante disso, criei uma pequena interface para agilizar esse processo.

Por exemplo as instruções do tipo I:

![Instrução I](https://github.com/natansantoz/Memoria-Cache/blob/main/arquivos/instrucoesI.jpg)

<br>

```c++
Disposição da quantidade de bits de cada campo:
3 3 4 6

addi $r2, $r1, $4

Campos em binário:
001 010 0001 000100

Campos em decimal:
1 2 1 4
```

<br>

![Interface](https://github.com/natansantoz/Memoria-Cache/blob/main/arquivos/interface.jpg)

Ao final do programa, os valores finais das posições da memória referentes às variáveis de soma (soma1 à soma5) são, respectivamente, 155, 155, 310, 75 e 516. 

![Somas](https://github.com/natansantoz/Memoria-Cache/blob/main/arquivos/somas.jpg)

Valores os quais estavam presentes nas respectivas posições em cada uma das nossas submemórias ao final da execução. 

![Valores Nas Memorias](https://github.com/natansantoz/Memoria-Cache/blob/main/arquivos/valores_nas_memorias.png)

Dessa forma, foi possível validar a corretude da cache.

<br>

<h2 align="center">Referências</h2>

**PATTERSON**, David, HENNESSY, John .Organização e Projeto de Computadores: Interface
Hardware/Software. 4° Edição. Rio de Janeiro, Editora Elsevier, 2014.

**STALLINGS**, William. Arquitetura e Organização de Computadores. 10ª Edição. São Paulo:
Pearson Pratice Hall, 2010.