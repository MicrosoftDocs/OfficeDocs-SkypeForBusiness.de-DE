---
title: Set-CcExternalCertificateFilePath
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 443d071e-633e-4337-b20b-f30cdfbd4aaf
description: Das Cmdlet „Set-CcExternalCertificateFilePath“ gibt den Pfad an, in dem das Zertifikat für den Vermittlungsserver oder den Edgeserver gespeichert ist.
ms.openlocfilehash: 89216fb2b56130dd76b711a483c6279ac1073392
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="set-ccexternalcertificatefilepath"></a>Set-CcExternalCertificateFilePath
 
Das Cmdlet „Set-CcExternalCertificateFilePath“ gibt den Pfad an, in dem das Zertifikat für den Vermittlungsserver oder den Edgeserver gespeichert ist.
  
Dieses Zertifikat ist während der Bereitstellung oder beim Hinzufügen neuer Appliances von Skype for Business Cloud Connector Edition erforderlich. Mit diesem Befehl können Sie auch nach der Bereitstellung ein neues Zertifikat für den Vermittlungsserver importieren.
  
Dieses Cmdlet gilt für Skype for Business Cloud Connector Edition 1.4.1 und 1.4.2.
  
```
Set-CcExternalCertificateFilePath [-Target] <string> {EdgeServer | MediationServer} [-Path] <string> [-Import]  [<CommonParameters>]
```

## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel wird der Pfad des Zertifikats für den Edgeserver festgelegt:
  
```
Set-CcExternalCertificateFilePath -Target EdgeServer -Path C:\CloudConnector\Certificates\AdatumPublicEdge.pfx
```

### <a name="example-2"></a>Beispiel 2

Im nächsten Beispiel wird der Pfad des Zertifikats für den Vermittlungsserver festgelegt:
  
```
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx
```

### <a name="example-3"></a>Beispiel 3

Im nächsten Beispiel wird das Zertifikat für den Vermittlungsserver aktualisiert:
  
```
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx -Import
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Bei der Bereitstellung oder beim Ändern der Topologie müssen Sie den Pfad für das Zertifikat des Edgeservers und optional des Vermittlungsservers angeben. 
  
Das Zertifikat für den Vermittlungsserver ist erforderlich, wenn zwischen den Gateways und dem Vermittlungsserver TLS verwendet wird. Wenn Sie eine Cloud-Connector Appliance bereitstellen und TLS bereitstellen möchten, können Sie den Pfad zu dem Zertifikat, das bereitgestellt wird nur auf dem Vermittlungsserver angeben. Wenn Sie jedoch das Vermittlungszertifikat in einer bereits bereitgestellten Appliance aktualisieren möchten, müssen Sie den Pfad und den Parameter „-Import“ angeben. Um den Pfad anzuzeigen, verwenden Sie das Cmdlet „Get-CCExternalCertificateFilePath“.
  
## <a name="parameters"></a>Parameter
<a name="DetailedDescription"> </a>

|**Parameter**|**Erforderlich**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
|  Target <br/> | Erforderlich <br/> |System.String  <br/> |Der Typ des angeforderten Dateipfads. Mögliche Typen:  <br/> „EdgeServer“ (Standard)  <br/> MediationServer  <br/> |
|Import  <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Gibt an, dass das Zertifikat auf dem Vermittlungsserver importiert werden muss. Dieser Parameter ist bei der ersten Bereitstellung einer Appliance nicht notwendig. Der Parameter ist erforderlich, wenn Sie das vorhandene Zertifikat einer bereits bereitgestellten Version ändern möchten.  <br/> |
   
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Das Cmdlet „Set-CcExternalCertificateFilePath“ akzeptiert keine Pipelineeingaben.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md)
  

