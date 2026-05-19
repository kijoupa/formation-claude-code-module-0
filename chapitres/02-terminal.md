# Chapitre 0.2 — Le terminal apprivoisé

> **Durée :** 30 à 45 minutes
> **Objectif :** Être à l'aise avec 7 commandes essentielles, pas plus.

## La bonne nouvelle

Tu vas voir, le terminal n'est pas si terrible. Pour 95% de ce que tu auras besoin de faire dans cette formation, **7 commandes suffisent**. On va les voir une par une, avec des exercices.

## L'image mentale à avoir

Ton terminal est ouvert sur un **dossier précis** de ton ordinateur (on dit "répertoire courant" en jargon). Toutes les commandes que tu tapes s'exécutent depuis ce dossier. C'est comme si tu avais ouvert une fenêtre du Finder (Mac) ou de l'Explorateur (Windows), sauf qu'au lieu de cliquer, tu tapes.

> 💡 **Astuce mentale** : pense au terminal comme à une discussion avec ton ordinateur, où chaque ligne est une instruction. Si tu te trompes, il te le dit. Si tu réussis, soit il fait l'action en silence, soit il te répond.

## Les 7 commandes vitales

### 1. `pwd` — "Où suis-je ?"

`pwd` veut dire **Print Working Directory**. Cette commande affiche le dossier dans lequel tu te trouves actuellement.

```bash
pwd
```

Résultat possible sur Mac/Linux :
```
/Users/alex
```

Sur Windows PowerShell :
```
C:\Users\Alex
```

Tu es dans ton "dossier personnel" (ton "home"), aussi écrit `~`.

### 2. `ls` — "Qu'est-ce qu'il y a ici ?"

`ls` veut dire **list**. Cette commande affiche tous les fichiers et dossiers du répertoire courant.

```bash
ls
```

Tu vas voir s'afficher la liste de ce qu'il y a dans ton dossier personnel : `Documents`, `Téléchargements`, `Bureau`, etc.

> 📝 **Note Windows** : `ls` fonctionne dans PowerShell, mais c'est en réalité un alias pour `Get-ChildItem`. Ne t'inquiète pas, ça marche pareil.

### 3. `cd` — "Aller quelque part"

`cd` veut dire **change directory**. C'est la commande que tu vas le plus utiliser.

```bash
cd Documents
```

Tu es maintenant dans le dossier `Documents`. Vérifie-le avec `pwd`.

Pour **remonter** d'un niveau (vers le dossier parent) :
```bash
cd ..
```

Pour revenir directement à ton dossier personnel :
```bash
cd ~
```

Ou simplement :
```bash
cd
```

### 4. `mkdir` — "Créer un dossier"

`mkdir` veut dire **make directory**.

```bash
mkdir mon-premier-dossier
```

Vérifie qu'il a bien été créé avec `ls`.

### 5. `touch` — "Créer un fichier vide"

```bash
touch notes.txt
```

Tu viens de créer un fichier vide nommé `notes.txt`. Vérifie avec `ls`.

> 📝 **Note Windows** : `touch` ne fonctionne pas en PowerShell par défaut. Utilise plutôt `New-Item notes.txt` ou (plus simple) installe Git Bash au chapitre 0.4 et utilise-le à la place de PowerShell.

### 6. `cat` — "Afficher le contenu d'un fichier"

`cat` (abréviation de **concatenate**) affiche le contenu d'un fichier dans le terminal.

```bash
cat notes.txt
```

Pour l'instant ton fichier est vide, donc tu ne vois rien s'afficher. C'est normal.

### 7. `rm` — "Supprimer" (⚠️ commande dangereuse)

`rm` veut dire **remove**. Attention, **il n'y a pas de corbeille** : ce qui est supprimé est supprimé.

```bash
rm notes.txt
```

Pour supprimer un dossier (et tout ce qu'il contient), il faut ajouter l'option `-r` :
```bash
rm -r mon-premier-dossier
```

> ⚠️ **DANGER ABSOLU** : ne tape **JAMAIS** `rm -rf /` ni `rm -rf *` à la racine de ton système. Ces commandes peuvent effacer tout ton ordinateur. Quand tu utilises `rm -r`, vérifie deux fois ce que tu supprimes.

## Exercice pratique validé

On va maintenant mettre tout ça en application. Suis les étapes dans l'ordre.

### Étape 1 : ouvre ton terminal

Cmd+Espace puis "Terminal" sur Mac, touche Windows puis "PowerShell" sur Windows.

### Étape 2 : vérifie où tu es

```bash
pwd
```

Tu devrais être dans ton dossier personnel.

### Étape 3 : crée la structure suivante

```bash
mkdir claude-formation
cd claude-formation
mkdir module-0
cd module-0
touch notes.txt
```

### Étape 4 : vérifie

```bash
pwd
ls
```

Tu devrais voir `notes.txt` dans la liste.

### Étape 5 : écris quelque chose dans le fichier

Pour écrire dans un fichier sans ouvrir d'éditeur, tu peux utiliser `echo` avec une redirection (le `>`) :

```bash
echo "J'ai survécu au chapitre 0.2" > notes.txt
```

### Étape 6 : lis le contenu

```bash
cat notes.txt
```

Tu devrais voir : `J'ai survécu au chapitre 0.2`

**Bravo, tu viens de faire un cycle complet : créer un dossier, naviguer dedans, créer un fichier, écrire dedans, le lire.** C'est exactement ce qu'on fait des centaines de fois par jour en développement.

## Astuces qui changent la vie

### La touche Tab pour l'autocomplétion

Quand tu tapes `cd Doc`, appuie sur **Tab**. Le terminal complète automatiquement en `Documents/`. Énorme gain de temps et zéro faute de frappe.

### Les flèches Haut/Bas

Appuie sur **Flèche haut** : tu retrouves les commandes précédentes. Très utile pour ne pas tout retaper.

### Effacer l'écran

Si ton terminal est trop chargé visuellement :
```bash
clear
```

Ou en raccourci : **Ctrl+L**.

### Annuler une commande en cours

Si tu lances quelque chose et tu veux l'arrêter : **Ctrl+C**.

## Pièges classiques

| Symptôme | Cause | Solution |
|----------|-------|----------|
| `command not found` | Faute de frappe ou commande inexistante | Vérifie l'orthographe |
| `No such file or directory` | Le fichier/dossier n'est pas dans le répertoire courant | Fais `pwd` puis `ls` pour vérifier |
| `Permission denied` | Tu n'as pas les droits sur ce fichier | Ne le force pas, demande de l'aide |
| Le terminal est "figé" | Une commande est en train de tourner | Attends, ou Ctrl+C pour annuler |
| Espace dans un nom | `cd Mon Dossier` ne marche pas | Mets des guillemets : `cd "Mon Dossier"` |

## Ce que tu maîtrises maintenant

- [x] `pwd` : savoir où tu es
- [x] `ls` : voir ce qu'il y a autour
- [x] `cd` : te déplacer
- [x] `mkdir` : créer un dossier
- [x] `touch` : créer un fichier (Mac/Linux/Git Bash)
- [x] `cat` : lire un fichier
- [x] `rm` : supprimer (avec prudence)
- [x] Tab pour autocompléter, flèche haut pour rappeler

## Et après ?

Tu vas pouvoir naviguer dans n'importe quel projet sans paniquer. Direction le [chapitre 0.3 — Créer tes comptes](03-comptes.md).

---

[← Chapitre précédent](01-bienvenue.md) · [README](../README.md) · [Chapitre suivant →](03-comptes.md)
