---
title: Création du Document Office Open XML Source (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 61ccd6fb-0c47-4075-afdf-5b5021330f21
ms.openlocfilehash: 124f22e3a4b3e43dd454aca9389691a89debcf6f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54617445"
---
# <a name="creating-the-source-office-open-xml-document-visual-basic"></a>Création du Document Office Open XML Source (Visual Basic)
Cette rubrique montre comment créer le document WordprocessingML Office Open XML utilisé par les autres exemples de ce didacticiel. Si vous suivez ces instructions, votre sortie correspondra à la sortie fournie dans chaque exemple.  
  
 Toutefois, les exemples présentés dans ce didacticiel fonctionnent avec n'importe quel document WordprocessingML valide.  
  
 Pour créer le document utilisé par ce didacticiel, Microsoft Office 2007 ou une version ultérieure, ou bien Microsoft Office 2003 avec le Module de compatibilité Microsoft Office pour les formats de fichiers Word, Excel et PowerPoint 2007 doit être installé sur votre ordinateur.  
  
## <a name="creating-the-wordprocessingml-document"></a>Création du document WordprocessingML  
  
#### <a name="to-create-the-wordprocessingml-document"></a>Pour créer le document WordprocessingML  
  
1.  Créez un nouveau document Microsoft Word.  
  
2.  Collez le texte suivant dans le nouveau document :  
  
    ```  
    Parsing WordprocessingML with LINQ to XML  
  
    The following example prints to the console.  
  
    Imports System  
  
    Class Program  
        Public Shared  Sub Main(ByVal args() As String)  
            Console.WriteLine("Hello World")  
        End Sub  
    End Class  
  
    This example produces the following output:  
  
    Hello World  
    ```  
  
3.  Mettez en forme la première ligne à l'aide du style « Titre 1 ».  
  
4.  Sélectionnez les lignes qui contiennent le code Visual Basic. La première ligne commence par le mot clé `Imports`. La dernière ligne est « End Class ». Mettez en forme les lignes avec la police Courrier. Mettez-les en forme avec un nouveau style et nommez le nouveau style « Code ».  
  
5.  Pour finir, sélectionnez la ligne entière qui contient la sortie et mettez-la en forme avec le style `Code`.  
  
6.  Enregistrez le document et nommez-le SampleDoc.docx.  
  
    > [!NOTE]
    >  Si vous utilisez Microsoft Word 2003, sélectionnez **Document Word 2007** dans la liste déroulante **Type de fichier**.  
  
## <a name="see-also"></a>Voir aussi
- [Tutoriel : Manipulation de contenu dans un Document WordprocessingML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)
