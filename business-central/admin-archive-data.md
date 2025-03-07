---
title: L’extension d’archivage de données
description: L’archivage des données crée une sauvegarde à faible coût de vos enregistrements.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bknudsen
ms.topic: conceptual
ms.date: 01/30/2023
ms.custom: bap-template
ms.search.form: 630
---

# <a name="the-data-archive-extension" />L’extension d’archivage de données

Au fil du temps, votre entreprise accumulera une quantité substantielle de données et, en tant qu’administrateur, il est probablement judicieux d’avoir une stratégie d’archivage des données. Avoir beaucoup de données peut ralentir les choses. Par exemple, il peut falloir un peu plus de temps pour générer des rapports, ou même pour verrouiller des enregistrements. De plus, de grandes quantités de données peuvent entraîner une augmentation des coûts de stockage.

L’extension Data Archive fournit une infrastructure de base pour l’archivage et la sauvegarde des données dans le cadre de la compression selon la date. La compression de données regroupe les entrées associées en une seule entrée et supprime les originaux. Pour plus d’informations, voir [Compresser les données avec la compression selon la date](admin-manage-documents.md#compress-data-with-date-compression). Cependant, il peut être utile de conserver ces données, donc plutôt que de les supprimer, vous pouvez les archiver pour les utiliser ultérieurement.

## <a name="start-archiving-data" />Démarrer l’archivage des données

L’extension est pré-installée et disponible dans la **Gestion des extensions**, vous n’avez donc rien à faire pour commencer. L’extension est également disponible sur AppSource.

Vos archives de données sont répertoriées sur la page **Liste des archives de données**. Chaque archive peut contenir des données de plusieurs tables et peut contenir jusqu’à 10 000 enregistrements. S’il y a plus de 10 000 enregistrements dans une table, une deuxième archive sera créée pour les 10 000 enregistrements suivants, et ainsi de suite. Par exemple, si vous archivez 10 100 écritures GL, Business Central crée une archive « écriture GL » pour les 10 000 premières écritures, puis une seconde archive pour les 100 écritures restantes.

Après avoir archivé les données, vous pouvez les explorer en utilisant Microsoft Excel ou sous forme de fichier CSV.

* Si vous utilisez l’option Excel, le classeur contiendra une feuille de calcul pour chaque table d’archivage de données.
* Si vous utilisez l’option CSV, vous obtiendrez un fichier ZIP contenant un fichier CSV pour chaque table d’archive de données.

> [!TIP]
> Les options Excel et CSV facilitent l’utilisation d’une autre application ou d’un autre service pour déplacer les données vers un autre emplacement, tel que le stockage blob Azure ou un outil d’analyse, tel que Microsoft Power BI.

L’extension Data Archive est utilisée par les traitements en lot suivants pour la compression selon la date.

|Traitements en lot  |
|---------|
|Comp. Date Écritures budget article |
|Compresser écritures banque |
|Compr. date écritures client |
|Compr. date écritures immo. |
|Compr. date écritures GL |
|Compr. date écritures assur. |
|Compresser écritures maint. |
|Compresser écritures maint. |
|Compr. date écritures ress. |
|Compresser écritures TVA |
|Compr. date écritures fourn. |
|Compresser écritures Écritures |
|Compr. Date Écritures budget |

Pour démarrer l’archivage des données lorsque vous exécutez l’un des traitements en lot, activez le bouton à bascule **Archiver les entrées supprimées**.

## <a name="storage-considerations" />Considérations relatives au stockage

Les données archivées sont stockées dans la table **Média abonné**. Nous vous recommandons d’exporter les anciennes archives vers, par exemple, un fichier CSV, puis de supprimer les anciens enregistrements d’archives.

## <a name="see-also" />Voir aussi

[Gérer le stockage en supprimant des documents ou en compressant des données](admin-manage-documents.md)
