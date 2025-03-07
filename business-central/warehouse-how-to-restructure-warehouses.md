---
title: Restructurer les entrepôts
description: Découvrez comment restructurer votre entrepôt avec de nouveaux codes de zone et de nouvelles caractéristiques de zone pour atteindre ou maintenir une opération plus efficace.
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: null
ms.search.form: '9813, 9814'
ms.date: 06/25/2021
ms.author: edupont
---
# <a name="restructure-warehouses" />Restructurer les entrepôts
Vous pouvez souhaiter restructurer votre entrepôt avec de nouveaux codes et caractéristiques zone. Ce type d'activité n'intervient que très rarement, mais un reclassement peut s'avérer nécessaire pour mettre à jour une opération ou la rendre plus efficace. Par exemple :  

- Vous pouvez souhaitez passer à des codes de zone prenant en charge l'utilisation de la saisie automatisée avec des appareils portables.  
- L'entrepôt peut avoir acheté un nouveau système de stockage garantissant de nouvelles possibilités pour stocker les articles.  
- La compagnie peut avoir modifié son assortiment d'articles et déplacé l'entrepôt vers un nouvel emplacement pour prendre en charge cette modification.  

Si votre entrepôt est configuré pour utiliser des zones, mais sans prélèvement ni rangement suggérés, restructurez-le en créant les nouvelles zones à utiliser à l'avenir.  

## <a name="to-restructure-a-basic-warehouse-that-uses-bins-only" />Pour restructurer un entrepôt de base qui utilise uniquement des emplacements
1.  Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Emplacements**, puis choisissez le lien associé.  
2.  Dans le raccourci **Entrepôt**, paramétrez le champ **Sélection zone par déf.** sur **Dernière zone utilisée**.  
3.  Déplacez le contenu des emplacements actuels vers les emplacements que vous venez de créer.  

    1.  Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Journal reclassement article**, puis sélectionnez le lien associé.  
    2.  Sélectionnez une ligne journal, puis choisissez l'action **Extraire contenu de la zone**.  
    3.  Sur le raccourci **Contenu de la zone**, définissez des filtres dans les champs **Code d'emplacement**, **Code de zone** et **N° article** pour indiquer le contenu que vous souhaitez déplacer.  
    4.  Cliquez sur le bouton **OK** pour renseigner une ligne feuille.  
    5.  Dans le champ **Nouveau code emplacement**, sélectionnez l'emplacement vers lequel les articles doivent être déplacés.  
    6.  Répétez les étapes b à e pour tout le contenu de la zone que vous souhaitez déplacer.  
    7.  Sélectionnez l'action **Valider**.  

Vous avez à présent vidé les emplacements où les articles se trouvaient auparavant. Les emplacements par défaut des articles sont alors remplacés par les nouveaux emplacements.  

## <a name="to-restructure-an-advanced-warehouse-that-uses-directed-put-away-and-pick" />Pour restructurer un entrepôt avancé qui utilise le prélèvement et le rangement suggérés

1.  Créez les emplacements à utiliser ultérieurement. Pour plus d'informations, voir [Créer zones](warehouse-how-to-create-individual-bins.md).  
2.  Déplacez le contenu des emplacements actuels vers les emplacements que vous venez de créer.  

    1.  Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Journal reclassement entrepôt**, puis sélectionnez le lien associé.  
    2.  Pour les emplacements sans mouvement réel d'articles, créez une ligne pour chacun de vos emplacements actuels dans la **feuille reclassement entrepôt** avec l'ancien code emplacement , **Du code emplacement**, et le nouveau code emplacement , **Du code emplacement**.  
    3.  Si certains mouvements nécessitent des mouvements physiques réels de la part des employés, utilisez les **feuilles mouvements** pour préparer les instructions mouvement au lieu d'utiliser la feuille reclassement entrepôt. Pour plus d'informations, voir [Déplacer des articles dans les configurations de stockage avancées](warehouse-how-to-move-items-in-advanced-warehousing.md).  

3.  Lorsque les anciens emplacements sont vidés, reclassez-les en tant qu'emplacements de type **CQ** pour vous assurer qu'ils ne sont pas inclus dans les flux d'articles.  

    1.  Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Emplacements**, puis choisissez le lien associé.  
    2.  Sélectionnez la ligne indiquant l'emplacement, puis, choisissez l'action **Zones**.  
    3.  Sur la page **Zones**, dans le champ **Code type zone**, entrez **CQ** pour chacune des anciennes zones que vous avez vidées à l'étape 3 de la procédure précédente.  

Vous avez à présent supprimé les zones du flux entrepôt et les avez reclassées en tant que zones de type CQ. Pour les zones de ce type, aucun des champs d'activité de la page **Types de zone** n'est sélectionné, par conséquent ils ne sont pas pris en compte par le flux d'articles. Pour plus d'informations, voir [Configurer des types de zone](warehouse-how-to-set-up-bin-types.md).  

## <a name="to-delete-a-bin" />Pour supprimer une zone

1.  Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Emplacements**, puis choisissez le lien associé.  
2.  Sélectionnez l'emplacement à partir duquel vous souhaitez supprimer des zones. Choisissez l'action **Zones**.  
3.  Sélectionnez les lignes des emplacements que vous souhaitez supprimer.  
4.  Cliquez sur l'action **Supprimer**.  

Si vous sélectionnez le bouton **Oui**, l'emplacement est supprimé pour ne plus être utilisé, mais le code emplacement de toutes les écritures entrepôt reste le même.  

Pour renommer une zone de façon à ce que tous les enregistrements associés à cette zone soient également renommés, y compris les enregistrements comprennent le contenu des zones, les lignes activité entrepôt, les lignes activité entrepôt enregistrées, les lignes feuille entrepôt, les lignes réception entrepôt, les lignes réception entrepôt reportées, les lignes livraison entrepôt, les lignes livraison entrepôt reportées et les écritures entrepôt, vous pouvez utiliser la page **Zones**.  

## <a name="to-rename-a-bin-and-change-the-bin-code-in-all-records" />Pour renommer une zone et modifier le code de zone de tous les enregistrements

1.  Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Emplacements**, puis choisissez le lien associé.  
2.  Sélectionnez l'emplacement dans lequel vous souhaitez renommer une zone ou modifier le code de zone, puis choisissez l'action **Zones**.  
3.  Sélectionnez l'emplacement que vous souhaitez modifier et entrez un nouveau code emplacement dans le champ **Code**.  
4.  Cliquez sur le bouton **Oui**.  

> [!NOTE]  
>  Si vous sélectionnez **Oui** et que de nombreuses écritures se rapportent à cet emplacement, parce que vous n'avez pas supprimé de documents entrepôt depuis longtemps, par exemple, l'attribution d'un nouveau nom à tous les enregistrements peut prendre un certain temps. Par conséquent, si vous utilisez cette méthode, nous vous recommandons d'exécuter le traitement par lots **Supprimer documents entr. enreg.** avant de lancer le processus lié à l'attribution de nouveaux noms. Notez également que les seuls documents supprimés dans ce traitement en lot sont des rangements, des prélèvements, et des mouvements.  
>   
>  Si vous renommez une zone réception ou une zone livraison, toutes les réceptions ou livraisons reportées se rapportant à la zone concernée sont renommées.  

## <a name="see-also" />Voir aussi
[Vue d’ensemble de Warehouse Management](design-details-warehouse-management.md)
[Inventaire](inventory-manage-inventory.md)  
[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)     
[Gestion d'assemblage](assembly-assemble-items.md)    
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
