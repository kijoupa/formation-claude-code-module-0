# Chapitre 0.3 — Créer tes comptes

> **Durée :** 20 minutes
> **Objectif :** Avoir un compte GitHub sécurisé et un compte Anthropic prêt à l'emploi.

## Pourquoi deux comptes ?

Tu vas utiliser deux services en ligne tout au long de cette formation :

- **GitHub** : c'est l'endroit où tu vas stocker ton code et tes projets. C'est aussi la plateforme où les développeurs du monde entier partagent et collaborent. **Compte gratuit.**
- **Anthropic** : c'est l'entreprise qui développe Claude (l'IA derrière Claude Code). Tu as besoin d'un compte avec un abonnement actif pour utiliser Claude Code. **Compte payant.**

Les deux sont indépendants. Tu les crées dans l'ordre que tu veux, mais on va commencer par GitHub car il est gratuit.

---

## Partie 1 : créer ton compte GitHub

### Étape 1 — Aller sur GitHub

Va sur [github.com](https://github.com) et clique sur **"Sign up"** (en haut à droite).

### Étape 2 — Remplir les informations

GitHub te demande :

1. **Email** : utilise une adresse à laquelle tu as accès facilement. Tu vas devoir la confirmer.
2. **Mot de passe** : choisis-en un fort. Vraiment fort. Utilise un gestionnaire de mots de passe (Bitwarden, 1Password, le trousseau Apple…) si tu n'en as pas déjà un, c'est le moment.
3. **Nom d'utilisateur (username)** : c'est ton identité publique sur GitHub. Il apparaîtra dans toutes les URL de tes projets (`github.com/ton-username/ton-projet`). Choisis quelque chose de **propre et durable** — pas `xx-killer-xx-92`. Idéalement, ton nom ou un pseudonyme professionnel.

> 💡 **Conseil important** : ton nom d'utilisateur GitHub est souvent vu par des recruteurs et collègues. Pense-le comme une carte de visite.

### Étape 3 — Vérifier ton email

GitHub t'envoie un email. Clique sur le lien dedans pour confirmer ton adresse.

### Étape 4 — Activer la double authentification (2FA)

**Cette étape n'est pas optionnelle.** Tu vas connecter ton compte GitHub à ton ordinateur, et il va contenir potentiellement du code professionnel. Sans 2FA, c'est trop risqué.

1. En haut à droite, clique sur ton avatar → **Settings**.
2. Dans le menu de gauche, va dans **Password and authentication**.
3. Section **Two-factor authentication**, clique sur **Enable two-factor authentication**.
4. Choisis **Set up using an app** (recommandé).
5. Scanne le QR code avec une application d'authentification :
   - **Authy** (multi-appareils, gratuit, recommandé)
   - **Google Authenticator** (simple mais lié à un seul appareil)
   - **1Password** ou **Bitwarden** si tu utilises l'un d'eux
6. Entre le code à 6 chiffres affiché dans l'app.
7. **Sauvegarde les codes de récupération que GitHub te donne.** Imprime-les, mets-les dans un endroit sûr. Si tu perds ton téléphone, ce sont eux qui te sauveront.

> ⚠️ **Vraiment, ne saute pas l'étape des codes de récupération.** Si tu perds l'accès à ton authentificateur sans les codes, tu perds ton compte GitHub. C'est arrivé à des gens. Ne sois pas l'un d'eux.

### Étape 5 — Vérifier que tout fonctionne

Déconnecte-toi de GitHub, puis reconnecte-toi. Tu devrais devoir entrer ton code 2FA. Parfait.

---

## Partie 2 : créer ton compte Anthropic

### Étape 1 — Aller sur Claude.ai

Va sur [claude.ai](https://claude.ai) et clique sur **"Sign up"**.

### Étape 2 — Créer le compte

Tu peux utiliser :
- Une adresse email + mot de passe
- Ou ton compte Google

> 💡 **Astuce** : utilise la même adresse email que pour GitHub. Ça t'évitera de t'emmêler.

### Étape 3 — Choisir un plan

C'est l'étape importante. Voici ce que tu dois savoir.

#### Les options disponibles

| Plan | Prix | Inclut Claude Code ? | Recommandé pour cette formation ? |
|------|------|----------------------|-----------------------------------|
| **Free** | 0 € | Non | ❌ Insuffisant |
| **Pro** | ~ 20 €/mois | ✅ Oui (usage modéré) | ✅ **Recommandé pour démarrer** |
| **Max** | ~ 100 à 200 €/mois | ✅ Oui (usage intensif) | Pour plus tard, si tu deviens accro |
| **Team / Enterprise** | Plus cher | ✅ Oui | Pour les entreprises |
| **Console (API)** | À la consommation | ✅ Oui (via clé API) | Pour automatisations avancées |

#### Notre recommandation : Claude Pro

Pour suivre cette formation, **Claude Pro à environ 20 €/mois suffit largement**. Tu auras assez d'usage pour faire tous les exercices, et tu pourras monter en gamme plus tard si tu te rends compte que tu utilises Claude Code intensivement.

> 💡 **Bonne pratique** : commence en Pro, observe pendant un mois ton usage réel, puis ajuste. Inutile de payer Max dès le départ.

### Étape 4 — Effectuer le paiement

Renseigne ta carte bancaire. L'abonnement est mensuel et résiliable à tout moment depuis tes paramètres.

### Étape 5 — Vérifier ton accès

Une fois l'abonnement actif, tu peux te connecter sur claude.ai et discuter avec Claude. Fais un essai : pose-lui une question quelconque. Tu confirmes ainsi que ton compte fonctionne.

---

## Tu as fini ce chapitre quand…

- [ ] Tu as un compte GitHub avec un nom d'utilisateur propre.
- [ ] La double authentification est activée sur ton compte GitHub.
- [ ] Tu as sauvegardé tes codes de récupération GitHub.
- [ ] Tu as un compte Anthropic avec un abonnement Claude Pro (ou supérieur) actif.
- [ ] Tu as réussi à te connecter aux deux services.

## Pièges classiques

- **"Je n'arrive pas à recevoir l'email de vérification GitHub"** : vérifie tes spams. Si rien, fais "Resend" sur GitHub. Si toujours rien, c'est peut-être ton fournisseur qui bloque — essaye avec une autre adresse.
- **"L'app d'authentification ne reconnaît pas le code"** : vérifie que l'heure de ton téléphone est bien synchronisée automatiquement. C'est la cause numéro un.
- **"Je veux la version Free de Claude pour économiser"** : la version Free n'inclut pas Claude Code. Tu ne pourras pas suivre la formation. Au minimum Pro.

## Et après ?

Tes comptes sont prêts. Direction le [chapitre 0.4 — Installer les outils](04-outils.md), où on va installer Git, VS Code, et enfin Claude Code lui-même.

---

[← Chapitre précédent](02-terminal.md) · [README](../README.md) · [Chapitre suivant →](04-outils.md)
