---
title: Sobre o Site...
tags: sobre uepb calculo
##article_header:
#  type: cover
 # image:
 #   src: /screenshot.jpg
---

#### Veja como a nota é calculada, incluindo os links para os arquivos oficiais.
<!--more-->
### A motivação para o site

É de se esperar que em um universidade sempre tenha alunos que vão para a final em alguma disciplina, e durante meus anos na UEPB percebi que quando se aproximava a data das provas finais muitas pessoas ficavam se perguntando como calucular a nota necessária para ser aprovado na final, então como não tinha nenhuma forma fácil, resolvi criar esse site para auxiliar os alunos nessa tarefa (que ironia né, alunos de um campus de Exatas tendo que render a um uma forma fácil de calcular uma coisa tão simples haha)

### A UEPB

Segunda a <a href="https://auniao.pb.gov.br/servicos/arquivo-digital/doe/2009/fevereiro/diario-oficial-19-02-2009.pdf/@@download/file/Diario%20Oficial%2019-02-2009.pdf">RESOLUÇÃO/UEPB/CONSEPE/030/2008</a>, para o estudante ser considerando aprovado em uma disciplina, ele precisa obter:

* Frequência às atividades didáticas programadas igual ou superior a 75% (setenta e cinco por cento);

* Média aritmética das notas obtidas nos componentes curriculares normativamente prevista, igual ou superior a 7,0 (sete), ou ainda, aquele que não obtendo a média prevista, tenha se submetido à prova final e atinja, como resultado da média ponderada, nota igual ou superior a 5,0 (cinco), sendo atribuído peso 6,0 (seis) à média das unidades temáticas e peso 4,0 (quatro) à nota da prova final. 

### O Calculo

A partir desses dados, desenvolvi a seguinte função para calcular primeiramente o quanto você precisa tirar na final, de acordo com sua médias da duas unidades
(lógico que tinha que ter um pouco de humor envolvido haha).
```javascript
    function calc1() {
            num1 = parseFloat(document.getElementById("unidade1").value) || 0;
            num2 = parseFloat(document.getElementById("unidade2").value) || 0;
            media = ((num1 + num2) / 2)
            resultado = (12.5 - ((3 / 4) * (num1 + num2)));


        if (resultado > 10) {
            document.getElementById("P1").innerHTML = "<pp id='pp'>Cara, tu precisa tirar mais de 10 na final, acho que você ja entendeu...</pp>";
        }
        else if (media >= 7) {
            document.getElementById("P1").innerHTML = "<pp id='pp'>Cara, se tu tem uma média maior ou igual a 7, pra que tu vai fazer final?? wtf??</pp>";
        } else {
             if ((document.getElementById("pp")) === null) {
                document.getElementById("result1").innerHTML = (resultado).toFixed(2);

         } else {
             document.getElementById('pp').innerHTML = "<p1 id='P1'> você precisa tirar <span id='result1'></span> na final para ser aprovado.</p1>";
             document.getElementById("result1").innerHTML = (resultado).toFixed(2);
            }

         }

    }
```

E também essa outra função, para calcular se você passou na final (já que a maioria dos professores só avisam isso quando a nota está no sistema)
```javascript
    function calc2() {
             num1 = parseFloat(document.getElementById("unidade11").value) || 0;
             num2 = parseFloat(document.getElementById("unidade22").value) || 0;
              final1 = parseFloat(document.getElementById("final11").value) || 0;
              resultado = ((num1 + num2) * 3 + final1 * 4) / 10;

         if (resultado < 5) {
             if ((document.getElementById("F2")) === null) {
                  document.getElementById("result2").innerHTML = "<p1 id='F1'>Infelizmente, não foi dessa vez, você ficou com média final de <span id='result22'></span></p1> ";
                 document.getElementById("result22").innerHTML = (resultado).toFixed(2);
         } else {
                 document.getElementById("F2").innerHTML = "<span1 id='result2'></span1>";
                 document.getElementById("result2").innerHTML = "<p1 id='F1'>Infelizmente, não foi dessa vez, você ficou com média final de <span id='result22'></span></p1> ";
                 document.getElementById("result22").innerHTML = (resultado).toFixed(2);
         }

        } else if (resultado >= 5) {
                if ((document.getElementById("F1")) === null) {
                 document.getElementById("result2").innerHTML = "<p1 id='F2'> Parabéns, sua média final ficou <span id='result22'></span></p2>";
                 document.getElementById("result22").innerHTML = (resultado).    toFixed(2);
         } else {
               document.getElementById("F1").innerHTML = "<span1 id='result2'></span1>";
               document.getElementById("result2").innerHTML = "<p1 id='F2'> Parabéns, sua média final ficou <span id='result22'></span></p2>";
              document.getElementById("result22").innerHTML = (resultado).toFixed(2);
             }
         }

    }
```
Dessa maneira, preparei esse site para que você possa calcular com facilidade o quanto precisa tirar na prova final ou mesmo se você foi aprovado após receber a nota da final.


<!--more-->
