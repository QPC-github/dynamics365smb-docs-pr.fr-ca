---
title: "Réponse aux demandes relatives aux données personnelles"
description: "Vous devez répondre aux demandes des sujets des données."
author: bholtorf
ms.service: dynamics365-business-central
ms.author: bholtorf
ms.custom: na
ms.date: 05/25/2018
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.translationtype: HT
ms.sourcegitcommit: 2286b728a464943841b192031cfea13644441013
ms.openlocfilehash: b90577cbab4167894fe79a3e8e8a0c61ce8c70e9
ms.contentlocale: fr-ca
ms.lasthandoff: 06/28/2018

---

# <a name="responding-to-requests-about-personal-data"></a>Réponse aux demandes relatives aux données personnelles  
Les sujets des données peuvent demander plusieurs types d'actions concernant leurs données personnelles. Par exemple, en vertu du Règlement général sur la protection des données (RGPD), les résidents de l'UE ont le droit de demander l'exportation, la suppression et la modification de leurs données personnelles. Cela est appelé *Demande du sujet des données*. Si vous avez classé la sensibilité de vos données et si vous êtes sûr qu'elles sont correctes, un administrateur peut répondre aux demandes à l'aide des options disponibles sous **Confidentialité des données** dans le tableau de bord **Gérer les utilisateurs, les groupes d'utilisateurs et les autorisations** ou, si vous utilisez le client Windows, dans le tableau de bord **Responsable informatique**. Pour plus d'informations sur la classification des données et la classification de la sensibilité des données dans [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)], voir [Classification des données](/dynamics-nav/classifying-data?toc=/dynamics365/business-central/toc.json) et [Classification de la sensibilité des données](admin-classifying-data-sensitivity.md).  

## <a name="types-of-requests"></a>Types de demandes

Le tableau suivant donne des exemples des types de demandes auxquelles vous pouvez répondre.

> [!Note]
> Nous fournissons des fonctionnalités pour répondre à ces types de demande et permettre l'accès aux données personnelles, mais il vous incombe de veiller à ce que vos données personnelles et sensibles soient stockées et classées de manière appropriée.

|Type de demande|Description et réponse suggérée|
|-----|-----|
|Demandes de portabilité|Un sujet des données peut faire une demande de portabilité des données, ce qui signifie que vous devez exporter les données personnelles du sujet des données à partir de vos systèmes et les fournir dans un format couramment utilisé et structuré. Pour répondre à ces demandes, vous pouvez utiliser l'**Utilitaire de confidentialité des données** pour exporter les données personnelles vers un fichier Excel ou un package de configuration RapidStart. À l'aide d'Excel, vous pouvez modifier les données personnelles et les enregistrer dans un format couramment utilisé et lisible par machine, par exemple .csv ou .xml. Pour les packages de configuration RapidStart, vous pouvez configurer les tables de données principales et leurs tables associées contenant des données personnelles. <br><br> **Remarque :** lorsque vous exportez des données, vous spécifiez un niveau de sensibilité minimal. L'exportation inclut le niveau de sensibilité minimal et tous les niveaux de sensibilité au-dessus de celui-ci. Par exemple, si vous choisissez d'exporter des données classées comme personnelles, l'exportation inclut également les données classées comme sensibles. <br><br>Lors de l'exportation des données associées à un sujet de données, l'**Utilité de confidentialité des données** recherche des relations directes entre le sujet de données et les données qui lui sont associées. Les relations indirectes entre les données associées au sujet de données et les autres données ne sont pas exportées automatiquement par l'**Utilité de confidentialité des données**. Par exemple, la table Contact a directement associé les données Réponses profil contact, et la table Réponses profil contact est ensuite associée aux données Questions profil. Si vous souhaitez exporter également les questions de profil, vous devez ajouter manuellement cette table en tant que ligne avec les filtres appropriés dans le package de configuration créé par l'**Utilité de confidentialité des données**.|
|Demandes de suppression|Un sujet des données peut demander la suppression de ses données personnelles. Il existe plusieurs méthodes de suppression des données personnelles à l'aide des fonctions de personnalisation, mais la décision et l'implémentation vous incombent. Dans certains cas, vous pouvez choisir de modifier directement vos données, par exemple en supprimant un contact et en exécutant ensuite le traitement en lot Supprimer l'interaction annulée pour supprimer les interactions du contact. <br><br> **Remarque :** si vous avez spécifié une date dans le champ **Autoriser suppr. doc. av.** des pages **Configuration ventes et à recevoir** ou **Configuration achats et à payer**, vous devrez peut-être modifier la date afin de pouvoir supprimer les documents vente et achat reportés que vous avez imprimés et dont les dates de report sont au plus tard à cette date.|
|Demandes de correction|Un sujet des données peut demander la correction des données personnelles incorrectes. Plusieurs méthodes sont possibles. Dans certains cas, vous pouvez exporter des listes vers Excel afin de modifier en bloc plusieurs enregistrements et importer les données mises à jour. Pour plus d'informations, voir [Exportation de vos données métier vers Excel](about-export-data.md). Vous pouvez également modifier manuellement les champs contenant des données personnelles, par exemple modifier les informations sur un client dans la fiche Client. Toutefois, les enregistrements de transaction comme les écritures générales, client et taxe sont essentiels à l'intégrité du système de planification des ressources de l'entreprise. Si vous stockez des données personnelles dans les enregistrements de transaction, pensez à utiliser les fonctions de personnalisation pour modifier ces données personnelles.|

## <a name="restrict-data-processing-for-a-data-subject"></a>Restreindre le traitement des données pour un sujet des données
Un sujet des données peut demander l'arrêt temporaire du traitement de ses données personnelles. Pour honorer ces demandes, vous pouvez marquer son enregistrement comme bloqué pour des raisons de confidentialité afin d'arrêter le traitement de ses données. Lorsqu'un enregistrement est marqué comme bloqué, vous ne pouvez pas créer des transactions qui utilisent cet enregistrement. Par exemple, vous ne pouvez pas créer une facture pour un client lorsque le client ou le représentant est bloqué. Pour marquer un sujet des données comme bloqué, ouvrez la fiche correspondante, par exemple les fiches Client, Fournisseur ou Contact, puis activez la case à cocher **Confidentialité bloquée**. Vous devez peut-être choisir **Afficher plus** pour afficher le champ.  

## <a name="handling-data-subject-requests-while-in-trial"></a>Gestion des demandes de sujets de données dans une version d'évaluation
Certains types de données personnelles font partie de votre compte Office 365 et nécessitent un accès administratif pour les exporter, si vous recevez une demande de sujet de données d'un utilisateur concernant ce type de données personnelles dans le cadre du Règlement général sur la protection des données (RGPD). Le processus de gestion des demandes de sujets de données diffère selon le type d'abonné [!INCLUDE[d365fin](includes/d365fin_md.md)].  

Si vous disposez d'un abonnement payant pour [!INCLUDE[d365fin](includes/d365fin_md.md)], vous devez contacter l'administrateur abonné de votre organisation pour faire une demande de sujet de données. L'administrateur dispose des droits et outils d'administration pour traiter votre demande.  

Si vous vous êtes inscrit à [!INCLUDE[d365fin](includes/d365fin_md.md)] à partir de la page [Versions d'évaluation](https://trials.dynamics.com/), et si vous n'avez pas changé cette version d'évaluation via un abonnement payant par l'administrateur abonné de votre organisation, vous pouvez traiter votre propre demande de sujet de données dans la [page Confidentialité au travail et à l'école du portail Azure](https://portal.azure.com#blade/Microsoft_AAD_IAM/GDPRViralBlade). Vous pouvez exporter et télécharger vos données personnelles.

Sur la page Confidentialité au travail et à l'école, vous pouvez également fermer votre compte. Toutefois, il est recommandé de vérifier que vous avez exporté et supprimé au préalable toutes les données, car la suppression de votre compte implique que vous n'avez plus accès à [!INCLUDE[d365fin](includes/d365fin_md.md)].  

Vous pouvez toujours marquer des personnes comme bloquées pour des raisons de confidentialité et exporter, modifier ou supprimer des transactions, comme expliqué ailleurs dans cet article.  

## <a name="exporting-data-from-tables-not-classified-by-data-subject"></a>Exportation de données à partir de tables non classées par sujet de données
Si vous devez exporter des données non classées de manière à pouvoir les exporter automatiquement, par exemple les données de la table Réponses profil, vous devez procéder comme suit : 
-   Demandez-vous si vous souhaitez ou devez vraiment exporter ces données supplémentaires qui n'ont aucun rapport avec le contact, c'est-à-dire sans relation directe avec lui. 
-   Ajoutez cette table et cette relation manuellement au package Rapid Start et exportez-les directement à partir du package Rapid Start. Nous générons un package Rapid Start pour vous, afin que vous puissiez le modifier dans de telles situations.

## <a name="handling-data-about-minors"></a>Gestion des données concernant les mineurs
Si l'âge d'un contact est inférieur à l'âge de consentement légal défini par les lois de votre région, vous pouvez l'indiquer en activant la case à cocher **Mineur** sur la fiche **Contact**. La case à cocher **Confidentialité bloquée** est alors automatiquement activée. Lorsque vous recevez l'accord du parent ou du tuteur légal du mineur, vous pouvez activer la case à cocher **Accord parental reçu** pour débloquer le contact. Même si vous pouvez traiter les données personnelles des mineurs, vous ne pouvez pas utiliser la fonctionnalité de profilage dans Microsoft Dynamics 365 for Sales.

> [!Note]
> Le journal des modifications peut enregistrer des détails, par exemple quand et par qui la case à cocher **Accord parental reçu** a été activée. Un administrateur peut le configurer en utilisant le guide **Configuration du journal de modification** et en activant la case à cocher **Modification du journal pour l'accord parental reçu** sur la fiche **Contact**. Pour plus d'informations, voir [Journalisation des modifications](across-log-changes.md).  

## <a name="see-also"></a>Voir aussi
[Classification des données](/dynamics-nav/classifying-data?toc=/dynamics365/business-central/toc.json)  
[Classification de la sensibilité des données](admin-classifying-data-sensitivity.md)  
[Exportation de vos données métier vers Excel](about-export-data.md)  
[Journalisation des modifications](across-log-changes.md)  
[Demandes de sujet de données pour le RGPD](/microsoft-365/compliance/gdpr-data-subject-requests)  
