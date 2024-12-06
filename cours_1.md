
# **Introduction à Git et au contrôle de version**

## Présentation générale

### Qu'est-ce que les systèmes de contrôle de version ?

Créé par **Linus Torvalds** en 2005, **Git** est aujourd'hui l'un des outils les plus populaires pour le développement logiciel.

**Git**, **Mercurial** (Hg) et **SVN** (Subversion) sont tous des systèmes de contrôle de version. 

![Outils de contrôle de version ](https://i.ibb.co/jVk4ZN4/version-control2.jpg)

Ils sont utilisés pour suivre les modifications apportées aux fichiers, généralement dans des projets de développement logiciel. Ils permettent aux développeurs de collaborer efficacement, de gérer différentes versions de leur code et de revenir à des états précédents si nécessaire. 

Ils diffèrent dans leur architecture :

- **Mercurial** et **Git** sont des **systèmes de contrôle de version distribués** c'est à dire que chaque utilisateur dispose d'une copie complète du dépôt, **y compris tout l'historique des modifications**. 

- Au contraire **SVN** est un **système de contrôle de version centralisé** sur un serveur. Les utilisateurs travaillent avec des copies locales des fichiers sans disposer de l'intégralité de l'historique. Cela signifie qu'une connexion au serveur est nécessaire pour effectuer certaines opérations (comme obtenir l'historique ou valider son code).

**GitHub** a popularisé Git en offrant un hébergement collaboratif simple et efficace pour héberger les dépôts Git. **GitHub** a été racheté par Microsoft en 2018. Après ce rachat, une partie de la communauté a migré vers d'autres plateformes. 

### Présentation rapide des caractéristiques

| **Caractéristique**                         | **Git**                    | **Subversion (SVN)**                     | **Mercurial (Hg)**          |
|--------------------------------------------|----------------------------|-----------------------------|-----------------------------|
| **Architecture**                            | Distribuée                | Centralisée                 | Distribuée |
| **Branches**                                | Légères, rapides, faciles | Lentes et lourdes           | Légères, mais moins flexibles que Git |
| **Performance (rapidité)**                  | Très rapide         | Plus lent                   | Rapide, mais Git est souvent plus performant|
| **Travail hors ligne**                      | Oui | Non                         | Oui               |
| **Gestion des fusions (merge)**             | Puissante (merge, rebase)  | Basique                     | Bonne, mais moins avancée que Git |
| **Popularité et communauté**                | Très élevée (standard actuel) | Déclin                     | Modérée, mais en déclin    |
| **Écosystème et intégrations**              | Étendu (GitHub, GitLab, CI/CD, IDE) | Moins dynamique         | Moins riche que Git   |
| **Plateformes majeures**                    | GitHub, GitLab, Bitbucket  | Rarement utilisé            | Bitbucket (support Mercurial arrêté en 2020)|
| **Workflows modernes (pull requests, CI)**  | Parfaitement adapté        | Moins adapté                | Moins répandu que Git |
| **Courbe d’apprentissage**                  | Moyenne                        | Facile                      | Moyenne               |

### Pourquoi utiliser Git ?

Nous étudierons spécifiquement **GIT** pour les raisons suivantes :

- **Historique des modifications** : Git conserve un journal détaillé de toutes les modifications apportées, y compris qui a fait quoi et quand.
- **Flexibilité** : Git s'adapte à divers workflows, qu'il s'agisse de petites équipes ou de projets open source à grande échelle.
- **Efficacité** : Il est conçu pour être rapide et performant, même pour les projets de grande envergure. Bien que la différence de rapidité ne soit pas significative sur des projets de taille moyenne.
- **Ecosystème et intégration** : Git est intégré dans de très nombreuses plateformes, comme **GitHub**, **GitLab** ou **Bitbucket**, qui permettent une gestion simplifiée des dépôts distants. Son écosystème est très dynamique.

### Installation et configuration

Pour pouvoir utiliser **GIT**, il faut d'abord installer GIT et ses dépendances.

Pour cela, se rendre sur :
[https://git-scm.com/](https://git-scm.com/) (Suivre l'aide en ligne en cas de besoins)
   - Installer Git (Windows, macOS, Linux). Dans notre exemple, utiliser la version Windows 64 bits.
   - L'installeur va automatiquement configurer les informations de l'utilisateur par rapport aux informations du système. En ligne de commande, cela se ferait avec les commandes suivantes :

     ```bash
     git config --global user.name "Votre Nom"
     git config --global user.email "votre.email@example.com"
     ```

### Exemple de workflow simple (avec explications des commandes)

1. **Initialisation** : Créer ou cloner un dépôt (référentiel distant).
  - **Si vous démarrez un nouveau projet**, initialisez un dépôt Git dans un **dossier existant** :

	 ```bash
     # Initialisation de git
     git init
	```

**Explication** : La commande `git init` crée un dépôt Git local dans le dossier courant. Elle initialise un dossier caché `.git` contenant les métadonnées nécessaires pour gérer le projet avec Git.

   - **Si vous travaillez sur un projet existant**, clonez un dépôt distant :
     ```bash
     # Récupération d'un dépôt distant
     git clone https://github.com/utilisateur/mon_projet.git
     cd mon_projet
     ```
     **Explication** : La commande `git clone` télécharge une copie complète du dépôt distant spécifié (dans cet exemple, sur GitHub) et crée un dossier local avec le même contenu.

2. **Modification des fichiers** : Éditez ou ajoutez des fichiers dans votre projet.
   Par exemple, créez un fichier `README.md` et ajoutez-y du contenu dans votre éditeur de texte.

3. **Ajout au suivi** : Ajoutez les fichiers à l'index (staging area) pour les inclure dans le prochain commit.
   ```bash
   git add README.md
   ```
   **Explication** : La commande `git add` place les modifications du fichier `README.md` dans la staging area (zone de préparation). Cela signifie que ce fichier sera inclus dans le prochain commit.

4. **Enregistrement des modifications** : Créez un commit pour sauvegarder vos modifications avec un message descriptif.
   ```bash
   git commit -m "Ajout du fichier README.md"
   ```
   **Explication** : La commande `git commit` enregistre les modifications ajoutées à l'index (via `git add`) dans l'historique du projet.  
L'option **`-m`** permet de fournir un **message descriptif (message de commit)** pour expliquer les changements effectués.  
Par exemple : `"Ajout du fichier README.md"` indique clairement ce qui a été modifié dans ce commit. (Il est possible de voir l'historique des commits avec la commande `git log`).

5. **Synchronisation avec un dépôt distant** : Si un dépôt distant est configuré, envoyez vos modifications avec `git push` :
   ```bash
   git push origin main
   ```
   **Explication** : La commande `git push` transfère les commits locaux vers le dépôt distant.  
   - **`origin`** : C'est le **nom par défaut du dépôt distant** configuré lors du clonage ou de l'ajout d'un dépôt distant (via `git remote add origin <url>`).  
   - **`main`** : Représente la **branche principale** où les modifications doivent être envoyées. 

   **Attention** : Si d'autres collaborateurs ont ajouté des modifications sur le dépôt distant, vous devrez peut-être d'abord récupérer leurs changements avec `git pull origin main` avant de pouvoir pousser les vôtres. Si les mêmes morceaux de code ont été modifiés par deux développeurs, cela peut générer un **conflit**. C'est à dire qu'il faudra indiquer à git quel code doit être conservé.
---

### Résumé des commandes de l'exemple
```bash
# Initialisation
git init                            # Crée un dépôt Git local
# ou
git clone https://url_du_dépôt.git  # Clone un dépôt distant existant

# Modification
echo "# Mon Projet" > README.md     # Ajoute un fichier README avec du contenu ou avec un éditeur

# Ajoute le fichier au suivi git
git add README.md                   # Ajoute le fichier README à l'index

# Enregistrement
git commit -m "Ajout du fichier README.md"  # Enregistre les modifications avec un message descriptif

# Synchronisation
git push origin main                # Envoie les modifications locales vers la branche 'main' du dépôt distant
