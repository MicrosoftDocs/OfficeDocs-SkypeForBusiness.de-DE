---
title: Testen von SIP-trunkkonfigurationseinstellungen in Skype für Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
description: 'Zusammenfassung: Informationen Sie zum Testen der SIP-trunkkonfigurationseinstellungen mithilfe der Skype für Business Server-Verwaltungsshell.'
ms.openlocfilehash: d602f24c3342e6c8460cab41d5f14e68ba17188b
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898966"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Testen von SIP-trunkkonfigurationseinstellungen in Skype für Business Server
 
**Zusammenfassung:** Erfahren Sie, wie SIP-Trunk-Konfigurationseinstellungen mithilfe der Skype für Business Server-Verwaltungsshell zu testen.
  
SIP-Trunk-Konfigurationseinstellungen definieren die Beziehung und die Funktionen zwischen einem Vermittlungsserver und dem PSTN-Gateway (Public Switched Telephone Network, Festnetz), einer IP-Nebenstellenanlage (Public Branch Exchange, PBX) oder einem Session Border Controller (SBC) beim Dienstanbieter. Diese Einstellungen geben unter anderem Folgendes an:
  
- Ob Medienumgehung für die Trunks aktiviert werden soll.
    
- Die Bedingungen, unter denen RTCP-Pakete (Real-Time Transport Control Protocol) gesendet werden.
    
- Ob SRTP-Verschlüsselung (Secure Real-Time Protocol) für jeden Trunk erforderlich ist.
    
Wenn Sie Skype für Business Server installieren, wird eine globale Auflistung von SIP-trunkkonfigurationseinstellungen für Sie erstellt. Darüber hinaus können Administratoren benutzerdefinierte Auflistungen mit Einstellungen auf Standort- oder Dienstebene erstellen (nur für den PSTN-Gatewaydienst). Administratoren können außerdem mit dem Test-CsTrunkConfiguration-Cmdlet überprüfen, ob ein Trunk eine von einem Benutzer gewählte Rufnummer in eine für das Gateway kompatible Rufnummer konvertieren kann.
  
Trunk-Konfigurationseinstellungen können nur mit Windows PowerShell und dem [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/test-cstrunkconfiguration?view=skype-ps)-Cmdlet. Dieses Cmdlet kann von der Skype für Business Server-Verwaltungsshell oder von einer Remotesitzung von Skype für Business Server-Verwaltungsshell ausgeführt werden.
  
### <a name="to-test-sip-trunk-configuration-settings"></a>Testen von Konfigurationseinstellungen für SIP-Trunks

- Mit dem folgenden Befehl wird überprüft, ob mit den Trunk-Konfigurationseinstellungen für den Standort Redmond die gewählte Rufnummer 4255551212 ordnungsgemäß konvertiert werden kann.
    
  ```
  $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
  Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
  ```


