---
title: 'Procédure : Importer le fichier WSDL personnalisé'
ms.date: 03/30/2017
ms.assetid: ddc3718d-ce60-44f6-92af-a5c67477dd99
ms.openlocfilehash: dba3ec52d03939a306709e7756ff4e801699cf38
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54575604"
---
# <a name="how-to-import-custom-wsdl"></a>Procédure : Importer le fichier WSDL personnalisé
Cette rubrique décrit comment importer un fichier WSDL personnalisé. Pour gérer le fichier WSDL personnalisé, vous devez implémenter l'interface <xref:System.ServiceModel.Description.IWsdlImportExtension>.  
  
### <a name="to-import-custom-wsdl"></a>Pour importer le fichier WSDL personnalisé  
  
1.  Implémentez <xref:System.ServiceModel.Description.IWsdlImportExtension>. Implémentez la méthode <xref:System.ServiceModel.Description.IWsdlImportExtension.BeforeImport%28System.Web.Services.Description.ServiceDescriptionCollection%2CSystem.Xml.Schema.XmlSchemaSet%2CSystem.Collections.Generic.ICollection%7BSystem.Xml.XmlElement%7D%29> pour modifier les métadonnées avant qu'elles ne soient importées. Implémentez les méthodes <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportEndpoint%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlEndpointConversionContext%29> et <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportContract%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlContractConversionContext%29> pour modifier les contrats et points de terminaison importés des métadonnées. Pour accéder au contrat ou point de terminaison importé, utilisez l'objet de contexte correspondant (<xref:System.ServiceModel.Description.WsdlContractConversionContext> ou <xref:System.ServiceModel.Description.WsdlEndpointConversionContext>) :  
  
    ```  
    public class WsdlDocumentationImporter : IWsdlImportExtension  
       {  
          public void ImportContract(WsdlImporter importer, WsdlContractConversionContext context)  
    {  
            // Contract documentation  
         if (context.WsdlPortType.Documentation != null)  
         {  
               context.Contract.Behaviors.Add(new WsdlDocumentationImporter(context.WsdlPortType.Documentation));  
    }  
    // Operation documentation  
    foreach (Operation operation in context.WsdlPortType.Operations)  
    {  
    if (operation.Documentation != null)  
    {  
    OperationDescription operationDescription = context.Contract.Operations.Find(operation.Name);  
    if (operationDescription != null)  
    {  
                            operationDescription.Behaviors.Add(new WsdlDocumentationImporter(operation.Documentation));  
    }  
    }  
    }  
    }  
  
    public void BeforeImport(ServiceDescriptionCollection wsdlDocuments, XmlSchemaSet xmlSchemas, ICollection<XmlElement> policy)   
            {  
                Console.WriteLine("BeforeImport called.");  
            }  
  
    public void ImportEndpoint(WsdlImporter importer, WsdlEndpointConversionContext context)   
            {  
                Console.WriteLine("ImportEndpoint called.");  
            }  
       }  
    ```  
  
2.  Configurez l'application cliente pour utiliser l'importateur WSDL personnalisé. Notez que si vous utilisez Svcutil.exe, vous devez ajouter la configuration suivante au fichier de configuration de Svcutil.exe (Svcutil.exe.config) :  
  
    ```xml  
    <system.serviceModel>  
          <client>  
            <endpoint   
              address="http://localhost:8000/Fibonacci"   
              binding="wsHttpBinding"  
              contract="IFibonacci"  
            />  
            <metadata>  
              <wsdlImporters>  
                <extension type="Microsoft.WCF.Documentation.WsdlDocumentationImporter, WsdlDocumentation" />  
              </wsdlImporters>  
            </metadata>  
          </client>  
        </system.serviceModel>  
    ```  
  
3.  Créez une instance <xref:System.ServiceModel.Description.WsdlImporter> (en passant l'instance <xref:System.ServiceModel.Description.MetadataSet> qui contient les documents WSDL à importer), puis appelez <xref:System.ServiceModel.Description.WsdlImporter.ImportAllContracts%2A> :  
  
    ```  
    WsdlImporter importer = new WsdlImporter(metaDocs);          System.Collections.ObjectModel.Collection<ContractDescription> contracts  = importer.ImportAllContracts();  
    ```  
  
## <a name="see-also"></a>Voir aussi
- [Métadonnées](../../../../docs/framework/wcf/feature-details/metadata.md)
- [Exportation et importation de métadonnées](../../../../docs/framework/wcf/feature-details/exporting-and-importing-metadata.md)
- [Publication WSDL personnalisée](../../../../docs/framework/wcf/samples/custom-wsdl-publication.md)
