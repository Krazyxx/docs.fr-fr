---
title: Espaces blancs dans les littéraux XML (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- white space [XML in Visual Basic]
- XML literals [Visual Basic], white space
ms.assetid: dfe3a9ff-d69a-418e-a6b5-476f4ed84219
ms.openlocfilehash: ef371a984d03485ccaf1ee5d61aa3cf39d80ef32
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/28/2019
ms.locfileid: "56979058"
---
# <a name="white-space-in-xml-literals-visual-basic"></a>Espaces blancs dans les littéraux XML (Visual Basic)
Le compilateur Visual Basic incorpore uniquement les caractères d’espace blanc significatif à partir d’un littéral XML lorsqu’il crée un [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objet. Les caractères d’espaces blancs non significatifs ne sont pas incorporées.  
  
## <a name="significant-and-insignificant-white-space"></a>Espaces blancs significatifs et non significatifs  
 Caractères d’espace blanc dans les littéraux XML sont significatifs que dans trois zones :  
  
-   Lorsqu’ils sont dans une valeur d’attribut.  
  
-   Quand ils font partie d’un élément contenu de texte et le texte contient également d’autres caractères.  
  
-   Lorsqu’ils sont dans une expression incorporée pour le contenu de texte d’un élément.  
  
 Sinon, le compilateur traite les caractères d’espace blanc comme insignifiants et ne les inclut pas dans le [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objet pour le littéral.  
  
 Pour inclure des espaces blancs non significatifs dans un littéral XML, utilisez une expression incorporée qui contient un littéral de chaîne avec les espaces blancs.  
  
> [!NOTE]
>  Si le `xml:space` attribut apparaît dans un littéral d’élément XML, le compilateur Visual Basic inclut l’attribut dans le <xref:System.Xml.Linq.XElement> objet, mais l’ajout de cet attribut ne modifie pas la façon dont le compilateur traite l’espace blanc.  
  
## <a name="examples"></a>Exemples  
 L’exemple suivant contient deux éléments XML, externes et internes. Les deux éléments contiennent un espace blanc dans leur contenu de texte. L’espace blanc dans l’élément externe est insignifiant, car il contient uniquement un espace blanc et un élément XML. L’espace blanc dans l’élément interne est significatif, car elle contient un espace blanc et texte.  
  
 [!code-vb[VbXMLSamples#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#29)]  
  
 Lorsque vous exécutez, ce code affiche le texte suivant.  
  
```xml  
<outer>  
  <inner>  
                                          Inner text  
                                      </inner>  
</outer>  
```  
  
## <a name="see-also"></a>Voir aussi
- [Création de code XML dans Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
