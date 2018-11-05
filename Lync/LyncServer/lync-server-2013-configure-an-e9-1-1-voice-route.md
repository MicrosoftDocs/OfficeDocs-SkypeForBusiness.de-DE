---
title: Konfigurieren einer E9-1-1-VoIP-Route in Lync Server 2013
TOCTitle: Konfigurieren einer E9-1-1-VoIP-Route in Lync Server 2013
ms:assetid: 6933b840-0e7b-4509-ae43-bc9065677547
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398496(v=OCS.15)
ms:contentKeyID: 49294283
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren einer E9-1-1-VoIP-Route in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-17_

Zum Bereitstellen des Notruf-Features ("E9-1-1") müssen Sie zunächst eine VoIP-Route für Notrufe konfigurieren. Ausführliche Informationen zum Erstellen von VoIP-Routen finden Sie unter [Erstellen einer VoIP-Route in Lync Server 2013](lync-server-2013-create-a-voice-route.md). Sie können auch mehrere Routen definieren, zum Beispiel wenn Ihre Bereitstellung einen primären und einen sekundären SIP-Trunk enthält.


> [!NOTE]
> Wenn Sie Standortinformationen in einem E9-1-1-INVITE-Befehl aufnehmen möchten, müssen Sie zunächst den SIP-Trunk konfigurieren, der zum Routen von Notrufen über das Gateway eine Verbindung mit dem E9-1-1-Dienstanbieter herstellt. Setzen Sie zu diesem Zweck im <STRONG>Set-CsTrunkConfiguration</STRONG>-Cmdlet das Flag "EnablePIDFLOSupport" auf "True". Der Standardwert für "EnablePIDFLOSupport" lautet "False". Beispiel: <CODE>Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.</CODE><BR>Es ist nicht erforderlich, Empfangsstandorte für Ausweich-PSTN-Gateways und -ELIN-Gateways (Emergency Location Identification Number) zu aktivieren.



Ausführliche Informationen zum Arbeiten mit VoIP-Routen finden Sie in der Lync Server-Verwaltungsshell-Dokumentation für die folgenden Cmdlets:

  - **Set-CsPstnUsage**

  - **Get-CsPstnUsage**

  - **New-CsVoiceRoute**

  - **Get-CsVoiceRoute**

  - **Set-CsVoiceRoute**

  - **Remove-CsVoiceRoute**

## So konfigurieren Sie eine E9-1-1-VoIP-Route

1.  Melden Sie sich mit einem Konto, das Mitglied der Gruppe "RTCUniversalServerAdmins" oder der Administratorrolle "CsVoiceAdministrator" ist, am Computer an.

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Führen Sie das folgende Cmdlet aus, um einen neuen PSTN-Verwendungsdatensatz zu erstellen.
    
    Das muss der gleiche Name sein, den Sie bei der Einstellung **PSTN** in der Standortrichtlinie verwenden möchten. Obgleich Ihre Bereitstellung mehrere Telefonverwendungsdatensätze enthalten wird, fügt das folgende Beispiel der aktuellen Liste der verfügbaren PSTN-Verwendungen den Datensatz "Notfallverwendung" hinzu. Nähere Informationen dazu finden Sie unter [Konfigurieren von VoIP-Richtlinien und PSTN-Verwendungsdatensätzen zum Autorisieren von Anruffunktionen und -berechtigungen in Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).
    
        Set-CsPstnUsage -Usage @{add='EmergencyUsage'}

4.  Führen Sie das folgende Cmdlet aus, um eine neue VoIP-Route unter Verwendung des eben erstellten PSTN-Verwendungsdatensatzes zu erstellen.
    
    Das Nummernmuster muss das gleiche wie das in der Einstellung **Notrufwählzeichenfolge** in der Standortrichtlinie verwendete sein. Ein Pluszeichen "+" ist erforderlich, weil Lync das Pluszeichen "+" zu Notrufen hinzufügt. "Co1-pstngateway-1" ist die Dienst-ID des SIP-Trunks für den Notrufdienstanbieter oder für das ELIN-Gateway. Im folgenden Beispiel wird für die VoIP-Route der Name "EmergencyRoute" festgelegt.
    
        New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}

5.  Bei SIP-Trunk-Verbindungen wird optional die Ausführung des folgenden Cmdlets empfohlen, um eine lokale Route für Anrufe zu erstellen, die nicht über den SIP-Trunk des Anbieters für die Notrufunterstützung verarbeitet werden. Diese Route wird verwendet, wenn die Verbindung zu dem Anbieter für Notrufunterstützung nicht verfügbar ist.
    
    Im folgenden Beispiel wird davon ausgegangen, dass der Benutzer in seiner VoIP-Richtlinie über die Verwendung "Local" verfügt.
    
        New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}

