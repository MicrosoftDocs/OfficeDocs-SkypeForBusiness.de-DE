---
title: Konfigurieren der verschiedenen Richtlinien
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Configuring the Various Policies
ms:assetid: e3b3cbda-7c17-470b-acb0-82fdcc473184
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945610(v=OCS.15)
ms:contentKeyID: 51541436
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17116443361749bd3bcce75d5a9d38a08a3ba95c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147768"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-the-various-policies"></a>Konfigurieren der verschiedenen Richtlinien

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-24_

<div>

## <a name="configuring-the-various-policies"></a>Konfigurieren der verschiedenen Richtlinien

Im folgenden finden Sie die verschiedenen Richtlinien, die Sie in ihrer lync Server 2013 Topologie konfigurieren können, bevor Sie das Tool für die lync Server 2013 Spannung und Leistung ausführt.

<div>

## <a name="configuring-the-archiving-policy"></a>Konfigurieren der Archivierungsrichtlinie

Siehe das Beispielskript ArchivingPolicy. ps1. Sie müssen dieses Skript nur verwenden, wenn ein Archivierungsserver in Ihrer Topologie bereitgestellt wird. Ausführliche Informationen finden Sie in der lync Server 2013-Dokumentation und im Cmdlet-Hilfe zum [Archivieren und Überwachen von Cmdlets in lync Server 2013](https://technet.microsoft.com/library/gg415629\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-the-conferencing-policy"></a>Konfigurieren der konferenzrichtlinie

Siehe das Beispielskript meetingpolicy ". ps1. Ausführliche Informationen finden Sie in der lync Server 2013-Dokumentation und in der Cmdlet-Hilfe für [Webkonferenz-Cmdlets in lync Server 2013](https://technet.microsoft.com/library/gg415675\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-the-contacts-policy"></a>Konfigurieren der Kontakt Richtlinie

Siehe das Beispiel ContactsPolicy. ps1. Ausführliche Informationen finden Sie in der lync Server 2013-Dokumentation und in der Cmdlet-Hilfe für [Sofortnachrichten-und Anwesenheits-Cmdlets in lync Server 2013](https://technet.microsoft.com/library/gg398611\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-the-federation-policy"></a>Konfigurieren der Verbund Richtlinie

Siehe das Beispiel FederationPolicy. ps1. Ausführliche Informationen finden Sie in der lync Server 2013-Dokumentation und in der Cmdlet-Hilfe für [Edgeserver-Cmdlets in lync Server 2013](https://technet.microsoft.com/library/gg415635\(v=ocs.15\)) und [Cmdlets für den Verbund und den externen Zugriff in lync Server 2013](https://technet.microsoft.com/library/gg415651\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-the-call-admission-control-policy"></a>Konfigurieren der Richtlinie für die Anrufsteuerung

Siehe das Beispiel BandwidthPolicy. ps1. Ausführliche Informationen finden Sie in der lync Server 2013-Dokumentation über die [Anrufsteuerung in lync Server 2013](https://technet.microsoft.com/library/gg398529\(v=ocs.15\)) und in der Cmdlet-Hilfe für [Cmdlets für die Anrufsteuerung in lync Server 2013](https://technet.microsoft.com/library/gg415676\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-the-voice-routing-rules"></a>Konfigurieren der VoIP-Weiterleitungsregeln

Siehe das Beispiel RoutingRules. ps1. Wenn Sie die Regeln für das VoIP-Routing konfigurieren, notieren Sie sich den Telefonkontext (d./Location Profil oder/SimpleName) sowie interne/externe Vorwahl, damit Sie Sie beim Erstellen von Benutzern und während der LyncPerfTool-Konfiguration (speziell für PSTN-UC und UC-PSTN) angeben können. Beispielsweise sollte der Parameter SimpleName im Aufruf des **New-CsDialPlan-** Cmdlets im RoutingRules. ps1-Beispiel für den LocationProfile-Wert in der folgenden Abbildung von UserProfileGenerator. exe verwendet werden.

![Beispiel für VoIP-Routingregel.](images/JJ945610.9f34d971-4ed0-4a4c-b101-086a91c4578c(OCS.15).jpg "Beispiel für VoIP-Routingregel.")

Ausführliche Informationen finden Sie in der lync Server 2013-Dokumentation und in der Cmdlet-Hilfe für [Enterprise-VoIP-Cmdlets in lync Server 2013](https://technet.microsoft.com/library/gg415658\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-conferencing-attendant-application"></a>Konfigurieren von Konferenzzentrale

Siehe das Beispiel ConferenceAutoAttendantConfiguration. ps1. Notieren Sie sich die ConferencingAutoAttendant-Telefonnummer (standardmäßig 1121111111), damit Sie Sie zur Konfigurations Generierung in das LyncPerf-Tool-Konfigurationstool eingeben können.

![Konfigurieren der Konferenzzentrale](images/JJ945610.0618a22f-27a9-423a-9085-d2bf71e82db6(OCS.15).jpg "Konfigurieren der Konferenzzentrale")

Ausführliche Informationen finden Sie in der lync Server 2013-Dokumentation und in der Cmdlet-Hilfe für [Webkonferenz-Cmdlets in lync Server 2013](https://technet.microsoft.com/library/gg415675\(v=ocs.15\)) und [Cmdlets für Einwahlkonferenzen in lync Server 2013](https://technet.microsoft.com/library/gg415630\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-lync-server-call-park-service"></a>Konfigurieren lync Server-Dienst zum Parken von Anrufen

Das Parken von anrufen ist standardmäßig deaktiviert. Siehe das Beispiel CallParkConfiguration. ps1. Ausführliche Informationen finden Sie in der lync Server 2013-Dokumentation und in der Cmdlet-Hilfe für [Anwendung zum Parken von Anrufen-Cmdlets in lync Server 2013](https://technet.microsoft.com/library/gg415639\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-emergency-calls"></a>Konfigurieren von Notrufen

Führen Sie die folgenden Schritte aus, um Belastungs-und Leistungstests für Notfallanrufe zu konfigurieren.

1.  Richten Sie eine VoIP-Route für Notfallanrufe ein. Ein Beispiel für das Einrichten dieser VoIP-Route finden Sie im RoutingRules. ps1-Skript unter dem Kommentar "Route E911 to PSTN".
    
    <div>
    

    > [!WARNING]  
    > Der Beispielbefehl in RoutingRules. ps1 weist ein Nummernmuster auf, das die Zahl 119 statt 911 enthält. Vermeiden Sie die Verwendung von 911 (oder ihrer tatsächlichen lokalen Notrufnummer), um versehentliche Anrufe bei Ihren lokalen Notrufbetreibern während Auslastungstests zu verhindern. Diese Konfiguration dient nur zu Simulationszwecken.

    
    </div>

2.  Konfigurieren Sie Adressen, indem Sie die Werte auf der Registerkarte **LIS** in der UserProvisioningTool eingeben, wie in der folgenden Abbildung dargestellt.
    
    ![Konfigurieren des Standort Informationsdiensts](images/JJ945610.8ac1faa1-e9f9-40d0-b8b7-b159f4f459f7(OCS.15).jpg "Konfigurieren des Standort Informationsdiensts")  

3.  Klicken Sie auf **LIS-Konfigurationsdateien generieren**.

4.  CSV-Dateien für Ports, Subnetze, Switches und drahtlose Zugriffspunkte (WAPs) und eine XML-Datei für das lync Server 2013 Stress and Performance Tool werden generiert. Die CSV-Dateien müssen als Eingaben (im gleichen Ordner) verwendet werden, wenn Sie Standortinformationsdienst (LIS) mit dem LisConfiguration. ps1-Skript konfigurieren. Verschiebt die generierte Locations0. XML-Datei in denselben Ordner wie die ausführbare Datei für das lync Server 2013 Stress und das Leistungs Tool (LyncPerfTool. exe), in der die Szenarien für Standortprofile (Wähleinstellungen) ausgeführt werden.

</div>

<div>

## <a name="creating-enabling-configuring-and-disabling-users"></a>Erstellen, aktivieren, konfigurieren und Deaktivieren von Benutzern

Sie sollten alle Ihre Benutzer erstellen, bevor Sie die folgenden Skripts ausführen. Befolgen Sie die Anweisungen unter [Create users and Contacts](create-users-and-contacts.md) to Create users. Ausführliche Informationen finden Sie in der Dokumentation zum lync Server 2013-Cmdlet für die Cmdlets [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)), [CsUser](https://technet.microsoft.com/library/gg398510\(v=ocs.15\))und [Disable-CsUser](https://technet.microsoft.com/library/gg398747\(v=ocs.15\)) .

</div>

<div>

## <a name="configuring-response-group-application"></a>Konfigurieren von Reaktionsgruppenanwendung

Siehe das Beispiel ResponseGroupConfiguration. ps1. Ausführliche Informationen finden Sie in der lync Server 2013-Dokumentation und in der Cmdlet-Hilfe für [Reaktionsgruppenanwendung-Cmdlets in lync Server 2013](https://technet.microsoft.com/library/gg415654\(v=ocs.15\)). Informationen zum Überprüfen der Reaktionsgruppenanwendung Konfiguration `https://<poolfqdn>/RgsConfig/`finden Sie unter, wie in der folgenden Abbildung dargestellt.

![Das Tool für die Reaktionsgruppen Konfiguration.](images/JJ945610.480a9440-2283-4533-98f8-86daaab4781c(OCS.15).jpg "Das Tool für die Reaktionsgruppen Konfiguration.")

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

