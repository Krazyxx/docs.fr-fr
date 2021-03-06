---
title: 'Procédure : Obtenir une valeur d’une propriété (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- property values [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- Visual Basic code, properties
- properties [Visual Basic], values
ms.assetid: 3954423e-6ab7-4a4c-b55c-a8d27be47891
ms.openlocfilehash: de5719527216411c7bd156f2cc0d369442eaee20
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/28/2019
ms.locfileid: "56964771"
---
# <a name="how-to-get-a-value-from-a-property-visual-basic"></a>Procédure : Obtenir une valeur d’une propriété (Visual Basic)
Vous récupérez des valeur d’une propriété en incluant le nom de propriété dans une expression.  
  
 La propriété `Get` procédure récupère la valeur, mais vous ne l’appelez pas explicitement par son nom. Vous utilisez la propriété tout comme vous utiliseriez une variable. Visual Basic effectue les appels à des procédures de la propriété.  
  
### <a name="to-retrieve-a-value-from-a-property"></a>Pour récupérer une valeur à partir d’une propriété  
  
1.  Utilisez le nom de propriété dans une expression de la même façon que vous utiliseriez un nom de variable. Vous pouvez utiliser une propriété partout où vous pouvez utiliser une variable ou une constante.  
  
     ou  
  
     Utilisez le nom de propriété suivant égaux (`=`) connectez-vous à une instruction d’assignation.  
  
     L’exemple suivant lit la valeur de Visual Basic `Now` propriété implicitement en appelant son `Get` procédure.  
  
     [!code-vb[VbVbalrDateProperties#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDateProperties/VB/Module1.vb#4)]  
  
2.  Si la propriété prend des arguments, faites suivre le nom de propriété entre parenthèses pour encadrer la liste d’arguments. S’il n’y a aucun argument, vous pouvez éventuellement omettre les parenthèses.  
  
3.  Placez les arguments dans la liste d’arguments entre parenthèses, séparées par des virgules. Veillez à que vous fournir les arguments dans le même ordre que la propriété définit les paramètres correspondants.  
  
 La valeur de la propriété participe à l’expression comme une variable ou constante serait, ou il est stocké dans la variable ou la propriété sur le côté gauche de l’instruction d’assignation.  
  
## <a name="see-also"></a>Voir aussi
- [Procédures](./index.md)
- [Procédures de propriété](./property-procedures.md)
- [Paramètres et arguments d’une procédure](./procedure-parameters-and-arguments.md)
- [Property (instruction)](../../../../visual-basic/language-reference/statements/property-statement.md)
- [Différences entre les propriétés et les Variables en Visual Basic](./differences-between-properties-and-variables.md)
- [Guide pratique pour Créer une propriété](./how-to-create-a-property.md)
- [Guide pratique pour Déclarer une propriété avec des niveaux d’accès mixtes](./how-to-declare-a-property-with-mixed-access-levels.md)
- [Guide pratique pour Appeler une procédure de propriété](./how-to-call-a-property-procedure.md)
- [Guide pratique pour Déclarer et appeler une propriété par défaut en Visual Basic](./how-to-declare-and-call-a-default-property.md)
- [Guide pratique pour Placer une valeur dans une propriété](./how-to-put-a-value-in-a-property.md)
