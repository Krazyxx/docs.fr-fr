---
title: 'Procédure : Guide pratique pour substituer la méthode ToString - Guide de programmation C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- ToString method, overriding in C#
- inheritance [C#], overriding OnPaint and ToString
ms.assetid: 8016db69-1f19-420c-8e17-98e8bebb7749
ms.openlocfilehash: fd73deb4682ec12b982740f6e9e9c1e38a5688a3
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/01/2019
ms.locfileid: "57202429"
---
# <a name="how-to-override-the-tostring-method-c-programming-guide"></a>Procédure : Guide pratique pour substituer la méthode ToString (Guide de programmation C#)
En C#, chaque classe ou struct hérite implicitement de la classe <xref:System.Object>. Ainsi, chaque objet en C# obtient la méthode <xref:System.Object.ToString%2A>, qui retourne une représentation sous forme de chaîne de cet objet. Par exemple, toutes les variables de type `int` ont une méthode `ToString`, ce qui leur permet de retourner leur contenu sous forme de chaîne :  
  
 [!code-csharp[csProgGuideInheritance#37](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#37)]  
  
 Quand vous créez une classe ou un struct personnalisé, vous devez substituer la méthode <xref:System.Object.ToString%2A> pour fournir des informations sur votre type au code client.  
  
 Pour plus d’informations sur l’utilisation de chaînes de format et d’autres types de mise en forme personnalisée avec la méthode `ToString`, consultez [Mise en forme des types](../../../standard/base-types/formatting-types.md).  
  
> [!IMPORTANT]
>  Quand vous choisissez les informations à fournir par l’intermédiaire de cette méthode, déterminez si votre classe ou struct sera utilisé par du code non fiable. Veillez à ne pas fournir d’informations susceptibles d’être exploitées par du code malveillant.  
  
### <a name="to-override-the-tostring-method-in-your-class-or-struct"></a>Pour substituer la méthode ToString dans votre classe ou struct  
  
1.  Déclarez une méthode `ToString` avec les modificateurs et le type de retour suivants :  
  
    ```csharp  
    public override string ToString(){}  
    ```  
  
2.  Implémentez la méthode pour qu’elle retourne une chaîne.  
  
     L’exemple suivant retourne le nom de la classe en plus des données propres à une instance particulière de la classe.  
  
     [!code-csharp[csProgGuideInheritance#36](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#36)]  
  
     Vous pouvez tester la méthode `ToString` comme illustré dans l’exemple de code suivant :  
  
     [!code-csharp[csProgGuideInheritance#38](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#38)]  
  
## <a name="see-also"></a>Voir aussi

- <xref:System.IFormattable>
- [Guide de programmation C#](../../../csharp/programming-guide/index.md)
- [Classes et structs](../../../csharp/programming-guide/classes-and-structs/index.md)
- [Chaînes](../../../csharp/programming-guide/strings/index.md)
- [string](../../../csharp/language-reference/keywords/string.md)
- [new](../../../csharp/language-reference/keywords/new.md)
- [override](../../../csharp/language-reference/keywords/override.md)
- [virtual](../../../csharp/language-reference/keywords/virtual.md)
- [Mise en forme des types](../../../standard/base-types/formatting-types.md)
