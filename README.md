# Arquivo PDF: Estudo do formato

## Criação de um Hello World mínimo

Este artigo é uma adaptação da série de artigos [IDR Make your own PDF file](https://blog.idrsolutions.com/2010/09/grow-your-own-pdf-file-part-1-pdf-objects-and-data-types/) que ensina ao leitor como criar um arquivo PDF funcional mínimo com o texto "Hello World" usando apenas um editor de texto e um editor de hexadecimal. Pode-se relacionar o formato PDF com o HTML, onde uma codificação descreve um documento visual que é interpretado e mostrado por um visualizador, seja um browser ou um leitor de PDFs.

### 1 - Objectos e tipos de dados

Um arquivo PDF a principio **é um arquivo de texto** que descreve **um conjunto de objetos conectados entre si hierarquicamente** que representam páginas, fontes, imagens, etc.

Cada objeto deve ser de um dos oito tipos de dados que um leitor de PDF pode entender:

- Strings;
- Arrays;
- Números (inteiros e reais);
- Booleanos (verdadeiro/falso);
- Objetos nomeados (veremos a seguir);
- Arrays associados (chamados de *dictionarys*);
- Streams (que consiste em um dicionário e uma carga de dados binários)
- Objeto nulo.

Se você abrir um PDF no bloco de notas verá vários objetos, aqui um exemplo:

```
41 0 obj<</Type/Pages/Kids[34 0 R 43 0 R 52 0 R]/Count 3>>
endobj
```

Este é um objeto identificado como **41**, esse primeiro número é o *nome/identificação dele*.

O segundo número, o **0** é o *número da revisão*, funciona como um versionamento do objeto, mas não é muito usado, na maioria das vezes será sempre 0.

O **obj** diz que é um *objeto*, e se você seguir o texto encontrará um **endobj** que define o *fim desse objet*o e tudo que está dentro disso, é parte dele.

Os **chevrons << >>** indicam que o objeto 41 é do tipo *Dictionary*. Um dicionário é um tipo de dado frequente em arquivos PDF, eles possuem uma lista de pares chave-valor descrevendo algum aspecto do documento. O valor pode ser de qualquer a um dos 8 tipos de dados, incluindo outro dicionário.


### Referências
- [IDR: Learning about PDF](https://blog.idrsolutions.com/2009/08/learning-about-pdf/)
- [IDR: Make your own PDF file](https://blog.idrsolutions.com/2010/09/grow-your-own-pdf-file-part-1-pdf-objects-and-data-types/)
- [Skia: PDF Theory of Operation](https://skia.org/dev/design/pdftheory)
- [An example of a simple PDF file structure](https://www.researchgate.net/figure/An-example-of-a-simple-PDF-file-structure-that-consists-of-one-page-that-contains-a_fig1_326102942)
