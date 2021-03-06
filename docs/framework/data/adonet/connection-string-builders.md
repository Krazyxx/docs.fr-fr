---
title: Builders de chaînes de connexion
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8434b608-c4d3-43d3-8ae3-6d8c6b726759
ms.openlocfilehash: ab72fe5a22ca88b33a93d94d4b5e16bbc470a4da
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54733218"
---
# <a name="connection-string-builders"></a>Builders de chaînes de connexion
Dans les versions antérieures de [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)], la vérification des chaînes de connexion avec la chaîne concaténée ne prenaient pas de valeurs, afin qu’au moment de l’exécution, un mot clé incorrect est généré lors de la compilation un <xref:System.ArgumentException>. Chacun des fournisseurs de données [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] utilisait une syntaxe différente pour les mots clés de chaîne de connexion, ce qui rendait difficile la génération de chaînes de connexion valides si l'opération était effectuée manuellement. Pour résoudre ce problème, [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] 2.0 a introduit de nouveaux générateurs de chaînes de connexion pour chaque fournisseur de données [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]. Chaque fournisseur de données inclut une classe de générateur de chaînes de connexion fortement typée qui hérite de <xref:System.Data.Common.DbConnectionStringBuilder>. Le tableau suivant répertorie les fournisseurs de données [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] et leurs classes de générateur de chaînes de connexion associées.  
  
|Fournisseur|Classe ConnectionStringBuilder|  
|--------------|-----------------------------------|  
|<xref:System.Data.SqlClient>|<xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=nameWithType>|  
|<xref:System.Data.OleDb>|<xref:System.Data.OleDb.OleDbConnectionStringBuilder?displayProperty=nameWithType>|  
|<xref:System.Data.Odbc>|<xref:System.Data.Odbc.OdbcConnectionStringBuilder?displayProperty=nameWithType>|  
|<xref:System.Data.OracleClient>|<xref:System.Data.OracleClient.OracleConnectionStringBuilder?displayProperty=nameWithType>|  
  
## <a name="connection-string-injection-attacks"></a>Attaques par injection de chaîne de connexion  
 Une attaque par injection de chaîne de connexion peut se produire lorsqu'une concaténation de chaîne dynamique est utilisée pour générer des chaînes de connexion se basant sur l'entrée d'utilisateur. Si la chaîne n'est pas validée et que du texte ou des caractères malveillants ne font pas l'objet d'un échappement, un attaquant peut éventuellement accéder à des données sensibles ou à d'autres ressources sur le serveur. Par exemple, un attaquant peut organiser une attaque en fournissant un point-virgule et en ajoutant une valeur supplémentaire. La chaîne de connexion est alors analysée à l'aide de l'algorithme « last one wins », de sorte que l'entrée hostile soit remplacée par une valeur légitime.  
  
 Les classes de générateur de chaînes de connexion sont conçues pour éliminer le travail de recherche et pour se protéger contre les erreurs de syntaxe et les failles en matière de sécurité. Elles fournissent des méthodes et des propriétés qui correspondent aux paires clé/valeur connues autorisées par chaque fournisseur de données. La classe maintient une collection fixe de synonymes et peut traduire un synonyme vers le nom de la clé connue correspondante. Des vérifications sont effectuées pour contrôler la validité des paires clé/valeur et une paire non valide lève une exception. En outre, les valeurs injectées sont gérées de manière sécurisée.  
  
 L'exemple suivant montre comment <xref:System.Data.SqlClient.SqlConnectionStringBuilder> gère une valeur supplémentaire insérée pour le paramètre `Initial Catalog`.  
  
```vb  
Dim builder As New System.Data.SqlClient.SqlConnectionStringBuilder  
builder("Data Source") = "(local)"  
builder("Integrated Security") = True  
builder("Initial Catalog") = "AdventureWorks;NewValue=Bad"  
Console.WriteLine(builder.ConnectionString)  
```  
  
```csharp  
System.Data.SqlClient.SqlConnectionStringBuilder builder =  
  new System.Data.SqlClient.SqlConnectionStringBuilder();  
builder["Data Source"] = "(local)";  
builder["integrated Security"] = true;  
builder["Initial Catalog"] = "AdventureWorks;NewValue=Bad";  
Console.WriteLine(builder.ConnectionString);  
```  
  
 La sortie montre que <xref:System.Data.SqlClient.SqlConnectionStringBuilder> a agi correctement en plaçant dans une séquence d'échappement, entre des guillemets doubles, la valeur supplémentaire au lieu de l'ajouter à la chaîne de connexion en tant que nouvelle paire clé/valeur.  
  
```  
data source=(local);Integrated Security=True;  
initial catalog="AdventureWorks;NewValue=Bad"  
```  
  
## <a name="building-connection-strings-from-configuration-files"></a>Génération de chaînes de connexion à partir de fichiers de configuration  
 Si certains éléments d'une chaîne de connexion sont connus à l'avance, ils peuvent être stockés dans un fichier de configuration et récupérés au moment de l'exécution pour générer une chaîne de connexion complète. Par exemple, le nom de la base de données peut être connue à l'avance, mais pas celui du serveur. Ou bien, vous pouvez souhaiter qu'un utilisateur fournisse un nom et un mot de passe au moment de l'exécution mais sans pouvoir injecter d'autres valeurs dans la chaîne de connexion.  
  
 L'un des constructeurs surchargés d'un générateur de chaînes de connexion prend <xref:System.String> en tant qu'argument, ce qui vous permet de fournir une chaîne de connexion partielle qui pourra ensuite être complétée à partir de l'entrée d'utilisateur. La chaîne de connexion partielle peut être stockée dans un fichier de configuration et récupérée au moment de l'exécution.  
  
> [!NOTE]
>  L'espace de noms <xref:System.Configuration> autorise l'accès par programme aux fichiers de configuration qui utilisent <xref:System.Web.Configuration.WebConfigurationManager> pour les applications Web et <xref:System.Configuration.ConfigurationManager> pour les applications Windows. Pour plus d’informations sur l’utilisation des chaînes de connexion et les fichiers de configuration, consultez [chaînes de connexion et les fichiers de Configuration](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md).  
  
### <a name="example"></a>Exemple  
 Cet exemple montre comment récupérer une chaîne de connexion partielle d'un fichier de configuration et comment la compléter en définissant les propriétés <xref:System.Data.SqlClient.SqlConnectionStringBuilder.DataSource%2A>, <xref:System.Data.SqlClient.SqlConnectionStringBuilder.UserID%2A> et <xref:System.Data.SqlClient.SqlConnectionStringBuilder.Password%2A> de <xref:System.Data.SqlClient.SqlConnectionStringBuilder>. Le fichier de configuration est défini comme suit.  
  
```xml  
<connectionStrings>  
  <clear/>  
  <add name="partialConnectString"   
    connectionString="Initial Catalog=Northwind;"  
    providerName="System.Data.SqlClient" />  
</connectionStrings>  
```  
  
> [!NOTE]
>  Vous devez définir une référence à `System.Configuration.dll` dans votre projet pour le code à exécuter.  
  
 [!code-csharp[DataWorks SqlConnectionStringBuilder.UserNamePwd#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlConnectionStringBuilder.UserNamePwd/CS/source.cs#1)]
 [!code-vb[DataWorks SqlConnectionStringBuilder.UserNamePwd#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlConnectionStringBuilder.UserNamePwd/VB/source.vb#1)]  
  
## <a name="see-also"></a>Voir aussi
- [Chaînes de connexion](../../../../docs/framework/data/adonet/connection-strings.md)
- [Confidentialité et sécurité des données](../../../../docs/framework/data/adonet/privacy-and-data-security.md)
- [Fournisseurs managés ADO.NET et centre de développement DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
