# BEM VINDO AO MEU INCRIVEL REPOSITORIO EM QUE EU VOU FAZER VARIOS TUTORIAIS PRO MEU AMIGO QUERIDO ALEX

---

## Qual o meu objetivo em fazer isso aqui?
A real é que fazendo meus tutoriais pra você no github eu literalmente já te ajudo em duas coisas IMPORTANTISSIMAS.
1 - Vou te ajudar com os códigos e etc
2 - vou te ajudar a entender como funciona e mexe no github, **ainda mais depois da humilhação do ronildo hoje**

---

## Mas como o grandissimo amigo arthur pretende fazer isso?
Acho que primeiramente vou deixar esse readme gigante aqui pra vc só entender como funciona o código de javascript que você pediu mesmo, e mais pra frente, quando você precisar de mais tutoriais e mais ajudas nessa área eu posso ir transformando isso em algo cada vez maior
Ai fica bom tanto pra você sempre voltar e sempre ter tutoriais aqui, como também um acervo pessoal meu, então é basicamente jogo ganho pra nós dois

---

# Código do JavaScript

## Parte do bloco dos cursos
Primeiramente, o que precisamos entender é a nossa `div` que contem os cursos que vamos clicar pra aparecer a mensagem
```
<div class="curso-item">
  <div class="curso-box">
    <img src="imagens/log.png" alt="Logística">
  </div>
  <p class="curso-nome">Logística</p>
</div>
```
O que temos aqui de importante é o parágrafo `<p>` que coloca o nome do curso em baixo da imagem, CAAASO você tenha prestado bem atenção, você pode perceber que a classe que a gente colocou nesse parágrafo foi "curso-nome", e presta atenção nisso porque isso vai ser BEEEEM importante mais pra frente

---

## Parte do código em si do javascript

O mais importante que você precisa saber é, o código de javascript sempre vai estar dentro de um comando `<script>`, e ele tem que estar sempre no FINAL do body, mas ainda dentro do body, por exemplo:

```
<!DOCTYPE html>
<html lang="pt-br">
<head>
  <title>Cursos Modulares</title>
</head>

<body>

  <h1>Gosto muito do ronildo </h1>

  <p>Mas gosto mais da cristiane!</p>

  <!--Ta vendo? o script ta exatamente antes do final do body no meu site exemplo-->
  <script> 
    bla bla bla bla script legal aqui
  </script>

</body>
</html>
```

---

Agora, o que precisamos fazer é **entender** o meu código de JavaScript pra mostrar a mensagem dos cursos
```
<script>
        const cursosInfo = {
            "Administração": "curso do povo chato que rouba nosso banco na entrada",
            "Saneamento": "curso que nem existe mais sinceramente ent ngm liga",
            "Agrimensura": "curso inutl pra vc aprender a medir solo fds."
        };

        const itens = document.querySelectorAll(".curso-item");
        const area = document.getElementById("area-descricao");
        const titulo = document.getElementById("titulo-curso");
        const texto = document.getElementById("texto-curso");

        itens.forEach(item => {
            item.addEventListener("click", () => {
                const nomeCurso = item.querySelector(".curso-nome").innerText;

                titulo.innerText = nomeCurso;
                texto.innerText = cursosInfo[nomeCurso];

                area.style.display = "block";
            });
        });
</script>
```
Na primeira linha do Script, podemos perceber o código `Const cursosInfo = {` e logo depois a lista dos cursos que tem no meu site, vamos imaginar um cenário hipotético em que o meu site tem apenas os três cursos, Adm, Saneamento e Agrimensura, o que eu faria primeiramente é criar a div dos cursos e colocar dentro do parágrafo com a classe `<p class="curso-nome">` o nome EXATO do curso, por exemplo:
```
<div class="curso-item">
  <div class="curso-box">
    <img src="imagens/adm.png" alt="Administração">
  </div>
  <p class="curso-nome">Administração</p>
</div>
```

Agora, vamos entender o que a segunda parte do código do javascript faz, essa parte aqui ó:
```
const itens = document.querySelectorAll(".curso-item");
        const area = document.getElementById("area-descricao");
        const titulo = document.getElementById("titulo-curso");
        const texto = document.getElementById("texto-curso");
```

Basicamente o que ela vai fazer é que ela vai **pegar** os atributos do curso que você colocou laaa no html dentro da `<div>` dos cursos e jogar ele pra dentro do nosso scriptiznho aqui.

Proxima parte do código, essa daqui:
```
itens.forEach(item => {
```
Esse código aqui basicamente faz que pra cada curso da página...
```
item.addEventListener("click", () => {
```
Vai acontecer algo quando você clicar nele

Agora, a parte mais importante do código, essa linha aqui ó
```
const nomeCurso = item.querySelector(".curso-nome").innerText;
```
ela vai pegar ESPECIFICADAMENTE o nome do curso que a gente colocou, pra então, com esse código aqui...
```
titulo.innerText = nomeCurso;
texto.innerText = cursosInfo[nomeCurso];
```
... ele alterar o texto para o CursosInfo (que caso você não se lembre, é a constante que a gente colocou as descrições dos cursos lá em cima)

---

Agora, a parte da caixa em si que vai mostrar a mensagem
```
area.style.display = "block";
``` 
Esse código aqui basicamente fazer a caixa aparecer, porque o CSS da caixa está com o `display: none;`, ou seja, desligado, sumido, desaparecido JUUUUSTAMENTE pra caixa não aparecer enquanto você não clicar em nenhum curso, porque pensa bem, imagina só vc abre o site e ja tem logo uma caixa explicando sobre um curso que você nem clicou?

---
## Ta bom, mas e o html da caixa?
Taaa aqui meu amorzinho
```
<div id="area-descricao" class="area-descricao">
  <h2 id="titulo-curso"></h2>
  <p id="texto-curso"></p>
</div>
```

E agora o css dele:
```
.area-descricao {
    display: none; /*Faz ele ficar invisivel até ser clicado*/
    width: 80%; /*Tamanho dele*/
    margin: 20px auto 40px auto; /*Margem*/
    padding: 30px; /*É basicamente um outro tipo de "margem"*/
    background-color: #B20000; /*Cor de fundo*/
    color: #f8f8f8; /*Cor do texto*/
    border-radius: 30px; /*Caixa em formato mais arredondado nos cantos*/
    box-shadow: 0px 4px 20px 0px rgba(0,0,0,0.25); /*Sombra na caixa*/
}
```
---
Alguma dúvida, mandar msg no meu whatsapp e reze pra que eu saiba responder :p


