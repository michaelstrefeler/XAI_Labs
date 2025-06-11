# Synthèse pour décideur – Prédiction du churn client télécom

## Résumé des résultats

Nous avons développé un modèle de prédiction du départ client (churn) pour un opérateur télécom, en utilisant les données historiques de clients. Deux types de modèles ont été testés : un modèle transparent (arbre de décision) et un modèle performant mais complexe (réseau de neurones).  
Le modèle réseau de neurones offre la meilleure performance pour anticiper le churn, mais il est difficile à expliquer. Pour garantir la compréhension métier, nous avons utilisé des outils d'explicabilité permettant d''identifier les facteurs qui influencent le plus la décision du modèle. On a choisi d'utiliser un arbre de décision pour expliquer le modèle (surrogate tree). On utilise SHAP avec cet arbre et LIME avec le réseau de neurones.

## Explication des principales décisions du modèle

Les variables qui influencent le plus la prédiction du churn sont :
- Le montant total payé par le client (TotalCharges)
- Le montant mensuel (MonthlyCharges)
- L'ancienneté (tenure)
- Le type de contrat (engagement court ou long)
- Le mode de paiement (notamment le paiement électronique)
- La présence ou non de services additionnels (Internet, sécurité, etc.)

Par exemple, un client avec un contrat mensuel, un paiement électronique, une faible ancienneté et des charges élevées a un risque de churn plus élevé.

## Justification et limitation de l'utilisation du XAI

**Pourquoi XAI ?**
- Les modèles performants (réseaux de neurones) sont des boîtes noires : ils prédisent bien mais n'expliquent pas leurs décisions.
- Les outils XAI (SHAP, LIME, surrogate tree) permettent de rendre ces modèles interprétables, en identifiant les variables qui pèsent le plus dans la décision, globalement et pour chaque client.

**Limites :**
- Les explications sont une approximation : elles reflètent le comportement du modèle, pas forcément la réalité métier.
- Les outils XAI peuvent être sensibles à la qualité des données et à la façon dont le modèle a été entraîné.
- Les explications locales (LIME) sont valables pour un individu, mais peuvent varier d'un cas à l'autre.

## Recommandations concrètes

- **Cibler les clients à risque :** Utiliser le modèle pour identifier les clients ayant un score de churn élevé, en se concentrant sur ceux avec des contrats courts, des paiements électroniques et des charges élevées.
- **Personnaliser la rétention :** Adapter les offres de fidélisation selon les facteurs de risque identifiés (ex : proposer un contrat plus long ou une réduction sur les charges mensuelles).
- **Transparence et confiance :** Utiliser les explications XAI pour justifier les actions auprès des clients et des équipes internes, et pour améliorer la confiance dans le modèle.
- **Surveiller les limites :** Garder à l'esprit que le modèle ne remplace pas l'analyse métier : il doit être utilisé comme un outil d'aide à la décision, pas comme une vérité absolue.
- **Amélioration continue :** Réévaluer régulièrement le modèle et ses explications à mesure que de nouvelles données sont collectées ou que l'offre évolue.
