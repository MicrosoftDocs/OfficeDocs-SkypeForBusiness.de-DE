---
title: Update-CcServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/11/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: cd2889c4-0eb1-4752-9274-93a5a68a8080
description: Das Cmdlet Update-CcServerCertificate erneuert die Zertifikate für Skype for Business Cloud Connector Edition, wenn sie bald ablaufen oder bereits abgelaufen sind.
ms.openlocfilehash: 0545f4923a4f1abd654674024313c6f22665cb7123d87d9d21c3676452bd8fcf
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54344524"
---
# <a name="update-ccservercertificate"></a>Update-CcServerCertificate
 
Das Cmdlet Update-CcServerCertificate erneuert die Zertifikate für Skype for Business Cloud Connector Edition, wenn sie bald ablaufen oder bereits abgelaufen sind. 
  
```powershell
Update-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel werden die Zertifikate für die zentrale Verwaltung Store, den Vermittlungsserver und den Edgeserver erneuert, wenn die Zertifikate bald ablaufen oder bereits abgelaufen sind:
  
```powershell
Update-CcServerCertificate
```

### <a name="example-2"></a>Beispiel 2

Im nächsten Beispiel werden die Zertifikate für den Vermittlungsserver und den Edgeserver erneuert, wenn sie bald ablaufen oder bereits abgelaufen sind:
  
```powershell
Update-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Interne Cloud Connector-Zertifikate, die an die zentrale Verwaltungs-Store, den Vermittlungsserver und den Edgeserver ausgestellt wurden, sind zwei Jahre lang gültig, nachdem sie von einem Zertifizierungsstellendienst ausgestellt wurden. Wenn Zertifikate bald ablaufen oder bereits abgelaufen sind, führen Sie das Cmdlet Update-CcServerCertificate aus, um die Zertifikate zu erneuern. 
  
Dieser Befehl ersetzt das Cmdlet Renew-CcServerCertificate in Cloud Connector 2.0 und höher.
  
## <a name="parameters"></a>Parameter
<a name="DetailedDescription"> </a>

|**Parameter**|**Required**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
|Rollen  <br/> |Optional  <br/> |System.Array  <br/> | Array von Cloud Connector-Serverrollen. <br/> |
   
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das cmdlet Update-CcServerCertificate akzeptiert keine weitergeleitete Eingabe.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

