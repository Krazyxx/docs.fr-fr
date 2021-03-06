---
title: 'Procédure : écrire les services par programmation'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- services, creating
- Windows Service applications, creating
ms.assetid: 3abbb2ec-78d2-41e6-b9f9-6662d4e2cdc7
author: ghogen
ms.openlocfilehash: 70a2c184e7b39af7b4f0466ac9ac627cff98f0c0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54672910"
---
# <a name="how-to-write-services-programmatically"></a>Procédure : écrire les services par programmation
Si vous choisissez de ne pas utiliser le modèle de projet Service Windows, vous pouvez écrire vos propres services en configurant vous-même l’héritage et d’autres éléments d’infrastructure. Quand vous créez un service par programmation, vous devez effectuer plusieurs étapes qui sont normalement gérées pour vous par le modèle :  
  
-   Vous devez configurer votre classe de service pour qu’elle hérite de la classe <xref:System.ServiceProcess.ServiceBase>.  
  
-   Vous devez créer une méthode `Main` pour votre projet de service qui définit les services à exécuter et appelle la méthode <xref:System.ServiceProcess.ServiceBase.Run%2A> sur ceux-ci.  
  
-   Vous devez substituer les procédures <xref:System.ServiceProcess.ServiceBase.OnStart%2A> et <xref:System.ServiceProcess.ServiceBase.OnStop%2A> et indiquer le code que vous souhaitez qu’elles exécutent.  
  
### <a name="to-write-a-service-programmatically"></a>Pour écrire un service par programmation  
  
1.  Créez un projet vide, puis une référence aux espaces de noms nécessaires. Pour cela, effectuez les étapes suivantes :  
  
    1.  Dans **l’Explorateur de solutions**, cliquez avec le bouton droit sur le nœud **Références**, puis cliquez sur **Ajouter une référence**.  
  
    2.  Sous l’onglet **.NET Framework**, faites défiler jusqu’à **System.dll**, puis cliquez sur **Sélectionner**.  
  
    3.  Faites défiler jusqu’à **System.Diagnostics.dll**, puis cliquez sur **Sélectionner**.  
  
    4.  Cliquez sur **OK**.  
  
2.  Ajoutez une classe et configurez-la pour qu’elle hérite de <xref:System.ServiceProcess.ServiceBase> :  
  
     [!code-csharp[VbRadconService#7](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#7)]
     [!code-vb[VbRadconService#7](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#7)]  
  
3.  Ajoutez le code suivant pour configurer votre classe de service :  
  
     [!code-csharp[VbRadconService#8](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#8)]
     [!code-vb[VbRadconService#8](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#8)]  
  
4.  Créez une méthode `Main` pour votre classe, et utilisez-la pour définir le service qui sera contenu dans votre classe. `userService1` est le nom de la classe :  
  
     [!code-csharp[VbRadconService#9](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#9)]
     [!code-vb[VbRadconService#9](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#9)]  
  
5.  Substituez la méthode <xref:System.ServiceProcess.ServiceBase.OnStart%2A>, et définissez le traitement qui doit se produire au démarrage de votre service.  
  
     [!code-csharp[VbRadconService#10](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#10)]
     [!code-vb[VbRadconService#10](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#10)]  
  
6.  Substituez les autres méthodes pour lesquelles vous souhaitez définir un traitement personnalisé, et écrivez le code nécessaire pour déterminer les actions que le service doit prendre dans chaque cas.  
  
7.  Ajoutez les programmes d'installation nécessaires à votre application de service. Pour plus d'informations, voir [Procédure : ajouter des programmes d’installation à votre application de service](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).  
  
8.  Générez votre projet en sélectionnant **Générer la solution** dans le menu **Générer**.  
  
    > [!NOTE]
    >  N'appuyez pas sur la touche F5 pour exécuter votre projet : vous ne pouvez pas exécuter un projet de service de cette manière.  
  
9. Créez un projet d’installation et les actions personnalisées pour installer votre service. Pour obtenir un exemple, consultez [Procédure pas à pas : Création d’une application de service Windows dans le Concepteur de composants](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md).  
  
10. Installez le service. Pour plus d'informations, voir [Procédure : Installer et désinstaller des services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).  
  
## <a name="see-also"></a>Voir aussi
- [Introduction aux applications de service Windows](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
- [Guide pratique pour créer des services Windows](../../../docs/framework/windows-services/how-to-create-windows-services.md)
- [Guide pratique pour ajouter des programmes d’installation à votre application de service](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)
- [Guide pratique pour enregistrer des informations relatives aux services](../../../docs/framework/windows-services/how-to-log-information-about-services.md)
- [Procédure pas à pas : Création d’une application de service Windows dans le Concepteur de composants](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)
