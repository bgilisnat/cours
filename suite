
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
```
### Exercice 1 : Mise en pratique des bases
   - Initialiser un projet local.
   - Créer un fichier et le modifier
   - Committer.
   - Modifier le fichier 
   - Commiter
   - Afficher la liste des commits
   
### Exercice 2 : trouver la suite du cours 

Vous allez récupérer la suite du cours en clonant un dépôt distant.

## Les dépôts

Un **dépôt** (ou **repository** en anglais) est un espace de stockage où est conservé un projet, incluant tous ses fichiers, l'historique des modifications, et les informations nécessaires pour gérer les versions du projet. 

### Contenu d’un dépôt Git

Un dépôt Git contient :

1. **Les fichiers du projet** (code source, documentation, etc.).
2. **L’historique des versions** :  
   - L’historique inclut les informations sur les changements, leur auteur, et leur date.
3. **Les branches** :
   - Différentes versions ou lignes de développement du projet.
   - Par exemple, une branche principale, et des branches secondaires pour de nouvelles fonctionnalités ou corrections.
4. **Les tags** :
   - Ils marquent des versions spécifiques, comme des versions stables (`v1.0`, `v2.0`).

### Types de dépôts

1. **Dépôt local**
   - C'est une version du dépôt qui réside sur votre machine.
   - Quand vous travaillez avec **Git**, vous effectuez des modifications, des commits (validations), et d'autres actions directement sur ce dépôt.

2. **Dépôt distant**
   - C'est une version du dépôt hébergée sur un serveur ou une plateforme (comme GitHub, GitLab, ou Bitbucket).
   - Il permet à plusieurs collaborateurs de partager leur travail.
   - Vous pouvez synchroniser votre dépôt local avec le dépôt distant via les commandes `git push` (pour envoyer des modifications) et `git pull` (pour récupérer des modifications).

## Les branches
### Qu'est-ce qu'une branche ?

Une **branche** (ou *branch* en anglais) est une fonctionnalité fondamentale de Git qui permet de **de développer sur plusieurs lignes parallèles**. Chaque branche représente une version distincte de votre code source, permettant à différentes versions ou fonctionnalités d’être développées, testées et évoluées de manière indépendante.

Une branche se comporte comme une copie **isolée** de votre projet, où vous pouvez expérimenter ou apporter des modifications sans affecter la version principale.

### Fonctionnement d'une branche
Par défaut, Git commence avec une branche initiale appelée `main` 

- **Du point de vue du développeur**
Lorsque vous créez une nouvelle branche, Git duplique l'état actuel du projet (les fichiers, commits, etc.), mais les changements que vous apportez dans cette nouvelle branche seront **indépendants** de la branche d'origine jusqu'à ce que vous décidiez de fusionner ces changements.

- **D'un point de vue technique**
	-   Une branche est simplement un **pointeur** léger (quelques octets) vers un commit
	-   Lors de la création d'une nouvelle branche, Git ne duplique **aucun** fichier
	-   Git crée **uniquement** un nouveau **pointeur vers le commit actuel** (et crée un graphe de commit)
	-   **Les fichiers ne bougent pas**
	-   Seuls les **nouveaux commits** créés dans chaque branche **sont stockés** différemment

- **C'est pourquoi** :
	-   La création de branche est quasi instantanée
	-   Les branches sont très légères en mémoire
	-   Git peut gérer efficacement des milliers de branches
	-   Le changement de branche (checkout) est rapide

**Note** : Historiquement la branche principale se nommait `master`et est devenu `main`. Les terminologies **master/slave** sont progressivement remplacées dans les versions existantes des projets Git (en lien avec le mouvement **"Black Lives Matter"**).

### Que se passe t'il lors d'un changement de branche ?

Git remplace les fichiers dans votre répertoire de travail par ceux qui correspondent au dernier commit de la branche sur laquelle vous basculez.

   -   Si un **fichier existe** mais n'existe pas dans la branche cible, Git le supprime.
   -   Si un **fichier n'existe pas** mais existe dans la branche cible, Git l'ajoute.
   -   Si un **fichier a été modifié**, dans la branche cible, Git remplace son contenu par la version cible.
   -   Si des **fichiers sont non suivis** (non ajoutés avec `git add`), ils ne seront pas affectés.
   -   Si vous avez des **modifications non commités** dans des fichiers suivis, Git refusera de changer de branche si ces modifications entrent en conflit avec les fichiers de la branche cible.  Pour résoudre cela, vous pouvez :
       -  **Commiter** vos modifications avant de changer de branche
       - Mettre de côté vos modifications (**Stash**) pour pouvoir les restaurer plus tard.

### Exemple
1. Vous êtes sur la branche `main` et créez une nouvelle branche `feature/login-page` : 
2. Vous travaillez sur la branche`feature/login-page` et faites plusieurs commits → ces changements **n'affecteront pas** `main` tant que vous ne fusionnez pas la branche.

3. Une fois les modifications terminées et validées, vous pouvez **fusionner** `feature/login-page` dans `main` les modifications seront alors visible dans `main`

### Avantages du travail avec plusieurs branches

L’utilisation de **plusieurs branches** dans Git offre de nombreux avantages :

- 1. **Isolation des modifications** : Chaque branche est un espace de travail isolé.
-  2. **Collaboration simplifiée** : Chaque développeur travaille sur sa propre branche. Une fois les changements terminés et validés, ils peuvent être fusionnés dans une branche principale après une revue (code review).
- 3. **Gestion des versions et des environnements** : Les branches permettent de gérer facilement les différentes versions ou environnements d’un projet :
     - Une branche `main` pour la version production.
     - Une branche `develop` pour le développement.
     - ...
 - 4. **Facilité de rollback/reprise/expérimentation** : Si une branche fonctionne pas comme prévu, vous pouvez simplement **la supprimer** sans affecter la branche principale.

- 5. **Support pour les workflows structurés**
   - Plusieurs workflows Git, comme **GitFlow** ou le **Trunk-Based Development**, reposent sur l'utilisation de branches pour organiser efficacement le développement. (voir [Informations sur les workflows git](https://scalastic.io/git-workflows/))
   - Exemple **Gitflow** :
     - `feature/*` pour les nouvelles fonctionnalités.
     - `release/*` pour préparer des versions.
     - `hotfix/*` pour des corrections d'urgence en production.
     - `bugfix/*` pour des corrections de bug.

- 6. **Meilleure traçabilité** : Les branches permettent de garder un historique clair des changements apportés.
- 7. **Réduction des conflits** :  En travaillant sur des branches indépendantes, les **conflits** (lorsque deux développeurs modifient la même partie du code en même temps) sont réduits. Les conflits ne se produisent qu'au moment de la fusion, et Git propose des outils pour les résoudre.

### Résumé

| **Avantage**                           | **Explication**                                                                                     |
|----------------------------------------|-----------------------------------------------------------------------------------------------------|
| **Isolation des modifications**        | Les branches permettent de travailler sans perturber le reste du projet.                          |
| **Collaboration simplifiée**           | Chaque développeur travaille sur des branches séparées. |
| **Gestion des versions/environnements** | Les branches peuvent représenter des environnements, des versions, ...         |
| **Rollback/expérimentation facile**                    | Si une branche échoue, elle peut être supprimée sans affecter la branche principale.               |
| **Support des workflows**   | Les branches permettent d’implémenter des workflows comme GitFlow.      |
| **Meilleure traçabilité**              | Historique clair des changements  |
| **Réduction des conflits**             | Les conflits ne surviennent qu’au moment de la fusion.            |



## Workspace, staging area et repository

###  Workspace (Espace de travail)
#### Qu'est-ce que c'est ?
  
  Le **Workspace** est l'endroit où vous travaillez : c'est votre répertoire de travail local, contenant les fichiers et dossiers du projet. Tous les fichiers que vous modifiez, ajoutez ou supprimez le sont dans cet espace.

-   C'est le répertoire local où tous les fichiers du projet sont présents.
-   **Tous les fichiers (suivis ou non suivis) sont dans le workspace.**
    -   **Fichiers suivis** : Des fichiers déjà pris en compte par Git dans un commit précédent.
    -   **Fichiers non suivis** : Des fichiers qui existent dans le répertoire mais que Git ne suit pas encore (par exemple, des fichiers nouvellement créés mais pas encore ajoutés avec `git add`).
#### Caractéristiques
  - Les fichiers modifiés dans le workspace ne sont pas encore suivis par Git (jusqu'à ce que vous les ajoutiez à l'index).
  - Vous pouvez consulter l'état de vos fichiers dans le workspace avec la commande `git status`.

#### Exemple
  - Vous ouvrez un fichier `main.ncl` dans votre éditeur de code et y ajoutez/modifiez du code.
  - Ces modifications sont dans votre espace de travail, mais Git ne les a pas encore "préparées" pour un commit.
---

### Staging Area (Zone de préparation ou Index)
#### Qu'est-ce que c'est ?
  
  La **Staging Area**(en quelque sorte la "zone de préparation"). C'est une zone intermédiaire où vous sélectionnez (ou **"stager"**) les fichiers que vous souhaitez inclure dans le prochain commit. 

Elle agit comme un espace temporaire pour les modifications avant de les enregistrer dans l'historique.

#### Caractéristiques
1. **Zone tampon intermédiaire**
   Prépare les fichiers ou modifications avant de les enregistrer dans un commit.  
   
2. **Ajout manuel**
   Vous choisissez les fichiers à inclure avec `git add`. Les fichiers non ajoutés restent dans le **Workspace**.

3. **Flexibilité**
   - Ajoutez uniquement certains fichiers ou parties de fichiers
   - Retirez un fichier de la Staging Area

#### Exemple
   - Ajouter à la Staging Area :  
     ```bash
     git add fichier.txt
     ```
   - Vérifier les fichiers dans la Staging Area :  
     ```bash
     git status
     ```
   - Retirer un fichier de la Staging Area :  
     ```bash
     git reset fichier.txt
     ```

---
### Local Repository (Historique git)  

#### Qu'est-ce que c'est ?
  Une base de données contenant l'historique des commits, c'est-à-dire les enregistrements des états des fichiers.  
  
#### Caractéristiques
  - Les modifications ajoutées à la Staging Area sont enregistrées dans l'historique avec `git commit`.  
  - L'historique est local au départ, mais vous pouvez le synchroniser avec un dépôt distant (via `git push`).  

#### Exemple
  Vous enregistrez les modifications de `main.ncl` dans l'historique avec :  
  ```bash
  git commit -m "Message descriptif"
  ```

---
### Récapitulatif

| **Zones**          | **Description**                                                                                   | **Commande associée**                     |
|--------------------|---------------------------------------------------------------------------------------------------|-------------------------------------------|
| **Workspace**      | C'est l'endroit où vous modifiez vos fichiers localement.                                         | Aucun (modification directe dans l'éditeur) |
| **Staging Area**   | Zone de préparation où vous sélectionnez les fichiers/modifications que vous souhaitez committer. | `git add fichier`                         |
| **Historique (Local Repository)**         | Capture définitive des modifications présentes dans la staging area (commit) et l'ajoute à l'historique.                              | `git commit -m "Message descriptif"`      |

---

#### **En résumé**
L'enchaînement classique est le suivant : 
```plaintext
Workspace → git add → Staging Area → git commit → Local Repository (Historique git) 
```  
---

### **Exemple concret**

1. **Modification d'un fichier dans le workspace :**
   ```bash
   echo "print('Hello, Git!')" > main.py
   ```

2. **Ajout du fichier à la staging area :**
   ```bash
   git add main.py
   ```

3. **Création d'un commit :**
   ```bash
   git commit -m "Ajout du fichier main.py avec un message d'accueil"
   ```

À la fin de ce workflow :
- Le fichier `main.py` est enregistré dans l'historique Git comme une modification définitive (commit).

---
## Les commandes 
### Commandes importantes

- **Init** : Initialise un nouveau dépôt Git dans le dossier pour qu'il soit suivi. Git va ajouter un répertoire **.git**, qui contient toutes les données nécessaires pour gérer les versions et l'historique du projet.
  ```bash
  git init
  ```

- **Clone** : Crée une copie locale d'un dépôt distant.  
  ```bash
  git clone url_du_dépôt
  ```
  
- **Add** : Ajoute des fichiers à l'index (staging area) pour le prochain commit.  
  ```bash
  git add chemin_du_fichier
  ```

- **Commit** : Enregistre un état spécifique des fichiers dans le dépôt. Chaque modification est enregistrée avec un identifiant unique (hash).  
  ```bash
  git commit -m "Message décrivant les modifications"
  ```

- **Pull** : Récupère les modifications depuis un dépôt distant et les fusionne avec la branche actuelle.  
  ```bash
  git pull
  ```

- **Push** : Envoie les modifications locales validées vers un dépôt distant.  
  ```bash
  git push
  ```

- **Revert/Reset** : Permet de revenir à des versions antérieures d'un projet.  
  - **Revert** : Annule un ou plusieurs commits sans supprimer l'historique.  
    ```bash
    git revert id_du_commit
    ```
  - **Reset** : Supprime un ou plusieurs commits et réécrit l'historique.  
    ```bash
    git reset --hard id_du_commit
    ```
### Gestion des branches
La commande `git branch` est utilisée pour lister, créer ou supprimer des branches.  

- **Lister les branches** :
  ```bash
  git branch
  ```
  Cela affiche toutes les branches locales, avec un astérisque (*) indiquant la branche actuelle.

- **Créer une nouvelle branche** :
  ```bash
  git branch <branch_name>
  ```
  Exemple :  
  ```bash
  git branch feature/new-feature
  ```

- **Supprimer une branche** :
  ```bash
  git branch -d <branch_name>
  ```
  Exemple :  
  ```bash
  git branch -d feature/old-feature
  ```

	**Note** : `git branch` ne bascule pas sur la branche créée. Pour cela, utilisez `git checkout` (historique) ou `git switch`(recommandé).

- **Merge** : Fusionne les modifications de la branche avec la branche en cours.  
  ```bash
  git merge nom_de_la_branche
  ```
  
- **Switch** : Change de branche et/ou en crée une nouvelle  
  ```bash
  # Change de branche
  git merge nom_de_la_branche
  ```
  
- **Checkout** : Le cas de checkout est particulier. Cette commande, que vous retrouverez partout, a historiquement été utilisée pour plusieurs tâches différentes :
	- Basculer entre des branches.
	- Créer de nouvelles branches.
	- Restaurer des fichiers spécifiques.
	- Passer à un commit précédent (mode "détaché" cad naviguer dans l'historique sans être attaché à une branche)

	Depuis Git 2.23+, pour **plus de clarté**. La commande checkout a donné naissance à deux autres commandes plus parlantes : `git switch` (pour changer de branche ou en créer une) et `git restore` (pour restaurer un fichier d'une autre branche) il est **recommandé d'utiliser git switch** pour changer de branche ou en créer une nouvelle

	 ```bash
  # Cette commande historique crée la branche et passe sur la branche créée
  git checkout -b feature/JIRA-2432 
  
  # Cette commande fait exactement la même chose (RECOMMANDE)
  git switch -c feature/JIRA-2432
  ```
   
---
### Commandes supplémentaires

- **Status** : Affiche l'état des fichiers dans le dépôt (suivis, modifiés, en attente de commit, etc.).  
  ```bash
  git status
  ```

- **Log** : Affiche l'historique des commits du projet.  
  ```bash
  git log
  ```

- **Diff** : Montre les différences entre les fichiers modifiés et leur version précédente.  
  ```bash
  git diff
  ```

- **Checkout** : Permet de basculer entre les branches ou de revenir à une version spécifique d’un fichier.  
  ```bash
  git checkout nom_de_la_branche
  ```

- **Stash** : Sauvegarde temporairement les modifications **non commitées** pour les restaurer plus tard (concept proche du shelve de Mercurial). Cela permet de mettre de côté des modifications.
  ```bash
  git stash
  ```

- **Tag** : Crée un tag (marqueur) pour identifier une version spécifique (souvent utilisé pour les versions stables).  
  ```bash
  git tag nom_du_tag
  ```

- **Remote** : Gère les dépôts distants (ajout, suppression, ou modification).  
  - Ajouter un dépôt distant :  
    ```bash
    git remote add origin url_du_dépôt
    ```
  - Afficher les dépôts distants :  
    ```bash
    git remote -v
    ```

Avec ces commandes, vous avez un aperçu des actions les plus courantes et essentielles pour travailler avec Git.

### Aide mémoire des commandes 
Voici un tableau récapitulatif des commandes Git mentionnées précédemment, organisé avec une description concise pour chacune d'elles :

| **Commande**                | **Description**                                                                                   | **Exemple**                             |
|-----------------------------|---------------------------------------------------------------------------------------------------|-----------------------------------------|
| **`git init`**              | Initialise un nouveau dépôt Git dans un dossier.                                                 | `git init`                              |
| **`git clone`**             | Crée une copie locale d'un dépôt distant.                                                        | `git clone https://url_du_dépôt.git`    |
| **`git status`**            | Affiche l'état des fichiers (modifiés, suivis, etc.) dans le dépôt.                              | `git status`                            |
| **`git add`**               | Ajoute des fichiers ou des modifications à l'index (staging area).                               | `git add fichier.txt`                   |
| **`git commit`**            | Enregistre les modifications de l'index avec un message descriptif.                              | `git commit -m "Message du commit"`     |
| **`git log`**               | Affiche l'historique des commits du projet.                                                      | `git log`                               |
| **`git branch`**            | Liste, crée ou supprime des branches.                                                            | `git branch nouvelle_branche`           |
| **`git checkout`**          | Permet de basculer entre les branches ou de restaurer des fichiers. **(Historique)**                              | `git checkout nom_branche`              |
|**`git switch`** | Permet de basculer entre les branches et d'en créer **(Recommandé)** |`git switch nom_branche`
|**`git restore`** | Permet de restaurer des fichiers (annule les modifications en cours) **(Recommandé)** |`git restore nom_ficher`
| **`git merge`**             | Combine les modifications d'une branche dans la branche actuelle.                                | `git merge nom_branche`                 |
| **`git push`**              | Envoie les commits locaux vers un dépôt distant.                                                 | `git push origin main`                  |
| **`git pull`**              | Récupère et fusionne les modifications depuis un dépôt distant dans la branche actuelle.         | `git pull origin main`                  |
| **`git stash`**             | Sauvegarde temporairement les modifications non commitées pour les restaurer plus tard.          | `git stash`                             |
| **`git stash apply`**       | Réapplique les modifications sauvegardées dans le stash sans les supprimer du stash.             | `git stash apply`                       |
| **`git stash pop`**         | Réapplique les modifications sauvegardées dans le stash et supprime ce dernier.                  | `git stash pop`                         |
| **`git stash list`**        | Affiche la liste des stashes sauvegardés.                                                        | `git stash list`                        |
| **`git reset`**             | Annule des modifications ou réécrit l'historique des commits.                                    | `git reset --hard id_commit`            |
| **`git revert`**            | Crée un nouveau commit pour annuler un commit précédent sans modifier l'historique.              | `git revert id_commit`                  |
| **`git diff`**              | Affiche les différences entre les fichiers modifiés et leur version précédente.                  | `git diff`                              |
| **`git tag`**               | Marque une version spécifique du projet (souvent pour des versions stables).                     | `git tag v1.0`                          |
| **`git remote`**            | Gère les dépôts distants (ajout, suppression, affichage).                                         | `git remote add origin url_du_dépôt`    |
| **`git stash clear`**       | Supprime tous les stashes sauvegardés.                                                           | `git stash clear`                       |

---


### Git et son vocabulaire : un univers parfois déconcertant

Git **introduit un vocabulaire spécifique** qui peut sembler déroutant pour les débutants. Cette terminologie propre est d'autant plus compliquée qu'il existe des variations entre les plateformes et outils, ce qui peut rendre l'apprentissage encore plus difficile.

Voici quelques illustrations de ces spécificités :

####  1. Différences entre les plateformes

 **Exemple**: Pull request et Merge request
- **Pull Request (PR)**
	-   **Outil principal** : GitHub (et Bitbucket).
	-   **Concept** : Un **Pull Request** est une demande pour "tirer" (pull) les modifications d'une branche de travail vers une autre branche (souvent la branche principale).
	-   **Nom** : Le terme "pull" vient de la perspective du mainteneur du projet : il va "tirer" vos modifications dans sa branche.
- **Merge Request (MR)**
	- **Outil principal** : GitLab.
	-   **Concept** : Une **Merge Request** est une demande pour "fusionner" (merge) vos modifications d'une branche dans une autre.
	-   **Nom** : Le terme "merge" met l'accent sur l'action finale (fusionner les modifications) plutôt que sur l'idée de tirer les modifications.

**Résumé**

Dans les deux cas, il s'agit de demander à quelqu'un de **réviser, valider et fusionner des changements**. Ces différences de nom sont purement un choix de terminologie propre à chaque outil.

**Autre exemple de différences de terminologie**

- **Issue** (GitHub, GitLab) et **Ticket** (Jira, Bitbucket) désignent souvent des éléments similaires : des tâches ou des problèmes à résoudre.

- **Git add** est fréquemment renommé en `Ajouter des fichiers`. Ou certains IDE proposent directement `Choisir les fichiers à inclure` dans le commit pour chaque nouveau fichier.
		
####   2. Changement de nom ou fusion de commandes

Certains outils ou extensions rendent l'utilisation de Git plus simple en **regroupant plusieurs commandes**, en les **renommant** ou en **adoptant une terminologie uniforme** quel que soit le système de gestion de version. Bien que cela puisse être pratique, cela peut également créer de la confusion si l'on ne comprend pas ce qui se passe réellement en arrière-plan.

**Exemple** : `push`

`push` dans certains outils peut combiner en réalité **deux commandes distinctes**:

1.  **`git commit`** : Valide les modifications
2.  **`git push`** : Envoie sur la branche distante

Cette simplification peut devenir problématique si vous ne souhaitez pas valider votre travail directement.

Cette confusion provient d’une différence avec des systèmes comme **SVN**, où un commit est automatiquement synchronisé avec le serveur, contrairement à Git, qui sépare clairement les étapes locales et distantes. 

Ce comportement peut être paramétrable dans les outils.

### **Bonnes pratiques Git**

#### 1. Les commits

- **Créez des commits atomiques** :  
  Chaque commit doit être petit et représenter **une seule modification ou fonctionnalité**. Cela rend l'historique clair et facile à comprendre.  
  
  *Exemple : Evitez de combiner la correction d'un bug et l'ajout d'une nouvelle fonctionnalité dans le même commit.*

- **Ajoutez des messages de commit clairs** :  
  Décrivez ce que vous avez fait dans le commit. Un bon message de commit doit être précis et informatif.  
  
  **Exemple :**
  ```plaintext
  Mauvais : "Fix urgent"
  Bon : "Correction du bug empêchant l'utilisateur de se connecter"
  ```

  Structure recommandée pour un message clair :
  - Une ligne concise (50-80 caractères max) décrivant le changement.
  - Une description plus détaillée (optionnelle) si nécessaire.

- **Évitez les commits inutiles ou désordonnés** :  
Ne faites pas de commits comme "WIP" (_Work In Progress_) ou "Test". Finalisez vos modifications avant de committer. Ils vont **polluer l'historique** et risquent de pauser problème aux autres membres de l'équipe.

-   **Récupérez toujours les dernières modifications avant de travailler** :  
    Avant de commencer à travailler, synchronisez votre dépôt local avec le dépôt distant.   
    
-   **Poussez régulièrement vos commits** :  
    N'attendez pas trop longtemps avant de partager votre travail avec l'équipe. Cela **réduit les conflits** potentiels.

#### 2. Les branches

- **Travaillez toujours sur des branches** :  
  Ne travaillez **jamais** directement sur la branche principale. Créez une branche pour chaque fonctionnalité ou correction de bug. La brache principale est alimentée par la fusion des branches, il est d'ailleurs possible d'interdire un commit sur la branche principale.

- **Nommez vos branches de manière explicite** :  
  Utilisez des noms descriptifs pour vos branches, comme `feature/nom-fonctionnalité` ou `bugfix/nom-correctif`.

  **Exemple :**
  ```bash
  # Cette commande crée la branche et passe sur la branche créée
  git switch -c feature/JIRA-2432 
  ```
	  
- **Fusionnez proprement vos branches** :  
  Avant de fusionner une branche dans `main`, assurez-vous **toujours** qu'elle est à jour avec la branche principale et qu'elle a été correctement testée. Si possible, utilisez une Pull Request (PR) pour une revue de code si vous travaillez en équipe.

3. **Les outils et processus** :
   - **Utilisation de plateformes** comme GitHub, GitLab ou Bitbucket pour collaborer.
   - Définir un processus de **revue de code** via des pull requests/merge requests ou peer review.
   - Définir le **workfow** et l'organisation des branches avec l'équipe.
   - Simplifier vous la vie en utilisant des **outils graphiques** pour utiliser GIT :
		-   **GitHub Desktop** : Une interface simple pour gérer vos dépôts GitHub localement.
		-   **Sourcetree** : Un outil pour visualiser et gérer les branches et commits.
		-   **GitKraken** : Une interface intuitive avec des fonctionnalités avancées pour collaborer.
		-   **Les IDE** : VS Code (avec l'extension Git), IntelliJ, Eclipse, ...
---

## Gestion des conflits

### Qu'est-ce qu'un conflit dans Git ?

Un conflit survient lorsque Git ne peut pas fusionner automatiquement des modifications qui ont été apportées à un même fichier dans des branches ou des commits différents. Cela se produit généralement lorsque :

-   Deux personnes modifient la même partie d’un fichier.
-   Vous modifiez un fichier localement, mais une version différente a été poussée sur le dépôt distant.

Quand vous effectuez une fusion, Git compare les versions et se basant sur :

-   **Base commune** : La dernière version commune des fichiers avant la divergence.
-   **Votre branche** : Les changements locaux que vous avez faits.
-   **Branche distante** (ou autre branche) : Les changements faits par quelqu’un d’autre.

Si les modifications ne se chevauchent pas, Git effectue une fusion automatique. Sinon, un conflit est détecté et une résolution manuelle est nécessaire.

**Exemple de résolution de conflit manuelle dans un IDE**

![Résolution de conflits dans IntelliJ](https://i.ibb.co/CPV0QF5/conflict-resolution-tool-legend-dark.png)

Voici un exemple de résolution de conflit dans IntelliJ. Les codes couleurs sont les suivants :
1. Ligne modifiée    
2.  Ligne supprimée    
3.  Ligne ajoutée    
4.  Ligne en conflit

L'écran est divisé en trois parties :
- **Partie gauche** : version de la branche en cours (lecture seule)
- **Partie centrale** : version reprenant la base commune sur laquelle on peut venir gérer les ajouts/suppressions/modifications de code
- **Partie de droite**: version de branche distante (ou de la branche comparée) (lecture seule)

### Les marques de conflit dans Git

Lorsque Git détecte un conflit dans un fichier, il ajoute des **marques de conflit** directement dans ce fichier pour indiquer les parties en désaccord, les IDE permettent de visualiser simplement ces marques. Voici à quoi cela elles ressemblent :

-   `<<<<<<< HEAD` : Indique le début de vos modifications **locales**.
-   `=======` : Sépare vos modifications locales de celles de la branche distante.
-   `>>>>>>> branch_name` : Indique la fin des modifications de la branche distante

**Exemple**
![Création d'un conflit](https://i.ibb.co/sH6xj0T/conflit.png)

Va générer les marques de révision suivantes :
```bash
<<<<<<< HEAD
// Code de votre branche actuelle
echo "chat"
=======
// Code de la branche distante
echo "chien"
>>>>>>> nom_branche
```
Il faudra alors choisir les lignes à conserver.


## Exercices sur le Travail collaboratif

   - Créer un projet github
   - Inviter un collaborateur
   - Simuler un projet à plusieurs.
   - Gérer les branches
   - Créer une branche et résoudre des conflits.
