<h1 align="center">Cache Direta</h1>
<p align="center">
		<a href=""><img alt="Logisim" src="https://img.shields.io/badge/Platform-Logisim-blue.svg" height="20"/></a>
<a href=""><img alt="Architecture" src="https://img.shields.io/badge/Architecture-MIPS-green.svg" height="20"/></a>
</p>


Projeto desenvolvido como parte da conclusão da disciplina **Arquitetura de Computadores II**, tendo como objetivo a implementação de uma **cache com mapeamento direto** utilizando o simulador Logisim.

O sistema implementa uma cache de 8 linhas com política de escrita direta _write-through_, integrada a um processador MIPS adaptado e memória principal.

### Características da Implementação
- **Cache Direta**: 8 linhas de 4 palavras de 16 bits cada (512 bits/64 bytes total)
- **Política de Escrita**: Write-through (escrita direta)
- **Processador**: Arquitetura MIPS adaptada

Os subcircuitos criados foram omitidos visando tornar o readme conciso.

[![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/aqua.png)](#table-of-contents)


<h3 align="center">Circuito Principal </h3>

![Circuito Principal](https://github.com/natansantoz/Memoria-Cache/blob/main/arquivos/circuito_principal.jpg)


[![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/aqua.png)](#table-of-contents)


<h3 align="center">Cache Direta </h3>

![Cache Direta](https://github.com/natansantoz/Memoria-Cache/blob/main/arquivos/cache.png)

[![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/aqua.png)](#table-of-contents)


<h3 align="center">Processador </h3>

![Processador](https://github.com/natansantoz/Memoria-Cache/blob/main/arquivos/processador.jpg)

[![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/aqua.png)](#table-of-contents)


<h3 align="center">Memória Principal </h3>

![Memória Principal](https://github.com/natansantoz/Memoria-Cache/blob/main/arquivos/memoria_principal.jpg)


<br>

[![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/aqua.png)](#table-of-contents)


<h3 align="center">Processador </h3>

O processador utilizado foi desenvolvido no trabalho de conclusão da disciplina de Arquitetura I. No entanto, foram realizadas adaptações como a adição de um novo registrador no banco, alterações no tamanho dos campos das instruções do conjunto de instruções, entre outras.


<br>

[![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/aqua.png)](#table-of-contents)


<h3 align="center">Cache Direta </h3>


A cache possui 8 linhas, cada uma composta de 4 palavras de 16 bits cada. Logo, o tamanho da cache é de 512 bits ou 64 bytes.


<br>

[![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/aqua.png)](#table-of-contents)


<h3 align="center">Política de Escrita </h3>

A política de escrita adotada foi a de escrita direta (write-through). 

Nesse sentido, as operações de escrita são realizadas na memória principal e na cache, de modo que ambas sempre estão atualizadas.


<br>

[![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/aqua.png)](#table-of-contents)


<h3 align="center">Memória Principal </h3>

Tendo em vista que o componente “Memória RAM” do Logisim possui apenas um barramento de saída e que a comunicação entre a memória principal e a cache é por blocos de quatro palavras, a criação de uma memória principal que possibilitasse tal comunicação foi necessária.

À luz das características supracitadas, combinamos quatro componentes “Memória RAM” do Logisim visando permitir a comunicação via bloco entre memória principal e cache.


<br>

[![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/aqua.png)](#table-of-contents)


<h3 align="center">Validando a Cache </h3>


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

[![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/aqua.png)](#table-of-contents)

<h3 align="center">Referências</h3>

**PATTERSON**, David, HENNESSY, John .Organização e Projeto de Computadores: Interface
Hardware/Software. 4° Edição. Rio de Janeiro, Editora Elsevier, 2014.

**STALLINGS**, William. Arquitetura e Organização de Computadores. 10ª Edição. São Paulo:
Pearson Pratice Hall, 2010.
