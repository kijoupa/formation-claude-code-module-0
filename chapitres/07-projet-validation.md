# Chapitre 0.7 — Projet de validation

> **Durée :** 30 minutes
> **Objectif :** Prouver que tu maîtrises l'ensemble du Module 0 en réalisant un mini-projet complet, de zéro à GitHub.

## L'idée

Tu vas créer **ton propre repo GitHub**, le cloner sur ton ordinateur, lancer Claude Code dedans, lui faire générer un petit fichier de présentation de toi, puis pousser ton travail sur GitHub.

C'est exactement le cycle que tu vas répéter des centaines de fois dans la suite de la formation. **Si tu réussis ce mini-projet, tu es prêt·e pour le Module 1.**

---

## L'énoncé

À la fin de ce chapitre, tu auras :

- Un nouveau repo public sur ton compte GitHub, nommé `bienvenue-claude-code`.
- Ce repo contiendra un fichier `bio.md` avec une présentation de toi en plusieurs sections.
- Ce repo contiendra un `README.md` qui explique ce qu'est le projet.
- Au moins **2 commits** signés à ton nom.
- Le travail aura été fait avec l'aide de Claude Code.

## Étape 1 : créer le repo sur GitHub depuis le terminal

> 💡 On pourrait le créer via l'interface web de GitHub, mais autant en profiter pour apprendre la méthode du terminal — plus rapide et plus pro.

Place-toi dans ton dossier de formation :

```bash
cd ~/claude-formation
```

Crée le repo avec GitHub CLI :

```bash
gh repo create bienvenue-claude-code --public --description "Mon premier repo après avoir suivi le Module 0 de la formation Claude Code" --clone
```

Décortique cette commande :

- `gh repo create` : créer un repo
- `bienvenue-claude-code` : le nom du repo
- `--public` : il sera visible publiquement (parfait pour ton portfolio)
- `--description "..."` : la description qui apparaît sur GitHub
- `--clone` : cloner automatiquement le repo sur ton ordinateur

Une fois la commande exécutée, tu as :

1. Un nouveau repo sur ton GitHub (va voir sur `github.com/ton-username/bienvenue-claude-code`).
2. Un dossier local du même nom.

## Étape 2 : entrer dans le repo

```bash
cd bienvenue-claude-code
ls -a
```

Le `-a` affiche aussi les fichiers cachés. Tu vois un dossier `.git` — c'est lui qui contient toute la magie du versionning.

## Étape 3 : lancer Claude Code

```bash
claude
```

Claude démarre dans ton repo vide.

## Étape 4 : faire générer le contenu

Dans Claude Code, tape une demande comme celle-ci (adapte avec tes vraies infos) :

```
Bonjour. Je commence la formation Claude Code. Crée-moi deux fichiers dans ce repo :

1. Un fichier `bio.md` qui me présente avec :
   - Mon nom : [TON PRENOM] [TON NOM]
   - Mon parcours en deux phrases (laisse un placeholder que je remplirai)
   - Pourquoi j'apprends Claude Code (laisse un placeholder)
   - Ce que je veux faire dans 6 mois (laisse un placeholder)

2. Un fichier `README.md` qui explique :
   - Que ce repo est mon premier projet réalisé après le Module 0 de la formation Claude Code
   - Qu'il a été créé avec l'aide de Claude Code
   - Avec un petit "à propos" qui renvoie au fichier bio.md
```

Claude va te proposer un plan, te demander la permission, créer les fichiers. Approuve.

## Étape 5 : compléter les placeholders

Quitte Claude Code (`/exit`) et ouvre VS Code dans le repo :

```bash
code .
```

Ouvre `bio.md` et remplis les placeholders avec tes vraies informations. Sauvegarde (`Cmd+S` / `Ctrl+S`).

## Étape 6 : premier commit

Dans ton terminal, depuis le dossier du repo :

```bash
git status
```

Tu vois que tu as deux nouveaux fichiers non suivis (`README.md` et `bio.md`).

Ajoute-les :

```bash
git add .
```

Le `.` veut dire "tous les changements dans le dossier courant".

Commit :

```bash
git commit -m "Ajout du bio et du README initial"
```

## Étape 7 : pousser sur GitHub

```bash
git push
```

Au premier push, Git peut te demander à quelle branche distante pousser. Si c'est le cas :

```bash
git push -u origin main
```

(Le `-u origin main` lie ta branche locale à la branche distante. À refaire qu'une seule fois par branche.)

## Étape 8 : vérifier sur GitHub

Va sur ton GitHub dans le navigateur (`github.com/ton-username/bienvenue-claude-code`). **Tes fichiers sont là.** 🎉

Tu peux aussi y aller directement depuis le terminal :

```bash
gh repo view --web
```

## Étape 9 : faire un deuxième commit

Pour valider que tu sais répéter le cycle, fais une petite modification.

Relance Claude Code :

```bash
claude
```

Demande-lui :

```
Ajoute une section "Mes objectifs avec Claude Code" à la fin du fichier bio.md, avec trois objectifs à puces que tu vas inventer mais qui sont cohérents avec quelqu'un qui démarre.
```

Approuve. Quitte Claude.

Refais le cycle Git :

```bash
git status
git add .
git commit -m "Ajout de la section objectifs"
git push
```

Tu peux constater sur GitHub que ton historique contient maintenant deux commits.

---

## Validation du module

Tu as réussi le Module 0 si **tous ces points sont validés** :

- [ ] Le repo `bienvenue-claude-code` existe sur ton GitHub, en public.
- [ ] Il contient un `README.md` et un `bio.md`.
- [ ] Le `bio.md` contient tes vraies informations (pas des placeholders).
- [ ] L'historique du repo montre **au moins 2 commits** à ton nom.
- [ ] Tu as utilisé Claude Code pour générer au moins une partie du contenu.

Pour confirmer ta validation à ton formateur (si la formation le prévoit), envoie l'URL de ton repo :

```
https://github.com/TON-USERNAME/bienvenue-claude-code
```

---

## Pièges classiques

| Symptôme | Cause | Solution |
|----------|-------|----------|
| `gh repo create` échoue | Pas authentifié, ou nom déjà pris | `gh auth status` pour vérifier ; renomme si besoin |
| `git push` demande un mot de passe | GitHub CLI n'a pas configuré l'auth Git | Refais `gh auth login` et accepte la config Git |
| Le push échoue avec "rejected" | La branche distante a un commit que tu n'as pas | `git pull` d'abord, puis re-push |
| `bio.md` n'apparaît pas sur GitHub | Tu as oublié le push | Refais `git push` |
| Commit fait sans `-m`, vim s'ouvre | Tu es coincé dans vim | Tape `:wq` (sauvegarder et quitter) ou `:q!` (quitter sans sauvegarder) |

---

## Ce que tu sais faire maintenant

Tu peux, de mémoire :

1. Ouvrir un terminal et naviguer dans tes fichiers.
2. Créer un repo GitHub depuis ton terminal.
3. Lancer Claude Code dans un projet.
4. Lui faire effectuer des tâches concrètes (création/modification de fichiers).
5. Versionner ton travail avec Git (`add`, `commit`, `push`).
6. Synchroniser avec GitHub.

**C'est un socle considérable.** Tu as franchi la barrière d'entrée la plus dure. Tout le reste de la formation s'appuie sur ces fondations.

## Et après ?

Le **Module 1 — Git & GitHub solides** te plonge dans le versionning de code en profondeur : branches, fusions, conflits, pull requests. C'est le socle qui te permettra de collaborer avec d'autres personnes.

Mais d'abord, **fais une pause**. Prends un café. Tu l'as mérité.

---

[← Chapitre précédent](06-claude-code.md) · [README](../README.md) · **Fin du Module 0** 🎉
