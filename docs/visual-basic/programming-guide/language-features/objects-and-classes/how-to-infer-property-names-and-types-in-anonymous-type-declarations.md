---
title: 'Procédure : Déduire les noms de propriété et les Types dans les déclarations de Type anonyme (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- inferring property names [Visual Basic]
- anonymous types [Visual Basic], inferring property names and types
- inferring property types [Visual Basic]
ms.assetid: 7c748b22-913f-4d9d-b747-6b7bf296a0bc
ms.openlocfilehash: c5f960b9f043cc886e5b5ac0307ed807c1602f43
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/28/2019
ms.locfileid: "56971753"
---
# <a name="how-to-infer-property-names-and-types-in-anonymous-type-declarations-visual-basic"></a>Procédure : Déduire les noms de propriété et les Types dans les déclarations de Type anonyme (Visual Basic)
Les types anonymes ne fournissent pas de mécanisme permettant de spécifier directement les types de données des propriétés. Les types de toutes les propriétés sont déduits. Dans l’exemple suivant, les types de `Name` et de `Price` sont déduits directement des valeurs utilisées pour les initialiser.  
  
 [!code-vb[VbVbalrAnonymousTypes#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#1)]  
  
 Les types anonymes peuvent également déduire les types et les noms de propriété à partir d’autres sources. Les sections qui suivent décrivent les cas où l’inférence est possible et des cas où elle ne l’est pas.  
  
## <a name="successful-inference"></a>Inférence possible  
  
#### <a name="anonymous-types-can-infer-property-names-and-types-from-the-following-sources"></a>Les types anonymes peuvent déduire les types et les noms de propriété à partir des sources suivantes :  
  
-   Noms de variable. Le type anonyme `anonProduct` a deux propriétés : `productName` et `productPrice`. Leurs types de données sont ceux des variables initiales, `String` et `Double`respectivement.  
  
     [!code-vb[VbVbalrAnonymousTypes#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#11)]  
  
-   Noms de propriété ou de champ d’autres objets. Prenez l’exemple d’un objet `car` de type `CarClass` qui a les propriétés `Name` et `ID` . Pour créer une instance de type anonyme `car1`avec les propriétés `Name` et `ID` initialisées avec les valeurs de l’objet `car` , vous pouvez écrire ce qui suit :  
  
     [!code-vb[VbVbalrAnonymousTypes#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#34)]  
  
     La déclaration qui précède équivaut à la plus longue ligne de code qui définit le type anonyme `car2`.  
  
     [!code-vb[VbVbalrAnonymousTypes#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#35)]  
  
-   Noms de membre XML.  
  
     [!code-vb[VbVbalrAnonymousTypes#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#12)]  
  
     Le type résultant pour `anon` a alors une seule propriété, `Book`, de type <xref:System.Collections.IEnumerable>(Of XElement).  
  
-   Fonction n’ayant aucun paramètre, telle que `SomeFunction` (voir l’exemple suivant).  
  
     `Dim sc As New SomeClass`  
  
     `Dim anon1 = New With {Key sc.SomeFunction()}`  
  
     La variable `anon2` présente dans le code suivant est un type anonyme qui a une seule propriété, un caractère nommé `First`. Ce code affiche la lettre « E », qui est la lettre retournée par la fonction <xref:System.Linq.Enumerable.First%2A>.  
  
     [!code-vb[VbVbalrAnonymousTypes#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#13)]  
  
## <a name="inference-failures"></a>Inférence impossible  
  
#### <a name="name-inference-will-fail-in-many-circumstances-including-the-following"></a>L’inférence de nom échoue dans de nombreux cas, notamment les suivants :  
  
-   L’inférence dérive de l’appel d’une méthode, d’un constructeur ou d’une propriété paramétrable qui nécessite des arguments. La déclaration précédente de `anon1` échoue si `someFunction` a un ou plusieurs arguments.  
  
     `' Not valid.`  
  
     `' Dim anon3 = New With {Key sc.someFunction(someArg)}`  
  
     L’assignation à un nouveau nom de propriété résout le problème.  
  
     `' Valid.`  
  
     `Dim anon4 = New With {Key .FunResult = sc.someFunction(someArg)}`  
  
-   L’inférence dérive d’une expression complexe.  
  
    ```  
    Dim aString As String = "Act "  
    ' Not valid.  
    ' Dim label = New With {Key aString & "IV"}  
    ```  
  
     L’erreur peut être résolue en assignant le résultat de l’expression à un nom de propriété.  
  
     [!code-vb[VbVbalrAnonymousTypes#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#14)]  
  
-   L’inférence pour plusieurs propriétés produit deux propriétés ou plus, qui portent le même nom. Dans les déclarations des exemples précédents, vous ne pouvez pas spécifier `product.Name` et `car1.Name` en tant que propriétés du même type anonyme. Sinon, l’identificateur déduit pour chaque propriété serait `Name`.  
  
     `' Not valid.`  
  
     `' Dim anon5 = New With {Key product.Name, Key car1.Name}`  
  
     Le problème peut être résolu en assignant les valeurs à des noms de propriété distincts.  
  
     [!code-vb[VbVbalrAnonymousTypes#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#36)]  
  
     Notez que les changements de casse (majuscules et minuscules) ne produisent pas deux noms distincts.  
  
     `Dim price = 0`  
  
     `' Not valid, because Price and price are the same name.`  
  
     `' Dim anon7 = New With {Key product.Price, Key price}`  
  
-   Le type et la valeur d’origine d’une propriété dépendent d’une autre propriété qui n’est pas encore établie. Par exemple, `.IDName = .LastName` n’est pas valide dans une déclaration de type anonyme, sauf si `.LastName` est déjà initialisé.  
  
     `' Not valid.`  
  
     `' Dim anon8 = New With {Key .IDName = .LastName, Key .LastName = "Jones"}`  
  
     Dans cet exemple, vous pouvez résoudre le problème en inversant l’ordre de déclaration des propriétés.  
  
     [!code-vb[VbVbalrAnonymousTypes#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#15)]  
  
-   Un nom de propriété de type anonyme est identique au nom d’un membre de la méthode <xref:System.Object>. Par exemple, la déclaration suivante échoue, car `Equals` est une méthode <xref:System.Object>.  
  
     `' Not valid.`  
  
     `' Dim relationsLabels1 = New With {Key .Equals = "equals", Key .Greater = _`  
  
     `'                       "greater than", Key .Less = "less than"}`  
  
     Vous pouvez résoudre le problème en modifiant le nom de la propriété :  
  
     [!code-vb[VbVbalrAnonymousTypes#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#16)]  
  
## <a name="see-also"></a>Voir aussi
- [Initialiseurs d’objets : Types nommés et anonymes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [Inférence de type local](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Types anonymes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [Key](../../../../visual-basic/language-reference/modifiers/key.md)
