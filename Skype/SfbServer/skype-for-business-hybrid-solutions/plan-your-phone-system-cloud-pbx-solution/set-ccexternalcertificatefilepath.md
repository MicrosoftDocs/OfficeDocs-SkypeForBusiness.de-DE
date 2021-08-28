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
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 443d071e-633e-4337-b20b-f30cdfbd4aaf
description: Das cmdlet Set-CcExternalCertificateFilePath gibt den Pfad an, in dem das Zertifikat für den Vermittlungsserver oder Edgeserver gespeichert ist.
ms.openlocfilehash: b8555d3a3c6770481e1a66f79fd4a1060d3d9936
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58615521"
---
# <a name="set-ccexternalcertificatefilepath"></a>Set-CcExternalCertificateFilePath
 
Das cmdlet Set-CcExternalCertificateFilePath gibt den Pfad an, in dem das Zertifikat für den Vermittlungsserver oder Edgeserver gespeichert ist.
  
Dieses Zertifikat ist während der Bereitstellung oder beim Hinzufügen neuer Appliances von Skype for Business Cloud Connector Edition erforderlich. Der Befehl ermöglicht auch das Importieren eines neuen Zertifikats für den Vermittlungsserver nach der Bereitstellung.
  
Dieses Cmdlet gilt für Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Set-CcExternalCertificateFilePath [-Target] <string> {EdgeServer | MediationServer} [-Path] <string> [-Import]  [<CommonParameters>]
```

## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel wird der Pfad des Zertifikats für den Edgeserver festgelegt:
  
```powershell
Set-CcExternalCertificateFilePath -Target EdgeServer -Path C:\CloudConnector\Certificates\AdatumPublicEdge.pfx
```

### <a name="example-2"></a>Beispiel 2

Im nächsten Beispiel wird der Pfad des Zertifikats für den Vermittlungsserver festgelegt:
  
```powershell
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx
```

### <a name="example-3"></a>Beispiel 3

Im nächsten Beispiel wird das Zertifikat für den Vermittlungsserver aktualisiert:
  
```powershell
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx -Import
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Während der Bereitstellung oder beim Ändern der Topologie müssen Sie den Pfad für das Edgeserverzertifikat und optional für das Vermittlungsserverzertifikat angeben. 
  
Das Zertifikat für den Vermittlungsserver ist erforderlich, wenn TLS zwischen den Gateways und dem Vermittlungsserver verwendet wird. Wenn Sie eine Cloud Connector-Appliance bereitstellen und TLS bereitstellen möchten, können Sie nur den Pfad zum Zertifikat angeben, das auf dem Vermittlungsserver bereitgestellt wird. Wenn Sie jedoch das Vermittlungszertifikat in einer bereits bereitgestellten Appliance aktualisieren möchten, müssen Sie den Pfad und den Parameter "-Import" angeben. Verwenden Sie das Cmdlet Get-CCExternalCertificateFilePath, um den Pfad anzuzeigen.
  
## <a name="parameters"></a>Parameter
<a name="DetailedDescription"> </a>

|**Parameter**|**Required**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
| Target <br/> | Erforderlich <br/> |System.String  <br/> |Typ des angeforderten Dateipfads. Zu den Typen gehören:  <br/> EdgeServer (Standard)  <br/> MediationServer  <br/> |
|Import  <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Gibt an, dass das Zertifikat in den Vermittlungsserver importiert werden muss. Dieser Parameter ist nicht erforderlich, wenn Sie eine Appliance zum ersten Mal bereitstellen. Der Parameter ist erforderlich, wenn Sie das vorhandene Zertifikat in einer bereits bereitgestellten Version ändern möchten.  <br/> |
   
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Das cmdlet Set-CcExternalCertificateFilePath akzeptiert keine weitergeleitete Eingabe.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md)
  

