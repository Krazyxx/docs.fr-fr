---
title: 'Procédure : Utiliser plusieurs jetons de sécurité du même Type'
ms.date: 03/30/2017
ms.assetid: cf179f48-4ed4-4caa-86a5-ef8eecc231cd
ms.openlocfilehash: a532d40d8c31894c63a382ecad0cbcf8b42e3a66
ms.sourcegitcommit: bef803e2025642df39f2f1e046767d89031e0304
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2019
ms.locfileid: "56303762"
---
# <a name="how-to-use-multiple-security-tokens-of-the-same-type"></a>Procédure : Utiliser plusieurs jetons de sécurité du même Type
-   Dans le [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 3.0, un message client ne pouvait contenir qu'un jeton d'un type donné. Désormais, les messages peuvent contenir plusieurs jetons d'un type donné. Cette rubrique explique comment inclure plusieurs jetons du même type dans un message client.  
  
-   Notez que vous ne pouvez pas configurer un service ainsi : un service peut contenir un seul jeton de prise en charge.  
  
### <a name="to-use-multiple-security-tokens-of-the-same-type"></a>Pour utiliser plusieurs jetons de sécurité du même type  
  
1.  Créez une collection d'éléments de liaison vide à remplir.  
  
     [!code-csharp[C_CustomBinding#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#9)]  
  
2.  Créez un <xref:System.ServiceModel.Channels.SecurityBindingElement> en appelant <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateMutualCertificateBindingElement%2A>.  
  
     [!code-csharp[C_CustomBinding#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#10)]  
  
3.  Créez une collection <xref:System.ServiceModel.Security.Tokens.SupportingTokenParameters>.  
  
     [!code-csharp[C_CustomBinding#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#11)]  
  
4.  Ajoutez des jetons SAML à la collection.  
  
     [!code-csharp[C_CustomBinding#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#12)]  
  
5.  Ajoutez la collection à <xref:System.ServiceModel.Channels.SecurityBindingElement>.  
  
     [!code-csharp[C_CustomBinding#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#13)]  
  
6.  Ajoutez des éléments de liaison à la collection d'éléments de liaison.  
  
     [!code-csharp[C_CustomBinding#14](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#14)]  
  
7.  Retournez une nouvelle liaison personnalisée créée à partir de la collection d'éléments de liaison.  
  
     [!code-csharp[C_CustomBinding#15](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#15)]  
  
## <a name="example"></a>Exemple  
 Vous trouverez ci-dessous la méthode complète décrite par la procédure précédente.  
  
 [!code-csharp[C_CustomBinding#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#7)]  
