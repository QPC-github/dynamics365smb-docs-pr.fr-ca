---
title: Ajuster les coûts article manuellement
description: 'Vous pouvez ajuster manuellement l’évaluation de l’inventaire d’un article à l’aide des méthodes FIFO ou d’évaluation inventaire moyen, lorsque les coûts de produits changent.'
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'cost adjustment, cost forwarding, costing method, inventory valuation, costing'
ms.date: 06/16/2021
ms.author: edupont
---
# <a name="adjust-item-costs" />Ajuster coûts et prix article
Le coût d'un article (valeur inventaire) que vous achetez et vendez ultérieurement peut changer au cours de sa durée de vie, par exemple parce que des frais de transport sont ajoutés à son coût d'achat après que vous avez vendu l'article. L'ajustement des coûts est particulièrement utile dans les situations où vous vendez des biens avant de facturer leur achat. Pour toujours connaître la valeur correcte de l'inventaire, les coûts article doivent donc être ajustés régulièrement. Cela garantit que les statistiques vente et profit sont à jour et que les indicateurs clés financiers sont corrects. Pour plus d'informations, voir [Détails de conception : modes évaluation stock](design-details-cost-adjustment.md).

En règle générale, la valeur du champ **Coût unitaire** sur la fiche article repose sur le coût standard des articles utilisant le mode évaluation stock standard. Pour les articles utilisant d'autres modes évaluation coût, la valeur repose sur le calcul de l'inventaire disponible (coûts facturés et prévus) divisé par la quantité disponible. Pour plus d'informations, voir [Comprendre le calcul du coût unitaire](inventory-how-adjust-item-costs.md#understanding-unit-cost-calculation).

Dans [!INCLUDE[prod_short](includes/prod_short.md)], les coûts article sont automatiquement ajustés chaque fois qu'une transaction inventaire se produit, par exemple lors du report d'une facture achat pour un article.

Vous pouvez également utiliser une fonction pour ajuster manuellement les coûts d'un ou de plusieurs articles. Cela est utile, par exemple, si vous savez que les coûts article ont changé pour d'autres raisons que des mouvements de stock.

Les coûts article sont ajustés selon la méthode FIFO ou d'évaluation coût moyen, selon la sélection effectuée dans le guide de configuration assistée **Configurer ma compagnie** ou dans le champ **Mode évaluation stock** sur la fiche article. Pour plus d'informations, reportez vous à [Enregistrer de nouveaux articles](inventory-how-register-new-items.md).  

Si vous utilisez la méthode de coût FIFO, le coût unitaire d'un article est la valeur réelle de toute réception de l'article. L'inventaire est évalué en supposant que les premiers articles placés dans l'inventaire sont les premiers vendus.

Si vous utilisez la méthode de l'évaluation stock moyen, le coût unitaire d'un article est calculé comme le coût unitaire moyen à chaque moment après un achat. L'inventaire est évalué en supposant que tous les inventaires sont vendus simultanément. Pour les articles utilisant ce mode d'évaluation stock, vous pouvez choisir le champ **Coût unitaire** de la fiche article pour afficher l'historique des transactions à partir duquel est calculé le coût moyen

La fonction d'ajustement des coûts traite uniquement les écritures valeur non encore ajustées. Si la fonction est confrontée à une situation où des coûts entrants modifiés doivent être transférés à des écritures sortantes associées, de nouvelles écritures valeur ajustées sont créées, sur la base des informations des écritures valeur d'origine, mais contenant le montant de l'ajustement. La fonction d'ajustement des coûts utilise la date de report de l'écriture valeur d'origine dans l'écriture d'ajustement, sauf si la date est comprise dans une période d'inventaire fermée. Dans ce cas, l'application utilise la date début de la période d'inventaire ouverte suivante. Si aucune période inventaire n'est utilisée, la date du champ **Début période report** de la page **Configuration du grand livre** définira la date de report de l'écriture ajustée.

## <a name="to-adjust-item-costs-manually" />Pour ajuster les coûts article manuellement
1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Ajuster coûts : Écr. article**, puis sélectionnez le lien associé.
2. Sur la page **Ajuster coûts - Écr. article**, spécifiez les articles pour lesquels ajuster les coûts.
3. Cliquez sur le bouton **OK**.

## <a name="to-make-general-changes-in-the-direct-unit-cost" />Pour apporter des modifications générales au coût unitaire direct
Si vous devez modifier le coût unitaire direct de plusieurs articles, vous pouvez utiliser le traitement en lot **Ajuster coûts et prix article**.  

 Le traitement par lots modifie la valeur du champ **Prix unitaire** sur la fiche article. Le traitement en lot modifie la valeur du champ de la même manière pour tous les articles (ou pour les articles sélectionnés). Le traitement en lot multiplie la valeur du champ par un facteur appliqué que vous devez indiquer.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Ajuster coûts/prix article**, puis sélectionnez le lien associé.  
2. Dans le champ **Ajuster champ**, indiquez l'article ou le champ de la fiche Unité de stock à modifier.  
3. Dans le champ **Facteur appliqué**, indiquez le facteur d'ajustement de la valeur. Par exemple, entrez **1,5** pour augmenter la valeur de 50 %.  
4. Sous le raccourci **Article**, définissez des filtres pour indiquer, par exemple, les articles à traiter avec le traitement par lots.  
5. Cliquez sur le bouton **OK**.  

## <a name="understanding-unit-cost-calculation" />Comprendre le calcul du coût unitaire
En règle générale, la valeur du champ **Coût unitaire** sur la fiche article repose sur le coût standard des articles utilisant le mode évaluation stock standard. Pour les articles utilisant d'autres modes évaluation coût, la valeur repose sur le calcul de l'inventaire disponible (coûts facturés et prévus) divisé par la quantité disponible.  

 Pour en savoir plus sur les incidences de la valeur du champ **Mode évaluation stock** sur le calcul du coût unitaire pour les achats et les ventes, consultez les chapitres suivants.  

## <a name="unit-cost-calculation-for-purchases" />Calcul du coût unitaire pour les achats
 Lorsque vous achetez des articles, le programme copie toujours la valeur du champ **Dernier coût direct** de la fiche article vers le champ **Coût unitaire direct** d'une ligne achat ou vers la ligne Montant unitaire sur une ligne journal article.  

 L'élément sélectionné dans le champ **Mode d'évaluation du stock** détermine la façon dont [!INCLUDE[prod_short](includes/prod_short.md)] calcule le contenu du champ **Coût unitaire** sur les lignes.  

### <a name="costing-method-fifo-lifo-specific-or-average" />Modes d'évaluation du stock FIFO, LIFO, spécifique ou moyen
 [!INCLUDE[prod_short](includes/prod_short.md)] calcule la valeur du champ **Coût unitaire $** sur la ligne achat, ou la valeur du champ **Coût unitaire** sur la ligne journal article sur la base de la formule suivante :  

 Coût unitaire $ = (Coût unitaire direct - (Montant de l'escompte/Quantité)) x (1 + % du coût indirect/100) + Frais généraux  

### <a name="costing-method-standard" />Mode évaluation stock Standard
 Le champ **Coût unitaire $** sur la ligne achat, ou le champ **Coût unitaire** est renseigné sur la ligne journal article en copiant la valeur du champ **Coût unitaire** de la fiche article. En utilisant le mode évaluation stock Standard, il repose toujours sur le coût standard.  

 Lorsque vous reportez l'achat, le coût unitaire de la ligne achat ou de la ligne journal article est copié vers l'écriture facture article d'achat, et vous pouvez le visualiser dans la liste des écritures de l'article.  

### <a name="all-costing-methods" />Tous les modes évaluation stock
 Le programme utilise toujours le coût unitaire de la ligne document source pour calculer la valeur du champ **Coût indiqué (réel)**, ou éventuellement du champ **Coût indiqué (prévu)** concernant cette écriture article, quel que soit la méthode évaluation coût de l'article.  

## <a name="unit-cost-calculation-for-sales" />Calcul du coût unitaire pour les ventes
 Lorsque vous vendez des articles, le coût unitaire est copié du champ Coût unitaire de la fiche article vers la ligne vente ou la ligne feuille article.  

 Lorsque vous reportez, le programme copie le coût unitaire vers l'écriture article facture vente, et il peut être vu dans la liste d'écritures de l'article. [!INCLUDE[prod_short](includes/prod_short.md)] utilise le coût unitaire de la ligne document source pour calculer la valeur du champ **Coût indiqué (réel)**, ou éventuellement du champ **Coût indiqué (prévu)** dans l'écriture valeur concernant cette écriture article.  

## <a name="see-also" />Voir aussi
[Gestion des coûts ajustés](finance-manage-inventory-costs.md)  
[Inventaire](inventory-manage-inventory.md)  
[Vente](sales-manage-sales.md)  
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
