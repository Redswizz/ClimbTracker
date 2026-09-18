## Décision : Normalisation des cotations couleurs/Fontainebleau

**Contexte / Problème**
L'application permet aux utilisateurs de coter leurs blocs selon deux systèmes 
différents (couleurs ou Fontainebleau) car les salles françaises n'utilisent 
pas de convention unique, bien que généralement, les niveaux soient similaires 
selon la couleur. Or, la fonctionnalité de graphe de progression nécessite de 
comparer des niveaux de difficulté entre eux, sur une seule échelle.

**Options envisagées**
1. Un graphe séparé par méthode de cotation → écarté, car un utilisateur 
   changeant de salle perdrait la continuité de sa progression
2. Un graphe unique sans ordre logique entre les couleurs → écarté, car 
   ça ne représente plus une "progression" au sens propre
3. Table de correspondance couleur → Fontainebleau, utilisée pour calculer 
   un indice numérique normalisé → RETENU

**Décision**
Mise en place d'un mécanisme de conversion associant chaque cotation (quelle 
que soit sa méthode d'origine) à un indice numérique unique, basé sur une 
table de correspondance approximative. L'implémentation technique précise 
(service dédié, méthode statique, etc.) sera définie lors de la conception 
de l'architecture logicielle du projet.

**Limite assumée**
Cette correspondance est une moyenne indicative : les échelles de couleur 
varient réellement d'une salle à l'autre en France. Le choix est documenté 
et assumé comme simplification volontaire pour la v1, avec la possibilité 
d'évoluer vers une correspondance personnalisable par salle en v2.