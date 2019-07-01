# Sintaxe Básica

### Tags PHP
Quando o PHP interpreta um arquivo ele procura pelas tags de abertura e fechamento, `<?php` e `?>`, que dizem ao PHP para iniciar ou parar a interpretação do código entre elas.

Se um arquivo for código PHP puro, é preferível omitir a tag de fechamento `?>` no final do arquivo. Prevenindo a existência de espaços ou linhas em branco após a tag, que podem causar efeitos indesejáveis, por que o PHP iniciará o buffer de saída quando não existir intenção do programador de enviar alguma saída neste ponto do script.

**Standard tag**
 ```php
    <?php // tag abertura
    
    echo "Olá mundo"; // Olá mundo
 ```
**Short tag**
 ```php
    <?= $hello_world ?> // Olá mundo
 ```

 **!!Aviso!!**
| Versão | Descrição |
|--------|-----------|
 | 7.0.0 | As tags ASP `<%`, `%>`, `<%=` e a script tag `<script language="php">` foram removidos do PHP.|
| 5.4.0 | A tag `<?=` sempre está disponível, independente do da configuração `short_open_tag ini`.|

### Comentários
O PHP suporta comentários no estilo 'C', 'C++' e do Unix shell (estilo Perl)

```php
    <?php

    echo 'Isto é um teste'; // Estilo de comentário de uma linha

    /* Este é um comentário de múltiplas linhas
       ainda outra linha de comentário */
    echo 'Isto é ainda outro teste';

    echo 'Um teste final'; # Comentário de uma linha no estilo shell
 ```

