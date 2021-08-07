---
title: 'Skype for Business Server: Testen der SIP-Trunkkonfigurationseinstellungen'
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
description: 'Zusammenfassung: Erfahren Sie, wie Sie SIP-Trunkkonfigurationseinstellungen mithilfe der Skype for Business Server-Verwaltungsshell testen.'
ms.openlocfilehash: 19e0ad72b33d6ebbd5411fb269c3cdcbf2849a18
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "53772756"
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
