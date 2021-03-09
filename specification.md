# Specification

## note:
trouver des squelettes (Tokio)
tableau comparatif de veille 

## Structure/Arborescence du projet:
```
src/
| --> parallel.rs
| --> remote/
        | --> server/
        | --> client/
| --> core/
		|--> parser/
		|--> job/
```

## Diagramme de classe détails :
Parallel : Classe principale, appellera le Parser afin de générer les objets Jobs, puis créera les JobManager permettant l’exécution
Parser : Parse l’entrée du programme afin de créer des objets Jobs
JobManager : Créer et ordonnance les JobExecutor, effectuera l’attribution des Jobs
JobExecutor : Objet Thread?
Job : Objets contenant les informations sur le Job qu’on va vouloir exécuter



## Choix d’implémentation :
=> Définir quelles fonctionnalités on souhaite implémenter
=> Énoncer les crates externes utilisées s’il y’en a 
=> Structure du code : Binary crates, library crates, test, benchmark
=> Choix important : Décision d’implémenter la remote execution, choix d’une librairie au lieu d’une autre pour des optimisations conséquentes

## Enjeux technique : 
=> Parler des exigences (ENF ?) ??
=> 

## Objectifs 
### Objectifs finaux de Rust Parallel :
- parsing de commande avec arguments en objets Rust (voir diagramme de classe)
- exécution de commandes externes à parallel (comme echo par exemple)
- fonctionnalités parallel
- lire l'entrée standard (utilisation d'une pipe avant parallel)
- l'argument ":::" (peut être invoqué plusieurs fois)
- simple guillemet pour interprétation de caractères spéciaux
- l'argument {} et/ou {1}, {2}.
- fonctionnalité --dry-run. 
- fonctionnalité --keep-order.
- fonctionnalité --pipe.
- multi-threader
- --jobs / -j : choisir le nombre de thread

### Objectifs secondaires : 
exécution à distance (via crates Tokio)

Diagramme de Gantt :
fixer les étapes

## Diagramme


## Grammaire (avec récursivité)
```
*S → parallel options commands separators

options → ε
          | --dry-run options
          | --keep-order options
	    | --pipe options
	    | --jobs number options
	    | --j number options
	    | --help options

commands → string arguments

arguments → ε
           | string arguments
           | 'string' arguments 

separators → ε
            | ::: input separators

input → number nextInput        
       | string nextInput

nextInput → ε
	     | input 
```