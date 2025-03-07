---
title: Créer et modifier des présentations personnalisées pour les rapports et les documents
description: 'Découvrez comment créer des présentations personnalisées qui vous permettent de personnaliser l’apparence d’un rapport lorsqu’il est consulté, imprimé ou enregistré.'
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'customized report, document layout, logo, personalize'
ms.search.form: '9650, 9652'
ms.date: 03/06/2022
ms.author: edupont
---
# <a name="legacy-create-and-modify-custom-report-layouts" />(Hérité) Créer et modifier des présentations de rapport personnalisées

[!INCLUDE[legacy-custom-layouts](includes/legacy-custom-layouts.md)]

Par défaut, les rapports ont une présentation intégrée. La présentation de rapport peut être de type RDLC (langage de définition de rapport côté client), Microsoft Word, ou les deux. Vous ne pouvez pas modifier les présentations intégrées, mais vous pouvez créer des présentations personnalisées. Un rapport peut avoir plusieurs présentations de rapport personnalisées.

> [!NOTE]  
> Dans [!INCLUDE[prod_short](includes/prod_short.md)], le terme « rapport » couvre également les documents externes, tels que les factures vente et les confirmations de commande que vous envoyez aux clients sous la forme de fichiers PDF.

Pour créer une présentation personnalisée, copiez une présentation personnalisée existante ou ajoutez une nouvelle présentation personnalisée. Les présentations personnalisées sont souvent basées sur une présentation intégrée. Lorsque vous ajoutez une nouvelle présentation personnalisée, vous pouvez choisir d’ajouter une présentation de rapport de type RDLC ou Word, ou les deux. La nouvelle présentation personnalisée est basée sur la présentation intégrée pour le rapport s’il y en a une disponible. S’il n’y a pas de présentation intégrée pour le type de rapport, une nouvelle présentation vierge est créée. Vous devez modifier et concevoir cette mise en page vierge à partir de zéro. Pour en savoir plus sur les présentations de rapport RDLC et Word, les présentations intégrées et personnalisées, et plus encore, voir [Gérer la présentation des rapports](ui-manage-report-layouts.md).  

> [!TIP]
> Utilisez les rapports financiers pour obtenir un aperçu des données financières enregistrées dans votre plan comptable. Pour en savoir plus, voir [Préparer la génération de rapports financiers avec des données financières et des catégories de compte](bi-how-work-account-schedule.md).

Après avoir défini vos présentations de rapport personnalisées, vous pouvez les sélectionner sur les pages Fiche client et Fiche fournisseur. Les présentations seront utilisées lorsque vous créerez des documents pour le client ou le fournisseur. En savoir plus sur [Définir des présentations de document pour les clients et les fournisseurs](ui-define-customer-vendor-document-layouts.md).

Vous pouvez également utiliser des présentations de rapport personnalisées pour ajouter du contenu aux courriels. Les présentations de rapport peuvent vous faire gagner du temps et contribuer à assurer la cohérence, car elles réutilisent le même contenu lorsque vous communiquez avec vos clients. Pour utiliser des présentations de rapport personnalisées avec le courriel, le type de fichier de la présentation doit être Word, et non RDLC. Pour en savoir plus, voir [Configurer des textes et des présentations de courriel réutilisables](admin-how-setup-email.md#set-up-reusable-email-texts-and-layouts).

## <a name="create-a-custom-layout" />Créer une présentation personnalisée

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Sélection présentation rapport**, puis sélectionnez le lien associé.

    La page **Sélection présentation rapport** répertorie tous les rapports disponibles pour la compagnie spécifiée dans le champ **Nom de la compagnie** en haut de la page.
2. Dans le champ **Nom de la compagnie**, choisissez la compagnie pour laquelle vous souhaitez créer la présentation de rapport.
3. Sélectionnez la ligne du rapport pour lequel vous souhaitez créer la présentation, puis sélectionnez l’action **Présentations personnalisées**.  

   La page **Présentations rapport personnalisées** s’affiche et répertorie toutes les présentations personnalisées disponibles pour le rapport sélectionné.
4. Si vous souhaitez créer une copie d’une présentation personnalisée existante, sélectionnez cette dernière, puis sélectionnez l’action **Copier**.  

   La copie de la présentation personnalisée s'affiche sur la page **Présentations rapport personnalisées**. Le terme *Copie* figure dans le champ **Description**.
5. Si vous voulez ajouter une nouvelle présentation personnalisée basée sur une présentation intégrée, procédez comme suit :  
   1. Sélectionnez l'action **Nouveau**. La page **Insérer présentation intégrée pour un rapport** s’affiche avec les champs **Code** et **Nom** automatiquement renseignés.
   2. Activez le bouton à bascule **Insérer présentation Word** pour ajouter une présentation rapport Word personnalisée OU activez le bouton à bascule **Insérer présentation RDLC** pour ajouter une présentation de rapport RDLC personnalisée.
   4. Cliquez sur le bouton **OK**.  

    La nouvelle présentation personnalisée s’affiche désormais sur la page **Présentations rapport personnalisées**. Si une nouvelle présentation est basée sur une présentation intégrée, les termes **Copie d’une présentation intégrée** figurent dans le champ **Description**. S’il n’y avait aucune présentation intégrée pour le rapport, les termes **Nouvelle présentation** figurent dans le champ **Description** de la nouvelle présentation, pour indiquer que la présentation personnalisée est vide.
6. Par défaut, le champ **Nom de la compagnie** est vide, ce qui signifie que la présentation personnalisée est disponible pour les rapports de toutes les compagnies. Afin que la présentation personnalisée soit disponible pour une compagnie spécifique uniquement, sélectionnez **Modifier**, puis définissez le champ **Nom de la compagnie** sur la compagnie que vous souhaitez.

La mise en page personnalisée a été créée et vous pouvez la modifier à votre guise.

> [!TIP]
> Vous pouvez exporter les résultats de rapport dans un fichier Microsoft Excel pour afficher l’ensemble de données complet, y compris toutes les colonnes, mais sans la présentation. Le fichier Excel peut vous aider à confirmer que le rapport renvoie les données attendues ou diagnostique des problèmes. Pour en savoir plus, voir [Analyse des données de rapport avec Excel](report-analyze-excel.md).

## <a name="a-namemodifycustomlayoutamodifying-a-custom-layout" /><a name="ModifyCustomLayout"></a>Modification d'une présentation personnalisée

Pour modifier une présentation de rapport personnalisée, vous devez d’abord exporter la présentation de rapport sous forme de fichier vers un emplacement sur votre ordinateur ou réseau. Ensuite, ouvrez le document exporté et apportez les modifications. Lorsque vous avez terminé d’apporter les modifications, vous importez la présentation de rapport.

### <a name="modify-a-custom-layout" />Modifier une présentation personnalisée

1. Exportez une présentation personnalisée à partir de la page **Présentations rapport personnalisées**. Si cette page n’est pas déjà ouverte, recherchez et ouvrez la page **Sélection présentation rapport**, sélectionnez le rapport dont vous souhaitez modifier la présentation, puis choisissez l’action **Présentations personnalisées**.  
2. Sur la page **Présentations rapport personnalisées**, sélectionnez la présentation à modifier, choisissez l’action **Exporter présentation**, puis choisissez **Enregistrer** ou **Enregistrer sous** pour enregistrer le document de présentation de rapport dans un emplacement sur votre ordinateur ou réseau.  
3. Ouvrez le document de présentation de rapport que vous avez enregistré, puis apportez les modifications.

   Si vous modifiez une présentation Word, ouvrez le document de présentation dans Word. Pour en savoir plus sur la modification des rapports Word, voir [Utiliser des présentations Word](ui-how-add-fields-word-report-layout.md)<!--the next section [Making Changes to the Report Layout](ui-how-create-custom-report-layout.md#MakeChangesToLayout)-->.

   Les présentations de rapport RDLC sont plus avancées que les présentations de rapport Word. Pour plus d’informations sur la modification d’une présentation de rapport RDLC, voir [Création de présentations de rapport RDLC](/dynamics-nav/Designing-RDLC-Report-Layouts).

   Pensez à enregistrer vos modifications une fois que vous avez terminé.

4. Retournez à la page **Présentations rapport personnalisées**, sélectionnez la présentation de rapport que vous avez exportée et modifiée, puis choisissez l’action **Importer présentation**.  

5. Dans la boîte de dialogue **Importer**, sélectionnez **Choisir** pour rechercher et sélectionner le document de présentation de rapport modifié, puis choisissez **Ouvrir**.

> [!IMPORTANT]
> N’oubliez pas d’importer le document de mise en page de rapport que vous avez modifié. Sinon, la nouvelle mise en page du rapport ne sera pas disponible.

<!--
## <a name="a-namemakechangestolayouta-create-and-modify-custom-report-layouts" /><a name="MakeChangesToLayout"></a> Create and modify custom report layouts

To make general formatting and layout changes, such as changing text font, adding and modifying a table, or removing a data field, just use the basic editing features of Word like you do with any Word document.

If you're designing a Word report layout from scratch or adding new data fields, then start by adding a table that includes rows and columns that will eventually hold the data fields.

> [!TIP]  
> Show the table gridlines so that you see the boundaries of table cells. Remember to hide the gridlines when you're done editing. To show or hide table gridlines, select the table, and then under **Layout** on the **Table** tab, choose **View Gridlines**.

### <a name="embedding-fonts-in-word-layouts-for-consistency" />Embedding fonts in Word layouts for consistency

To ensure that reports always display and print with the intended fonts, wherever users open or print the reports, you can embed the fonts in the Word document. However, embedding fonts can significantly increase the size of the Word files. Learn more about embedding fonts in Word at [Embed fonts in Word, PowerPoint, or Excel](https://support.office.com/article/Embed-fonts-in-Word-PowerPoint-or-Excel-cb3982aa-ea76-4323-b008-86670f222dbc).

### <a name="a-nameremovefielda-removing-label-and-data-fields-in-word-layouts" /><a name="RemoveField"></a> Removing label and data fields in Word layouts

 Label and data fields of a report are contained in content controls in Word. The following figure illustrates a content control when it's selected in the Word document.  

 ![Content control for field in Word report layout.](media/nav_wordreportlayouts_contentcontrol.png "NAV_WordReportLayouts_ContentControl")  

 The name of the label or data field name displays in the content control. In the example, the field name is CompanyAddr1.  

### <a name="to-remove-a-label-or-data-field" />To remove a label or data field

1. Right-click the field you want to delete, then choose **Remove Content Control**.  

     The content control is removed, but the field name remains as text.  

2. Delete the remaining text as needed.  

### <a name="adding-data-fields" />Adding data fields

Adding data fields from a report dataset is more advanced and requires some knowledge of the report dataset. Learn more about adding fields for data, labels, and images at [Add Fields to a Word Report Layout](ui-how-add-fields-word-report-layout.md).  -->

## <a name="see-related-microsoft-trainingtrainingmoduleschange-documents-dynamics-365-business-centralindex" />Voir la [formation Microsoft](/training/modules/change-documents-dynamics-365-business-central/index) associée

## <a name="see-also" />Voir aussi .

[Gestion des présentations de rapport](ui-manage-report-layouts.md)  
[Modifier la présentation actuelle du rapport](ui-how-change-layout-currently-used-report.md)  
[Importer et exporter une présentation de rapport ou de document personnalisée](ui-how-import-and-export-report-layout.md)  
[Utiliser des rapports, des traitements en lot et des XMLports](ui-work-report.md)  
[Préparer la génération de rapports financiers avec des données financières et des catégories de compte](bi-how-work-account-schedule.md)  
[Veille économique](bi.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
