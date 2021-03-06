---
title: Fonctions de chaîne (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- string functions
ms.assetid: f1bf9ac2-cbcf-4298-ae51-53182076bdc8
ms.openlocfilehash: 11ea31ae245d34525ea33d5d2a53a72f1c415b16
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/28/2019
ms.locfileid: "56981450"
---
# <a name="string-functions-visual-basic"></a>Fonctions de chaîne (Visual Basic)
Le tableau suivant répertorie les fonctions fournies par Visual Basic pour rechercher et manipuler des chaînes.  
  
|Méthode .NET framework|Description|  
|---------------------------|-----------------|  
|<xref:Microsoft.VisualBasic.Strings.Asc%2A>, <xref:Microsoft.VisualBasic.Strings.AscW%2A>|Retourne un `Integer` valeur représentant le code de caractère correspondant à un caractère.|  
|<xref:Microsoft.VisualBasic.Strings.Chr%2A>, <xref:Microsoft.VisualBasic.Strings.ChrW%2A>|Retourne le caractère associé au code de caractère spécifié.|  
|<xref:Microsoft.VisualBasic.Strings.Filter%2A>|Retourne un tableau de base zéro qui contient un sous-ensemble d’un `String` tableau basé sur des critères de filtre spécifiés.|  
|<xref:Microsoft.VisualBasic.Strings.Format%2A>|Retourne une chaîne mise en forme conformément aux instructions contenues dans un format `String` expression.|  
|<xref:Microsoft.VisualBasic.Strings.FormatCurrency%2A>|Retourne une expression sous formatée de valeur monétaire utilisant le symbole monétaire défini dans le panneau de configuration système.|  
|<xref:Microsoft.VisualBasic.Strings.FormatDateTime%2A>|Retourne une expression de chaîne représentant une valeur de date/heure.|  
|<xref:Microsoft.VisualBasic.Strings.FormatNumber%2A>|Retourne une expression sous formatée de nombre.|  
|<xref:Microsoft.VisualBasic.Strings.FormatPercent%2A>|Retourne une expression au format pourcentage (c’est-à-dire multipliée par 100) avec le caractère de fin %.|  
|<xref:Microsoft.VisualBasic.Strings.InStr%2A>|Retourne un entier spécifiant la position de début de la première occurrence d’une chaîne dans une autre.|  
|<xref:Microsoft.VisualBasic.Strings.InStrRev%2A>|Retourne la position de la première occurrence d’une chaîne dans une autre, à partir du côté droit de la chaîne.|  
|<xref:Microsoft.VisualBasic.Strings.Join%2A>|Retourne une chaîne créée par la jonction de plusieurs sous-chaînes contenues dans un tableau.|  
|<xref:Microsoft.VisualBasic.Strings.LCase%2A>|Retourne une chaîne ou un caractère converti en minuscules.|  
|<xref:Microsoft.VisualBasic.Strings.Left%2A>|Retourne une chaîne contenant un nombre spécifié de caractères du côté gauche d’une chaîne.|  
|<xref:Microsoft.VisualBasic.Strings.Len%2A>|Retourne un entier qui contient le nombre de caractères dans une chaîne.|  
|<xref:Microsoft.VisualBasic.Strings.LSet%2A>|Retourne une chaîne alignée à gauche contenant la chaîne spécifiée ajustée à la longueur spécifiée.|  
|<xref:Microsoft.VisualBasic.Strings.LTrim%2A>|Retourne une chaîne contenant une copie d’une chaîne spécifiée sans espaces à gauche.|  
|<xref:Microsoft.VisualBasic.Strings.Mid%2A>|Retourne une chaîne contenant un nombre spécifié de caractères à partir d’une chaîne.|  
|<xref:Microsoft.VisualBasic.Strings.Replace%2A>|Retourne une chaîne dans laquelle une sous-chaîne spécifiée a été remplacée par une autre sous-chaîne, un nombre de fois spécifié.|  
|<xref:Microsoft.VisualBasic.Strings.Right%2A>|Retourne une chaîne contenant un nombre spécifié de caractères depuis la partie droite d’une chaîne.|  
|<xref:Microsoft.VisualBasic.Strings.RSet%2A>|Retourne une chaîne alignée à droite contenant la chaîne spécifiée ajustée à la longueur spécifiée.|  
|<xref:Microsoft.VisualBasic.Strings.RTrim%2A>|Retourne une chaîne contenant une copie d’une chaîne spécifiée sans espaces à droite.|  
|<xref:Microsoft.VisualBasic.Strings.Space%2A>|Retourne une chaîne composée d’un nombre spécifié d’espaces.|  
|<xref:Microsoft.VisualBasic.Strings.Split%2A>|Retourne un tableau unidimensionnel de base zéro qui contient un nombre spécifié de sous-chaînes.|  
|<xref:Microsoft.VisualBasic.Strings.StrComp%2A>|Retourne -1, 0 ou 1, selon le résultat d’une comparaison de chaînes.|  
|<xref:Microsoft.VisualBasic.Strings.StrConv%2A>|Retourne une chaîne convertie comme spécifié.|  
|<xref:Microsoft.VisualBasic.Strings.StrDup%2A>|Retourne une chaîne ou un objet constitué du caractère spécifié répété le nombre de fois spécifié.|  
|<xref:Microsoft.VisualBasic.Strings.StrReverse%2A>|Retourne une chaîne dans laquelle l’ordre des caractères d’une chaîne spécifiée est inversé.|  
|<xref:Microsoft.VisualBasic.Strings.Trim%2A>|Retourne une chaîne contenant une copie d’une chaîne spécifiée sans espaces de début ou de fin.|  
|<xref:Microsoft.VisualBasic.Strings.UCase%2A>|Retourne une chaîne ou un caractère contenant la chaîne spécifiée convertie en majuscules.|  
  
 Vous pouvez utiliser la [Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md) instruction pour définir si les chaînes sont comparées à l’aide d’un texte respectant la casse trier l’ordre déterminé par les paramètres régionaux de votre système (`Text`) ou par les représentations binaires internes de le (des caractères `Binary`). La méthode de comparaison de texte par défaut est `Binary`.  
  
## <a name="example"></a>Exemple  
 Cet exemple utilise le `UCase` fonction pour retourner une version en majuscules d’une chaîne.  
  
 [!code-vb[VbVbalrStrings#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#31)]  
  
## <a name="example"></a>Exemple  
 Cet exemple utilise le `LTrim` fonction pour supprimer les espaces de début et la `RTrim` des espaces à partir d’une variable de chaîne de fonction à la fin de la frange. Il utilise le `Trim` (fonction) pour supprimer les deux types d’espaces.  
  
 [!code-vb[VbVbalrStrings#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#25)]  
  
## <a name="example"></a>Exemple  
 Cet exemple utilise le `Mid` fonction pour retourner un nombre spécifié de caractères à partir d’une chaîne.  
  
 [!code-vb[VbVbalrStrings#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#17)]  
  
## <a name="example"></a>Exemple  
 Cet exemple utilise `Len` pour retourner le nombre de caractères dans une chaîne.  
  
 [!code-vb[VbVbalrStrings#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#33)]  
  
## <a name="example"></a>Exemple  
 Cet exemple utilise le `InStr` fonction pour retourner la position de la première occurrence d’une chaîne dans une autre.  
  
 [!code-vb[VbVbalrStrings#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#8)]  
  
## <a name="example"></a>Exemple  
 Cet exemple illustre différentes utilisations de la `Format` fonction des valeurs de format à l’aide de deux `String` formats et les formats définis par l’utilisateur. Pour le séparateur de date (`/`), séparateur d’heure (`:`) et les indicateurs AM/PM (`t` et `tt`), la sortie mise en forme réelle affichée par votre système dépend des paramètres régionaux utilisés par le code. Lorsque heures et dates sont affichées dans l’environnement de développement, le format d’heure courte et le format de date courte des paramètres régionaux de code sont utilisés.  
  
> [!NOTE]
>  Pour les paramètres régionaux qui utilisent une horloge de 24 heures, les indicateurs AM/PM (`t` et `tt`) n’affichent rien.  
  
 [!code-vb[VbVbalrStrings#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#27)]  
  
## <a name="see-also"></a>Voir aussi
- [Mots clés](../../../visual-basic/language-reference/keywords/index.md)
- [Membres de la bibliothèque runtime Visual Basic](../../../visual-basic/language-reference/runtime-library-members.md)
- [Liste des manipulations de chaînes](../../../visual-basic/language-reference/keywords/string-manipulation-summary.md)
