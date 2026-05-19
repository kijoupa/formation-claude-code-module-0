# Chapitre 0.5 — Connecter ton ordinateur à GitHub

> **Durée :** 30 minutes
> **Objectif :** Pouvoir cloner des projets depuis GitHub et y pousser tes modifications sans devoir taper ton mot de passe à chaque fois.

## Le problème qu'on résout

Tu as un compte GitHub. Tu as Git installé sur ton ordinateur. Mais pour l'instant, les deux ne se connaissent pas. Si tu essayais maintenant de récupérer un projet privé ou d'y pousser du code, GitHub te demanderait de t'authentifier — et il refuserait ton simple mot de passe (par sécurité, GitHub n'accepte plus ça depuis 2021).

Il y a deux solutions classiques pour résoudre ça :

1. **GitHub CLI** (`gh`) — facile, recommandé pour démarrer.
2. **Clés SSH** — plus technique, mais plus universel à long terme.

**On va utiliser GitHub CLI.** C'est plus simple, et tu pourras toujours apprendre les clés SSH plus tard.

---

## Installer GitHub CLI

### macOS

Si tu as Homebrew (gestionnaire de paquets pour Mac) :

```bash
brew install gh
```

Si tu n'as pas Homebrew, va sur [cli.github.com](https://cli.github.com) et télécharge l'installeur `.pkg`.

### Windows

Avec winget (installé par défaut sur Windows récent) :

```powershell
winget install --id GitHub.cli
```

Ou télécharge l'installeur `.msi` sur [cli.github.com](https://cli.github.com).

> 📝 Après installation, **ouvre un nouveau terminal**.

### Linux

Suis les instructions officielles à [github.com/cli/cli#installation](https://github.com/cli/cli#installation). Pour Ubuntu/Debian :

```bash
sudo apt update
sudo apt install gh -y
```

### Vérifier l'installation

```bash
gh --version
```

Tu devrais voir quelque chose comme `gh version 2.x.x`.

---

## S'authentifier auprès de GitHub

Dans ton terminal :

```bash
gh auth login
```

L'outil te pose plusieurs questions. Voici comment répondre :

1. **What account do you want to log into?** → `GitHub.com`
2. **What is your preferred protocol for Git operations?** → `HTTPS` (plus simple à ce stade)
3. **Authenticate Git with your GitHub credentials?** → `Yes`
4. **How would you like to authenticate GitHub CLI?** → `Login with a web browser`

Il va t'afficher un **code à 8 caractères** (par exemple `A1B2-C3D4`) et te demander d'appuyer sur Entrée pour ouvrir ton navigateur.

Dans le navigateur :
1. Connecte-toi à ton compte GitHub si ce n'est pas fait.
2. Entre le code à 8 caractères.
3. Autorise GitHub CLI.
4. Valide avec ta 2FA.

Une fois validé dans le navigateur, retourne à ton terminal. Tu devrais voir :

```
✓ Authentication complete.
✓ Logged in as ton-username
```

### Vérifier que tout fonctionne

```bash
gh auth status
```

Tu devrais voir une confirmation que tu es bien connecté.

---

## Premier clone : récupérer le repo de la formation

C'est le moment de récupérer ce repo (celui que tu lis actuellement sur GitHub) sur ton ordinateur.

### Étape 1 : se placer dans le bon dossier

Ouvre ton terminal et place-toi dans le dossier `claude-formation` que tu as créé au chapitre 0.2 :

```bash
cd ~/claude-formation
```

Vérifie où tu es :

```bash
pwd
```

### Étape 2 : cloner le repo

> 📝 **Note** : remplace `TON-FORMATEUR/formation-claude-code-module-0` ci-dessous par l'URL exacte du repo que ton formateur t'a communiquée.

```bash
gh repo clone TON-FORMATEUR/formation-claude-code-module-0
```

Tu vois quelque chose comme :

```
Cloning into 'formation-claude-code-module-0'...
remote: Enumerating objects: ...
Receiving objects: 100% ...
```

### Étape 3 : vérifier ce que tu as récupéré

```bash
ls
```

Tu vois maintenant un dossier `formation-claude-code-module-0`. Entre dedans :

```bash
cd formation-claude-code-module-0
ls
```

Tu retrouves la structure du repo : `README.md`, `chapitres/`, `exercices/`, etc. **Tu as ton premier projet Git en local.**

### Étape 4 : explorer dans VS Code

Toujours dans le terminal, depuis le dossier du projet, tape :

```bash
code .
```

Le `.` veut dire "le dossier courant". VS Code s'ouvre avec le projet chargé. **C'est comme ça qu'on ouvre un projet 99% du temps.** Note l'astuce, tu vas la réutiliser tout le temps.

Dans VS Code, à gauche, tu vois l'arborescence du projet. Tu peux cliquer sur n'importe quel fichier pour le lire. Essaye d'ouvrir le `README.md`.

---

## Test final : faire un petit commit

On va vérifier que tout est connecté en faisant ton tout premier commit Git. Ne t'inquiète pas, on reverra Git en profondeur plus tard — pour l'instant tu fais juste un test.

### Étape 1 : créer un fichier dans le dossier exercices

Dans ton terminal, depuis le dossier `formation-claude-code-module-0` :

```bash
mkdir -p exercices/chapitre-05
echo "Test de mon premier commit" > exercices/chapitre-05/test.txt
```

### Étape 2 : voir l'état de Git

```bash
git status
```

Git te dit qu'il a détecté un nouveau fichier non suivi (`Untracked files`). Normal.

### Étape 3 : ajouter le fichier

```bash
git add exercices/chapitre-05/test.txt
```

### Étape 4 : faire le commit

```bash
git commit -m "Mon premier commit dans cette formation"
```

Tu vois apparaître un message de confirmation avec un identifiant de commit (du genre `[main 3f2a1b9]`).

**Bravo, tu viens de faire ton premier commit Git.** 🎉

> 📝 **Note** : on ne va pas **pousser** ce commit sur GitHub (parce que tu n'as pas les droits d'écriture sur le repo du formateur). C'est normal. Au chapitre 0.7 tu créeras ton propre repo où tu pourras pousser librement.

---

## Tu as fini ce chapitre quand…

- [ ] `gh --version` retourne un numéro.
- [ ] `gh auth status` confirme que tu es connecté à GitHub.
- [ ] Tu as cloné le repo de la formation localement.
- [ ] Tu as ouvert le projet dans VS Code avec `code .`.
- [ ] Tu as réussi à faire un commit Git de test.

## Pièges classiques

| Symptôme | Cause | Solution |
|----------|-------|----------|
| `gh: command not found` | Terminal non rechargé après install | Ferme l'app et rouvre-la |
| L'authentification dans le navigateur ne se finalise pas | 2FA bloquée | Vérifie que ton app d'authentification fonctionne |
| `git commit` ouvre un éditeur étrange (vim) | Tu as oublié le `-m "message"` | Tape `:q!` puis Entrée pour sortir, refais avec `-m` |
| `Please tell me who you are` | Identité Git non configurée | Refais le chapitre 0.4 partie configuration Git |
| `Permission denied` quand tu essayes de push | Tu essayes de push sur un repo qui n'est pas le tien | Normal, tu créeras ton propre repo au chapitre 0.7 |

## Ce que tu maîtrises maintenant

- GitHub CLI installé et authentifié.
- Clone d'un repo depuis GitHub.
- Ouverture d'un projet dans VS Code avec `code .`.
- Premier commit Git effectué.

## Et après ?

Tu as tout pour commencer à parler à Claude. Direction le [chapitre 0.6 — Premier contact avec Claude Code](06-claude-code.md).

---

[← Chapitre précédent](04-outils.md) · [README](../README.md) · [Chapitre suivant →](06-claude-code.md)
