<h1 align="center">Git</h1>

---
---
## 1. La configuration globale de git 👍
---

* ## Configurer votre nom et votre email :  
---  
`git config --global user.name "ERRAMI Fadel Ellah"`  
`git config --global user.email fadelellaherrami@gmail.com`
*  ## configuer les couleurs :  
---
`git config --global color.diff auto`  
`git config --global color.status auto ` 
		
		La commande git config --global color.diff auto est utilisée pour
 	activer la coloration syntaxique des différences de code dans Git.
 	Elle permet d'afficher des différences de couleur pour les modifications,
 	ajouts et suppressions de fichiers dans les commandes Git telles que git diff.
	Les commandes git config --global color.status auto et git config --global color.
	diff auto activent tous deux la coloration syntaxique dans Git, mais pour des éléments différents.

	La commande git config --global color.status auto active la coloration syntaxique pour les états de 
	fichiers dans Git, tels que les fichiers modifiés, ajoutés ou supprimés dans la commande git status. 
	Cela permet d'afficher des couleurs pour chaque état de fichier, ce qui rend l'affichage des états de 
	fichiers plus facile à comprendre et à visualiser.

	La commande git config --global color.diff auto, quant à elle, active la coloration syntaxique pour 
	les différences de code dans Git, telles que les modifications, ajouts et suppressions de fichiers 
	dans la commande git diff. Cela permet d'afficher des différences de couleur pour les modifications 
	apportées au code, ce qui rend la visualisation et la compréhension des modifications plus facile.

`git config --global color.branch auto`  

`git config --global core.editor vim`  
`git config --global merge.tool vimdiff`   

	vim est un éditeur de texte en ligne de commande populaire, qui est installé par défaut sur
 	de nombreuses distributions Linux et est également disponible sur d'autres systèmes d'exploitation.
	vimdiff est une fonctionnalité de Vim qui permet de comparer deux fichiers côte à côte dans une vue
 	à deux panneaux. Cela peut être utile pour visualiser les différences entre deux versions d'un même 
	fichier, ou pour comparer deux fichiers différents.
	Lorsque vous exécutez la commande vimdiff file1 file2, Vim ouvre deux fenêtres côte à côte,
 	affichant les deux fichiers en question. Les différences sont surlignées dans chaque fichier, permettant
 	de visualiser rapidement les différences entre les deux fichiers. Vous pouvez également naviguer entre les
 	différences à l'aide de commandes spécifiques de Vim.

`git init` 

		Cette commande va initialiser votre dépot , en créant un dossier caché .git dans votre dossier courant 
	ce dossier contient la configuration de votre projet git , ces objets et son pointeur .

	
	Pour vérifier que vos paramètres ont bien été pris en compte, et vérifier les autres paramètres, il suffit de passer la commande 
` git config --list`   

---  
---
## 2. Appréhendez le fonctionnement de git et github 👍
---
---    
![Texte alternatif](git.PNG)    


	Dans Git, il existe trois états principaux pour les fichiers d'un projet : untracked (non suivi), staging (prêt pour validation), et commit (validé et enregistré dans l'historique des versions).

**Untracked** : Les fichiers qui sont présents dans le répertoire de travail (working directory) mais qui ne sont pas encore suivis par Git sont considérés comme non suivis (untracked). Cela signifie que Git ne suit pas les modifications apportées à ces fichiers et ne les inclura pas dans le prochain commit. Pour suivre ces fichiers, vous devez les ajouter à l'index (staging).

**Staging** : Lorsque vous ajoutez des fichiers à l'index (staging), vous les préparez pour la validation (commit). Les fichiers en staging ont été sélectionnés pour être inclus dans le prochain commit, mais ils ne sont pas encore enregistrés dans l'historique des versions.

**Commit** : Une fois que vous avez ajouté des fichiers à l'index (staging) et que vous êtes satisfait des modifications apportées, vous pouvez les enregistrer dans l'historique des versions en effectuant un commit. Cela crée une nouvelle version de votre projet qui inclut les modifications apportées aux fichiers en staging.  

---
---
## 3. Le système de branche dans git 👍
---
---   

![branche](branche.PNG)  

		Les branches dans Git sont un moyen de diviser le développement d'un projet en plusieurs lignes de développement distinctes. Chaque branche est une copie complète du code source du projet, et peut être modifiée de manière indépendante des autres branches.

		Les branches sont particulièrement utiles dans les projets où plusieurs développeurs travaillent sur différentes fonctionnalités en même temps, ou lorsque vous souhaitez ajouter une nouvelle fonctionnalité ou corriger un bug sans affecter le code principal du projet. Les branches permettent également d'expérimenter des idées de manière isolée, sans perturber le code de production.

		Dans Git, la branche principale est généralement appelée "master" ou "main", et chaque nouvelle branche est créée à partir de cette branche principale. Vous pouvez travailler sur une branche en toute sécurité, en faisant autant de modifications que vous le souhaitez, sans affecter le code sur d'autres branches ou sur la branche principale. Une fois que vous avez terminé vos modifications sur une branche, vous pouvez fusionner (merge) les modifications de cette branche dans la branche principale ou dans une autre branche.


	Pour connaître les branches présentes dans notre projet, il faut taper la ligne de commande :
`git branch`  

	Dans un premier temps, vous n’aurez que :  
`* main`  

	L’étoile signifie que c’est la branche sur laquelle vous vous situez, et que c’est sur celle-ci qu'actuellement vous réalisez vos modifications.  
	
	Cette commande va créer la branche Cagnotte en local. Cette dernière ne sera pas dupliquée sur le dépôt distant.
`git branch cagnotte`  

	Alors maintenant por afficher nos branches on tape : 
`git branch`  
`* main`  
`cagnotte`  

	Pour basculer de branche, nous allons utiliser :

`git checkout cagnotte`  

	Vous aurez donc :

`git branch`
`main`
`* cagnotte`

	Maintenant que vous êtes dans votre branche principale, vous pouvez fusionner votre branche "cagnotte" à celle-ci grâce à la commande suivante :

`git merge cagnotte`  
`Merge made by the 'recursive' strategy`  

---
---
---

	Imaginons que vous deviez travailler sur un projet avec des amis. Ces derniers ont créé le repository sur GitHub. Il est temps pour vous de récupérer le code pour apporter vos modifications :

	Tout d’abord, vous allez récupérer l’URL du dépôt distant : cela se passe sur GitHub !  
	Retournez sur Git Bash, et tapez la commande suivante :


`git clone https://github.com/FADELELLAHerrami/jee_training`  

	Pour donner un nom à notre dépot 
`git remote add jee https://github.com/FADELELLAHerrami/jee_training`  

		Une fois cette commande exécutée, vous pouvez utiliser le nom jee pour vous référer au référentiel distant dans les commandes Git. Par exemple, vous pouvez utiliser git push jee main pour pousser vos modifications locales vers la branche main sur le référentiel distant nommé jee.  
	
	La commande git pull origin main est utilisée pour récupérer les dernières modifications du référentiel distant nommé origin et les fusionner automatiquement avec votre branche locale main.

	Plus précisément, la commande:

		Utilise le mot-clé pull pour récupérer les modifications depuis le référentiel distant et les fusionner avec votre branche locale.
		Utilise le nom origin pour spécifier le référentiel distant à partir duquel vous souhaitez récupérer les modifications. Dans ce cas, origin est souvent utilisé comme nom par défaut pour le référentiel distant lors de la configuration initiale du projet.
		Utilise le nom main pour spécifier la branche locale sur laquelle vous souhaitez appliquer les modifications. main est souvent utilisé comme nom par défaut pour la branche principale du projet.
		En exécutant cette commande, vous récupérerez toutes les modifications qui ont été apportées à la branche main dans le référentiel distant depuis la dernière fois que vous avez synchronisé votre référentiel local avec celui-ci. Si des conflits surviennent pendant la fusion, Git vous demandera de les résoudre manuellement.   

---
---  

## 4. Collaborez sur github 👍  
---  
---  
<video src="02-16-04.mp4" autoplay></video>  



















