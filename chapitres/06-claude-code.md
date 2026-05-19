# Chapitre 0.6 — Premier contact avec Claude Code

> **Durée :** 30 minutes
> **Objectif :** Lancer Claude Code pour la première fois, comprendre ce que tu vois, et lui faire effectuer ta première vraie tâche.

## Le moment qu'on attendait

Tu as tout préparé : terminal apprivoisé, comptes créés, outils installés, GitHub connecté. Maintenant on lance Claude Code et on le met au travail.

## Étape 1 : se placer dans un projet

Claude Code travaille **dans un dossier précis**, qu'il considère comme "ton projet". Il a accès aux fichiers de ce dossier (et seulement ceux-là). C'est une sécurité importante.

Place-toi dans le dossier de la formation :

```bash
cd ~/claude-formation/formation-claude-code-module-0
pwd
```

Tu dois être dans le bon dossier (le `pwd` confirme).

## Étape 2 : lancer Claude Code

```bash
claude
```

Tape la commande. Appuie sur Entrée.

### À la première utilisation : l'authentification

Si c'est ta première fois, Claude Code te demande de t'authentifier. Il te propose plusieurs méthodes ; choisis :

**"Log in with your Claude account"** (ou similaire — c'est la méthode OAuth navigateur).

Il ouvre ton navigateur, tu te connectes à ton compte Anthropic (celui que tu as créé au chapitre 0.3), tu autorises Claude Code, puis tu reviens dans le terminal.

> 💡 Cette étape d'authentification ne se fait **qu'une seule fois**. Les sessions suivantes, tu lances `claude` et c'est parti.

### Ce que tu vois à l'écran

Une fois authentifié, tu te retrouves dans une **interface conversationnelle**. Il y a :

- Un titre en haut qui indique le dossier de travail.
- Un espace de conversation au milieu.
- Une **zone de saisie en bas** où tu écris tes messages.
- Des informations en bas (modèle utilisé, raccourcis clavier).

C'est ta nouvelle maison.

## Étape 3 : première conversation

Dans la zone de saisie, tape simplement :

```
Salut ! Peux-tu lire le README.md de ce projet et m'en faire un résumé en trois phrases ?
```

Appuie sur Entrée.

### Ce qui se passe

Claude :

1. **Demande la permission** de lire le fichier `README.md` (ou le fait automatiquement selon ta configuration).
2. Lit le fichier.
3. Te répond avec un résumé.

**Bravo. Tu viens d'avoir ta première vraie interaction avec Claude Code.** Tu peux continuer à discuter avec lui — pose-lui d'autres questions sur le projet.

## Étape 4 : comprendre les approbations

Claude Code est conçu autour d'un principe simple : **tu gardes le contrôle**. Avant toute action sensible (modifier un fichier, exécuter une commande), il te demande la permission.

Quand il te demande l'approbation, tu as généralement plusieurs choix :

- **Oui, une fois** : accepter cette action précise.
- **Oui, toujours pour ce type d'action** : autoriser toutes les actions similaires pour la session.
- **Non** : refuser, et expliquer pourquoi si tu veux.

> 💡 **Bonne pratique** : au début, accepte au cas par cas. Tu apprends ainsi ce que Claude essaye de faire. Tu pourras automatiser plus tard quand tu seras à l'aise.

## Étape 5 : faire modifier un fichier

On va maintenant lui faire modifier un fichier — un vrai test.

Tape dans Claude Code :

```
Crée un fichier exercices/chapitre-06/hello.md qui contient une présentation de moi en trois lignes. Mon prénom est [TON PRENOM] et je découvre Claude Code aujourd'hui.
```

Remplace `[TON PRENOM]` par ton vrai prénom.

### Ce que tu vas observer

1. Claude prépare un **plan** (parfois implicite, parfois affiché).
2. Il te demande la permission de créer le fichier.
3. Il te montre le contenu qu'il s'apprête à écrire.
4. Tu acceptes (ou tu refuses).
5. Le fichier est créé.

### Vérifier

Ouvre un autre terminal (ou utilise VS Code), et vérifie que le fichier existe :

```bash
ls exercices/chapitre-06/
cat exercices/chapitre-06/hello.md
```

Le fichier doit être là, avec le contenu généré par Claude.

## Étape 6 : le "plan mode" — voir avant d'agir

Pour les tâches plus complexes, Claude Code dispose d'un mode appelé **Plan Mode**. Tu peux l'activer en faisant **Shift+Tab** (deux fois) dans l'interface, ou en demandant explicitement un plan.

En plan mode, Claude réfléchit à ce qu'il va faire et te présente sa stratégie **avant** d'exécuter quoi que ce soit. Tu peux corriger sa direction avant qu'il agisse.

Essaye :

```
Active le plan mode et propose-moi un plan pour ajouter dans ce projet un fichier CONTRIBUTING.md qui explique comment quelqu'un pourrait contribuer à cette formation.
```

Claude te propose un plan numéroté. Tu peux :

- L'approuver tel quel.
- Lui demander d'ajuster ("ajoute aussi une section sur le code de conduite").
- Refuser et repartir sur une autre approche.

**C'est l'outil le plus précieux de Claude Code pour les tâches complexes.** Garde-le en tête.

## Étape 7 : quitter Claude Code

Quand tu as fini, tape `/exit` ou utilise `Ctrl+D` pour quitter Claude. Tu reviens à ton terminal normal.

Pour relancer plus tard, tu repasses simplement dans ton dossier de projet et tu tapes `claude`. Claude se souvient du contexte de ton projet (les fichiers), mais **pas de tes conversations passées** par défaut.

---

## Les commandes utiles à connaître dans Claude Code

| Commande | Effet |
|----------|-------|
| `/help` | Affiche l'aide |
| `/exit` | Quitte la session |
| `/clear` | Efface la conversation en cours |
| `/model` | Change de modèle (Sonnet, Opus, Haiku) |
| `/cost` | Affiche le coût de la session en cours |
| `Shift+Tab` | Bascule entre les modes (normal / plan / auto-accept) |
| `Ctrl+C` | Annule l'opération en cours |

Tu n'as pas à les retenir tout de suite. `/help` les liste à tout moment.

---

## Tu as fini ce chapitre quand…

- [ ] Tu as lancé Claude Code (`claude`) dans un dossier de projet.
- [ ] Tu t'es authentifié avec ton compte Anthropic.
- [ ] Tu as eu une première conversation (lui demander de résumer le README).
- [ ] Tu as fait créer un fichier par Claude (le `hello.md`).
- [ ] Tu as testé le plan mode au moins une fois.
- [ ] Tu sais quitter Claude Code proprement.

## Pièges classiques

| Symptôme | Cause | Solution |
|----------|-------|----------|
| `claude: command not found` | PATH non chargé après installation | Ferme et rouvre ton terminal complètement |
| Claude ne voit pas tes fichiers | Tu n'es pas dans le bon dossier | Vérifie avec `pwd` avant de lancer `claude` |
| L'auth navigateur ne se finalise pas | Bloqueur de pop-up ou cookies | Désactive le bloqueur temporairement |
| "Quota exceeded" rapidement | Ton plan n'inclut pas Claude Code ou est saturé | Vérifie ton abonnement (Pro minimum) |
| Claude propose des modifs étranges | Le contexte est confus | Fais `/clear` pour repartir propre |

## Bonnes pratiques dès le début

1. **Sois explicite dans tes demandes.** "Améliore mon code" est trop vague. "Refactore cette fonction pour qu'elle gère les valeurs nulles" est précis.
2. **Lis les diffs avant d'approuver.** Au début surtout. C'est comme ça qu'on apprend.
3. **N'aie pas peur de refuser.** Si Claude propose quelque chose qui te semble bizarre, refuse et explique pourquoi.
4. **Utilise `/clear` quand tu changes de sujet.** Ça évite que le contexte précédent pollue tes nouvelles demandes.
5. **Surveille `/cost`.** Pas pour stresser, mais pour comprendre comment se construit la facturation.

## Ce que tu maîtrises maintenant

- Lancer Claude Code depuis un projet.
- Avoir une conversation et faire effectuer des tâches simples.
- Comprendre et utiliser les approbations.
- Activer le plan mode pour les tâches complexes.
- Quitter proprement.

## Et après ?

Tu sais tout ce qu'il faut pour démarrer. Il ne reste plus qu'à valider tout ça avec un mini-projet. Direction le [chapitre 0.7 — Projet de validation](07-projet-validation.md).

---

[← Chapitre précédent](05-github.md) · [README](../README.md) · [Chapitre suivant →](07-projet-validation.md)
