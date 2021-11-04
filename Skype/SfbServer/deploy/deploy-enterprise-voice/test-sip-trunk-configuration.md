---
title: 'Skype for Business Server: Testen der SIP-Trunkkonfigurationseinstellungen'
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
description: 'Zusammenfassung: Erfahren Sie, wie Sie SIP-Trunkkonfigurationseinstellungen mithilfe der Skype for Business Server-Verwaltungsshell testen.'
ms.openlocfilehash: e6acdc50aaabffabf5b54dd0566143ea0d27d155
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60764863"
---
# <a name="skype-for-business-server-test-sip-trunk-configuration-settings"></a>Skype for Business Server: Testen der SIP-Trunkkonfigurationseinstellungen
 
**Zusammenfassung:** Erfahren Sie, wie Sie SIP-Trunkkonfigurationseinstellungen mithilfe der Skype for Business Server-Verwaltungsshell testen.
  
Sip trunk configuration settings define the relationship and capabilities between a Mediation Server and the Public Switched Telephone Network (PSTN) gateway, an IP-Public Branch eXchange (PBX) or a Session Border Controller (SBC) at the service provider. Mit diesen Einstellungen kann Folgendes angegeben werden:
  
- Gibt an, ob die Medienumgehung für die Trunks aktiviert werden soll.
    
- Die Bedingungen, unter denen RTCP-Pakete (Realtime Transport Control Protocol) gesendet werden
    
- Gibt an, ob die SRTP-Verschlüsselung (Secure Realtime Transport Protocol) für jeden Trunk erforderlich ist.
    
Wenn Sie Skype for Business Server installieren, wird eine globale Auflistung von SIP-Trunkkonfigurationseinstellungen für Sie erstellt. Darüber hinaus können Administratoren benutzerdefinierte Einstellungssammlungen auf Standort- oder Dienstebene erstellen (nur für den PSTN-Gatewaydienst). Administratoren können auch das Cmdlet Test-CsTrunkConfiguration verwenden, um zu überprüfen, ob ein Trunk eine von einem Benutzer gewählte Nummer in eine Nummer konvertieren kann, die das Gateway verarbeiten kann.
  
Trunkkonfigurationseinstellungen können nur mit Windows PowerShell und dem Cmdlet ["Test-CsTrunkConfiguration"](/powershell/module/skype/test-cstrunkconfiguration) getestet werden. Dieses Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung Skype for Business Server Verwaltungsshell ausgeführt werden.
  
### <a name="to-test-sip-trunk-configuration-settings"></a>So testen Sie SIP-Trunkkonfigurationseinstellungen

- Mit diesem Befehl wird überprüft, ob die Trunkkonfigurationseinstellungen für den Standort Redmond die gewählte Nummer 4255551212 ordnungsgemäß konvertieren können.
    
  ```powershell
  $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
  Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
  ```
