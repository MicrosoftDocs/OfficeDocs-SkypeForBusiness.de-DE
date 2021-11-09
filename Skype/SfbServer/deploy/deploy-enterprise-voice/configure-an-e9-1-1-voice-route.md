---
title: Konfigurieren einer E9-1-1-VoIP-Route in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.assetid: 6933b840-0e7b-4509-ae43-bc9065677547
description: Konfigurieren von E9-1-1-VoIP-Routen in Skype for Business Server Enterprise-VoIP.
ms.openlocfilehash: 86904c32db6ae43b9fa1b6f184048d3b9f419089
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60833951"
---
# <a name="configure-an-e9-1-1-voice-route-in-skype-for-business-server"></a>Konfigurieren einer E9-1-1-VoIP-Route in Skype for Business Server
 
Konfigurieren von E9-1-1-VoIP-Routen in Skype for Business Server Enterprise-VoIP. 
  
Zum Bereitstellen des Notruf-Features ("E9-1-1") müssen Sie zunächst eine VoIP-Route für Notrufe konfigurieren. Ausführliche Informationen zum Erstellen von VoIP-Routen finden Sie unter [Erstellen oder Ändern einer VoIP-Route in Skype for Business](create-or-modify-a-voice-route.md). Sie können auch mehrere Routen definieren, zum Beispiel wenn Ihre Bereitstellung einen primären und einen sekundären SIP-Trunk enthält. 
  
> [!NOTE]
> Wenn Sie Standortinformationen in einem E9-1-1-INVITE-Befehl aufnehmen möchten, müssen Sie zunächst den SIP-Trunk konfigurieren, der zum Routen von Notrufen über das Gateway eine Verbindung mit dem E9-1-1-Dienstanbieter herstellt. Setzen Sie zu diesem Zweck im **Set-CsTrunkConfiguration**-Cmdlet das Flag "EnablePIDFLOSupport" auf "True". Der Standardwert für "EnablePIDFLOSupport" lautet "False". Beispiel: `Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.` Es ist nicht erforderlich, Empfangsstandorte für Fallback-PSTN-Gateways (Public Switched Telephone Network) und ELIN-Gateways (Emergency Location Identification Number) zu aktivieren.
  
### <a name="to-configure-an-e9-1-1-voice-route"></a>So konfigurieren Sie eine E9-1-1-VoIP-Route

1. Melden Sie sich mit einem Konto, das Mitglied der Gruppe "RTCUniversalServerAdmins" oder der Administratorrolle "CsVoiceAdministrator" ist, am Computer an.
    
2.  Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **"Start",** auf **"Alle Programme",** auf **Skype for Business 2015** und dann auf **Skype for Business Server Verwaltungsshell.**
    
3. Führen Sie das folgende Cmdlet aus, um einen neuen PSTN-Verwendungsdatensatz zu erstellen. 
    
    Das muss der gleiche Name sein, den Sie bei der Einstellung **PSTN** in der Standortrichtlinie verwenden möchten. Obgleich Ihre Bereitstellung mehrere Telefonverwendungsdatensätze enthalten wird, fügt das folgende Beispiel der aktuellen Liste der verfügbaren PSTN-Verwendungen den Datensatz "Notfallverwendung" hinzu. Ausführliche Informationen finden Sie unter [Konfigurieren von VoIP-Richtlinien, PSTN-Verwendungsdatensätzen und VoIP-Routen in Skype for Business.](voice-and-pstn.md)
    
   ```powershell
   Set-CsPstnUsage -Usage @{add='EmergencyUsage'}
   ```

4. Führen Sie das folgende Cmdlet aus, um eine neue VoIP-Route unter Verwendung des eben erstellten PSTN-Verwendungsdatensatzes zu erstellen.
    
    Das Nummernmuster muss das gleiche wie das in der Einstellung **Notrufwählzeichenfolge** in der Standortrichtlinie verwendete sein. Ein "+"-Zeichen ist erforderlich, da Skype for Business Notrufen "+" hinzufügt. "Co1-pstngateway-1" ist die Dienst-ID des SIP-Trunks für den Notrufdienstanbieter oder für das ELIN-Gateway. Im folgenden Beispiel wird für die VoIP-Route der Name "EmergencyRoute" festgelegt.
    
   ```powershell
   New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}
   ```

5. Optional wird für SIP-Trunkverbindungen empfohlen, dass Sie das folgende Cmdlet ausführen, um eine lokale Route für Anrufe zu erstellen, die nicht vom SIP-Trunk des E9-1-1-Dienstanbieters verarbeitet werden. Diese Route wird verwendet, wenn die Verbindung zu dem Anbieter für Notrufunterstützung nicht verfügbar ist. 
    
    Im folgenden Beispiel wird davon ausgegangen, dass der Benutzer in seiner VoIP-Richtlinie über die Verwendung "Local" verfügt.
    
   ```powershell
   New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}
   ```


