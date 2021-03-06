---
title: <synchronousReceive> (élément)
ms.date: 03/30/2017
ms.assetid: cc070387-3d11-4b02-a952-bc08ad2df05a
ms.openlocfilehash: f4a8868304ebae9a7ed5e6afbfb14fb2116afc49
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55278471"
---
# <a name="synchronousreceive-element"></a>\<synchronousReceive > élément
Cet élément de configuration est utilisé en vue de spécifier le comportement de réception des messages au moment de l'exécution dans une application cliente ou de service. Il n'a aucun attribut ou élément enfant.  
  
 \<system.ServiceModel>  
\<behaviors>  
\<endpointBehaviors>  
\<behavior>  
\<synchronousReceive>  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
<synchronousReceive />
```  
  
## <a name="attributes-and-elements"></a>Attributs et éléments  
 Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.  
  
### <a name="attributes"></a>Attributs  
 Aucun.  
  
### <a name="child-elements"></a>Éléments enfants  
 Aucun.  
  
### <a name="parent-elements"></a>Éléments parents  
  
|Élément|Description|  
|-------------|-----------------|  
|[\<behavior>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Spécifie un comportement de point de terminaison.|  
  
## <a name="remarks"></a>Notes  
 Utilisez ce comportement pour indiquer à l’écouteur de canal d’utiliser une réception synchrone au lieu de celle par défaut (asynchrone). Windows Communication Foundation (WCF) émet un nouveau thread pour pomper Chaque canal accepté. Si le nombre de canaux est important, il est possible de rencontrer une insuffisance de threads.  
  
## <a name="see-also"></a>Voir aussi
- <xref:System.ServiceModel.Configuration.SynchronousReceiveElement>
- <xref:System.ServiceModel.Description.SynchronousReceiveBehavior>
