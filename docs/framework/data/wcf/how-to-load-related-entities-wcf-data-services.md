---
title: 'Procédure : Charger des entités connexes (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, deferred content
- WCF Data Services, loading data
ms.assetid: 6f143d30-d997-4e6b-bcf0-d5c394ecb108
ms.openlocfilehash: a05d294f80943e771a298b4442a521de86ff2f19
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54616964"
---
# <a name="how-to-load-related-entities-wcf-data-services"></a>Procédure : Charger des entités connexes (WCF Data Services)
Lorsque vous devez charger des entités connexes dans [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], vous pouvez utiliser la méthode <xref:System.Data.Services.Client.DataServiceContext.LoadProperty%2A> sur la classe <xref:System.Data.Services.Client.DataServiceContext>. Vous pouvez également utiliser le <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> méthode sur le <xref:System.Data.Services.Client.DataServiceQuery%601> pour exiger que connexes chargement anticipé des entités dans la même réponse de requête.  
  
 L'exemple dans cette rubrique utilise l'exemple de service de données Northwind et des classes de service de données clientes générées automatiquement. Ce service et les classes de données client sont créés lorsque vous complétez le [démarrage rapide WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Exemple  
 L'exemple suivant montre comment charger explicitement le `Customer` associé à chaque instance `Orders` retournée.  
  
 [!code-csharp[Astoria Northwind Client#LoadRelatedOrderCustomer](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#loadrelatedordercustomer)]
 [!code-vb[Astoria Northwind Client#LoadRelatedOrderCustomer](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#loadrelatedordercustomer)]  
  
## <a name="example"></a>Exemple  
 L'exemple ci-dessous montre comment utiliser la méthode <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> pour retourner `Order Details` qui appartient au `Orders` retourné par la requête.  
  
 [!code-csharp[Astoria Northwind Client#ExpandOrderDetails](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#expandorderdetails)]
 [!code-vb[Astoria Northwind Client#ExpandOrderDetails](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#expandorderdetails)]  
  
## <a name="see-also"></a>Voir aussi
- [Interrogation du service de données](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)
