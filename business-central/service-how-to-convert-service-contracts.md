---
title: Comment convertir les contrats de service
description: Cette rubrique décrit plusieurs autres méthodes pour convertir les contrats de service qui incluent les montants de TVA.
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: null
ms.date: 06/23/2021
ms.author: edupont
---
# <a name="convert-service-contracts-that-include-vat-amounts" />Convertir les contrats de service incluant des montants TVA
Étant donné que l'outil de modification du taux de TVA ne peut pas convertir les contrats de service, ces derniers doivent être convertis manuellement. Cette rubrique décrit plusieurs autres méthodes pour convertir les contrats de service.  

> [!NOTE]  
>  Cette rubrique montre un flux de haut niveau.  

 La procédure suivante décrit comment corriger une facture pour un contact de service prépayé, qui a été créé une année à l'avance.  

> [!NOTE]  
>  Pour cet exemple, vous devez modifier la date de travail sur 01.01.2017.  

### <a name="to-correct-an-invoice-for-a-prepaid-service-contract" />Pour corriger une facture pour un contrat de service prépayé
1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Gestion de contrats**, puis sélectionnez le lien associé.  
2. Sous l'onglet **Listes**, choisissez **Contrats de service**.  
3. Créez un modèle contrat de service prépayé. Saisissez une date de début **01.01.2017** et une année pour la période de facturation du client **20000**.  
4. Pour signer le contrat, sélectionnez l'action **Signer le contrat**.  
5. Créez une facture service.
6. La facture est répertoriée en tant que facture de service non reportée. Pour afficher la facture de service, sélectionnez l'action **Service**, l'action **Gestion des contrats**, puis l'action **Factures service**.  
7. Reportez la facture service.  

> [!NOTE]  
>  Ne modifiez pas la facture de service non reportée. Étant donné que les écritures service sont créées avec la facture, une modification de la facture non reportée ne modifiera pas les écritures service existantes. Cependant, les écritures TVA sont créées lorsqu'une facture est reportée. Ainsi, vous pouvez modifier les groupes de report produit général et GSP sur la facture de service non reportée.  

### <a name="to-create-a-credit-memo-for-vat-difference" />Pour créer une note de crédit pour la différence TVA
La procédure suivante décrit comment créer un avoir, qui comprend uniquement la différence TVA pour la période déjà facturée en commençant le **01.07.2017**. Dans cet exemple, le montant TVA est uniquement reporté sur le module Gestion financière et non sur le module Gestion des services. Les écritures TVA liées à l'écriture service ne seront pas corrigées.  

1. Créez un compte du grand livre pour la différence de TVA. Ce compte sera utilisé pour le report direct de la correction TVA.  
2. Ajoutez une nouvelle ligne à la configuration du report TVA.  

### <a name="to-create-contract-expiration-dates-in-contract-lines" />Pour créer des dates d'expiration de contrats sur les lignes correspondantes
La procédure suivante indique comment créer des contrats en utilisant leurs dates d'expiration dans les lignes correspondantes.  

1. Sur la page **Contrat de service**, définissez la date d'expiration du contrat sur **30.06.2017**.  
2. Choisissez l'action **Créer note de crédit** pour créer automatiquement une note de crédit de juillet 2017 à décembre 2017.  
3. Étant donné que le contrat expire, vous devez créer un contrat pour la période avec le nouveau taux de TVA du 1er juillet 2017 au 31 décembre 2017.  

### <a name="to-create-a-new-credit-memo" />Pour créer une note de crédit
La procédure suivante décrit comment créer un avoir à l'aide du traitement par lots **Obtenir écr. contrat prépayé**. Les écritures que vous ne souhaitez pas corriger de janvier 2017 à juin 2017 seront supprimées.  

1. Exécutez l'outil de modification du taux de TVA au 1er juillet 2017. Le groupe de report produit général ou le groupe de report produit TVA est modifié. Pour plus d'informations, voir [Utiliser la TVA sur les ventes et les achats](finance-work-with-vat.md).  
2. Après avoir exécuté l'outil de modification du taux de TVA, saisissez une date d'expiration pour le contrat de service. Vous pouvez désormais supprimer la ligne du contrat de service et en créer une qui soit identique à la précédente.  
3. Créez une facture pour la période s'échelonnant de janvier 2017 à décembre 2012 avec le nouveau taux de TVA.  
4. Pour créer une autre note de crédit, sur la page **Notes de crédit service**, choisissez l'action **Nouveau** pour créer une note de crédit de service.  
5. Choisissez l'action **Obtenir écr. contrat prépayé**.  
6. Une fois la conversion terminée, les écritures TVA et service seront correctes.  

## <a name="see-also" />Voir aussi
[Utiliser des contrats de service et des devis contrat de service](service-how-to-create-service-contracts-and-service-contract-quotes.md)  
[Finance](finance.md)  
[Déclarer la TVA aux autorités fiscales](finance-how-report-vat.md)  
[Utiliser la TVA sur les ventes et les achats](finance-work-with-vat.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
