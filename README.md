# Cómo usar el Analizador Léxico IMP

La estructura que sigue este proyecto es la siguiente:  \

|-- docs/ \
|     | --  Reporte.pdf \
| \
|-- main/ \
│    |-- Main.hs (Programa principal) \
│    |-- implementación.imp (Archivo de entrada para Main) \
| \
|-- src/ \
|    |-- AFD.hs (Lógica para pasar de AFN a AFD) \
|    |-- ADFmin.hs (Lógica para pasar de AFD a AFDmin) \
│    |-- AFN.hs (Lógica para pasar de AFNepsilon a AFN) \
|    |-- AFNEp.hs (Lógica para pasar de ER a AFNepsilon) \
|    |-- ER.hs (Lógica para construir una ER) \
|    |-- Gramatica.hs (Gramatica del lenguaje IMP) \
|    |-- Lexer.hs (Construcción de las MDD's) \
|    |-- MDD.hs (Lógica para construir una MDD con AFDmin) \
| \
|-- test/ \
|    |-- Test.hs (Pruebas unitarias) \
|    \
|-- package.yaml \
|-- Proyecto01-Analizador-L-xico.cabal \
|-- README.md (Este archivo) \
|-- stack.yaml \
\

La estrategia en general de toda la lógica es hacer varias MDDs en vez de solo una grandota. 

Para poder probar el proyecto se necesita tener instalado **Stack**. Lo primero que hay que hacer es estar en la carpeta Raiz, donde se encuentra 'stack.yaml' y 
'package.yaml'.

Para inicializar todo, podemos hacer ´fuck´ 
```
stack build
```

Luego, para probar el programa
