---
title: '#Directive de région (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.Region
- vb.#Region
helpviewer_keywords:
- Visual Basic compiler, compiler directives
- '#region directive'
- region directive (#region)
- '#Region keyword [Visual Basic]'
ms.assetid: 90a6a104-3cbf-47d0-bdc4-b585d0921b87
ms.openlocfilehash: d0abbdb9cb96ad9977a9af542f90eaad8a7e160e
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/28/2019
ms.locfileid: "56969711"
---
# <a name="region-directive"></a>#Region, directive
Réduit et masque des sections de code dans des fichiers Visual Basic.  
  
## <a name="syntax"></a>Syntaxe  

```vb
#Region "identifier_string"  
#End Region  
```  
  
## <a name="parts"></a>Composants  
  
|Terme|Définition|  
|---|---|  
|`identifier_string`|Obligatoire. Chaîne qui joue le rôle du titre d'une région quand elle est réduite. Les régions sont réduites par défaut.|  
|`#End Region`|Met fin au bloc `#Region`.|  
  
## <a name="remarks"></a>Notes  
 Utilisez la directive `#Region` pour spécifier un bloc de code que vous pouvez développer ou réduire dans le mode Plan de l'éditeur de code Visual Studio. Vous pouvez placer, ou *imbriquer*, régions dans d’autres régions pour grouper des régions semblables ensemble.  
  
## <a name="example"></a>Exemple  
 Cet exemple utilise la directive `#Region`.  
  
 [!code-vb[VbVbalrConditionalComp#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#4)]  
  
## <a name="see-also"></a>Voir aussi
- [#If...Then...#Else, directives](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [Mode Plan](/visualstudio/ide/outlining)
- [Guide pratique pour réduire et masquer des sections de code](../../../visual-basic/programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)
