---
title: Testen von Konfigurationseinstellungen für SIP-Trunks in Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
description: 'Zusammenfassung: Informationen Sie zum Testen der SIP-trunkkonfigurationseinstellungen mithilfe der Skype für Business Server-Verwaltungsshell.'
ms.openlocfilehash: 4e4c0c7ce117143f743dd40536bc49bfce92d978
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server-2015"></a>Testen von Konfigurationseinstellungen für SIP-Trunks in Skype for Business Server 2015
 
**Zusammenfassung:** Erfahren Sie, wie SIP-Trunk-Konfigurationseinstellungen mithilfe der Skype für Business Server-Verwaltungsshell zu testen.
  
SIP-Trunk-Konfigurationseinstellungen definieren die Beziehung und die Funktionen zwischen einem Vermittlungsserver und dem PSTN-Gateway (Public Switched Telephone Network, Festnetz), einer IP-Nebenstellenanlage (Public Branch Exchange, PBX) oder einem Session Border Controller (SBC) beim Dienstanbieter. Diese Einstellungen geben unter anderem Folgendes an:
  
- Ob Medienumgehung für die Trunks aktiviert werden soll
    
- Die Bedingungen, unter denen RTCP-Pakete (Real-Time Transport Control Protocol) gesendet werden.
    
- Ob SRTP-Verschlüsselung (Secure Real-Time Protocol) für jeden Trunk erforderlich ist.
    
Wenn Sie Skype für Business Server installieren, wird eine globale Auflistung von SIP-trunkkonfigurationseinstellungen für Sie erstellt. Darüber hinaus können Administratoren benutzerdefinierte Auflistungen mit Einstellungen auf Standort- oder Dienstebene erstellen (nur für den PSTN-Gatewaydienst). Administratoren können außerdem mit dem Test-CsTrunkConfiguration-Cmdlet überprüfen, ob ein Trunk eine von einem Benutzer gewählte Rufnummer in eine für das Gateway kompatible Rufnummer konvertieren kann.
  
Trunkkonfigurationseinstellungen können nur mithilfe von Windows PowerShell und das [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/test-cstrunkconfiguration?view=skype-ps) -Cmdlet getestet werden soll. Dieses Cmdlet kann von der Skype für Business Server-Verwaltungsshell oder von einer Remotesitzung von Skype für Business Server-Verwaltungsshell ausgeführt werden.
  
### <a name="to-test-sip-trunk-configuration-settings"></a>Testen von Konfigurationseinstellungen für SIP-Trunks

- Mit dem folgenden Befehl wird überprüft, ob mit den Trunk-Konfigurationseinstellungen für den Standort Redmond die gewählte Rufnummer 4255551212 ordnungsgemäß konvertiert werden kann.
    
  ```
  $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
  Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
  ```


