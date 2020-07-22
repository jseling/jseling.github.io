# Arquivo PDF: Estudo do formato

## Criação de um Hello World mínimo

Esta é uma adaptação da série de artigos [IDR Make your own PDF file](https://blog.idrsolutions.com/2010/09/grow-your-own-pdf-file-part-1-pdf-objects-and-data-types/) que ensina a criar um arquivo PDF funcional mínimo com o texto "Hello World" usando apenas um editor de texto e um editor de hexadecimal.

### 1 - Objetos e tipos de dados

Um arquivo PDF a principio **é um arquivo de texto** que descreve um conjunto de **objetos conectados entre si hierarquicamente** que representam páginas, fontes, imagens, etc.

Cada objeto deve ser de um dos oito tipos de dados que um leitor de PDF pode entender:

- [Strings](https://www.adobe.com/content/dam/acom/en/devnet/pdf/pdf_reference_archive/pdf_reference_1-7.pdf#page=53);
- [Arrays](https://www.adobe.com/content/dam/acom/en/devnet/pdf/pdf_reference_archive/pdf_reference_1-7.pdf#page=58);
- [Números](https://www.adobe.com/content/dam/acom/en/devnet/pdf/pdf_reference_archive/pdf_reference_1-7.pdf#page=52) (inteiros e reais);
- [Booleanos](https://www.adobe.com/content/dam/acom/en/devnet/pdf/pdf_reference_archive/pdf_reference_1-7.pdf#page=52) (verdadeiro/falso);
- [Objetos nomeados](https://www.adobe.com/content/dam/acom/en/devnet/pdf/pdf_reference_archive/pdf_reference_1-7.pdf#page=56) (veremos a seguir);
- [Arrays associativos](https://www.adobe.com/content/dam/acom/en/devnet/pdf/pdf_reference_archive/pdf_reference_1-7.pdf#page=59) (chamados de *dictionaries*);
- [Streams](https://www.adobe.com/content/dam/acom/en/devnet/pdf/pdf_reference_archive/pdf_reference_1-7.pdf#page=60) (que consiste em um dicionário e uma carga de dados binários);
- [Objeto nulo](https://www.adobe.com/content/dam/acom/en/devnet/pdf/pdf_reference_archive/pdf_reference_1-7.pdf#page=63).

Se você abrir um PDF no bloco de notas verá vários objetos, aqui um exemplo:

```
41 0 obj<</Type/Pages/Kids[34 0 R 43 0 R 52 0 R]/Count 3>>
endobj
```

Este é um objeto identificado como **41**. Esse primeiro número é o *nome/identificação dele*.

O segundo número, o **0** é o *número da revisão*. Funciona como um versionamento do objeto, mas não é muito usado, na maioria das vezes será sempre 0.

O **obj** diz que é um *objeto*, e se você seguir o texto encontrará um **endobj** que define o *fim desse objeto*. Tudo que está dentro disso, é parte dele.

Os **chevrons << >>** indicam que o objeto 41 é do tipo *Dictionary*. Um dicionário é um tipo de dado frequente em arquivos PDF, eles possuem uma lista de pares chave-valor descrevendo algum aspecto do documento. O valor pode ser de qualquer a um dos 8 tipos de dados, incluindo outro dicionário.


### Referências
- [IDR: Learning about PDF](https://blog.idrsolutions.com/2009/08/learning-about-pdf/)
- [IDR: Make your own PDF file](https://blog.idrsolutions.com/2010/09/grow-your-own-pdf-file-part-1-pdf-objects-and-data-types/)
- [Skia: PDF Theory of Operation](https://skia.org/dev/design/pdftheory)
- [An example of a simple PDF file structure](https://www.researchgate.net/figure/An-example-of-a-simple-PDF-file-structure-that-consists-of-one-page-that-contains-a_fig1_326102942)
