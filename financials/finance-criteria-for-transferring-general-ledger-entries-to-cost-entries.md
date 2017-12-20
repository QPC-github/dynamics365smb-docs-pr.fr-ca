---
title: "Critères de transfert des écritures GL vers les écritures de coûts | Microsoft Docs"
description: "Il est important de comprendre les critères pour le transfert des écritures aux écritures de coûts. Lors du transfert, le traitement en lot **Transférer les écritures vers CA** applique les critères suivants pour déterminer si les écritures sont transférées et comment."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 07/01/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 2c13559bb3dc44cdb61697f5135c5b931e34d2a8
ms.openlocfilehash: 59faad50504bff05e6cdb1c78d00553e85faf47e
ms.contentlocale: fr-ca
ms.lasthandoff: 09/22/2017

---
# <a name="criteria-for-transferring-general-ledger-entries-to-cost-entries"></a>Critères de transfert des écritures vers les écritures de coûts
Il est important de comprendre les critères pour le transfert des écritures aux écritures de coûts. Lors du transfert, le traitement par lots pour **Transférer les écritures comptables vers CA** applique les critères suivants pour déterminer si les écritures comptables sont transférées et comment.  

Les écritures sont transférées si :  

-   Les écritures ont des valeurs de dimension correspondant à un centre de coûts ou à un objet de coûts.  
-   Les écritures ont des valeurs de dimension correspondant à un centre de coûts et à un objet de coûts. Pour ces écritures, le centre de coûts est prioritaire. Vous pouvez ainsi éviter qu'un type de coût apparaisse à la fois dans un objet de coûts et dans un centre de coûts, ce qui le comptabiliserait deux fois dans les statistiques.  
-   Le numéro de document dans les écritures est vide. C'est pourquoi, il s'affichera avec le numéro de document 0000 dans les écritures de coûts.  
-   Les écritures sont transférées vers un type de coût qui autorise les écritures combinées. Ces écritures sont transférées ainsi sur une base mensuelle ou journalière.  

Les écritures ne sont pas transférées si :  

-   Les écritures ont des valeurs de dimension ne correspondant ni à un centre de coûts ni à un objet de coûts.  
-   Les écritures sont égales à zéro.  
-   Les écritures ont un compte du grand livre qui a été supprimé.  
-   Les écritures ont un compte général qui n'est pas du type **Comptes de gestion**.  
-   Les écritures ont un compte du grand livre sans type de coût affecté.  
-   La date de report des écritures est antérieure à la **Date début pour transfert grand livre**.  
-   Les écritures ont été reportées avec une date de fermeture. Il s'agit généralement des écritures qui redéfinissent le solde des états des résultats sur la fin de l'exercice.  

## <a name="see-also"></a>Voir aussi  
[Comptabilité pour les coûts](finance-manage-cost-accounting.md)  
 [Comment transférer les écritures comptables vers les écritures de coûts](finance-how-to-transfer-general-ledger-entries-to-cost-entries.md)   
 [Transfert et report des écritures de coûts](finance-transfer-and-post-cost-entries.md)   
 [À propos de la comptabilité analytique](finance-about-cost-accounting.md)  
 [Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
