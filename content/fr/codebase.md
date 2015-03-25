## I. Base de code
### Une seule base de code suivie dans un système de contrôle de révision

Une application à douze facteurs réside toujours dans un système de contrôle de révision (SCR), tel que [Git](http://git-scm.com/), [Mercurial](http://mercurial.selenic.com/), et [Subversion](http://subversion.apache.org/). Une copie de la base de données de ce système s'appelle un *dépôt de code*, souvent abrégé en *dépôt*.

Une *base de code* est définie comme étant un seul dépôt (dans un SCR centralisé comme Subversion), ou bien un ensemble de dépôts qui partagent une révision initiale (dans un système décentralisé comme Git).

![Une seule base de code est relié à plusieurs déploiements)](/images/codebase-deploys.png)

Il y a toujours une relation une-à-une entre la base de code et l'application:

* S'il existe plusieurs bases de code, on ne parle plus d'une application – on parle d'un système distribué dont chaque élément constitutif s'agit d'une application qui peut conformer elle-même aux douze facteurs.
* La méthodologie de douze facteurs interdit que plusieurs applications partagent la même base de code. Il est préférable de convertir la code commune en des bibliothèques de code qui peuvent être inclus par le [gestionnaire de dépendances](./dependencies).

Une application n'a qu'une seule seule base de code, mais il peut y avoir grand nombre de déploiements de l'application. Un *déploiement*, c'est une instance de l'application en cours d'exécution. Ce serait typiquement une site de production accompagnée d'une ou de plusieurs sites de mise-en-scène. En outre, chaque ingénieur possède sa propre copie de l'application qui s'exécute dans un environnement local de développement. Chacun de ces copies est considerée elle aussi comme un déploiement.

Tous les déploiements ont la même base de code, bien que leur version active peut être différente. Par exemple, un ingénieur qui a fait des commits ne les a pas peut-être encore déployés à l'environnment de mise-en-scène. L'environnement de mise-en-scène elle aussi contient des commits qui n'existent pas encore dans l'environnement de production. Mais puisque ces déploiements partagent une seule base de code elles appartiennent, par définition, à la même application.
