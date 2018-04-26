---
title: Konfigurieren einer E9-1-1-VoIP-Route für Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 6933b840-0e7b-4509-ae43-bc9065677547
description: Configure E9-1-1 voice routes in Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 17614a4daedfdfe437a09858649972ca1c3e779d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="configure-an-e9-1-1-voice-route-in-skype-for-business-server-2015"></a>Konfigurieren einer E9-1-1-VoIP-Route für Skype for Business Server 2015
 
Configure E9-1-1 voice routes in Skype for Business Server Enterprise Voice. 
  
Für die Bereitstellung von E9-1-1 müssen Sie zunächst eine VoIP-Route für Notrufe konfigurieren. For details about creating voice routes, see [Create or modify a voice route in Skype for Business 2015](create-or-modify-a-voice-route.md). Sie können auch mehrere Routen definieren, zum Beispiel wenn Ihre Bereitstellung einen primären und einen sekundären SIP-Trunk enthält. 
  
> [!NOTE]
> Wenn Sie Standortinformationen in einen E9-1-1-INVITE-Befehl aufnehmen möchten, müssen Sie zunächst den SIP-Trunk konfigurieren, der zum Routen von Notrufen über das Gateway eine Verbindung mit dem E9-1-1-Dienstanbieter herstellt. Legen Sie zu diesem Zweck im Cmdlet **** das Flag „EnablePIDFLOSupport“ auf „True“ fest. Der Standardwert für „EnablePIDFLOSupport“ lautet „False“. Es ist nicht erforderlich, Empfangsstandorte für Ausweich-PSTN-Gateways und -ELIN-Gateways (Emergency Location Identification Number) zu aktivieren.
  
### <a name="to-configure-an-e9-1-1-voice-route"></a>So konfigurieren Sie eine E9-1-1-VoIP-Route

1. Melden Sie sich mit einem Konto, das Mitglied der Gruppe „RTCUniversalServerAdmins“ oder der Administratorrolle „CsVoiceAdministrator“ ist, am Computer an.
    
2.  Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
3. Führen Sie das folgende Cmdlet aus, um einen neuen PSTN-Verwendungsdatensatz zu erstellen. 
    
    Der Name muss dem Namen entsprechen, den Sie für die Einstellung **PSTN** in der Standortrichtlinie verwenden möchten. Obgleich Ihre Bereitstellung mehrere Telefonverwendungsdatensätze enthalten wird, fügt das folgende Beispiel der aktuellen Liste der verfügbaren PSTN-Verwendungen den Datensatz „Notfallverwendung“ hinzu. Konfigurieren von VoIP-Richtlinien, PSTN-Verwendungsdatensätzen und VoIP-Routen in Skype for Business 2015
    
   ```
   Set-CsPstnUsage -Usage @{add='EmergencyUsage'}
   ```

4. Führen Sie das folgende Cmdlet aus, um eine neue VoIP-Route unter Verwendung des im vorherigen Schritte erstellten PSTN-Verwendungsdatensatzes zu erstellen.
    
    Das Nummernmuster muss dem Nummernmuster entsprechen, das in der Einstellung **Notrufwählzeichenfolge** in der Standortrichtlinie verwendet wird. Ein Pluszeichen „+“ ist erforderlich, weil  das Pluszeichen „+“ zu Notrufen hinzufügt. „Co1-pstngateway-1“ ist die Dienst-ID des SIP-Trunks für den E9-1-1-Dienstanbieter oder für das ELIN-Gateway. Im folgenden Beispiel wird für die VoIP-Route der Name „EmergencyRoute“ festgelegt.
    
   ```
   New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}

   ```

5. Bei SIP-Trunkverbindungen wird optional die Ausführung des folgenden Cmdlets empfohlen, um eine lokale Route für Anrufe zu erstellen, die nicht über den SIP-Trunk des E9-1-1-Dienstanbieters verarbeitet werden. Diese Route wird verwendet, wenn die Verbindung zum E9-1-1-Dienstanbieter nicht verfügbar ist. 
    
    Im folgenden Beispiel wird davon ausgegangen, dass der Benutzer in seiner VoIP-Richtlinie über die Verwendung „Local“ verfügt.
    
   ```
   New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}
   ```


