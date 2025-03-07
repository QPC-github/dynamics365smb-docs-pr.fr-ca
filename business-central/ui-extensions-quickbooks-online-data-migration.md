---
title: Extension de migration des données QuickBooks Online
description: 'Décrit comment utiliser l''extension pour migrer des clients, des fournisseurs, des articles, et des comptes de QuickBooks Online dans Business Central.'
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'extension, migrate, data, QuickBooks, import'
ms.search.form: '1830,'
ms.date: 06/24/2021
ms.author: bholtorf
---

# <a name="the-quickbooks-online-data-migration-extension" />Extension de migration des données QuickBooks Online

Cette extension est incluse dans le guide de configuration assistée **Migration des données** pour vous aider à migrer les données métier pertinentes de QuickBooks Online vers [!INCLUDE[prod_short](includes/prod_short.md)]. Par exemple, c'est utile si votre activité se développe, et que vous avez décidé de mettre à niveau votre application de gestion d'entreprise en commençant à utiliser [!INCLUDE[prod_short](includes/prod_short.md)].

## <a name="what-data-can-i-import-from-quickbooks-online" />Quelles données puis-je importer de QuickBooks Online ?

Vous pouvez importer les données suivantes de QuickBooks Online vers [!INCLUDE[prod_short](includes/prod_short.md)] :  

* Clients
* Fournisseurs
* Articles
* Plan comptable
* Commencer la transaction de soldes dans le grand livre
* Quantités disponibles pour les articles de l'inventaire
* Ouvrir des documents pour les clients et les fournisseurs, par exemple des factures, des avoirs, et des paiements

Nous effectuons une migration uniquement pour les montants complets dans les documents achat et vente. Nous ne mettons pas à jour les montants partiellement payés. Par exemple, si un client a payé 300 dollars sur un total de 500 dollars dans une facture vente, nous effectuons une migration des 500 complets. Si vous avez reçu des paiements partiels, vous devez les mettre à jour manuellement, avant ou après la migration de données. Nous vous recommandons d'affecter les transactions restantes avant d'exécuter une migration, pour faciliter la suite du processus.

> [!NOTE]  
> Nous n'effectuons pas de migration des commandes achat ou des commandes vente.

## <a name="before-you-start" />Avant de commencer

Une grande partie du processus de migration consiste à spécifier les comptes vers lesquels migrer les transactions. Il est judicieux de planifier ce mappage avant d'exécuter la migration de données. Par exemple, les comptes sur lesquels vous reportez des transactions :  

* La vente d'articles ou de services à un client.
* L'achat d'articles ou de service auprès d'un fournisseur.  
* Ajustements dans le grand livre.  

[!INCLUDE[prod_short](includes/prod_short.md)] nécessite que les comptes généraux aient des numéros de compte. S'assurer que les numéros de compte sont affectés aux comptes dans QuickBooks Online.

Si les transactions de QuickBooks Online ont des montants de taxe, vous devez créer un compte taxes pour vos juridictions fiscales dans [!INCLUDE[prod_short](includes/prod_short.md)] avant de pouvoir reporter des transactions.

## <a name="how-do-i-start-using-the-extension" />Comment commencer à utiliser à l'extension ?

La mise en route est simple. Il vous suffit d'exécuter le guide d'installation assistée **Migration des données**. Voici comment :

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Configuration assistée**, puis choisissez **Migrer les données de l’entreprise**.
2. Suivez les instructions à chaque étape du guide de configuration assistée.

## <a name="what-do-i-do-after-i-migrate-data" />Que faire après une migration des données ?

Après avoir effectué une migration des données, les transactions ont le statut **Non validé**, vous pouvez les consulter et faire des ajustements. Pour consulter les transactions, accédez à la page où vous les trouveriez normalement. Par exemple, pour examiner les factures vente non validées, accédez à la page **Factures vente**. Pour consulter des feuilles paiement, accédez à la page **Feuilles paiement**.  

Il existe quelques éléments en particulier que vous devez effectuer :

* Si les transactions dans QuickBooks Online avaient des montants de majoration ou d'escompte, vous devez ajouter manuellement les montants aux transactions associées dans [!INCLUDE[prod_short](includes/prod_short.md)] avant de les reporter.
* Si vous utilisez la taxe sur la valeur ajoutée (TVA), vous devez ajouter un groupe de report marché et un groupe de report produit à la configuration du report de manière à pouvoir reporter les montants TVA.
* Vérifiez les soldes de début des comptes du grand livre. QuickBooks Online ne stocke pas le solde actuel de tous les comptes, vous pouvez être amené à corriger les soldes d'ouverture.

## <a name="see-related-microsoft-trainingtrainingmodulesmigrate-data-dynamics-365-business-central" />Voir la [formation Microsoft](/training/modules/migrate-data-dynamics-365-business-central/) associée

## <a name="see-also" />Voir aussi .

[Importation des données métier à partir d'autres systèmes financiers](across-import-data-configuration-packages.md)  
[Personnalisation de [!INCLUDE[prod_short](includes/prod_short.md)] à l'aide des extensions](ui-extensions.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
