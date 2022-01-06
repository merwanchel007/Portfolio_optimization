# Portfolio_optimization

Fut un temps les stratégies optimales furent celles de buy and hold (i.e acheter et garder les actions), cependant lors des dernières décennies cette stratégie semble ne plus marcher.
C'est pourquoi il est désormais nécessaire pour les entreprises de gestions d'actifs de créer des portefeuilles optimaux pouvant être modifié "facilement".

C'est dans cet objectif que nous avons designer notre projet.
Le but "final" de ce dernier est de faire un programme qui pourrait être mis directement sur un serveur et puisse être lancé à un e fréquence regulière pour créer un portefeuille optimal.

Dans ce but, nous avons choisis d'essayer de battre S&P500 en faisant un portefeuille optimal composé d'actions du S&P500.

Notre programme marche comme suit :
- Dans un premier temps, nous recupérons les noms des actions qui composent le S&P500.
- Une fois cela fait, nous récupérons les titres des articles (de news) au sujet de chaques entreprises, puis nous faisons une analyse de sentiment dessus de façon à pouvoir garder uniquement les actions qui ont eu de bonnes nouvelles récemment et donc ont plus de chance d'avoir un cours haussier dans le future.
- Une fois les 20 actions sélectionnées, nous utilisons un modèle d'optimisation de portefeuille (de markovitz) à l'aide des cours boursiers passés des 20 actions.
- Enfin cela nous renvoie un portefeuille optimal.
