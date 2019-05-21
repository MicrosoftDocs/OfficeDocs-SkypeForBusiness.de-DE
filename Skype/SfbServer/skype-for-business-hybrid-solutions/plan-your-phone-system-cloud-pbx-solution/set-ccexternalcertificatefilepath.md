---
title: Set-CcExternalCertificateFilePath
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 443d071e-633e-4337-b20b-f30cdfbd4aaf
description: Das Cmdlet „Set-CcExternalCertificateFilePath“ gibt den Pfad an, in dem das Zertifikat für den Vermittlungsserver oder den Edgeserver gespeichert ist.
ms.openlocfilehash: bc22771c20277d9de99660551864d600f06b3acc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286985"
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
  
Das Zertifikat für den Vermittlungsserver ist erforderlich, wenn zwischen den Gateways und dem Vermittlungsserver TLS verwendet wird. Wenn Sie eine Cloud Connector-Appliance bereitstellen und TLS bereitstellen möchten, können Sie nur den Pfad zu dem Zertifikat angeben, das auf dem Vermittlungs Server bereitgestellt wird. Wenn Sie jedoch das Vermittlungszertifikat in einer bereits bereitgestellten Appliance aktualisieren möchten, müssen Sie den Pfad und den Parameter „-Import“ angeben. Um den Pfad anzuzeigen, verwenden Sie das Cmdlet „Get-CCExternalCertificateFilePath“.
  
## <a name="parameters"></a>Parameter
<a name="DetailedDescription"> </a>

|**Parameter**|**Erforderlich**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
|  Target <br/> | Erforderlich <br/> |System.String  <br/> |Der Typ des angeforderten Dateipfads. Mögliche Typen:  <br/> „EdgeServer“ (Standard)  <br/> „MediationServer“  <br/> |
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
  

