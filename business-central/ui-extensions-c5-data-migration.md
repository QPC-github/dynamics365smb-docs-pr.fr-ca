---
title: Utilisation de l'extension C5 Data Migration | Microsoft Docs
description: 'Utilisez cette extension pour migrer des clients, des fournisseurs, des articles et des comptes GL de Microsoft Dynamics C5 2012 vers Business Central.'
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'extension, migrate, data, C5, import'
ms.search.form: '1860, 1861, 1862, 1863, 1864, 1867, 1868, 1869, 1874, 1882, 1883, 1884, 1885, 1886, 1888, 1890, 1891, 1892, 1893, 1894, 1898, 1899, 1900, 1901, 1902, 1903, 1904, 1905, 1906'
ms.date: 04/01/2021
ms.author: bholtorf
---

# <a name="the-c5-data-migration-extension" />Extension C5 Data Migration

Cette extension facilite la migration de clients, de fournisseurs, d’articles et de vos comptes GL de Microsoft Dynamics C5 2012 vers [!INCLUDE[prod_short](includes/prod_short.md)]. Vous pouvez également migrer des écritures historiques pour des comptes GL.

> [!NOTE]
> La compagnie dans [!INCLUDE[prod_short](includes/prod_short.md)] ne doit pas contenir de données. En outre, après avoir commencé une migration, ne créez pas de clients, de fournisseurs, d'articles, ou de comptes jusqu'à la fin de la migration.

## <a name="what-data-is-migrated" />Quelles données sont migrées ?

Les données suivantes sont migrées pour chaque entité :

### <a name="customers" />Clients

* Contacts  
* Magasin
* Pays
* Dimensions client (service, centre, objectif)
* Méthode de livraison
* Vendeur
* Modalités de paiement
* Mode de règlement
* Groupe prix client
* Escompte facture client

Si vous migrez des comptes, les données suivantes sont également migrées :

* Configuration du report client
* Lot journal général
* Transactions ouvertes (écritures client)

### <a name="vendors" />Fournisseurs

* Contacts
* Magasin
* Pays
* Dimensions fournisseur (service, centre, objectif)
* Escompte de la facture
* Méthode de livraison
* Acheteur
* Modalités de paiement
* Mode de règlement
* Escompte de facture fournisseur

Si vous migrez des comptes, les données suivantes sont également migrées :

* Configuration du report fournisseur
* Lot journal général
* Transactions ouvertes (écritures fournisseur)

### <a name="items" />Articles

* Magasin
* Pays
* Dimensions article (service, centre, objectif)
* Escomptes de ligne de vente
* Groupes escompte client
* Groupes d'escompte sur article
* Prix vente
* Nomenclature produits
* Unités de mesure
* Code traçabilité
* Groupe prix client
* Nomenclatures d'assemblage

Si vous migrez des comptes, les données suivantes sont également migrées :

* Configuration du report d'inventaire
* Configuration report général
* Lot journal article
* Transactions ouvertes (écritures article)

> [!NOTE]
> S'il existe des transactions ouvertes qui utilisent des devises étrangères, les taux de change pour les devises sont également migrés. Les autres taux de change ne sont pas migrés.

### <a name="chart-of-accounts" />Plan comptable

* Dimensions standard : département, centre de coût, objectif  
* Transactions GL historiques  

> [!NOTE]
> Les transactions GL historiques sont traitées un peu différemment. Lorsque vous migrez des données, vous définissez un paramètre **Période courante**. Ce paramètre spécifie comment traiter les transactions GL. Les transactions postérieures à cette date sont migrées individuellement. Les transactions antérieures à cette date sont regroupées par compte et migrées en tant que montant unique. Par exemple, supposons qu'il existe des transactions en 2015, 2016, 2017, 2018 et que vous spécifiez le 01 janvier 2017 dans le champ Période courante. Pour chaque compte, les montants des transactions effectuées au plus tard le 31 décembre 2106 sont regroupés sur une ligne journal général unique pour chaque compte du grand livre. Toutes les transactions postérieures à cette date sont migrées individuellement.

## <a name="file-size-requirements" />Besoins de taille de fichier

La plus grande taille de fichier que vous pouvez télécharger dans [!INCLUDE[prod_short](includes/prod_short.md)] est de 150 Mo. Si le fichier que vous exportez de C5 est supérieur à cela, envisagez de migrer les données dans plusieurs fichiers. Par exemple, exportez un ou deux types d'entités de C5, tels que les clients et les fournisseurs, dans un fichier, puis exportez les articles vers un autre fichier, etc.. Vous pouvez importer des fichiers individuellement dans [!INCLUDE[prod_short](includes/prod_short.md)].

## <a name="to-migrate-data" />Pour migrer des données

Quelques étapes suffisent pour exporter des données de C5 et les importer dans [!INCLUDE[prod_short](includes/prod_short.md)]:  

1. Dans C5, utilisez la fonctionnalité **Exporter la base de données** pour exporter les données. Envoyez ensuite le fichier d'exportation vers un fichier compressé (zippé).  
2. Dans [!INCLUDE[prod_short](includes/prod_short.md)], sélectionnez l’![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Migration de données**, puis choisissez **Migration de données**.  
3. Exécutez les étapes du guide de configuration assistée. Veillez à choisir **Importer à partir de Microsoft Dynamics C5 2012** comme source de données.  

## <a name="viewing-the-status-of-the-migration" />Affichage de l'état de la migration

Utilisez la page **Vue d’ensemble de la migration des données** pour contrôler la réussite de la migration. La page affiche des informations telles que le nombre d’entités incluses dans la migration, l'état de la migration, ainsi que le nombre d’articles qui ont été migrés et l’état de réussite de leur migration. Elle affiche également le nombre d'erreurs, ce qui vous permet d'étudier ce qui ne s'est pas passé correctement et, si possible, d'accéder facilement à l'entité pour résoudre les problèmes. Pour plus d'informations, voir la section suivante de cette rubrique.  

> [!NOTE]
> Pendant que vous attendez les résultats de la migration, vous devez actualiser la page pour afficher les résultats.

## <a name="how-to-avoid-double-posting" />Comment éviter le double report

Pour éviter le double report dans le grand livre, les comptes de solde suivants sont utilisés pour les transactions ouvertes :  

* Pour les fournisseurs, nous utilisons le compte Comptabilité fournisseur dans le groupe de report fournisseur.  
* Pour les clients, nous utilisons le compte Comptabilité client dans le groupe de report client.  
* Pour les articles, nous créons une configuration de report générale dans laquelle le compte ajustement est le compte spécifié comme compte inventaire dans la configuration du report d'inventaire.  

## <a name="correcting-errors" />Correction des erreurs

Si quelque chose se passe mal et qu'une erreur survient, le champ **État** affiche **Terminé avec des erreurs**, et le champ **Nombre d'erreurs** en indique le nombre. Pour afficher la liste des erreurs, vous pouvez ouvrir la page **Erreurs de migration des données** en sélectionnant :  

* le nombre dans le champ **Nombre d'erreurs** pour l'entité.  
* l'entité, puis l'action **Afficher les erreurs**.  

Sur la page **Erreurs de migration des données**, pour corriger une erreur vous pouvez sélectionner un message d'erreur, puis **Modifier l'enregistrement** pour afficher les données migrées pour l'entité. Si vous avez plusieurs erreurs à résoudre, vous pouvez choisir **Erreurs de correction en bloc** pour modifier les entités dans la liste. Vous devez toujours ouvrir les enregistrements individuellement si l'erreur est due à une écriture associée. Par exemple, un fournisseur ne sera pas migré si une adresse de courriel de l'un de ses contacts a un format non valide.

Après avoir corrigé une ou plusieurs erreurs, vous pouvez sélectionner **Migrer** pour migrer uniquement les entités que vous avez corrigées, sans entièrement redémarrer la migration.  

> [!TIP]
> Si vous avez corrigé plusieurs erreur, vous pouvez utiliser la fonctionnalité **Sélectionner davantage** pour sélectionner plusieurs lignes à migrer. Sinon, s'il existe des erreurs qu'il n'est pas important de corriger, vous pouvez les sélectionner, puis cliquer sur **Ignorer les sélections**.

> [!NOTE]
> Si vous avez des articles inclus dans une nomenclature, vous pouvez être amené à effectuer la migration plus d'une fois si l'article d'origine n'est pas créé avant les variantes qui y font référence. Si une variante article est créée en premier lieu, la référence à l'article d'origine peut entraîner un message d'erreur.  

## <a name="verifying-data-after-migrating" />Vérifier les données après avoir effectué une migration

Si vous souhaitez vérifier que vos données ont été migrées correctement, vous pouvez consulter les pages suivantes dans C5 et [!INCLUDE[prod_short](includes/prod_short.md)].

|Microsoft Dynamics C5 2012 | Dynamics 365 Business Central| Traitement en lot à utiliser |
|---------------------------|------------------------------|------------------|
|Écritures client| Journaux généraux| CUSTMIGR |
|Écritures fournisseur| Journaux généraux| VENDMIGR|
|Ecritures article| Journaux article| ITEMMIGR |
|Écritures| Journaux généraux| GLACMIGR |

## <a name="stopping-data-migration" />Arrêter la migration des données

Vous pouvez arrêter de migrer les données en sélectionnant **Arrêter toutes les migrations**. Si vous le faites, toutes les migrations en attente sont également arrêtées.

## <a name="see-also" />Voir aussi .

[Personnalisation de [!INCLUDE[prod_short](includes/prod_short.md)] à l'aide des extensions](ui-extensions.md)  
[Préparation aux activités commerciales](ui-get-ready-business.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
