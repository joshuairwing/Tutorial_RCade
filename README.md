# Tutorial_RCade  

Este tutorial serve para ensinar a usar o pacote `RCade`    
Esse pacote permite rodar jogos em HTML dentro do RStudio.

Instalação
----------  

Esse pacote não está disponível no CRAN e segundo o autor nunca estará.  
Para usá-lo, é necessário baixar direto do github:

```r
# install.packages("devtools")
devtools::install_github('RLesur/Rcade')
```

Utilização
---------

Ver jogos disponíveis
---------------------

```r
Rcade::games
```

Jogar algo
----------

Ao rodar alguma coisa pela primeira vez, você precisará instalar o jogo. O processo é bem rápido.  

>Usando o código `Rcade::games` podemos ver os jogos instalados.

Para jogar algo, usamos este código:

```r
Rcade::games$`jogo`
```

Alguns exemplos: 

``` r
Rcade::games$`Pacman`
```

``` r
Rcade::games$`Mariohtml5`
```

### Adicionar novo jogo

O Rcade já vem com vários jogos, mas também existem vários outros disponíveis no github.  

Como exemplo, o autor desse pacote usou esse repositório: https://github.com/Zolmeister/pond  

Para adicionar esse jogo, este é o código:  

``` r
Pond <- Rcade:::HTML5Game$new(name = "pond", 
                              github = "Zolmeister/pond", 
                              need_servr = FALSE, 
                              path = "index.html")
```

E aqui um outro exemplo:

```r
SpaceInvaders <- Rcade:::HTML5Game$new(name = "SpaceInvaders", 
                              github = "StrykerKKD/SpaceInvaders", 
                              need_servr = FALSE, 
                              path = "index.html")
```

E para jogar, este é o código:

```r
Pond
```

ou 

```r
SpaceInvaders
```

Caso tenha qualquer problema ao jogar algo, o autor recomenda tentar jogar com servidor HTTP:

``` r
Pond$play(TRUE)
```

### Créditos

Este é um pacote de [RLesur](https://github.com/RLesur).  

Equipe do trabalho:  
- Irwing Joshua
- Lucas Henrique
- Willian Santos
