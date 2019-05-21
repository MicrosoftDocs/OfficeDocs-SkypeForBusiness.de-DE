---
title: Konfigurieren einer E9-1-1-VoIP-Route in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6933b840-0e7b-4509-ae43-bc9065677547
description: Konfigurieren von E9-1-1-VoIP-Routen in Skype for Business Server Enterprise-VoIP
ms.openlocfilehash: 0ef8b1ba2b64c74cb2166c90dfdccf134df42252
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303454"
---
# <a name="configure-an-e9-1-1-voice-route-in-skype-for-business-server"></a>Konfigurieren einer E9-1-1-VoIP-Route in Skype for Business Server
 
Konfigurieren von E9-1-1-VoIP-Routen in Skype for Business Server Enterprise-VoIP 
  
Für die Bereitstellung von E9-1-1 müssen Sie zunächst eine VoIP-Route für Notrufe konfigurieren. Details zum Erstellen von VoIP-Routen finden Sie unter [erstellen oder Ändern einer VoIP-Route in Skype for Business](create-or-modify-a-voice-route.md). Sie können auch mehrere Routen definieren, zum Beispiel wenn Ihre Bereitstellung einen primären und einen sekundären SIP-Trunk enthält. 
  
> [!NOTE]
> Wenn Sie Standortinformationen in einen E9-1-1-INVITE-Befehl aufnehmen möchten, müssen Sie zunächst den SIP-Trunk konfigurieren, der zum Routen von Notrufen über das Gateway eine Verbindung mit dem E9-1-1-Dienstanbieter herstellt. Legen Sie zu diesem Zweck im Cmdlet **Set-CsTrunkConfiguration** das Flag „EnablePIDFLOSupport“ auf „True“ fest. Der Standardwert für „EnablePIDFLOSupport“ lautet „False“. Beispiel: `Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.` es ist nicht erforderlich, Empfangsspeicherorte für Fallback-Gateways (Public Switched Telephone Network) und Elin-Gateway (Emergency Location Identification Number) zu aktivieren.
  
### <a name="to-configure-an-e9-1-1-voice-route"></a>So konfigurieren Sie eine E9-1-1-VoIP-Route

1. Melden Sie sich mit einem Konto, das Mitglied der Gruppe „RTCUniversalServerAdmins“ oder der Administratorrolle „CsVoiceAdministrator“ ist, am Computer an.
    
2.  Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
3. Führen Sie das folgende Cmdlet aus, um einen neuen PSTN-Verwendungsdatensatz zu erstellen. 
    
    Der Name muss dem Namen entsprechen, den Sie für die Einstellung **PSTN** in der Standortrichtlinie verwenden möchten. Obgleich Ihre Bereitstellung mehrere Telefonverwendungsdatensätze enthalten wird, fügt das folgende Beispiel der aktuellen Liste der verfügbaren PSTN-Verwendungen den Datensatz „Notfallverwendung“ hinzu. Ausführliche Informationen finden Sie unter [Konfigurieren von VoIP-Richtlinien, PSTN-Verwendungsdatensätzen und VoIP-Routen in Skype for Business](voice-and-pstn.md).
    
   ```
   Set-CsPstnUsage -Usage @{add='EmergencyUsage'}
   ```

4. Führen Sie das folgende Cmdlet aus, um eine neue VoIP-Route unter Verwendung des im vorherigen Schritte erstellten PSTN-Verwendungsdatensatzes zu erstellen.
    
    Das Nummernmuster muss dem Nummernmuster entsprechen, das in der Einstellung **Notrufwählzeichenfolge** in der Standortrichtlinie verwendet wird. Da Skype for Business "+" zu Notrufen hinzufügt, ist ein "+"-Zeichen erforderlich. „Co1-pstngateway-1“ ist die Dienst-ID des SIP-Trunks für den E9-1-1-Dienstanbieter oder für das ELIN-Gateway. Im folgenden Beispiel wird für die VoIP-Route der Name „EmergencyRoute“ festgelegt.
    
   ```
   New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}
   ```

5. Optional empfiehlt es sich, für SIP Trunk-Verbindungen das folgende Cmdlet auszuführen, um eine lokale Route für Anrufe zu erstellen, die nicht vom SIP-Stamm des E9-1-1-Serviceanbieters behandelt werden. Diese Route wird verwendet, wenn die Verbindung zum E9-1-1-Dienstanbieter nicht verfügbar ist. 
    
    Im folgenden Beispiel wird davon ausgegangen, dass der Benutzer in seiner VoIP-Richtlinie über die Verwendung „Local“ verfügt.
    
   ```
   New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}
   ```


