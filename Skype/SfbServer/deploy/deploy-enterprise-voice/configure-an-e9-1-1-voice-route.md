---
title: Konfigurieren einer E9-1-1-Voiceroute in Skype for Business Server
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
ms.assetid: 6933b840-0e7b-4509-ae43-bc9065677547
description: Konfigurieren Sie E9-1-1-Voicerouten in Skype for Business Server Enterprise-VoIP.
ms.openlocfilehash: b5f3d12bb586a65fc1c553a021c1a27efb0c7f77
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804175"
---
# <a name="configure-an-e9-1-1-voice-route-in-skype-for-business-server"></a>Konfigurieren einer E9-1-1-Sprachroute in Skype for Business Server
 
Konfigurieren Sie E9-1-1-Voicerouten in Skype for Business Server Enterprise-VoIP. 
  
Zum Bereitstellen des Notruf-Features ("E9-1-1") müssen Sie zunächst eine VoIP-Route für Notrufe konfigurieren. Weitere Informationen zum Erstellen von Sprachrouten finden Sie unter "Erstellen oder [Ändern einer Sprachroute in Skype for Business".](create-or-modify-a-voice-route.md) Sie können auch mehrere Routen definieren, zum Beispiel wenn Ihre Bereitstellung einen primären und einen sekundären SIP-Trunk enthält. 
  
> [!NOTE]
> Wenn Sie Standortinformationen in einem E9-1-1-INVITE-Befehl aufnehmen möchten, müssen Sie zunächst den SIP-Trunk konfigurieren, der zum Routen von Notrufen über das Gateway eine Verbindung mit dem E9-1-1-Dienstanbieter herstellt. Setzen Sie zu diesem Zweck im **Set-CsTrunkConfiguration**-Cmdlet das Flag "EnablePIDFLOSupport" auf "True". Der Standardwert für "EnablePIDFLOSupport" lautet "False". Beispiel: Es ist nicht erforderlich, Empfangsstandorte für `Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.` Fallbackgateways (Public Switched Telephone Network, PSTN) und ELIN(Emergency Location Identification Number)-Gateways zu aktivieren.
  
### <a name="to-configure-an-e9-1-1-voice-route"></a>So konfigurieren Sie eine E9-1-1-VoIP-Route

1. Melden Sie sich mit einem Konto, das Mitglied der Gruppe "RTCUniversalServerAdmins" oder der Administratorrolle "CsVoiceAdministrator" ist, am Computer an.
    
2.  Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **"Start",**"Alle **Programme",** **"Skype for Business 2015"** und dann auf **"Skype for Business Server-Verwaltungsshell".**
    
3. Führen Sie das folgende Cmdlet aus, um einen neuen PSTN-Verwendungsdatensatz zu erstellen. 
    
    Das muss der gleiche Name sein, den Sie bei der Einstellung **PSTN** in der Standortrichtlinie verwenden möchten. Obgleich Ihre Bereitstellung mehrere Telefonverwendungsdatensätze enthalten wird, fügt das folgende Beispiel der aktuellen Liste der verfügbaren PSTN-Verwendungen den Datensatz "Notfallverwendung" hinzu. Weitere Informationen finden Sie unter ["Konfigurieren von Sprachrichtlinien, PSTN-Verwendungsdatensätzen und Sprachrouten in Skype for Business".](voice-and-pstn.md)
    
   ```powershell
   Set-CsPstnUsage -Usage @{add='EmergencyUsage'}
   ```

4. Führen Sie das folgende Cmdlet aus, um eine neue VoIP-Route unter Verwendung des eben erstellten PSTN-Verwendungsdatensatzes zu erstellen.
    
    Das Nummernmuster muss das gleiche wie das in der Einstellung **Notrufwählzeichenfolge** in der Standortrichtlinie verwendete sein. Ein "+"-Zeichen ist erforderlich, da Skype for Business "+" zu Notrufen hinzufügt. "Co1-pstngateway-1" ist die Dienst-ID des SIP-Trunks für den Notrufdienstanbieter oder für das ELIN-Gateway. Im folgenden Beispiel wird für die VoIP-Route der Name "EmergencyRoute" festgelegt.
    
   ```powershell
   New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}
   ```

5. Für SIP-Trunk-Verbindungen wird optional empfohlen, das folgende Cmdlet zum Erstellen einer lokalen Route für Anrufe zu erstellen, die nicht vom SIP-Trunk des E9-1-1-Dienstanbieters verarbeitet werden. Diese Route wird verwendet, wenn die Verbindung zu dem Anbieter für Notrufunterstützung nicht verfügbar ist. 
    
    Im folgenden Beispiel wird davon ausgegangen, dass der Benutzer in seiner VoIP-Richtlinie über die Verwendung "Local" verfügt.
    
   ```powershell
   New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}
   ```


