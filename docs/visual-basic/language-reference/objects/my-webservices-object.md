---
title: My.WebServices (objet) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.WebServices
- My.MyProject.WebServices
helpviewer_keywords:
- My.WebServices object
ms.assetid: f188dc05-2c75-41b6-bb68-122d1c3110a2
ms.openlocfilehash: 1b4e703cb3f723ea283f725d0f4ce4711dca3c9e
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/28/2019
ms.locfileid: "56967813"
---
# <a name="mywebservices-object"></a>My.WebServices, objet
Fournit des propriétés pour la création et l’accès à une seule instance de chaque service Web XML référencé par le projet actuel.  
  
## <a name="remarks"></a>Notes  
 L’objet `My.WebServices` fournit une instance de chaque service web référencé par le projet actuel. Chaque instance est instanciée sur demande. Vous pouvez accéder à ces services web via les propriétés de l’objet `My.WebServices`. La propriété porte le même nom que le service web auquel elle accède. Toute classe qui hérite de <xref:System.Web.Services.Protocols.SoapHttpClientProtocol> est un service web. Pour plus d’informations sur l’ajout de services Web à un projet, consultez [l’accès aux applications Web Services](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).  
  
 Le `My.WebServices` objet expose uniquement les services Web associés au projet actuel. Il ne donne pas accès aux services Web déclarés dans les DLL référencées. Pour accéder à un service Web qui fournit une DLL, vous devez utiliser le nom qualifié du service Web, sous la forme *DllName*. *WebServiceName*. Pour plus d’informations, consultez [l’accès aux applications Web Services](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).  
  
 L’objet et ses propriétés ne sont pas disponibles pour les applications Web.  
  
## <a name="properties"></a>Properties  
 Chaque propriété de la `My.WebServices` objet fournit l’accès à une instance d’un service Web référencé par le projet actuel. Le nom de la propriété est le même que le nom du service Web qui accède à la propriété et le type de propriété est identique au type de service Web.  
  
> [!NOTE]
>  S’il existe un conflit de noms, le nom de propriété pour accéder à un service Web est *RootNamespace*_*Namespace*\_*ServiceName*. Par exemple, considérez deux services Web nommés `Service1`. Si une de ces services est dans l’espace de noms racine `WindowsApplication1` et dans l’espace de noms `Namespace1`, vous accédez à ce service à l’aide de `My.WebServices.WindowsApplication1_Namespace1_Service1`.  
  
 Lorsque vous tout d’abord accédez à l’un de le `My.WebServices` des propriétés de l’objet, il crée une nouvelle instance du service Web et le stocke. Les accès ultérieurs de cette propriété retournent cette instance du service Web.  
  
 Vous pouvez supprimer un service Web en assignant `Nothing` à la propriété pour ce service Web. L’accesseur Set de propriété assigne `Nothing` à la valeur stockée. Si vous assignez une valeur autre que `Nothing` à la propriété, l’accesseur Set lève une <xref:System.ArgumentException> exception.  
  
 Vous pouvez tester si une propriété de la `My.WebServices` objet stocke une instance du service Web à l’aide de la `Is` ou `IsNot` opérateur. Vous pouvez utiliser ces opérateurs pour vérifier si la valeur de la propriété est `Nothing`.  
  
> [!NOTE]
>  En règle générale, le `Is` ou `IsNot` opérateur doit lire la valeur de la propriété pour effectuer la comparaison. Toutefois, si la propriété stocke actuellement `Nothing`, la propriété crée une nouvelle instance du service Web et puis la retourne. Toutefois, le compilateur Visual Basic traite les propriétés de la `My.WebServices` spécialement de l’objet, ainsi que de la `Is` ou `IsNot` opérateur pour vérifier l’état de la propriété sans modifier sa valeur.  
  
## <a name="example"></a>Exemple  
 Cet exemple appelle la `FahrenheitToCelsius` méthode de la `TemperatureConverter` service Web XML et retourne le résultat.  
  
 [!code-vb[VbVbalrMyWebService#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWebService/VB/Form1.vb#1)]  
  
 Pour cet exemple fonctionne, votre projet doit référencer un service Web nommé `Converter`, et ce service Web doit exposer la `ConvertTemperature` (méthode). Pour plus d’informations, consultez [l’accès aux applications Web Services](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).  
  
 Ce code ne fonctionne pas dans un projet d’application Web.  
  
## <a name="requirements"></a>Spécifications  
  
### <a name="availability-by-project-type"></a>Disponibilité par Type de projet  
  
|Type de projet|Disponible|  
|---|---|  
|Application Windows|**Oui**|  
|Bibliothèque de classes|**Oui**|  
|Application console|**Oui**|  
|Bibliothèque de contrôles Windows|**Oui**|  
|Bibliothèque de contrôles Web|**Oui**|  
|Service Windows|**Oui**|  
|Site web|Aucune|  
  
## <a name="see-also"></a>Voir aussi
- <xref:System.Web.Services.Protocols.SoapHttpClientProtocol>
- <xref:System.ArgumentException>
- [Accès aux services web d’une application](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md)
