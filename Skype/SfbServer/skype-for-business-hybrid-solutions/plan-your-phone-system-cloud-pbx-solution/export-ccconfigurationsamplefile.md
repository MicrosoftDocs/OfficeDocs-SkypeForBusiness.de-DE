---
title: Export-CcConfigurationSampleFile
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
localization_priority: Normal
ms.assetid: 0aaacc05-3430-4579-acbf-d7c7670c3864
description: Das cmdlet Export-CcConfigurationSampleFile exportiert eine Skype for Business Cloud Connector Edition Beispielkonfigurationsdatei (.ini) in das Appliance-Verzeichnis einer Cloud Connector-Appliance. Sie können die für Ihre Bereitstellung zu verwendende Datei ändern und umbenennen.
ms.openlocfilehash: f59e93cf241ca762dcb41cf23d617017a62581b453cb84cebc915b1703f5a019
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54326261"
---
# <a name="export-ccconfigurationsamplefile"></a>Export-CcConfigurationSampleFile
 
Das cmdlet Export-CcConfigurationSampleFile exportiert eine Skype for Business Cloud Connector Edition Beispielkonfigurationsdatei (.ini) in das Appliance-Verzeichnis einer Cloud Connector-Appliance. Sie können die für Ihre Bereitstellung zu verwendende Datei ändern und umbenennen.
  
Dieses Cmdlet gilt für Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="parameters"></a>Parameter

Keine
  
## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel wird eine Beispielkonfigurationsdatei vom Microsoft-Standort heruntergeladen und in das Appliance-Verzeichnis der Cloud Connector-Appliance geschrieben:
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Für die aktuelle Version von Cloud Connector müssen Sie mehrere Parameter in der .ini-Datei angeben. Beispielsweise Parameter wie die IP-Adressen virtueller Computer für die Cloud Connector-Komponenten, Komponentennamen, Gatewayparameter usw.
  
Dieses Cmdlet lädt bei Ausführung auf dem Hostcomputer von Cloud Connector ein Beispiel .ini Datei mit Konfigurationsbeispielen von der Microsoft-Website herunter. Das Cmdlet schreibt die Datei in das Appliance-Verzeichnis der Cloud Connector-Appliance. Das Appliance-Verzeichnis wird mithilfe des Cmdlets Set-CcApplianceDirectory angegeben.
  
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das cmdlet Export-CcConfigurationSampleFile akzeptiert keine weitergeleitete Eingabe. 
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

