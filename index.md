---
title       : 'Pruebas de Hipóstesis e Inferencia'
subtitle    : 'Diseño de Experimentos'
author      : 'Carlos Neftaly Lozano A.'
logo     : EM.png
job         : 'Microbiólogo Industrial y Ambiental, Msc'
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : [mathjax]            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Una mirada NO estadística...

<img src="./figure/corte.jpg" title="plot of chunk unnamed-chunk-1" alt="plot of chunk unnamed-chunk-1" style="display: block; margin: auto;" />


En un juicio el jurado debe decidir entre dos hipótesis. La _hipótesis nula_ es: 


$$ H_0: \text{El acusado es  inocente} $$

_La hipótesis alternativa o del investigador es:_ 

$$H_a: \text{El acusado es culpable}$$

> El jurado _no sabe_ cual de las dos hipótesis es cierta. El debe tomar la decisión con base a la _evidencia_ presentada. 

--- .class #id 

## Una mirada NO estadística...

<span style="display:block; height: 2cm;"></span>

<img src="./figure/Inferencia.png" title="plot of chunk unnamed-chunk-2" alt="plot of chunk unnamed-chunk-2" style="display: block; margin: auto;" />

--- .class #id 

## Una mirada NO estadística...

A partir del veredicto del jurado se pueden presentar dos _tipos de errores_: 

> 1. El jurado condena a una persona inocente.
    + Es denominado _Error Tipo I_ y ocurre cuando rechazamos una hipótesis nula      verdadera. 
 

> 2. El jurado declara inocente a una persona culpable.
    + Es denominado _Error Tipo II_ y ocurre cuando no rechazamos una hipótesis nula      falsa.  

<img src="./figure/error.jpg" title="plot of chunk unnamed-chunk-3" alt="plot of chunk unnamed-chunk-3" style="display: block; margin: auto;" />

---

## Una mirada NO estadística: Conceptos claves

Bajo este panorama los conceptos críticos a tener en cuenta son:
>1. Hay dos hipótesis, $H_0$ y $H_a$.
>2. El desarollo de la inferencia asume de partida que la hipótesis nula ($H_0$) es verdadera. 
>3. El objetivo es determinar _si hay suficiente evidencia_ para inferir que la hipótesis alternativa es cierta o  que la nula es poca probable para ser verdadera. 
>4. Hay dos posibles decisiones: 
 + Rechazar la hipótesis nula
 + No hay suficiente evidencia para soportar $H_a$

---

## Conceptos en Pruebas de hipótesis

<img src="./figure/Muestra.jpg" title="plot of chunk unnamed-chunk-4" alt="plot of chunk unnamed-chunk-4" style="display: block; margin: auto;" />

---

## Comparando dos grupos... 

<img src="assets/fig/unnamed-chunk-5-1.png" title="plot of chunk unnamed-chunk-5" alt="plot of chunk unnamed-chunk-5" style="display: block; margin: auto;" />

--- 

## Comparando dos grupos...

<span style="display:block; height: 2cm;"></span>
$$ H_0: Promedio_{Pseudomonas} =  Promedio_{Serratia}$$
<img src="./figure/travolta.gif" title="plot of chunk unnamed-chunk-6" alt="plot of chunk unnamed-chunk-6" style="display: block; margin: auto;" />

---



## Comparando dos grupos...

<span style="display:block; height: 2cm;"></span>
$$ H_a: Promedio_{Pseudomonas} \neq  Promedio_{Serratia}$$

<img src="./figure/banana.gif" title="plot of chunk unnamed-chunk-7" alt="plot of chunk unnamed-chunk-7" style="display: block; margin: auto;" />

---

## Comparando dos grupos...

<span style="display:block; height: 5cm;"></span>


$$ t = \frac{ \bar{X_1} - \bar{X_2} }{S_{ \bar{X_1} -  \bar{X_2} }  } $$




---

## Comparando dos grupos...
<span style="display:block; height: 2cm;"></span>
<img src="./figure/tplot.png" title="plot of chunk unnamed-chunk-8" alt="plot of chunk unnamed-chunk-8" style="display: block; margin: auto;" />

---

## Reglas de decisión
<span style="display:block; height: 3cm;"></span>

>1. Intervalos de confianza
<span style="display:block; height: 2cm;"></span>
>2. Valores P 

---

## Interpretando el Valor P 

<span style="display:block; height: 2cm;"></span>

<img src="./figure/pvalue.png" title="plot of chunk unnamed-chunk-9" alt="plot of chunk unnamed-chunk-9" style="display: block; margin: auto;" />

--- 

## Salida Prueba _t_

```r
wdata = data.frame(
   Cepa = factor(rep(c("Pseudomonas sp.", "Serratia sp."), each=200)),
   Deg = c(rnorm(200, 52), rnorm(200, 58)))
t.test(Deg~Cepa, var.equal = T,data=wdata)
```

```
## 
## 	Two Sample t-test
## 
## data:  Deg by Cepa
## t = -62.385, df = 398, p-value < 2.2e-16
## alternative hypothesis: true difference in means is not equal to 0
## 95 percent confidence interval:
##  -6.241368 -5.860015
## sample estimates:
## mean in group Pseudomonas sp.    mean in group Serratia sp. 
##                      51.99143                      58.04212
```

