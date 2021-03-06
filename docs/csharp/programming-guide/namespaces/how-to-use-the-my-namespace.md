---
title: "Procédure : Utiliser l'espace de noms My - Guide de programmation C#"
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, My namespace access
ms.assetid: e7152414-0ea5-4c8e-bf02-c8d5bbe45ff4
ms.openlocfilehash: b56a421dd7b34bf006e1e6609bbb8ecc5f56e0bf
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/28/2019
ms.locfileid: "56971258"
---
# <a name="how-to-use-the-my-namespace-c-programming-guide"></a>Procédure : Utiliser l'espace de noms My (Guide de programmation C#)
L’espace de noms <xref:Microsoft.VisualBasic.MyServices> (`My` en Visual Basic) permet d’accéder de manière simple et intuitive à un certain nombre de classes .NET Framework, ce qui vous permet d’écrire du code qui interagit avec l’ordinateur, l’application, les paramètres, les ressources, etc. Bien que conçu à l’origine pour une utilisation avec Visual Basic, l’espace de noms `MyServices` peut être utilisé dans les applications C#.  
  
 Pour plus d’informations sur l’utilisation de l’espace de noms `MyServices` de Visual Basic, consultez [Développement avec My](../../../visual-basic/developing-apps/development-with-my/index.md).  
  
## <a name="adding-a-reference"></a>Ajout d’une référence  
 Pour pouvoir utiliser les classes `MyServices` dans votre solution, vous devez d’abord ajouter une référence à la bibliothèque Visual Basic.  
  
#### <a name="to-add-a-reference-to-the-visual-basic-library"></a>Pour ajouter une référence à la bibliothèque Visual Basic  
  
1.  Dans l’**Explorateur de solutions**, cliquez avec le bouton droit sur le nœud **Références**, puis sélectionnez **Ajouter une référence**.  
  
2.  Une fois la boîte de dialogue **Références** affichée, faites défiler la liste et sélectionnez Microsoft.VisualBasic.dll.  
  
     Vous pouvez aussi inclure la ligne suivante de la section `using` au début de votre programme.  
  
     [!code-csharp[csProgGuideNamespaces#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces3.cs#18)]  
  
## <a name="example"></a>Exemple  
 Cet exemple appelle plusieurs méthodes statiques contenues dans l’espace de noms `MyServices`. Pour compiler ce code, une référence à Microsoft.VisualBasic.DLL doit être ajoutée au projet.  
  
 [!code-csharp[csProgGuideNamespaces#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces3.cs#19)]  
  
 Certaines classes de l’espace de noms `MyServices` ne peuvent pas être appelées à partir d’une application C# : par exemple, la classe <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy> n’est pas compatible. Dans ce cas particulier, les méthodes statiques, qui font partie intégrante de <xref:Microsoft.VisualBasic.FileIO.FileSystem> et qui sont aussi contenues dans VisualBasic.dll, peuvent être utilisées à la place. Par exemple, voici comment utiliser une méthode de ce type pour dupliquer un répertoire :  
  
 [!code-csharp[csProgGuideNamespaces#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces3.cs#20)]  
  
## <a name="see-also"></a>Voir aussi

- [Guide de programmation C#](../../../csharp/programming-guide/index.md)
- [Espaces de noms](../../../csharp/programming-guide/namespaces/index.md)
- [Utilisation d’espaces de noms](../../../csharp/programming-guide/namespaces/using-namespaces.md)
