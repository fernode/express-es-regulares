# expressoes-regulares


## Classes  
Classes ssão funções que podemos usar para as buscas, ela poder ser já predefinas como \d que busca todos os caracteres numericos, mas também podemos utilizar nossas próprias classes utilizando o [expressão] posso escrever qualquer tipo de busca entre os colchetes.
## Quantifiers {}  
Definem a quantidade de vezes ou caracteres que algo pode aparecer na sua busca. Exemplo 1234.23.432  
Para buscar somente os 4 primeiros digitos ou qualquer sequencia de quatro números poderia fazer o seguinte: \d{4}


## Buscas numéricas
#### Busca para encontrar cnpj 15.123.321/8883-22  
\d{2}.\d{3}.\d{3}/\d{4}-\d{2}  
#### Buscar um IP 126.1.112.34  
\d{1,3}.\d{1,3}.\d{1,3}.\d{1,3}  
#### Buscar somente o CEP em João Fulano,123.456.789-00,21 de Maio de 1993,(21) 3079-9987,Rua do Ouvidor,50,20040-030,Rio de Janeiro  
\d{5}-\d{3}  
#### Buscar número de telefone  
Como o "()" também está sendo procurado ele precisa estar entre barras "\(\)" \(\d{2}\) \d{4}-\d{4}  
#### Buscar CPF sem formatação ou seja sem os pontos ou traço ex: 80812277799   
\d{3}.?\d{3}.?\d{3}-?\d{2} ou poderia ser assim também \d{3}.{0,1}\d{3}.{0,1}\d{3}-{0,1}  
#### Buscar CPF com formatação ou seja pode ter os pontos ou traço ex: 808.122.777.99  
\d{3}.?\d{3}.?\d{3}[-.]?\d{2} Sinal de interogação ? é um sinal corringa significa que algo pode ou não aparecer  
#### Buscar entre determinada faixa de caracteres utilizando classes []  
Buscar numeros de 1 a 3 e entre 6 e 10 por exemplo  
[1-36-10] quando utilizamos a RegExp utilizando colchetes estamos usando classes  
#### Buscar horários  
Uma hora com esse formato 19h32min16s posso fazer dessa forma  
\d{2}h\d{2}min\d{2}s


## Buscar strings  
Um exemplo é buscar somente o bloco de código "<code></code>" ex  
No <code>for</code>, o valor de <code>i</code> começa de zero e é incrementado a cada volta enquanto <code>i < 10</code>, portando o bloco de código do for é executado 10 vezes.  
Para fazer essa busca é só utilizar a expressão </?code>  
#### Busca placas de carro
Uma placa de carro nesse formato por exemplo SEAS-2345  
[A-Z]{3}-?\d{4} a fução de [A-Z] vai buscar todos as letras de A até Z maiúsculos na nossa busca o quantifier {} define o número de caracteres que podem aparecer o sinal corringa ? diz que pode ter ou não o caracter - na nossa busca.  
#### Filtrando notas de alunos aprovados  
Buscar nesta lista todos os alunos aprovados que tirarem notas entre 7.2 e 7.9  
9.8 - Robson, 7.1 - Teresa, 4.5 - Armênio, 6.5 - Zulu, 7.7 - Stefania, 7.8, 5.0 - Romeu, 7.2 - Pompilho, 3.1 - Reinaldo, 7.3 - Bernadete, 4.7 - Cinério  
A expressao deve ficar dessa maneira: 7.[2-9]\s+-\s[A-Z][a-z]+  
#### Nem tudo dentro de uma classe e um meta character  
dado o seguinte alvo: ?classes+poderosas*, para fazer essa busca devemos fazer dessa maneira [a-z?*+]+, todos os elementos colocados dentro da classe são considerados como string comum.Apenas os caracteres \ (barra invertida), - (hífen) e ^ (circunflexo) realmente são meta-chars dentro de uma classe.  
### Classes
Podemos definir facilmente a classe de qualquer caractere com o [A-Z].  
Conhecemos todos os quantifiers como ?, +, * e {n}.  
\s significa whitespace e é um atalho para [ \t\r\n\f].  
\w significa word char e é uma atalho para [A-Za-z0-9_].  
### Ancoras \b, \b\b, ^, $  
São basicamente um forma de encontrar um um conjunto de caracteres de uma maneira bem mais específica.  
\b\b, Pega um conjunto de caracteres específicos  
ex: aaa aaaa aaaa  
Queremos encontrar o conjunto com exatamente 3 a. Poderíamos simplesmente bucar pelos três aaa, mas isso retornaria todos os três as que existem na string que estamos buscando, não é isso o que queremos, então utilizamos as ancoras. Que sao representadas com \baaa\b nao pode ter caracteres no inicio nem no fim fora de uma palavra ja \baaa\b deve estar dentro de uma palavra.E o \B\B, diz que o caractere deve estar entre alguma coisa.  
^, Define que determinado caractere ou conjunto de caracteres deve estar no início.  
$, define que determinado caractere ou conjunto de caracteres deve estar no final.  
Ex: https://www.google.com.br/, definir que esse deve ser o tipo de URL utilizada  
^https.+\.br$