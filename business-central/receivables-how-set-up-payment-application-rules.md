---
title: Règles pour l’affectation automatique des paiements
description: Découvrez comment configurer des règles pour l’affectation automatique des paiements sur la page Règles d’affectation des paiements.
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'payment process, direct payment posting, reconcile payment, expenses, cash receipts'
ms.search.form: '1290, 1294, 1287'
ms.date: 06/25/2021
ms.author: edupont
---
# <a name="set-up-rules-for-automatic-application-of-payments" />Configurer des règles pour l'affectation automatique des paiements

Sur la page **Règles d'affectation de paiement**, vous configurez des règles pour définir comment le texte de paiement (sur une transaction bancaire) doit être automatiquement mis en correspondance avec le texte sur les factures, notes de crédit ou autres écritures ouvertes (impayées) associées lorsque vous utilisez la fonction **Affecter automatiquement** sur la page **Journal rapprochement paiement**. Pour plus d'informations, reportez-vous à [Rapprocher les paiements à l'aide du lettrage automatique](receivables-how-reconcile-payments-auto-application.md).

Pour définir de nouvelles règles d'affectation de paiement, choisissez quels types de données sur une ligne journal rapprochement bancaire doivent correspondre aux données sur une ou plusieurs écritures ouvertes avant que le paiement associé ne soit automatiquement affecté aux écritures ouvertes. La qualité de chaque affectation automatique est indiquée par une valeur de **Faible** à **Élevée** dans le champ **Fiabilité correspondance** sur la page **Journal rapprochement bancaire** selon la règle d'affectation de paiement qui a été utilisée.

Chaque ligne de la page **Règles d'affectation de paiement** représente une règle d'affectation de paiement. Les règles sont appliquées dans l'ordre spécifié par le champ **Ordre de tri**. Si plusieurs règles sont utilisées simultanément, c'est la fiabilité correspondance de la règle dont l'ordre de tri est le plus élevé qui est utilisée.

La fonction d'affectation automatique est basée sur des critères de correspondance classés par priorité. La fonction essaie d'abord, par ordre de priorité, de faire correspondre le texte dans les cinq champs **Partie associée** d'une ligne journal avec le texte du compte bancaire, du nom ou de l'adresse des clients ou des fournisseurs dont les documents impayés représentent des écritures ouvertes. La fonction essaie ensuite de faire correspondre le texte des champs **Texte transaction** et **Info transaction supplémentaire** sur une ligne journal avec le texte des champs **N° du document externe** et **N° document** sur les écritures ouvertes. Enfin, la fonction essaie de faire correspondre le montant du champ **Montant relevé** d'une ligne journal avec le montant sur les écritures ouvertes.

> [!NOTE]
> La correspondance de texte n'est possible que pour les textes contenant plus de quatre caractères.

Outre les critères de correspondance, les remarques suivantes s'appliquent concernant le signe du montant règlement :

- Pour les montants négatifs, une correspondance est d'abord établie par rapport aux écritures ouvertes représentant les factures client, et ensuite par rapport aux notes de crédit fournisseur.
- Pour les montants positifs, une correspondance est d'abord établie par rapport aux écritures ouvertes représentant les factures fournisseur, et ensuite par rapport aux notes de crédit client.

## <a name="to-set-up-a-payment-application-rule" />Pour configurer une règle d'affectation de paiement
1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Règles d’affectation des paiements**, puis choisissez le lien associé.
2. Définissez une règle d'affectation de paiement, nouvelle ou modifiée, en renseignant les champs sur une ligne tel que décrit dans le tableau suivant.

|Champ|Description|
|-|-|
|**Fiabilité correspondance**|Spécifie la fiabilité de la règle d'affectation que vous définissez sur la ligne. <br /></br>Une valeur spécifiée dans ce champ est affichée dans le champ **Fiabilité correspondance** sur la page **Journal rapprochement bancaire** en fonction de la qualité de l'affectation de paiement automatique sur la ligne journal.|
|**Priorité**|Spécifie la priorité de la règle d'affectation par rapport aux autres règles d'affectation définies en tant que lignes sur la page **Règles affectation paiement**. 1 représente la priorité la plus élevée.|
|**Correspondance partie associée**|Spécifie la quantité d'informations sur le client ou le fournisseur (par exemple, l'adresse, le nom de la ville et le numéro de compte bancaire) sur la ligne journal rapprochement bancaire qui doivent correspondre aux informations sur l'écriture ouverte avant que la règle d'affectation soit utilisée pour affecter automatiquement le paiement à l'écriture ouverte.|
|**Correspondance N° doc./N° doc. ext.**|Spécifie si le texte de la ligne journal rapprochement bancaire doit correspondre à la valeur du champ **N° document** ou du champ **N° document externe** sur l’écriture ouverte avant que la règle d’affectation soit utilisée pour affecter automatiquement le paiement avec l’écriture ouverte.|
|**Correspondance montant avec tolérance**|Spécifie combien d'écritures pour un client ou un fournisseur doivent correspondre au montant (tolérance de règlement comprise) avant que la règle d'affectation soit utilisée pour affecter automatiquement un paiement à l'écriture ouverte.|
|**Révision requise**|Spécifie si l’affectation de paiement automatique doit être révisée manuellement par l’utilisateur avant le report. Choisissez le champ **Lignes à vérifier** sur la page **Journal des affectations de paiement** pour démarrer une expérience guidée dans laquelle vous pouvez facilement examiner plusieurs affectations en série sur la page **Révision affectation paiement**.|

Le tableau suivant décrit les règles d’affectation de paiement standard dans [!INCLUDE[prod_short](includes/prod_short.md)].

> [!Important]
> Les règles d'affectation de paiement peuvent être différentes dans votre implémentation de [!INCLUDE[prod_short](includes/prod_short.md)].

| Fiabilité correspondance | Priorité | Correspondance partie associée | Correspondance N° doc./N° doc. ext. | Correspondance montant avec tolérance |
|------------------|----------|-----------------------|--------------------------------|--------------------------------|
| Élevée             | 1        | Intégrale                 | Oui - Multiple                 | Une correspondance                      |
| Élevée             | 2        | Intégrale                 | Oui - Multiple                 | Correspondances multiples               |
| Élevée             | 3        | Intégrale                 | Oui                            | Une correspondance                      |
| Élevée             | 4        | Intégrale                 | Oui                            | Correspondances multiples               |
| Élevée             | 5        | Partielle             | Oui - Multiple                 | Une correspondance                      |
| Élevée             | 6        | Partielle             | Oui - Multiple                 | Correspondances multiples               |
| Élevée             | 7        | Partielle             | Oui                            | Une correspondance                      |
| Élevée             | 8        | Intégrale                 | Non                             | Une correspondance                      |
| Élevée             | 9        | Non                    | Oui - Multiple                 | Une correspondance                      |
| Élevée             | 10       | Non                    | Oui - Multiple                 | Correspondances multiples               |
| Moyenne           | 1        | Intégrale                 | Oui - Multiple                 | Non applicable                 |
| Moyenne           | 2        | Intégrale                 | Oui                            | Non applicable                 |
| Moyenne           | 3        | Intégrale                 | Non                             | Correspondances multiples               |
| Moyenne           | 4        | Partielle             | Oui - Multiple                 | Non applicable                 |
| Moyenne           | 5        | Partielle             | Oui                            | Non applicable                 |
| Moyenne           | 6        | Non                    | Oui                            | Une correspondance                      |
| Moyenne           | 7        | Non                    | Oui-Multiple                   | Non applicable                 |
| Moyenne           | 8        | Partielle             | Non                             | Une correspondance                      |
| Moyenne           | 9        | Non                    | Oui                            | Non applicable                 |
| Faible              | 1        | Intégrale                 | Non                             | Aucune correspondance                     |
| Faible              | 2        | Partielle             | Non                             | Correspondances multiples               |
| Faible              | 3        | Partielle             | Non                             | Aucune correspondance                     |
| Mauvaises              | 4        | N°                    | N°                             | Une correspondance                      |
| Mauvaises              | 5        | N°                    | N°                             | Correspondances multiples               |

## <a name="see-related-microsoft-trainingtrainingmodulesreconciliation-journals-dynamics-365-business-centralindex" />Voir la [formation Microsoft](/training/modules/reconciliation-journals-dynamics-365-business-central/index) associée

## <a name="see-also" />Voir aussi
[Rapprocher les paiements à l'aide de l'application automatique](receivables-how-reconcile-payments-auto-application.md)  
[Gestion des comptes client](receivables-manage-receivables.md)  
[Vente](sales-manage-sales.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
