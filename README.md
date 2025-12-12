# Cómo usar el Analizador Léxico IMP

## Puto
## Integrantes \
hhu

## Genómica Computacional (2026 - 1)
**Profesor :** Sergio Hernández López \
**Ayudante :** Rafael López Martínez \
**Ayud. Lab. :** Jazmín de Jesús Santillán Manjarrez


## Integrantes del equipo
- Caballero Rosas Santiago \
- Hernández Amaro María Fernanda \
- f

```
Filogenias/
|
| - Docs/
|   |
|   | - Evolución_molecular_de_opsinas_visuales_en_Cetacea__análisis_filogenético_de_la_transición_terrestre_acuática.pdf (Reporte de nuestro trabajo)
|   | - Exposición.pdf
|
| - Ancestors Analysis/  (Cuidado con estas, fueron todas hechas sobre el arbol de LWS)
|   |
|   | - LWS/
|   |   |
|   |   | - Ancestral-states-details.txt
|   |   | - Changes List.txt
|   |   | - LWSexons_ancestors.png
|   |   | - LWSexons_ancestors_numbers.png
|   |   | - Most Probable Sequences.txt
|   |   | - site-41-ancestral-states.txt
|   |
|   | - RH1/
|   |   |
|   |   | - Ancestral States.txt
|   |   | - Ancestral-states-details.txt
|   |   | - Changes List.txt
|   |   | - Most Probable Sequences.txt
|   |   | - RH1 Exons.mtsx
|   |   | - RH1 Exons_ancestors.png
|   |   | - RH1 Exons_ancestors_numbers.png
|   |
|   | - SWS1/
|   |   |
|   |   | - Ancestral-states-details.txt
|   |   | - Changes List.txt
|   |   | - Most Probable Sequences.txt
|   |   | - site-1-ancestral-states.txt
|   |   | - SWS1exons_ancestors.png
|   |   | - SWS1exons_ancestors_numebrs.png
|
|
| - LWS/
|   |
|   | - LWS Exon 1 amplicon/
|   |   |
|   |   | - Caption_tree.txt
|   |   | - LWS Exon 1 amplicon.meg
|   |   | - LWS Exon 1 amplicon_tree.png
|   |   | - SEQ4.txt
|   |   | - SEQ4_MODELANALYSIWS.pdf
|   |   |  
|   |   | - Sessions/
|   |   |   |
|   |   |   | - LWS Exon 1 amplicon.mdsx
|   |   |   | - LWS Exon 1 amplicon_tree.mtsx
|   |
|   | - LWS_Exons/
|   |   |
|   |   | - Caption_tree.txt
|   |   | - LWSExons_MODELANALYSIS.pdf
|   |   | - LWSExons_tree.png
|   |   | - SEQ3.meg
|   |   | - SEQ3.txt
|   |   |  
|   |   | - Sessions/
|   |   |   |
|   |   |   | - Newick Export.nwk
|   |   |   | - SEQ3.mdsx
|   |   |   | - SEQ3_tree.mtsx
|   |   |   | - TREE_Nedwick
|
|
| - RH1/
|   |
|   | - RH1 Exons/
|   |   |
|   |   | - Caption_tree.txt
|   |   | - RH1 Exons.meg
|   |   | - RH1 Exons.txt
|   |   | - RH1 Exons_MODELANALYSIS.pdf
|   |   | - RH1 Exons_tree.png
|   |   |  
|   |   | - Sessions/
|   |   |   |
|   |   |   | - RH1 Exons.mdxs
|   |   |   | - RH1 Exons_tree.mtsx
|
|
| - SWS1/
|   |
|   | - SWS1_IntronesExones/
|   |   |
|   |   | - Caption_tree.txt
|   |   | - SWS1 Introns + Exons.meg
|   |   | - SWS1 Introns + Exons_MODELANALYSIS.pdf
|   |   | - SWS1 Introns + Exons_NUCLEOTIDCOMPOSITION
|   |   | - SWS1 Introns + Exons_treeanalysissummary
|   |   | - SWS1_EXONSINTRONS_TREE.png
|   |   |  
|   |   | - Session/
|   |   |   |
|   |   |   | - SEQ1.mdxs
|   |   |   | - SWS1_EXONSINTRONS_TREE.mtsx
```

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

Para inicializar todo, podemos hacer
```
stack build
```

Luego, para probar el programa, debemos ejecutar 
```
stack run
```

Lo que el programa hará será analizar el contenido del archivo `implementacion.imp` que contiene el "código" que se analizará. Este archivo por
defecto ya tiene una implementación hecha por nosotros, pero se puede modificar como el usuario lo desee si sigue las reglas del lenguaje IMP para evitar errores
o analisis incorrectos. 

La salida del programa es la lista de todos los tokens encontrados en la implementación de entrada.

Para poder ejecutar las pruebas (Nos faltas eso), se tiene que ejecutar
```
stack test
```
