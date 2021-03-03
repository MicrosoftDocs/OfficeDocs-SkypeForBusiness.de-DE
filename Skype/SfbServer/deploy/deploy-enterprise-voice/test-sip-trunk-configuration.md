---
title: Testen der Konfigurationseinstellungen für den SIP-Trunk in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
description: 'Zusammenfassung: Informationen zum Testen der Sip-Trunk-Konfigurationseinstellungen mithilfe der Skype for Business Server-Verwaltungsshell.'
ms.openlocfilehash: 8b3a98d54fd0d2dc8bb69e553e0c0a3a7b98b1ca
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830635"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Testen der Konfigurationseinstellungen für den SIP-Trunk in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie die Sip-Trunk-Konfigurationseinstellungen mithilfe der Skype for Business Server-Verwaltungsshell testen.
  
Sip-Trunk-Konfigurationseinstellungen definieren die Beziehung und die Funktionen zwischen einem Vermittlungsserver und dem PSTN-Gateway, einer IP-Public Branch eXchange (PBX) oder einem Session Border Controller (SBC) beim Dienstanbieter. Mit diesen Einstellungen kann Folgendes angegeben werden:
  
- Ob die Medienumgebung für Trunks aktiviert werden soll.
    
- Die Bedingungen, unter denen RtCP (Realtime Transport Control Protocol)-Pakete gesendet werden.
    
- Gibt an, ob für jeden Trunk eine Secure Realtime Transport Protocol (SRTP)-Verschlüsselung erforderlich ist.
    
Bei der Installation von Skype for Business Server wird eine globale Auflistung von Sip-Trunk-Konfigurationseinstellungen erstellt. Außerdem können Administratoren benutzerdefinierte Einstellungssammlungen auf Standortebene oder Dienstebene erstellen (nur für den PSTN-Gatewaydienst). Administratoren können auch das Cmdlet Test-CsTrunkConfiguration verwenden, um zu überprüfen, ob ein Trunk eine von einem Benutzer gewählte Nummer in eine Nummer konvertieren kann, die vom Gateway verarbeitet werden kann.
  
Trunkkonfigurationseinstellungen können nur mithilfe von Windows PowerShell und dem Cmdlet ["Test-CsTrunkConfiguration"](https://docs.microsoft.com/powershell/module/skype/test-cstrunkconfiguration?view=skype-ps) getestet werden. Dieses Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung der Skype for Business Server-Verwaltungsshell ausgeführt werden.
  
### <a name="to-test-sip-trunk-configuration-settings"></a>So testen Sie die Konfigurationseinstellungen für den SIP-Trunk

- Mit diesem Befehl wird überprüft, ob die Trunkkonfigurationseinstellungen für den Standort "Redmond" die gewählte Nummer 4255551212 ordnungsgemäß konvertieren können.
    
  ```powershell
  $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
  Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
  ```


