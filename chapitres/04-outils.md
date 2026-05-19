# Chapitre 0.4 — Installer les outils

> **Durée :** 45 minutes
> **Objectif :** Avoir Git, VS Code, et Claude Code installés et opérationnels sur ton ordinateur.

## Ce qu'on installe et pourquoi

Trois outils, qui te suivront pendant toute la formation :

| Outil | Rôle | Quand on l'utilise |
|-------|------|-------------------|
| **Git** | Versionner ton code (garder l'historique) | Tous les jours, en arrière-plan |
| **VS Code** | Éditeur de code pour visualiser et modifier | Pour lire et écrire du code |
| **Claude Code** | Assistant IA dans ton terminal | Le cœur de la formation |

Suis les étapes dans l'ordre. **Ne saute pas la configuration de Git** à la fin de chaque installation, c'est ce que les gens oublient.

---

## Partie 1 : installer Git

### macOS

Git est probablement déjà installé. Vérifie avec :

```bash
git --version
```

Si tu obtiens un numéro de version (par exemple `git version 2.39.0`), Git est installé. Tu peux passer à la configuration plus bas.

Si tu obtiens une popup proposant d'installer les outils de développement, accepte. Sinon, télécharge l'installeur officiel sur [git-scm.com/download/mac](https://git-scm.com/download/mac).

### Windows

1. Va sur [git-scm.com/download/win](https://git-scm.com/download/win).
2. Le téléchargement démarre automatiquement.
3. Lance l'installeur (fichier `.exe`).
4. **Garde les options par défaut**, sauf une : à l'étape "Adjusting your PATH environment", choisis **"Git from the command line and also from 3rd-party software"** (option du milieu, généralement déjà sélectionnée).
5. Important : à l'étape qui propose **Git Bash**, accepte. Git Bash est un terminal qui te permettra d'utiliser les commandes Mac/Linux sur Windows. **C'est ce qu'on va utiliser dans la suite de la formation pour rester cohérent.**
6. Termine l'installation avec les options par défaut pour le reste.

Une fois installé, **ferme tous tes terminaux ouverts** et ouvre **Git Bash** (cherche-le dans le menu Démarrer).

Vérifie l'installation :
```bash
git --version
```

### Linux

Selon ta distribution :

```bash
# Ubuntu / Debian
sudo apt update && sudo apt install git -y

# Fedora
sudo dnf install git -y

# Arch
sudo pacman -S git
```

Vérifie :
```bash
git --version
```

### Configurer Git (toutes plateformes — ne pas sauter)

Git a besoin de savoir qui tu es pour signer tes modifications. Dans ton terminal :

```bash
git config --global user.name "Ton Nom"
git config --global user.email "ton.email@example.com"
```

> ⚠️ **Important** : utilise **la même adresse email que celle de ton compte GitHub**. Sinon, tes commits n'apparaîtront pas comme étant les tiens sur GitHub.

Vérifie que c'est bien enregistré :
```bash
git config --global user.name
git config --global user.email
```

Configure aussi la branche par défaut (la convention moderne) :
```bash
git config --global init.defaultBranch main
```

---

## Partie 2 : installer VS Code

VS Code (Visual Studio Code) est un éditeur de texte gratuit développé par Microsoft. C'est l'éditeur le plus utilisé au monde par les développeurs.

### Installation

Va sur [code.visualstudio.com](https://code.visualstudio.com) et télécharge la version correspondant à ton système.

- **macOS** : un fichier `.zip` qui contient `Visual Studio Code.app`. Glisse-le dans ton dossier Applications.
- **Windows** : un `.exe`. Lance-le, garde les options par défaut, **coche bien "Add to PATH"** quand on te le propose.
- **Linux** : choisis le format adapté à ta distribution (`.deb` pour Ubuntu/Debian, `.rpm` pour Fedora).

### Vérifier que `code` est accessible depuis le terminal

Ouvre un nouveau terminal et tape :

```bash
code --version
```

Si tu obtiens un numéro de version, parfait.

#### Si la commande `code` n'est pas trouvée (sur macOS)

1. Ouvre VS Code.
2. Appuie sur **`Cmd + Maj + P`** pour ouvrir la palette de commandes.
3. Tape `Shell Command: Install 'code' command in PATH` et appuie sur Entrée.
4. Ferme et rouvre ton terminal.
5. Retest : `code --version`.

### Installer les extensions essentielles

Lance VS Code, puis dans la barre latérale gauche, clique sur l'icône des extensions (les 4 carrés). Recherche et installe :

- **Claude Code** (édité par Anthropic) — l'extension officielle, indispensable.
- **French Language Pack for Visual Studio Code** (optionnel) si tu veux l'interface en français.

> 💡 D'autres extensions viendront plus tard selon le langage qu'on utilisera. Pour l'instant, ça suffit.

---

## Partie 3 : installer Claude Code

Voilà l'événement principal. On va installer Claude Code lui-même.

**Anthropic recommande désormais l'installeur natif** (depuis octobre 2025), qui ne nécessite plus Node.js et qui se met à jour tout seul. C'est ce qu'on va utiliser.

### macOS

Ouvre ton terminal et tape :

```bash
curl -fsSL https://claude.ai/install.sh | bash
```

Le script télécharge et installe Claude Code. Attends qu'il se termine.

### Linux

Même commande que macOS :

```bash
curl -fsSL https://claude.ai/install.sh | bash
```

### Windows

Tu as deux options selon le terminal que tu utilises :

**Option A : Git Bash (recommandée si tu as installé Git Bash plus haut)**

```bash
curl -fsSL https://claude.ai/install.sh | bash
```

**Option B : PowerShell**

```powershell
irm https://claude.ai/install.ps1 | iex
```

> ⚠️ Sur Windows, ton antivirus peut bloquer le script. Si c'est le cas, autorise-le manuellement.

### Vérifier l'installation

**Ferme ton terminal et ouvre-en un nouveau** (important : ça permet de recharger le PATH).

Puis tape :

```bash
claude --version
```

Tu devrais voir un numéro de version (par exemple `2.1.140`). **Si oui, bravo, Claude Code est installé.** 🎉

### Si `claude --version` ne fonctionne pas

C'est presque toujours un problème de PATH (le système ne sait pas où trouver la commande). Solutions dans l'ordre :

1. **Ferme complètement ton terminal et rouvre-le.** Pas juste un nouvel onglet : ferme l'application.
2. Sur Mac/Linux, essaye :
   ```bash
   source ~/.bashrc
   # ou si tu utilises zsh (par défaut sur Mac récent)
   source ~/.zshrc
   ```
3. Sur Windows, redémarre ton ordinateur. Oui, vraiment.
4. Si rien ne marche, viens demander de l'aide sur le Discord avec le message d'erreur exact.

---

## Tu as fini ce chapitre quand…

- [ ] `git --version` retourne un numéro de version.
- [ ] `git config --global user.name` retourne ton nom.
- [ ] `git config --global user.email` retourne ton email (le même que GitHub).
- [ ] `code --version` retourne un numéro de version.
- [ ] L'extension Claude Code est installée dans VS Code.
- [ ] `claude --version` retourne un numéro de version.

## Pièges classiques

| Symptôme | Cause probable | Solution |
|----------|----------------|----------|
| `git: command not found` après installation Windows | PATH non configuré | Réinstalle en choisissant "Git from the command line and also from 3rd-party software" |
| `code: command not found` sur Mac | Le shim n'a pas été installé | Lance VS Code → Cmd+Shift+P → "Shell Command: Install 'code' in PATH" |
| `claude: command not found` après installation | Terminal non rechargé | Ferme **toute l'application** terminal et rouvre-la |
| Antivirus Windows bloque l'installeur Claude | Faux positif courant | Autorise manuellement, ou utilise l'option Git Bash |
| Conflits avec une ancienne version Node.js | Tu avais installé Claude Code via npm avant | Suis le guide de migration sur docs.claude.com |

## Ce que tu maîtrises maintenant

Trois outils installés et opérationnels :

- **Git**, configuré avec ton identité
- **VS Code**, avec l'extension Claude Code
- **Claude Code**, prêt à être lancé

## Et après ?

Tes outils sont prêts. Mais Claude Code ne peut pas encore parler à GitHub. C'est ce qu'on va régler. Direction le [chapitre 0.5 — Connecter ton ordinateur à GitHub](05-github.md).

---

[← Chapitre précédent](03-comptes.md) · [README](../README.md) · [Chapitre suivant →](05-github.md)
