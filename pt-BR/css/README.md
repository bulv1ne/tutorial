# CSS - deixe as coisas bonitas!

Nosso blog ainda parece feio, certo? Está na hora de deixar ele melhor! Para isso, nós usaremos o CSS.

## O que é CSS?

Cascading Style Sheets (CSS - Folhas de Estilo em Cascata, em português) é uma linguagem utilizada para descrever o visual e a formatação de um website escrito numa linguagem de marcação (como HTML). Veja ela como uma maquiagem para a nossa página web. :)

Mas nós não queremos começar do zero de novo, certo? Mais uma vez, usaremos algo que outros programadores lançaram na Internet de graça. Você sabe, reinventar a roda não é divertido.

## Vamos usar o Bootstrap!

Bootstrap é um dos frameworks HTML e CSS mais populares para desenvolver belos websites: https://getbootstrap.com/

Foi escrito por programadores que trabalharam no Twitter. Agora é desenvolvido por voluntários de todo o mundo!

## Instalar Bootstrap

Para instalar o Bootstrap, você precisa adicionar isso `<head>` no seu arquivo `.html`:

{% filename %}blog/templates/blog/post_list.html{% endfilename %}

```html
<link rel="stylesheet" href="//maxcdn.bootstrapcdn.com/bootstrap/3.2.0/css/bootstrap.min.css">
<link rel="stylesheet" href="//maxcdn.bootstrapcdn.com/bootstrap/3.2.0/css/bootstrap-theme.min.css">
```

Isso não adiciona nenhum arquivo ao seu projeto. Isso apenas aponta para arquivos que existem na Internet. Vá em frente, abra seu website e atualize a página. Aqui está!

![Figura 14.1](images/bootstrap1.png)

Já está parecendo melhor!

## Arquivos estáticos no Django

Finalmente, vamos dar uma olhada mais de perto nessas coisas que chamamos de **arquivos estáticos**. Arquivos estáticos são todos seu CSS e imagens. Seu conteúdo não depende do contexto de requisição e será o mesmo para todo usuário.

### Onde colocar os arquivos estáticos para o Django

Django, já sabe onde encontrar os arquivos estáticos para o app pré-instalado "admin". Agora só precisamos adicionar alguns arquivos estáticos para nosso próprio app, `blog`.

Fazemos isso através da criação de uma pasta chamada `static` dentro da aplicação blog:

    djangogirls
    ├── blog
    │   ├── migrations
    │   ├── static
    │   └── templates
    └── mysite
    

O Django vai automaticamente encontrar quaisquer pastas chamadas "static" dentro de quaisquer pastas dos seus apps. Então ele será capaz de usar seu conteúdo como arquivos estáticos.

## Seu primeiro arquivo CSS!

Vamos criar um arquivo CSS agora, para adicionar seu próprio estilo à sua página web. Crie um novo diretório chamado `css` dentro de seu diretório `static`. Em seguida, crie um novo arquivo chamado `blog.css` dentro do diretório `css`. Pronto(a)?

    djangogirls
    └─── blog
         └─── static
              └─── css
                   └─── blog.css
    

Hora de escrever algum CSS! Abra o arquivo `blog/static/css/blog.css` no seu editor de código.

Não vamos aprofundar muito a personalização e aprendizagem sobre CSS aqui. Existe no final desta página uma recomendação para um curso gratuito de CSS, caso pretendas aprender mais.

Mas vamos fazer pelo menos um pouco. Talvez possamos mudar a cor do nosso cabeçalho? Para entender as cores, os computadores usam códigos especiais. Esses códigos começam com `#` e são seguidos de 6 letras (A-F) e números (0-9). Por exemplo, o código para o azul é `#0000FF`. Você pode encontrar os códigos de diversas cores aqui: http://www.colorpicker.com/. Você pode também usar [cores predefinidas](http://www.w3schools.com/colors/colors_names.asp), como `red` e `green`.

Em seu arquivo `blog/static/css/blog.css` você deve adicionar o seguinte código:

{% filename %}blog/static/css/blog.css{% endfilename %}

```css
h1 a {
    color: #FCA205;
}
```

`h1 a` é um seletor CSS. Isto significa que estamos aplicando nossos estilos para qualquer elemento `a` dentro de um elemento `h1`. Então quando tivermos algo como um `<h1><a href="">link</a></h1>`, o estilo `h1 a` será aplicado. Neste caso, nós estamos dizendo para mudar a cor para `#FCA205`, que é laranja. Mas é claro que você pode colocar a cor que você quiser aqui!

Em um arquivo CSS nós determinamos estilos para elementos do arquivo HTML. A primeira maneira de identificar elementos é com o nome do elemento. Você pode se lembrar destes como as etiquetas da seção HTML. Coisas como `a` `h1` e `body` são exemplos de nomes de elementos. Também identificamos elementos pelo atributo `class` ou o atributo `id`. Class e id são nomes que você mesmo dá ao elemento. Classes definem grupos de elementos, e ids apontam para elementos específicos. Por exemplo, a tag a seguir pode ser identificada usando a tag de nome `a`, a classe `external_link` ou o id de `link_to_wiki_page`:

```html
<a href="https://en.wikipedia.org/wiki/Django" class="external_link" id="link_to_wiki_page">
```

Você pode ler mais sobre [Seletores CSS no w3schools](http://www.w3schools.com/cssref/css_selectors.asp).

Nós também precisamos dizer ao nosso template HTML que adicionamos algum CSS. Abra o arquivo `blog/templates/blog/post_list.html` e adicione esta linha bem no começo dele:

{% filename %}blog/templates/blog/post_list.html{% endfilename %}

```html
{% load staticfiles %}
```

Estamos apenas carregando arquivos estáticos aqui. :) Entre as tags `<head>` e `</head>`, depois dos links para os arquivos CSS do Bootstrap, adicione esta linha:

{% filename %}blog/templates/blog/post_list.html{% endfilename %}

```html
<link rel="stylesheet" href="{% static 'css/blog.css' %}">
```

O navegador lê os arquivos na ordem em que são dados, então precisamos ter certeza de que isso está no lugar certo. Do contrário, o código no nosso arquivo pode ser sobrescrito pelo código dos arquivos do Bootstrap. Acabamos de dizer ao nosso template onde se encontra nosso arquivo CSS.

Agora, seu arquivo deve estar assim:

{% filename %}blog/templates/blog/post_list.html{% endfilename %}

```html
{% load staticfiles %}
<html>
    <head>
        <title>Django Girls blog</title>
        <link rel="stylesheet" href="//maxcdn.bootstrapcdn.com/bootstrap/3.2.0/css/bootstrap.min.css">
        <link rel="stylesheet" href="//maxcdn.bootstrapcdn.com/bootstrap/3.2.0/css/bootstrap-theme.min.css">
        <link rel="stylesheet" href="{% static 'css/blog.css' %}">
    </head>
    <body>
        <div>
            <h1><a href="/">Django Girls Blog</a></h1>
        </div>

        {% for post in posts %}
            <div>
                <p>published: {{ post.published_date }}</p>
                <h1><a href="">{{ post.title }}</a></h1>
                <p>{{ post.text|linebreaksbr }}</p>
            </div>
        {% endfor %}
    </body>
</html>
```

OK, salve o arquivo e atualize o site!

![Figura 14.2](images/color2.png)

Bom trabalho! Talvez a gente também queira dar um pouco de ar ao nosso site e aumentar a margem do lado esquerdo? Vamos tentar!

{% filename %}blog/static/css/blog.css{% endfilename %}

```css
body {
    padding-left: 15px;
}
```

Adicione isto ao seu CSS, salve o arquivo e veja como funciona!

![Figura 14.3](images/margin2.png)

Talvez a gente possa customizar a fonte no nosso cabeçalho? Cole na seção `<head>` do arquivo `blog/templates/blog/post_list.html` o seguinte:

{% filename %}blog/templates/blog/post_list.html{% endfilename %}

```html
<link href="//fonts.googleapis.com/css?family=Lobster&subset=latin,latin-ext" rel="stylesheet" type="text/css">
```

Assim como antes, cheque a ordem e coloque antes do do link para `blog/static/css/blog.css`. Esta linha importará do Google Fonts (https://www.google.com/fonts) uma fonte chamada *Lobster*.

Encontre o bloco de declaração `h1 a` (o código entre chaves `{` e `}`) no arquivo CSS `blog/static/css/blog.css`. Agora adicione a linha `font-family: 'Lobster';` entre as chaves e atualize a página:

{% filename %}blog/static/css/blog.css{% endfilename %}

```css
h1 a {
    color: #FCA205;
    font-family: 'Lobster';
}
```

![Figura 14.3](images/font.png)

Incrível!

Como mencionado acima, o CSS tem um conceito de classes. Estas permitem que você nomeie uma parte do código HTML e aplique estilos apenas a esta parte, sem afetar outras partes. Isto pode ser super útil! Talvez você tenha duas divs que estão fazendo algo diferente (como o seu cabeçalho e seu post). Uma classe pode ajudá-lo a fazê-los parecer diferentes.

Vá em frente e o nomeie algumas partes do código HTML. Adicione uma classe chamada `page-header` para o `div` que contém o cabeçalho, assim:

{% filename %}blog/templates/blog/post_list.html{% endfilename %}

```html
<div class="page-header">
    <h1><a href="/">Django Girls Blog</a></h1>
</div>
```

E agora, adicione uma classe `post` em sua `div` que contém um post de blog.

{% filename %}blog/templates/blog/post_list.html{% endfilename %}

```html
<div class="post">
    <p>publicado: {{ post.published_date }}</p>
    <h1><a href="">{{ post.title }}</a></h1>
    <p>{{ post.text|linebreaksbr }}</p>
</div>
```

Agora adicionaremos blocos de declaração a seletores diferentes. Seletores começando com `.` se referem às classes. Existem vários tutoriais e explicações excelentes sobre CSS na Web que podem te ajudar a entender melhor o código a seguir. Por enquanto, basta copiar e colá-lo em seu arquivo `blog/static/css/blog.css`:

{% filename %}blog/static/css/blog.css{% endfilename %}

```css
.page-header {
    background-color: #ff9400;
    margin-top: 0;
    padding: 20px 20px 20px 40px;
}

.page-header h1, .page-header h1 a, .page-header h1 a:visited, .page-header h1 a:active {
    color: #ffffff;
    font-size: 36pt;
    text-decoration: none;
}

.content {
    margin-left: 40px;
}

h1, h2, h3, h4 {
    font-family: 'Lobster', cursive;
}

.date {
    color: #828282;
}

.save {
    float: right;
}

.post-form textarea, .post-form input {
    width: 100%;
}

.top-menu, .top-menu:hover, .top-menu:visited {
    color: #ffffff;
    float: right;
    font-size: 26pt;
    margin-right: 20px;
}

.post {
    margin-bottom: 70px;
}

.post h1 a, .post h1 a:visited {
    color: #000000;
}
```

Então envolva o código HTML que exibe os posts com declarações de classes. Substitua isto:

{% filename %}blog/templates/blog/post_list.html{% endfilename %}

```html
{% for post in posts %}
    <div class="post">
        <p>publicado: {{ post.published_date }}</p>
        <h1><a href="">{{ post.title }}</a></h1>
        <p>{{ post.text|linebreaksbr }}</p>
    </div>
{% endfor %}
```

no arquivo `blog/templates/blog/post_list.html` por isto:

{% filename %}blog/templates/blog/post_list.html{% endfilename %}

```html
<div class="content container">
    <div class="row">
        <div class="col-md-8">
            {% for post in posts %}
                <div class="post">
                    <div class="date">
                        <p>published: {{ post.published_date }}</p>
                    </div>
                    <h1><a href="">{{ post.title }}</a></h1>
                    <p>{{ post.text|linebreaksbr }}</p>
                </div>
            {% endfor %}
        </div>
    </div>
</div>
```

Salve esses arquivos e atualize seu site.

![Figura 14.4](images/final.png)

Uhuul! Parece incrível, certo? Olhe para o código que acabamos de colar para encontrar os locais onde adicionamos classes no HTML e as usamos no CSS. Onde você faria a mudança se você quisesse a data na cor turquesa?

Não tenha medo de mexer um pouco com esse CSS e tentar mudar algumas coisas. Brincar com o CSS pode ajudá-lo a entender o que diferentes coisas estão fazendo. Se você quebrar algo, não se preocuoe - você sempre pode desfazê-lo!

Nós realmente recomendamos realizar este curso gratuito on-line: [Curso de HTML & CSS do Codeacademy](https://www.codecademy.com/tracks/web). Isso pode ajudá-la a aprender tudo sobre como fazer seus sites mais bonito com CSS.

Pronta para o próximo capítulo?! :)