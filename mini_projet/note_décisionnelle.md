# Note décisionnelle – Prédiction du churn client télécom
## Michael Strefeler, Dr. Ing. Julien Billeter

## Réponses aux questions du projet (Churn)

### 1. Quels types de clients sont les plus susceptibles de résilier leur contrat ?

Les clients les plus susceptibles de résilier ont une faible ancienneté (tenure courte), paient par prélèvement électronique (Electronic check), un contrat mensuel (peu d'engagement), des charges mensuelles élevées, n'ont pas ou peu de services additionnels (sécurité, backup, etc.), et utilisent la fibre optique (InternetService_Fiber optic).

### 2. Le prix est-il un facteur déterminant ou s'agit-il plutôt du manque de services ?

Avec SHAP il est possible de voir que:
- Le prix (MonthlyCharges, TotalCharges) est un facteur important : les clients avec des factures élevées sont plus à risque.
- Mais le manque de services de sécurité/support (OnlineSecurity, TechSupport) et le type de contrat (mensuel vs annuel) sont aussi déterminants.
- L'analyse SHAP montre que ces facteurs sont tous importants, mais le prix et l'engagement ressortent en tête.

### 3. Quelles actions ciblées recommander (réductions, support technique, offres personnalisées) ?

- Proposer des réductions ciblées sur les charges mensuelles pour les clients à risque.
- Inciter à passer à un contrat plus long (engagement annuel ou bi-annuel).
- Offrir des services additionnels (sécurité, backup, support technique) gratuitement ou à tarif réduit.
- Mettre en place un support proactif pour les clients ayant contacté le service technique ou ayant peu de services.

### 4. Peut-on regrouper les clients à risque par profil pour des campagnes de rétention ?

Oui, il est possible de segmenter les clients à risque, par exemple : 
  - Jeunes clients à forte facture et peu de services : proposer des packs de services.
  - Clients avec contrat mensuel : proposer une offre d'engagement avec avantages.
  - Clients fibre optique sans sécurité : cibler avec une offre sécurité.

Ces groupes peuvent être identifiés à partir des variables importantes et utilisés pour des campagnes de rétention personnalisées.