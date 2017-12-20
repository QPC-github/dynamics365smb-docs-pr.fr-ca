---
title: "Facturation de paiements anticipés | Microsoft Docs"
description: "Les paiements anticipés sont des paiements qui sont facturés et reportés dans une commande paiement anticipé vente ou achat avant la facturation finale. Vous pouvez demander un acompte avant de produire les articles commandés ou demander à ce que le paiement soit effectué avant de livrer les articles à un client. La fonctionnalité d'acomptes vous permet de facturer et de collecter les acomptes requis des clients ou de régler des acomptes aux fournisseurs. Vous pouvez ainsi vous assurer que tous les paiements sont reportés sur une facture."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 08/07/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 2c13559bb3dc44cdb61697f5135c5b931e34d2a8
ms.openlocfilehash: 29e4380312724b08a7e250a65288d75d27444df0
ms.contentlocale: fr-ca
ms.lasthandoff: 09/22/2017

---
# <a name="invoicing-prepayments"></a>Facturation de paiements anticipés
Les paiements anticipés sont des paiements qui sont facturés et reportés dans une commande paiement anticipé vente ou achat avant la facturation finale. Vous pouvez demander un acompte avant de produire les articles commandés ou demander à ce que le paiement soit effectué avant de livrer les articles à un client. La fonctionnalité d'acomptes vous permet de facturer et de collecter les acomptes requis des clients ou de régler des acomptes aux fournisseurs. Vous pouvez ainsi vous assurer que tous les paiements sont reportés sur une facture.  

 Les conditions de paiement anticipé peuvent être définies pour un client ou un fournisseur pour tous les articles ou pour une sélection d'articles. Lorsque vous avez effectué la configuration requise, vous pouvez générer des factures paiement anticipé à partir des documents de vente et des bons de commande pour le montant paiement anticipé calculé. Au besoin, vous pouvez modifier les montants dans la facture. Par exemple, vous pouvez spécifier un montant total pour la commande entière. Vous pouvez également envoyer des factures paiement anticipé supplémentaires si, par exemple, des articles supplémentaires sont ajoutés à la commande. Vous pouvez augmenter les quantités ou ajouter de nouvelles lignes dans une commande après avoir émis un paiement anticipé, puis vous pouvez reporter une autre facture paiement anticipé. Si vous souhaitez supprimer une ligne pour laquelle un paiement anticipé a déjà été facturé, vous devez émettre une note de crédit paiement anticipé avant de la supprimer.  

 Le tableau suivant décrit une série de tâches et inclut des liens vers les rubriques qui les décrivent.

|**Pour**|**Voir**|  
|------------|-------------|  
|Configurez les groupes de report de paiement anticipé et les séries de numéros, et paramétrez les pourcentages de paiement anticipé par défaut pour les clients, fournisseurs et articles.|[Procédure : configurer des paiements anticipés](finance-set-up-prepayments.md)|
|Créer une commande, ajuster des montants paiement anticipé et émettre une facture pour les montants paiement anticipé.|[Procédure : créer des factures de paiement anticipé](finance-how-to-create-prepayment-invoices.md)|  
|Émettre une facture paiement anticipé supplémentaire, pour des articles supplémentaires ou pour un paiement anticipé supplémentaire dans la commande originale, ou émettre une note de crédit paiement anticipé.|[Procédure : corriger des acomptes](finance-how-to-correct-prepayments.md)|  

## <a name="see-also"></a>Voir aussi  
[Procédure pas à pas : configuration et facturation d'acomptes](walkthrough-setting-up-and-invoicing-sales-prepayments.md)  
[Finance](finance.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
