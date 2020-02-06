---
title: Get-CcExternalCertificateFilePath
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 62fdc9cc-e82e-463f-b8b3-05d5c6482ea2
description: Das Cmdlet „Get-CcExternalCertificateFilePath“ gibt den Pfad der externen Zertifikatdatei für die Skype for Business Cloud Connector Edition-Bereitstellung zurück. Der Benutzer bereitet dieses Zertifikat vor.
ms.openlocfilehash: 143595d30bb71756544a16ad464da05a229f476d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799905"
---
# <a name="get-ccexternalcertificatefilepath"></a>Get-CcExternalCertificateFilePath
 
Das Cmdlet „Get-CcExternalCertificateFilePath“ gibt den Pfad der externen Zertifikatdatei für die Skype for Business Cloud Connector Edition-Bereitstellung zurück. Der Benutzer bereitet dieses Zertifikat vor.
  
Dieses Cmdlet gilt für Skype for Business Cloud Connector Edition 1.4.1 und 1.4.2.
  
```powershell
Get-CcExternalCertificateFilePath [[-Target] <string> {EdgeServer | MediationServer}]
```

## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Das folgende Beispiel zeigt den Pfad des Zertifikats für den Edgeserver an:
  
```powershell
Get-CcExternalCertificateFilePath -Target EdgeServer
```

### <a name="example-2"></a>Beispiel 2

Das folgende Beispiel zeigt das für den Vermittlungsserver festgelegte Zertifikat an:
  
```powershell
Get-CcExternalCertificateFilePath -Target MediationServer
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Bei der Bereitstellung oder beim Ändern der Topologie müssen Sie den Pfad für das Zertifikat des Edgeservers und optional des Vermittlungsservers angeben. Das Zertifikat für den Vermittlungsserver ist erforderlich, wenn zwischen den Gateways und dem Vermittlungsserver TLS verwendet wird. Um den Pfad zu ändern, verwenden Sie das Cmdlet „Set-CcExternalCertificateFilePath“.
  
## <a name="parameters"></a>Parameter
<a name="DetailedDescription"> </a>

|**Parameter**|**Erforderlich**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
|Target  <br/> |Optional  <br/> | System.Management.Automation.SwitchParameter <br/> |Der Typ des angeforderten Dateipfads. Mögliche Typen:  <br/> „EdgeServer“ (Standard)  <br/> „MediationServer“  <br/> |
   
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Das Cmdlet „Get-CcExternalCertificateFilePath“ akzeptiert keine Pipelineeingaben.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Der Befehl gibt einen Dateipfad zurück.
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md)
  

