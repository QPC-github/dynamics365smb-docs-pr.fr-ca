---
title: "Procédure pas à pas : suivi des numéros de série et des numéros de lot | Microsoft Docs"
description: "En cas de produit défectueux, vous devez identifier les erreurs et empêcher les articles concernés d'être vendus. Si des articles défectueux ont déjà été livrés, vous devez procéder au suivi des destinataires et, au besoin, rappeler les articles."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 08/22/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: ba26b354d235981bd7291f9ac6402779f554ac7a
ms.openlocfilehash: face4821059b57c32e06dca46ec5144aba4ca528
ms.contentlocale: fr-ca
ms.lasthandoff: 11/10/2017

---
# <a name="walkthrough-tracing-serial-lot-numbers"></a>Procédure pas à pas : suivi des numéros de série et des numéros de lot
En cas de produit défectueux, vous devez identifier les erreurs et empêcher les articles concernés d'être vendus. Si des articles défectueux ont déjà été livrés, vous devez procéder au suivi des destinataires et, au besoin, rappeler les articles.  

Dans la gestion des défauts, la première chose à faire est de rechercher d'où venaient les articles défectueux et où ils ont été utilisés. Pour ce faire, vous pouvez vous baser sur des données historiques et, pour faciliter votre travail, vous pouvez rechercher l'article en utilisant l'option **Traçabilité**.  

Ensuite, déterminez si les articles suivis sont planifiés dans des documents en cours, comme des documents de vente non reportés ou des journaux consommation. Cela s'effectue dans la fenêtre **Naviguer**. Vous pouvez utiliser la fonction Naviguer pour rechercher tous les types d'enregistrements de données de base.  

## <a name="about-this-walkthrough"></a>À propos de cette procédure pas à pas  
Cette procédure pas à pas explique comment identifier les articles défectueux, leur fournisseur et l'endroit où ils sont utilisés afin que vous puissiez les bloquer ou les rappeler.  

Cette procédure pas à pas présente les tâches suivantes :  

-   Traçabilité de l'utilisation à l'origine.  
-   Traçabilité de l'origine à l'utilisation.  
-   Recherche de tous les enregistrements en cours contenant le numéro de série/lot suivi  

## <a name="roles"></a>Rôles  
Cette procédure pas à pas présente les tâches effectuées par les rôles utilisateur suivants :  

-   Contrôleur qualité  
-   Gestionnaire d'entrepôt  
-   Préparateur de commandes  
-   Agent d'achats  

## <a name="prerequisites"></a>Conditions préalables  
Pour exécuter ce processus pas à pas, vous devez :  

-   La société [!INCLUDE[d365fin](includes/d365fin_md.md)].  
-   Créer des articles et plusieurs transactions commerciales en suivant la section « Préparation d'exemples de données », plus loin dans cette procédure pas à pas.  

## <a name="story"></a>Scénario  
Ricardo, le contrôleur qualité, se charge d'un retour vente de l'article 1002, vélo de course. Le client, Selangorian Ltd., s'est plaint de fissures au niveau des joints de soudure. Les ingénieurs du contrôle qualité ont confirmé que le cadre du vélo renvoyé est défectueux. Le contrôleur qualité doit maintenant déterminer :  

-   le lot de cadres défectueux ;  
-   le bon de commande sur lequel le lot défectueux apparaît.  

Dans le département des ventes, le contrôleur qualité sait que le vélo de course renvoyé, l'article 1002, porte le numéro de série SN1. En utilisant cette information de base, il doit déterminer l'endroit où le vélo de course fini a été utilisé en dernier, puis il doit remonter jusqu'à l'origine pour connaître le numéro de lot duquel la composante défectueuse provient.  

Les résultats de cette première tâche de traçabilité permettent d'identifier les cadres défectueux et le fournisseur qui les a vendus. Ensuite, mais toujours dans la même procédure de traçabilité générale, le contrôleur qualité doit trouver tous les vélos de course vendus qui sont équipés d'un cadre provenant du lot défectueux, de manière à pouvoir stopper ou rappeler ces commandes. Enfin, le contrôleur qualité doit trouver des documents ouverts dans lesquels le lot défectueux est utilisé afin d'empêcher d'autres transactions.  

Les deux premières tâches de gestion des défauts sont exécutées dans la fenêtre **Traçabilité**. La dernière tâche est réalisée dans la fenêtre **Naviguer** en association avec la fenêtre **Traçabilité**.  

## <a name="prepare-sample-data"></a>Préparation d'exemples de données  
Vous devez créer les nouveaux articles suivants :  

-   2000, Cadre de course : traçabilité spécifique au lot, composante de 1002  
-   1002, Vélo de course : traçabilité spécifique au numéro de série  

Ensuite, vous devez créer plusieurs transactions d'achat, de production et de vente avec les deux articles.  

### <a name="to-create-the-items"></a>Pour créer les articles  

1.  Choisissez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Articles**, puis sélectionnez le lien connexe.  
2.  Sélectionnez l'action **Nouveau**.  
3.  Dans le champ **N°**, , entrez **2000**, puis complétez les champs suivants.  

    |Description|Unité de mesure de base|Groupe de report de produit|Groupe de report produit TVA|Groupe de report inventaire|Code de suivi d'article|  
    |-----------------|--------------------------|------------------------------|-----------------------------|-----------------------------|------------------------|  
    |Cadre de course|PCS|MAT PREM|VAT25|MAT PREM|LOTALL|  

    > [!NOTE]  
    >  Pour entrer l’unité de base, cliquez sur le bouton **Nouveau**, puis sélectionnez **PSC** dans la fenêtre **Unités article**.  

4.  Tous les autres champs contiennent des données par défaut acceptables ou ne doivent pas être remplis.  
5.  Choisissez le bouton **OK** pour créer la première fiche article, 2000.  
6.  Choisissez **Nouveau**.  
7.  Dans le champ **N°**, , entrez **1002**, puis complétez les champs suivants.  

    |Description|Unité de mesure de base|Groupe de report de produit|Groupe de report produit TVA|Groupe de report inventaire|Système de réapprovisionnement|Code de suivi d'article|  
    |-----------------|--------------------------|------------------------------|-----------------------------|-----------------------------|--------------------------|------------------------|  
    |Vélo de course|PCS|DÉTAIL|VAT25|TERMINÉ|Bon de prod.|SNALL|  

    > [!NOTE]  
    >  Pour entrer l’unité de base, cliquez sur le bouton **Nouveau**, puis sélectionnez **PSC** dans la fenêtre **Unités article**.  

    Ensuite, définissez la configuration de fabrication de l'article.

9. Sous l'onglet **Réapprovisionnement**, entrez **1000** dans le champ **N° itinéraire**.  
10. Choisissez le champ **N° nomenclature de production**, puis sélectionnez **Avancé**.  
11. Dans la fenêtre **Liste nomenclatures production**, choisissez la première ligne, **1000**, puis sélectionnez l'action **Modifier**.  
12. Dans la fenêtre **Nomenclature de production**, modifiez la valeur du champ **Statut**en **Modification en cours**.  
13. Accédez à une ligne vide, entrez **2000** dans le champ **N°** puis entrez **1** dans le champ **Quantité par**.  
14. Modifiez la valeur du champ **Statut** en **Validée**.  
15. Cliquez sur le bouton **OK** pour insérer la nomenclature de production dans la fiche article et fermer la fenêtre **Nomenclature de production**.  

    Ensuite, acheter des cadres de course de Custom Metals Incorporated.  

### <a name="to-purchase-components"></a>Pour acheter des composants  
1.  Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Bons de commande**, puis sélectionnez le lien associé.  
2.  Sélectionnez l'action **Nouveau**.  
3.  Créez un bon de commande pour le fournisseur, Custom Metals Incorporated, en renseignant les champs ligne suivants.  

    |Article|Quantité|N° de lot|  
    |----------|--------------|-------------|  
    |2000|10|LOT1|  

4.  Pour saisir le numéro de lot, choisissez l'action **Lignes traçabilité**.  
5.  Dans la fenêtre **Lignes traçabilité**, renseignez les champs **N° lot** et **Quantité (Base)**, puis fermez la fenêtre.  
6.  Dans le champ **N° facture fournisseur**, entrez une valeur.  
7.  Choisissez l'action **Reporter**, sélectionnez l'option **Recevoir et facturer**, puis cliquez sur le bouton **OK**.  

    Ensuite, achetez des cadres de course de Coolwood Technologies.  
8.  Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Bons de commande**, puis sélectionnez le lien associé.  
9. Sélectionnez l'action **Nouveau**.
10. Créez un bon de commande pour le fournisseur, Coolwood Technologies, en renseignant les champs ligne suivants.  

    |Article|Quantité|N° de lot|  
    |----------|--------------|-------------|  
    |2000|11|LOT2|  

11. Pour entrer le numéro de lot, dans le raccourci **Lignes**, dans le groupe **Ligne**, choisissez l'action **Lignes traçabilité**.  
12. Dans la fenêtre **Lignes traçabilité**, renseignez les champs **N° lot** et **Quantité (Base)**, puis fermez la fenêtre.  
13. Dans le champ **N° facture fournisseur**, entrez une valeur.  
14. Choisissez l'action **Reporter**, sélectionnez l'option **Recevoir et facturer**, puis cliquez sur le bouton **OK**.  

    Ensuite, deux produisez vélos de course, SN2 et SN1.  

### <a name="to-produce-end-items"></a>Pour produire des produits finis  
1.  Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Bons de production libérés**, puis sélectionnez le lien associé.  
2.  Choisissez le groupe **Nouveau**.  
3.  Créez un bon de production libéré en renseignant les champs suivants.  

    |-|-|-|  
    |N° origine|Quantité|N° de série|  
    |1002|2|SN1|  
    |1002|2|SN2|  

4.  Choisissez l'action **Actualiser O.F.**, puis choisissez le bouton **OK** pour remplir la ligne.  
5.  Pour saisir les numéros de série, choisissez l'action **Lignes traçabilité**.  
6.  Dans la fenêtre **Lignes traçabilité**, renseignez les champs **N° série** et **Quantité (Base)**, puis fermez la fenêtre.  

    Ensuite, reportez la consommation des cadres de course dans le LOT1.  
7.  Dans la fenêtre **Bon de production libéré**, choisissez l'action **Journal de production**.  
8.  Dans la fenêtre **Journal de production**, sélectionnez la ligne consommation pour l'article 2000, choisissez l'action **Lignes traçabilité**.
9. Dans la fenêtre **Lignes traçabilité**, sélectionnez le champ **N° lot**, choisissez **LOT1**, puis sélectionnez le bouton **OK** button.  
10. Ne modifiez pas les autres valeurs par défaut dans la fenêtre **Journal production**, et sélectionnez l'action **Reporter**.  

    Ensuite, deux produisez vélos de course supplémentaires, SN4 et SN3.  

11. Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Bons de production libérés**, puis sélectionnez le lien associé.  
12. Sélectionnez l'action **Nouveau**.  
13. Créez un bon de production libéré en renseignant les champs suivants dans l'en-tête.  

    |N° d'origine|Quantité|N° de série|  
    |----------------|--------------|----------------|  
    |1002|2|SN3|  
    |1002|2|SN4|  

14. Choisissez l'action **Actualiser O.F.** pour remplir la ligne.  
15. Pour saisir les numéros de série, choisissez l'action **Lignes traçabilité**, puis les numéros figurant sur deux lignes dans le champ **N° de série** de la fenêtre **Lignes traçabilité**.  

    Ensuite, reportez plus de consommation des cadres de course dans le LOT1.  
16. Dans la fenêtre **Bon de production libéré**, choisissez l'action **Journal de production**.  
17. Dans la fenêtre **Journal de production**, sélectionnez la ligne consommation pour l'article 2000, choisissez l'action **Lignes traçabilité**.
18. Dans la fenêtre **Lignes traçabilité**, sélectionnez le champ **N° lot**, choisissez **LOT1**, puis sélectionnez le bouton **OK** button.  
19. Ne modifiez pas les autres valeurs par défaut dans la fenêtre **Journal production**, et sélectionnez l'action **Reporter**.  

    Vous avez créé quatre vélos de course, SN1 à SN4, et utilisé quatre des dix cadres de course du LOT1, deux pour chaque bon de production.  

20. Fermez le journal de production et les bons de production.  

    Ensuite, vendez les vélos de course. Vendez d'abord le vélo de course portant le SN1 à Selangorian Ltd.  

### <a name="to-sell-the-end-items"></a>Pour vendre des articles finis  
1.  Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Commandes vente**, puis sélectionnez le lien connexe.  
2.  Choisissez l'action **Nouveau**, puis créez un document de vente en renseignant les champs suivants.  

    |Client|Article|Qté|N° de série|  
    |--------------|----------|----------|----------------|  
    |Selangorian Ltd.|1002|1|NS1|  

3.  Pour saisir le numéro de série, choisissez l'action **Lignes traçabilité**, puis le numéro figurant dans le champ **N° de série** de la fenêtre **Lignes traçabilité**.  
4.  Choisissez l'action **Reporter**, sélectionnez l'option **Livrer et facturer**, puis cliquez sur le bouton **OK**.  

    Ensuite, vendez le vélo de course portant le SN2 au Cannon Group PLC.  

5.  Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Commandes vente**, puis sélectionnez le lien connexe.  
6.  Choisissez l'action **Nouveau**, puis créez un document de vente en renseignant les champs suivants.  

    |Client|Article|Qté|N° de série|  
    |--------------|----------|----------|----------------|  
    |Cannon group PLC.|1002|1|NS2|  

7.  Pour saisir le numéro de série, choisissez l'action **Lignes traçabilité**, puis le numéro figurant dans le champ **N° de série** de la fenêtre **Lignes traçabilité**.  
8.  Choisissez l'action **Reporter**, sélectionnez l'option **Livrer et facturer**, puis cliquez sur le bouton **OK**.  

    Enfin, vendez séparément quelques cadres de course. Cannon Group PLC commande également quatre cadres de course distincts pour leur propre chaîne de montage.  

9. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Commandes vente**, puis sélectionnez le lien connexe.  
10. Choisissez l'action **Nouveau**, puis créez un document de vente en renseignant les champs suivants.  

    |Client|Article|Qté|N° de série|  
    |--------------|----------|----------|----------------|  
    |Cannon group PLC.|2000|5|LOT1|  

11. Pour saisir le numéro de série, dans le raccourci **Lignes**, dans le groupe **Ligne**, sélectionnez l'action **Lignes traçabilité**, puis le numéro dans le champ **N° de série** de la fenêtre **Lignes traçabilité**.  

    > [!NOTE]  
    >  Ne reportez pas le dernier document de vente pour les cinq cadres de course.  

    Vous avez terminé de préparer les données de démonstration des fonctions Traçabilité et Naviguer.  

## <a name="tracing-from-usage-to-origin"></a>Traçabilité de l'utilisation à l'origine  
 Dans le département des ventes, le contrôleur qualité sait que le vélo de course renvoyé, l'article 1002, porte le numéro de série SN1. En utilisant cette information de base, il peut déterminer l'endroit où le vélo de course a été utilisé en dernier, dans ce cas, sur la livraison vente de Selangorian Ltd. Il doit ensuite remonter jusqu'à l'origine pour connaître le numéro de lot duquel le composant défectueux provient.  

### <a name="to-determine-which-lot-included-the-faulty-frame-and-who-supplied-it"></a>Pour déterminer de quel lot le cadre défectueux provient et qui la fournit  
1.  Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Repérage d'article**, puis sélectionnez le lien associé.  
2.  Dans la fenêtre **Traçabilité**, entrez **SN1** dans le champ **Filtre n° de série**, puis entrez **1002** dans le champ **Filtre article**.  
3.  Conservez les paramètres par défaut de **Article suivi uniquement** dans le champ **Afficher composantes** et conservez la méthode de suivi par défaut **Utilisation - Origine** dans **Méthode de suivi**.  
4.  Choisissez l'action **Suivi**.  

    Remarque : un en-tête livraison ventes correspond aux critères de recherche. Avant de continuer le suivi, vérifiez que la livraison correspond à l'envoi du vélo de course défectueux à Selangorian Ltd.  

5.  Sélectionnez la ligne de suivi, puis sélectionnez l'action **Afficher document**.  

    Poursuivez maintenant la traçabilité de l'origine de la livraison vente du vélo de course portant le numéro SN1.  
6.  Choisissez l'icône + dans les lignes de suivi pour développer progressivement et remonter dans l'enchaînement de transactions d'où provient la livraison vente.  

    Vous pouvez suivre l'historique des transactions suivant :  

    -   Le premier document reporté en amont dans l'enchaînement de transactions est le report des sorties de SN1 à partir du premier bon de production libéré.  
    -   Le document reporté suivant en amont est le report de la consommation à partir du premier bon de production libéré. Dans ce cas, le contrôleur qualité constate qu'un cadre de course du LOT1 a été utilisé.  
    -   Le document reporté situé le plus bas dans cet enchaînement est la réception achat reportée sur laquelle les cadres de course du LOT1 ont été entrés dans l'inventaire.  

    Le contrôleur qualité a maintenant déterminé le lot de cadres de course défectueux et il peut rechercher la dernière ligne de suivi pour connaître leur fournisseur, dans ce cas Custom Metals Incorporated.  

    > [!NOTE]  
    >  Ne modifiez plus le résultat de la traçabilité, car vous allez l'utiliser dans la prochaine section.  

     La première tâche de gestion des défauts à l'aide de la fenêtre **Traçabilité** est à présent terminée. Le contrôleur qualité doit maintenant déterminer si d'autres documents reportés ont traité des cadres de course du LOT1.  

## <a name="tracing-from-origin-to-usage"></a>Traçabilité de l'origine à l'utilisation  
 Le contrôleur qualité a déterminé que les cadres de course défectueux provenaient du LOT1. Il doit maintenant retrouver les autres vélos de course équipés d'un cadre provenant du lot défectueux afin de pouvoir stopper ou rappeler ces vélos.  

 Une manière de préparer cette tâche de suivi dans la fenêtre **Traçabilité** est d'entrer manuellement LOT1 dans le champ **Filtre n° lot** et 2000 dans le champ **Filtre article**. Toutefois, cette procédure pas-à-pas utilisera la fonction **Opposé suivi - Ligne d'origine** .  

### <a name="to-find-all-usage-of-the-faulty-lot"></a>Pour trouver toutes les utilisations du lot défectueux  

1.  Dans la fenêtre **Traçabilité**, sélectionnez la ligne de la réception achat (la dernière ligne de suivi), choisissez **Opposé suivi - Ligne d'origine**.  

    Le résultat du suivi est maintenant basé sur les filtres de la ligne de suivi pour la réception achat, LOT1 et article 2000, et sur la méthode de suivi **Origine - Utilisation**.  

    Pour obtenir une vue d'ensemble de toutes les utilisations de l'article 2000 avec le LOT1, continuez de développer toutes les lignes de suivi.  

2.  Sélectionnez l'action **Développer tout**.  

    Les quatre premières lignes de suivi se rapportent à la livraison vente à Selangorian Ltd., qui est déjà résolue. La dernière ligne indique qu'un autre vélo de course, SN2, a été produit dans le même bon de production libéré, puis vendu et livré dans le cadre d'une autre livraison vente.  

    Le contrôleur qualité en informe immédiatement le département des ventes afin qu'il puisse envoyer un rappel du vélo de course défectueux au client, Cannon Group PLC.  

    Au même moment, il constate dans les trois dernières lignes de suivi que deux autres articles, SN3 et SN4, ont été fabriqués avec les cadres de course du LOT1. Il bloque ces produits finis dans l'inventaire.  

    Ainsi se termine la deuxième tâche de gestion des défauts à l'aide de la fenêtre **Traçabilité**. Étant donné que la fenêtre **Traçabilité** est basée uniquement sur des écritures reportées, le contrôleur qualité doit poursuivre jusqu'à la fenêtre **Naviguer** pour vérifier que le LOT1 n'est pas utilisé dans des documents qui ne sont pas reportés.  

## <a name="finding-all-records-of-a-seriallot-number"></a>Rechercher tous les enregistrements d'un numéro de série/lot  
 La fenêtre **Traçabilité** a permis au contrôleur qualité de constater que le LOT1 contenait les cadres de course défectueux, d'en découvrir le fournisseur ainsi que la transaction validée dans laquelle ils avaient été utilisés. Il doit maintenant déterminer si le LOT1 apparaît dans des documents ouverts en intégrant les résultats du suivi dans la fenêtre **Naviguer** dans laquelle il peut faire une recherche sur l'ensemble des enregistrements de base de données.  

### <a name="to-find-all-occurrences-of-lot1-in-non-posted-records-such-as-open-orders"></a>Pour rechercher toutes les occurrences du LOT1 dans les enregistrements non reportés, comme les commandes ouvertes  

1.  Dans la fenêtre **Traçabilité**, sélectionnez la première ligne de suivi, c'est-à-dire la réception achat du LOT1.  
2.  Sélectionnez l'action **Naviguer**.  

    La fenêtre **Naviguer** contient déjà des filtres de recherche basés sur le résultat du suivi du LOT1. Le contrôleur qualité constate que la majorité des enregistrements se rapportent à des documents déjà identifiés dans la fenêtre **Traçabilité**. Par exemple, la dernière ligne de la fenêtre Naviguer de type bon de production fait référence aux deux bons de production libérés qui ont consommé les cadres de course du LOT1.  

    Toutefois, la seconde ligne de la fenêtre Naviguer de type **Ligne vente** est une ligne document non reportée. Par conséquent, le contrôleur qualité continue ses recherches.  

3.  Pour ouvrir l'enregistrement de ligne vente, sélectionnez la seconde ligne de la fenêtre Naviguer, choisissez l'action **Afficher**. Sinon, choisissez la valeur dans le champ **Nombre d'enregistrements**.  

    Dans ce cas, le contrôleur qualité constate une ligne vente ouverte pour les cadres de course défectueux. Il suggère immédiatement au département des ventes l'annulation de cette commande et la création d'un nouveau bon de production, basé sur des cadres de course non défectueux.  

 Ainsi se termine la procédure pas à pas sur l'utilisation de la fenêtre **Naviguer** pour la gestion des défauts en association avec la fenêtre **Traçabilité**.  

## <a name="see-also"></a>Voir aussi
[Procédure : utiliser les numéros de lot et de série](inventory-how-work-item-tracking.md)  
[Procédure : tracer des articles suivis](inventory-how-to-trace-item-tracked-items.md)  
[Procédures pas à pas liées au processus entreprise](walkthrough-business-process-walkthroughs.md)  
