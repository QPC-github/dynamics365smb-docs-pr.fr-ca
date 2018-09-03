---
title: "Exécuter les paiements avec le service de conversion de données bancaires ou un virement SEPA | Microsoft Docs"
description: "Traitez les paiements à vos fournisseurs en exportant un fichier avec les informations de paiement provenant des lignes journal."
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 11/17/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: 99277cb2daf37fbce4548cf637e8967fa6688dbc
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="making-payments-with-bank-data-conversion-service-or-sepa-credit-transfer"></a>Exécution de paiements avec le service de conversion de données bancaires ou un virement SEPA
Dans la fenêtre **Feuille paiement**, vous pouvez traiter les paiements à vos fournisseurs en exportant un fichier avec les informations de paiement provenant des lignes feuille. Vous pouvez ensuite télécharger le fichier vers votre banque électronique, où sont traités les transferts d'argent associés. [!INCLUDE[d365fin](includes/d365fin_md.md)] prend en charge le format de virement SEPA, mais dans votre pays/région, d'autres formats de paiements électroniques peuvent être disponibles.   

 Pour activer les virements SEPA, vous devez d'abord créer un compte bancaire, un fournisseur, et le lot de journal général sur lequel le journal de paiements est basé. Vous préparez ensuite les paiements aux fournisseurs en renseignant automatiquement la fenêtre **Feuille paiement** avec les paiements dus aux dates comptabilisation spécifiées.  

> [!NOTE]  
>  Lorsque vous avez vérifié que les paiements sont traités avec succès par la banque, vous pouvez passer aux lignes journal des paiements.  

 Le tableau suivant décrit une série de tâches et inclut des liens vers les rubriques qui les décrivent.   

|**Pour**|**Voir**|  
|------------|-------------|  
|Activez la fonctionnalité du service de conversion de données bancaires pour convertir les fichiers de relevé bancaire dans un format que vous pouvez importer, ou pour convertir les fichiers de paiement exportés au format imposé par votre banque.|[Configurer le service de conversion de données bancaires](bank-how-setup-bank-statement-service.md)|  
|Configurez un compte bancaire, un fournisseur et un journal des paiements pour le virement SEPA.|[Configurer des virements SEPA](finance-how-to-set-up-sepa-credit-transfer.md)|  
|Remplissez le journal paiement avec des lignes pour les paiements dus aux fournisseurs, avec la possibilité d'insérer des dates report sur la base de la date d'échéance des documents achat associés.|[Gestion des comptes fournisseur](payables-manage-payables.md)|  
|Exportez les lignes journal paiement dans un fichier au format virement SEPA.|[Exporter des paiements vers un fichier bancaire](payables-how-export-payments-bank-file.md)|  
|Lorsque le paiement électronique est traité avec succès par la banque, reportez les paiements.|[Utilisation de feuilles comptabilité](ui-work-general-journals.md)|  

## <a name="see-also"></a>Voir aussi  
[Configurer le service de conversion de données bancaires](bank-how-setup-bank-statement-service.md)  
[Configurer des virements SEPA](finance-how-to-set-up-sepa-credit-transfer.md)  
[Gestion des comptes fournisseur](payables-manage-payables.md)   
[Utilisation de feuilles comptabilité](ui-work-general-journals.md)  
[Recouvrement de paiements par prélèvement automatique SEPA](finance-collect-payments-with-sepa-direct-debit.md)   
