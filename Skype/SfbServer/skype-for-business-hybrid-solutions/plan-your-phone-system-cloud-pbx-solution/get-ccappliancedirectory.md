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
description: Das cmdlet Get-CcApplianceDirectory ruft das Arbeitsverzeichnis auf dem Skype for Business Cloud Connector Edition Hostserver ab. Alle Bereitstellungsdateien werden in diesem Verzeichnis gespeichert.
ms.openlocfilehash: 9be21029aaf582ce080b85af87b8d3f02be11ffea3b615f2b003bb6aeb29002d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54347590"
---
# <a name="get-ccappliancedirectory"></a>Get-CcApplianceDirectory
 
Das cmdlet Get-CcApplianceDirectory ruft das Arbeitsverzeichnis auf dem Skype for Business Cloud Connector Edition Hostserver ab. Alle Bereitstellungsdateien werden in diesem Verzeichnis gespeichert. 
  
Dieses Cmdlet gilt für Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Get-CcApplianceDirectory
```

## <a name="parameters"></a>Parameter

Keine
  
## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Das folgende Beispiel zeigt den aktuellen Ordner, in dem konfigurations- und virtuelle Computerdateien von Cloud Connector-Komponenten gespeichert sind:
  
```powershell
Get-CcApplianceDirectory
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Das cmdlet Get-CcApplianceDirectory zeigt an, wo alle Konfigurations- und virtuellen Computerdateien, Protokolle und externen Zertifikate für die Cloud Connector-Appliance gespeichert sind.
  
Jede Cloud Connector-Appliance verfügt über vier Komponenten: Vermittlungsserver, zentrale Verwaltung Store, Edgeserver und einen Domänencontroller. Der Standardordner lautet "C:\Users \% userprofile%\CloudConnector\ApplianceRoot". Sie können diesen Ordner mithilfe des Cmdlets Set-CCApplianceDirectory ändern.
  
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das cmdlet Get-CCApplianceDirectory akzeptiert keine weitergeleitete Eingabe.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Der Befehl gibt einen Dateipfad zurück.
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

