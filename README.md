#  Projet APS - Analyse et Sémantique des Programmes

Ce projet est divisé en plusieurs parties (étapes de l'implémentation d'APS) :
- **APS0** : Noyau fonctionnel.
- **APS1** : Noyeau impératif.
- **APS1a** : Valeur ou référence.
- **APS2** : Tableaux.
- **APS3** : Fonctions procédurales.

##  Structure du projet

Chaque étape (APS0, APS1, APS1a, APS2, APS3) dispose de son propre répertoire :

```
├── APS0/
│    ├── AST_RESULTAT/
│    |   ├── ...
│    ├── EVAL_RESULTAT/
│    |   ├── ...
│    ├── Samples/
│    |   ├── ...
│    ├── TYPAGE_RESULTAT/
│    |   ├── ...
│    ├── ast.ml
│    ├── clean.sh
│    ├── compileAst.sh
│    ├── compileEval.sh
│    ├── compileTyper.sh
│    ├── eval.ml
│    ├── lexer.mll
│    ├── mainEval.ml
│    ├── mainTyper.ml
│    ├── parser.mly
│    ├── prologterm.ml
│    ├── README.md
│    └── typer.pl
├── APS1/
│    ├── ...
├── APS1a/
│    ├── ...
├── APS2/
│    ├── ...
└── APS3/
     ├── ...
```

##  Prérequis

Pour exécuter les différentes parties du projet, vous devez avoir installé :

- OCaml (ocamlc, ocamllex, ocamlyacc)
- SWI-Prolog (swipl)

Vérifiez les installations avec :

```bash
ocamlc --version
swipl --version
```

##  Compilation et Exécution

Chaque partie du projet dispose de scripts pour automatiser la compilation et l'exécution(Voir readme.md de chaque partie).

### 🔍 Exécuter l'interpréte :

1. Allez dans le répertoire souhaité (par exemple APS0) :

```bash
cd APS0
./compileAst.sh [fichier.aps]
```

- Si aucun fichier n'est fourni, tous les fichiers `.aps` du dossier `Samples/` seront traités.
- Les AST sont enregistrés dans `AST_RESULTAT/`.

###  Exécuter l'analyse du typage :

1. Allez dans le répertoire souhaité :

```bash
cd APS0
./compileTyper.sh [fichier.aps]
```

- Si aucun fichier n'est fourni, tous les fichiers `.aps` du dossier `Samples/` seront traités.
- Les résultats du typage sont enregistrés dans `TYPAGE_RESULTAT/`.

###  Exécuter l'évaluation :

1. Allez dans le répertoire souhaité :

```bash
cd APS0
./compileEval.sh [fichier.aps]
```

- Les résultats d'exécution sont enregistrés dans `EVAL_RESULTAT/`.

###  Nettoyer les fichiers générés :

Chaque partie inclut un script de nettoyage :

```bash
./clean.sh
```

##  Organisation des Résultats

- **AST_RESULTAT/** : Arbres syntaxiques abstraits (AST).
- **EVAL_RESULTAT/** : Résultats de l'évaluation des programmes.
- **TYPAGE_RESULTAT/** : Résultats du typage des programmes.

##  Exemple d'utilisation

Pour analyser et évaluer un fichier dans APS0 :

1. Placez votre fichier `.aps` dans `Samples/`.
2. Exécutez :

```bash
cd APS0
./compileTyper.sh Samples/exemple.aps
./compileEval.sh Samples/exemple.aps
```

3. Consultez les résultats dans `AST_RESULTAT/`, `EVAL_RESULTAT/` et `TYPAGE_RESULTAT/`.

##  Remarques

- Assurez-vous que les fichiers sont bien placés dans le dossier `Samples/`.
- En cas d'erreur, vérifiez l'installation d'OCaml et SWI-Prolog.

 Projet réalisé pour le cours **MU4IN503 - Analyse des Programmes et Sémantique**.
