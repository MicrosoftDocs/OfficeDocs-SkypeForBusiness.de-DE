---
title: Testen von SIP-Trunkkonfigurationseinstellungen in Skype for Business Server
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
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie die Konfigurationseinstellungen für den SIP-Trunk mithilfe der Skype for Business Server-Verwaltungsshell testen.'
ms.openlocfilehash: 6f569c7e397e7902cb347e13b4077acb5a9b34fb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103371"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Testen von SIP-Trunkkonfigurationseinstellungen in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie die Konfigurationseinstellungen für den SIP-Trunk mithilfe der Skype for Business Server-Verwaltungsshell testen.
  
Sip-Trunkkonfigurationseinstellungen definieren die Beziehung und Funktionen zwischen einem Vermittlungsserver und dem Public Switched Telephone Network (PSTN)-Gateway, einer IP-Public Branch eXchange (PBX) oder einem Session Border Controller (SBC) beim Dienstanbieter. Mit diesen Einstellungen kann Folgendes angegeben werden:
  
- Ob die Medienumgebung für Trunks aktiviert werden soll.
    
- Die Bedingungen, unter denen RtCP-Pakete (Realtime Transport Control Protocol) gesendet werden.
    
- Gibt an, ob für jeden Trunk eine Verschlüsselung des Secure Realtime Transport Protocol (SRTP) erforderlich ist.
    
Wenn Sie Skype for Business Server installieren, wird eine globale Auflistung von KONFIGURATIONSeinstellungen für den SIP-Trunk für Sie erstellt. Außerdem können Administratoren benutzerdefinierte Einstellungssammlungen auf Standortebene oder Dienstebene erstellen (nur für den PSTN-Gatewaydienst). Administratoren können auch das cmdlet Test-CsTrunkConfiguration verwenden, um zu überprüfen, ob ein Trunk eine Nummer, die von einem Benutzer gewählt wird, in eine Nummer konvertieren kann, die vom Gateway verarbeitet werden kann.
  
Trunkkonfigurationseinstellungen können nur mithilfe von Windows PowerShell und dem [Cmdlet Test-CsTrunkConfiguration](/powershell/module/skype/test-cstrunkconfiguration?view=skype-ps) getestet werden. Dieses Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung der Skype for Business Server-Verwaltungsshell ausgeführt werden.
  
### <a name="to-test-sip-trunk-configuration-settings"></a>So testen Sie die Konfigurationseinstellungen für SIP-Trunks

- Mit diesem Befehl wird überprüft, ob die Trunkkonfigurationseinstellungen für den Standort "Redmond" die gewählte Nummer 4255551212 korrekt konvertieren können.
    
  ```powershell
  $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
  Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
  ```