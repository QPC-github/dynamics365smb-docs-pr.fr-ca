---
title: Rapprocher des comptes bancaires et affecter des paiements | Microsoft Docs
description: "Décrit les tâches de rapprochement de vos comptes bancaires, client et fournisseur, reporter des règlements ou des frais et affecter des paiements automatiquement."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: payment process, direct payment posting, reconcile payment, expenses, cash receipts
ms.date: 02/28/2018
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: 992e51f11d11b86685cf6de813e0b7610350a6a7
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="applying-payments-automatically-and-reconciling-bank-accounts"></a>Lettrage automatique des paiements et rapprochement des comptes bancaires
Vous devez régulièrement rapprocher vos comptes bancaires, créances client et créances fournisseur dans Project en lettrant les paiements enregistrés au niveau de la banque à leurs factures impayées et avoirs associés ou à d'autres écritures ouvertes dans [!INCLUDE[d365fin](includes/d365fin_long_md.md)].  

Vous pouvez effectuer cette tâche dans la fenêtre **Feuille rapprochement bancaire** en important un fichier ou un flux de relevé bancaire pour enregistrer rapidement les paiements. Les paiements sont affectés aux écritures client ou fournisseur ouvertes selon les correspondances entre le texte de paiement et les informations d'écriture. Vous pouvez réviser et modifier les affectations automatiques avant de reporter le journal. Vous pouvez choisir de fermer les écritures de compte bancaire ouvertes associées aux écritures affectées lorsque vous reportez le journal. Le compte bancaire est automatiquement rapproché lorsque tous les paiements sont affectés.

Vous pouvez également rapprocher des comptes bancaires sans rapprocher simultanément des paiements. Vous effectuez ce travail dans la fenêtre **Rapprochement bancaire**. Pour plus d'informations, reportez vous à [Rapprocher des comptes bancaires séparément](bank-how-reconcile-bank-accounts-separately.md).   

Pour importer des relevés bancaires en tant que flux bancaire, vous devez d'abord configurer et activer le service de flux de la Envestnet Yodlee Bank, puis associer vos comptes bancaires aux comptes bancaires connexes en ligne. Pour plus d'informations, voir [Configurer le service de flux de la Envestnet Yodlee Bank](bank-how-setup-bank-statement-service.md).  

Vous pouvez également utiliser le service conversion données bancaires pour convertir un fichier de relevé bancaire, à partir de n'importe quel format, en flux de données que vous pouvez importer dans [!INCLUDE[d365fin](includes/d365fin_long_md.md)]. Pour plus d'informations, voir [Configurer le service de conversion de données bancaires](bank-how-setup-bank-data-conversion-service.md).  

Le tableau suivant décrit une série de tâches et inclut des liens vers les rubriques qui les décrivent.  

| À | Voir |
| --- | --- |
| Affecter des paiements aux écritures client ou fournisseur ouvertes en important un relevé de compte bancaire, et rapprocher le compte bancaire lorsque tous les paiements sont affectés. |[Rapprocher les paiements à l'aide de l'affectation automatique](receivables-how-reconcile-payments-auto-application.md) |
| Appliquer manuellement les paiements en affichant des informations détaillées sur les données de correspondance et des suggestions d'écritures ouvertes candidates auxquelles affecter des paiements. |[Réviser ou affecter les paiements après une affectation automatique](receivables-how-review-apply-payments-auto-application.md) |
| Résoudre les paiements qui ne peuvent pas être affectés automatiquement à leurs écritures ouvertes associées. Par exemple si les montants sont différents ou si une écriture associée n'existe pas. |[Rapprocher les paiements qui ne peuvent pas être affectés automatiquement](receivables-how-reconcile-payments-cannot-apply-auto.md) |
| Lier le texte des paiements à des comptes client, fournisseur ou grand livre spécifiques, pour toujours reporter les dépenses ou réceptions récurrentes en liquide sur ces comptes quand ils ne peuvent être affectés à aucun document. |[Mapper du texte sur les paiements récurrents aux comptes pour un rapprochement automatique](receivables-how-map-text-recurring-payments-accounts-auto-reconcilliation.md) |

## <a name="see-also"></a>Voir aussi
[Gestion des comptes client](receivables-manage-receivables.md)  
[Ventes](sales-manage-sales.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
