# expressoes-regulares

## Comandos para buscar digitos
Busca para encontrar cnpj 15.123.321/8883-22:  
\d{2}.\d{3}.\d{3}/\d{4}-\d{2}  
Buscar um IP 126.1.112.34:  
\d{1,3}.\d{1,3}.\d{1,3}.\d{1,3}  
Buscar somente o CEP em João Fulano,123.456.789-00,21 de Maio de 1993,(21) 3079-9987,Rua do Ouvidor,50,20040-030,Rio de Janeiro:  
\d{5}-\d{3}  
Buscar número de telefone :  
Como o "()" também está sendo procurado ele precisa estar entre barras "\(\)" \(\d{2}\) \d{4}-\d{4}  
