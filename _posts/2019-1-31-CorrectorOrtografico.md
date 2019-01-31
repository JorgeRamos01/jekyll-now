---
layout: post
title: Construyendo un corrector ortográfico!
---
En este post voy a mostrar como crear un corrector ortográfico para textos en español, aunque el concepto puede aplicarse de manera general a casi cualquier otro idioma.

El concepto es muy simple y esta basado en el uso de probabilidades bayesianas. Debido a esto último, debemos indicar una probabilidad *a priori* de que la palabra elegida por nuestro modelo es la correcta o que tan correcta parece. El modelo básico que se utilizara para la generación del corrector es el siguiente

$$ s = arg \max\limits_{s} P (s|w) = arg \max\limits_{s} P (w|s)P (s) $$


donde, $$P(s)$$ es el modelo del lenguaje, y representa la probabilidad de que la palabra s sea la que se intentó escribir. 
La probabilidad $$P(w|s)$$ representa el modelo de error o canal ruidoso, e indica la probabilidad de que, por alguna razón, se escribió la palabra w en lugar de la “correcta” s.
