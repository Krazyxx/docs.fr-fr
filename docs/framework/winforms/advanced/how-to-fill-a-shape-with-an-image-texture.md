---
title: 'Procédure : Remplir une forme avec une Texture d’Image'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], using with brushes
- bitmaps [Windows Forms], using texture
- shapes [Windows Forms], filling with images
ms.assetid: 508da5a6-2433-4d2b-9680-eaeae4e96e3b
ms.openlocfilehash: bf1e09548ff9bc4eb650048eb21a9c300f3f6405
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54601777"
---
# <a name="how-to-fill-a-shape-with-an-image-texture"></a>Procédure : Remplir une forme avec une Texture d’Image
Vous pouvez remplir une forme fermée avec une texture à l’aide de la <xref:System.Drawing.Image> classe et la <xref:System.Drawing.TextureBrush> classe.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant remplit une ellipse avec une image. Le code construit une <xref:System.Drawing.Image> de l’objet et passe ensuite l’adresse de ce <xref:System.Drawing.Image> objet en tant qu’argument à un <xref:System.Drawing.TextureBrush.%23ctor%2A> constructeur. La troisième instruction met à l’échelle de l’image et la quatrième remplit l’ellipse avec les copies répétées de l’image à l’échelle.  
  
 Dans le code suivant, le <xref:System.Drawing.TextureBrush.Transform%2A> propriété contient la transformation qui est appliquée à l’image avant qu’elle est dessinée. Supposons que l’image d’origine a une largeur de 640 pixels et une hauteur de 480 pixels. La transformation réduit l’image à 75 × 75 en définissant les valeurs de mise à l’échelle horizontales et verticales.  
  
> [!NOTE]
>  Dans l’exemple suivant, la taille de l’image est 75 × 75 et la taille de l’ellipse est 150 × 250. Étant donné que l’image est plus petite que l’ellipse qu’elle remplit, l’ellipse est affichée en mosaïque avec l’image. Signifie que l’image est répétée horizontalement et verticalement jusqu'à ce que la limite de la forme de mosaïque est atteinte. Pour plus d’informations sur la mosaïque, consultez [Comment : Remplir une forme avec une Image](../../../../docs/framework/winforms/advanced/how-to-tile-a-shape-with-an-image.md).  
  
 [!code-csharp[System.Drawing.UsingABrush#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.UsingABrush#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>Compilation du code  
 L'exemple précédent est conçu pour une utilisation avec Windows Forms et nécessite <xref:System.Windows.Forms.PaintEventArgs> `e`, qui est un paramètre du gestionnaire d'événements <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>Voir aussi
- [Utilisation d'un pinceau pour remplir des formes](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)
