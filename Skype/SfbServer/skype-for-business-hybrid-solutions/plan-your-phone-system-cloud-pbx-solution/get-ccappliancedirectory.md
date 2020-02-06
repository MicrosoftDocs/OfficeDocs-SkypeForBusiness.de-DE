---
title: Get-CcApplianceDirectory
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
ms.assetid: c2fda202-db2f-4122-b630-7df11a697c5f
description: 'Das Cmdlet „Get-CcApplianceDirectory“ ruft das Arbeitsverzeichnis auf dem Hostserver von Skype for Business Cloud Connector Edition ab. In diesem Verzeichnis werden alle Bereitstellungsdateien gespeichert. '
ms.openlocfilehash: 04764f312138132fb34c0979423da5dc4696ee63
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41800845"
---
# <a name="get-ccappliancedirectory"></a>Get-CcApplianceDirectory
 
Das Cmdlet „Get-CcApplianceDirectory“ ruft das Arbeitsverzeichnis auf dem Hostserver von Skype for Business Cloud Connector Edition ab. In diesem Verzeichnis werden alle Bereitstellungsdateien gespeichert.  
  
Dieses Cmdlet gilt für Skype for Business Cloud Connector Edition 1.4.1 und 1.4.2.
  
```powershell
Get-CcApplianceDirectory
```

## <a name="parameters"></a>Parameter

Keine
  
## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Das folgende Beispiel zeigt den aktuellen Ordner, in dem Konfigurations-und Virtual Machine-Dateien von Cloud Connector-Komponenten gespeichert werden:
  
```powershell
Get-CcApplianceDirectory
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Das Cmdlet "Get-CcApplianceDirectory" zeigt an, wo alle Konfigurations-und virtuellen Computer Dateien,-Protokolle und externen Zertifikate für die Cloud Connector-Appliance gespeichert sind.
  
Jede Cloud Connector-Appliance verfügt über vier Komponenten: Mediationsserver, zentraler Verwaltungsspeicher, Edgeserver und einen Domänen Controller. Der Standardordner lautet C:\Users\%USERPROFILE%\CloudConnector\ApplianceRoot. Sie können den Ordner mit dem Cmdlet „Set-CCApplianceDirectory“ ändern.
  
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das Cmdlet „Get-CCApplianceDirectory“ akzeptiert keine Pipelineeingaben.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Der Befehl gibt einen Dateipfad zurück.
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

