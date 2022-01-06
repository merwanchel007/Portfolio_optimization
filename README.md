# Portfolio_optimization

Fut un temps les stratégies optimales étaient celles de buy and hold (i.e acheter et garder les actions), cependant lors des dernières décennies cette stratégie semble ne plus être optimale.
C'est pourquoi il est désormais nécessaire pour les entreprises de gestions d'actifs de créer des portefeuilles optimaux pouvant être modifié "facilement".

C'est dans cet objectif que nous avons designer notre projet.
Le but "final" de ce dernier est de faire un programme qui pourrait être mis directement sur un serveur et puisse être lancé à une fréquence regulière pour créer un portefeuille optimal.

Dans ce but, nous avons choisis d'essayer de battre S&P500 en faisant un portefeuille optimal composé d'actions du S&P500.

Notre programme marche comme suit :
- Dans un premier temps, nous recupérons les noms des actions qui composent le S&P500.
- Ensuite, nous récupérons les titres des articles (de news) au sujet de chaques entreprises, puis nous faisons une analyse de sentiment dessus de façon à pouvoir garder uniquement les actions qui ont eu de bonnes nouvelles récemment et donc ont plus de chance d'avoir un cours haussier dans le futur.
- Une fois les 20 actions sélectionnées, nous utilisons un modèle d'optimisation de portefeuille (de markovitz) à l'aide des cours boursiers passés des 20 actions.
- Une fois notre portefeuille optimal obtenu, nous faisons une analyse sectorielle de ce dernier de façon à connaître le risque d'exposition en cas de recession sectorielle. (par exemple le covid a eu un risque très négatif sur le milieu de l'avation). Cela serait utile en entreprise puiqu'il pourrait être pertinent pour eux de créer des indicateurs sectoriel de façon à vendre les actions d'un secteur en cas de recession de ce dernier.

Le notebook à regarder est celui nommé code_scrapping sur la branche main uniquement.
Ce notebook est celui de la branche scrap_first que nous avons recopié ici et modifié (mise en forme ainsi que quelques changements) car le merge ne fonctionnait pas (trop de conflits).
Nous vous conseillons de lire le fichier en .html sur Onyxia (en activant Trust HTML) pour avoir accès aux différents graphiques.

Nb: concernant la fonction get_title_dictionnary : 
Lorsque cette fonction est utilisée, elle print une liste de toute les entreprises (c'est pourquoi à 2 reprises il y a de grands print de nom d'entreprise), celà est due à un débuggage nécessaire puisque notre fonction semblait bloquer sur Onyxia. Nous avons donc du vérifier cela et avons ouvert le document avec jupyter sur lequel il marchait sans soucis.
Nous n'avons pas relancé les fonctions sans le print (ce qui aurait été plus jolie dans notre notebook) à cause du long temps de calcul de nos fonctions (entre 30 minutes et 1 h).
