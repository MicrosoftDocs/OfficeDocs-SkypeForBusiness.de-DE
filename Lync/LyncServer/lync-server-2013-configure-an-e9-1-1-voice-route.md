---
title: 'Lync Server 2013: Konfigurieren einer E9-1-1-VoIP-Route'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure an E9-1-1 voice route
ms:assetid: 6933b840-0e7b-4509-ae43-bc9065677547
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398496(v=OCS.15)
ms:contentKeyID: 48184384
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59f4e2a6707d270f66a66663b19f975ac69961c2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839440"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-an-e9-1-1-voice-route-in-lync-server-2013"></a>Konfigurieren einer E9-1-1-VoIP-Route in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-17_

Für die Bereitstellung von E9-1-1 müssen Sie zunächst eine VoIP-Route für Notrufe konfigurieren. Details zum Erstellen von VoIP-Routen finden Sie unter [Erstellen einer VoIP-Route in lync Server 2013](lync-server-2013-create-a-voice-route.md). Sie können auch mehrere Routen definieren, zum Beispiel wenn Ihre Bereitstellung einen primären und einen sekundären SIP-Trunk enthält.

<div>


> [!NOTE]  
> Wenn Sie Standortinformationen in einen E9-1-1-INVITE-Befehl aufnehmen möchten, müssen Sie zunächst den SIP-Trunk konfigurieren, der zum Routen von Notrufen über das Gateway eine Verbindung mit dem E9-1-1-Dienstanbieter herstellt. Legen Sie zu diesem Zweck im Cmdlet <STRONG>Set-CsTrunkConfiguration</STRONG> das Flag „EnablePIDFLOSupport“ auf „True“ fest. Der Standardwert für „EnablePIDFLOSupport“ lautet „False“. Zum Beispiel:<CODE>Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.</CODE><BR>Es ist nicht erforderlich, Empfangsstandorte für Ausweich-PSTN-Gateways und -ELIN-Gateways (Emergency Location Identification Number) zu aktivieren.



</div>

Details zum Arbeiten mit VoIP-Routen finden Sie in der Dokumentation zur lync Server-Verwaltungsshell für die folgenden Cmdlets:

  - **Set-CsPstnUsage**

  - **Get-CsPstnUsage**

  - **Neu – CsVoiceRoute**

  - **Get-CsVoiceRoute**

  - **Satz-CsVoiceRoute**

  - **Remove-CsVoiceRoute**

<div>

## <a name="to-configure-an-e9-1-1-voice-route"></a>So konfigurieren Sie eine E9-1-1-VoIP-Route

1.  Melden Sie sich mit einem Konto, das Mitglied der Gruppe „RTCUniversalServerAdmins“ oder der Administratorrolle „CsVoiceAdministrator“ ist, am Computer an.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Führen Sie das folgende Cmdlet aus, um einen neuen PSTN-Verwendungsdatensatz zu erstellen.
    
    Der Name muss dem Namen entsprechen, den Sie für die Einstellung **PSTN** in der Standortrichtlinie verwenden möchten. Obgleich Ihre Bereitstellung mehrere Telefonverwendungsdatensätze enthalten wird, fügt das folgende Beispiel der aktuellen Liste der verfügbaren PSTN-Verwendungen den Datensatz „Notfallverwendung“ hinzu. Ausführliche Informationen finden Sie unter [Konfigurieren von VoIP-Richtlinien und PSTN-Verwendungsdatensätzen, um die Anruffunktionen und-Berechtigungen in lync Server 2013 zu autorisieren](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).
    
        Set-CsPstnUsage -Usage @{add='EmergencyUsage'}

4.  Führen Sie das folgende Cmdlet aus, um eine neue VoIP-Route unter Verwendung des im vorherigen Schritte erstellten PSTN-Verwendungsdatensatzes zu erstellen.
    
    Das Nummernmuster muss dem Nummernmuster entsprechen, das in der Einstellung **Notrufwählzeichenfolge** in der Standortrichtlinie verwendet wird. Ein "+"-Zeichen ist erforderlich, da lync "+" zu Notrufen hinzufügt. „Co1-pstngateway-1“ ist die Dienst-ID des SIP-Trunks für den E9-1-1-Dienstanbieter oder für das ELIN-Gateway. Im folgenden Beispiel wird für die VoIP-Route der Name „EmergencyRoute“ festgelegt.
    
        New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}

5.  Bei SIP-Trunkverbindungen wird optional die Ausführung des folgenden Cmdlets empfohlen, um eine lokale Route für Anrufe zu erstellen, die nicht über den SIP-Trunk des E9-1-1-Dienstanbieters verarbeitet werden. Diese Route wird verwendet, wenn die Verbindung zum E9-1-1-Dienstanbieter nicht verfügbar ist.
    
    Im folgenden Beispiel wird davon ausgegangen, dass der Benutzer in seiner VoIP-Richtlinie über die Verwendung „Local“ verfügt.
    
        New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}

</div>

</div>

<span> </span>

</div>

</div>

</div>

