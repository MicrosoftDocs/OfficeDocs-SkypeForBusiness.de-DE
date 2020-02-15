---
title: Überprüfen der Konfigurationseinstellungen
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify configuration settings
ms:assetid: 41dbf91c-f2e1-4b9a-88cf-959575558cf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204848(v=OCS.15)
ms:contentKeyID: 48183997
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9871d16c3e5b0af894653ac5d60c4614201e8e24
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "41983050"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-configuration-settings"></a>Überprüfen der Konfigurationseinstellungen

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-28_

Nachdem Sie die Topologie zusammengeführt und das **Import-CsLegacyConfiguration-** Cmdlet ausgeführt haben, stellen Sie sicher, dass Ihre Office Communications Server 2007 R2-Richtlinien und-Einstellungen in lync Server 2013 importiert wurden. In der folgenden Tabelle werden die Richtlinien und Einstellungen aufgelistet, die Sie überprüfen sollten.

<div>

## <a name="policies-and-settings-to-verify-after-migration"></a>Nach der Migration zu überprüfende Richtlinien und Einstellungen


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Verwendete Arbeitslast</th>
<th>Zu überprüfende Richtlinien und Einstellungen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Instant Messaging und Konferenzen</p></td>
<td><p>Anwesenheitsrichtlinie</p>
<p>Konferenzrichtlinie</p></td>
</tr>
<tr class="even">
<td><p>Einwahlkonferenzen</p></td>
<td><p>Zugriffsnummern für Einwahlkonferenz</p>
<p>Wählpläne</p></td>
</tr>
<tr class="odd">
<td><p>Enterprise-VoIP</p></td>
<td><p>VoIP-Richtlinie</p>
<p>VoIP-Routen</p>
<p>Wähleinstellungen</p>
<p>PSTN-Verwendungseinstellungen</p></td>
</tr>
<tr class="even">
<td><p>Communicator Web Access</p></td>
<td><p>Einfache URLs</p></td>
</tr>
<tr class="odd">
<td><p>Externe Benutzer</p></td>
<td><p>Richtlinien für den externen Zugriff</p></td>
</tr>
<tr class="even">
<td><p>Archivierung</p></td>
<td><p>Archivierungsrichtlinie</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-verify-policies-and-settings"></a>So überprüfen Sie Richtlinien und Einstellungen

1.  Notieren Sie sich in Ihrer Office Communications Server 2007 R2 Umgebung die Namen von Wähleinstellungen (früher als Standortprofile bezeichnet), Einwahlnummern (Zugriffs Telefonnummern und Regionen für die Konferenzzentrale), VoIP-Routen und die Richtlinien in der Liste obige Tabelle zusätzlich zu den für Communicator-Webzugriff verwendeten URLs.

2.  Öffnen Sie auf dem lync Server 2013-Front-End-Server lync Server-Systemsteuerung.

3.  Zum Überprüfen der importierten Konferenzrichtlinien klicken Sie im linken Bereich auf **Konferenzen**, dann auf **konferenzrichtlinie**, und stellen Sie sicher, dass alle Konferenzrichtlinien in Ihrer Office Communications Server 2007 R2 Umgebung in der Liste enthalten sind.
    
    <div>
    

    > [!NOTE]  
    > Die <STRONG>Besprechungs</STRONG> Richtlinie aus früheren Versionen von Office Communications Server wird nun in lync Server 2013 als konferenzrichtlinie bezeichnet. Darüber hinaus ist die Einstellung für <STRONG>Anonyme Teilnehmern</STRONG> aus früheren Versionen von Office Communications Server jetzt eine Einstellung in der lync Server 2013 konferenzrichtlinie.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Wenn in Office Communications Server 2007 R2 die konferenzrichtlinie nicht auf die <STRONG>Verwendung pro Benutzer</STRONG>festgelegt ist, werden nur globale Richtlinieneinstellungen importiert. In dieser Situation werden keine anderen Konferenzrichtlinien importiert.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Wenn <STRONG>Anonyme Teilnehmer</STRONG> in Ihrer Office Communications Server 2007 R2 konferenzrichtlinie auf <STRONG>erzwingen pro Benutzer</STRONG> festgelegt sind, werden während der Migration zwei Konferenzrichtlinien erstellt: eine mit <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> <STRONG>, und eine</STRONG> mit <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> , die auf <STRONG>false</STRONG>festgelegt ist.

    
    </div>

4.  Zum Überprüfen von migrierten Wählplänen klicken Sie auf **VoIP-Routing** und auf **Wählplan**, und stellen Sie dann sicher, dass alle Wählpläne in Ihrer Office Communicator 2007 R2-Umgebung in der Liste aufgeführt werden.
    
    <div>
    

    > [!NOTE]  
    > In lync Server 2013 werden <STRONG>Standortprofile</STRONG> jetzt als <STRONG>Wählpläne</STRONG>bezeichnet.

    
    </div>

5.  Zum Überprüfen der importierten VoIP-Richtlinien klicken Sie auf **VoIP-Routing**, dann auf **VoIP-Richtlinie**, und überprüfen Sie anschließend, ob alle VoIP-Richtlinien in Ihrer Office Communicator 2007 R2-Umgebung in der Liste enthalten sind.
    
    <div>
    

    > [!NOTE]  
    > Wenn für die VoIP-Richtlinie nicht die <STRONG>Verwendung pro Benutzer</STRONG> in Ihrer Office Communications Server 2007 R2 Umgebung festgelegt ist, werden nur globale Richtlinieneinstellungen importiert. In dieser Situation werden keine anderen VoIP-Richtlinien importiert.

    
    </div>

6.  Zum Überprüfen von migrierten VoIP-Routen klicken Sie auf **VoIP-Routing** und dann auf **Route**, und stellen Sie sicher, dass alle VoIP-Routen in Ihrer Office Communicator 2007 R2-Umgebung in der Liste enthalten sind.

7.  Zum Überprüfen der importierten PSTN-Verwendungseinstellungen klicken Sie auf **VoIP-Routing** und auf **PSTN-Verwendung**, und stellen Sie dann sicher, dass die PSTN-Verwendungseinstellungen aus der Office Communicator 2007 R2-Umgebung in der Liste enthalten sind.

8.  Zum Überprüfen der importierten Richtlinien für externen Zugriff klicken Sie auf **Partnerverbund und externer Zugriff** und auf **Externe Zugriffsrichtlinie**, und stellen Sie dann sicher, dass alle Richtlinien für externen Zugriff in der Office Communicator 2007 R2-Umgebung in der Liste enthalten sind.

9.  Klicken Sie zum Überprüfen der Archivierungsrichtlinien auf **Überwachung und Archivierung**, klicken Sie auf **Archivierungsrichtlinie**, und stellen Sie dann sicher, dass alle Archivierungsrichtlinien in Ihrer Office Communications Server 2007 R2 Umgebung in der Liste enthalten sind.

10. Öffnen Sie die Lync Server-Verwaltungsshell.

11. Geben Sie zum Überprüfen der Anwesenheitsrichtlinien an der Befehlszeile Folgendes ein:
    
        Get-CsPresencePolicy
    
    Stellen Sie sicher, dass alle Präsenz Richtlinien in Ihrer Office Communications Server 2007 R2 Umgebung importiert wurden, indem Sie den Namen im Parameter **Identity** betrachten.

</div>

<div>

## <a name="to-verify-policies-and-settings-by-using-cmdlets"></a>So überprüfen Sie Richtlinien und Einstellungen mithilfe von Cmdlets

1.  Öffnen Sie die Lync Server-Verwaltungsshell.

2.  Führen Sie die Cmdlets in der folgenden Tabelle aus, um Richtlinien und Einstellungen zu überprüfen.
    
    Die Syntax dieser Cmdlets entspricht dem folgenden Beispiel:
    
        Get-CsConferencingPolicy
    
    Wenn Sie ausführliche Informationen zu diesen Cmdlets benötigen, führen Sie folgenden Befehl aus:
    
        Get-Help <cmdlet name> -Detailed


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Zu überprüfende Richtlinie oder Einstellung</th>
<th>Cmdlet</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Anwesenheitsrichtlinie</p></td>
<td><p><strong>Get-CsPresencePolicy</strong></p></td>
</tr>
<tr class="even">
<td><p>Konferenzrichtlinie</p></td>
<td><p><strong>Get-CsConferencingPolicy</strong></p></td>
</tr>
<tr class="odd">
<td><p>Zugriffsnummern für Einwahlkonferenz</p></td>
<td><p><strong>Get-CsDialInConferencingAccessNumber</strong></p></td>
</tr>
<tr class="even">
<td><p>Wählpläne</p></td>
<td><p><strong>Get-CsDialPlan</strong></p></td>
</tr>
<tr class="odd">
<td><p>VoIP-Richtlinie</p></td>
<td><p><strong>Get-CsVoicePolicy</strong></p></td>
</tr>
<tr class="even">
<td><p>VoIP-Routen</p></td>
<td><p><strong>Get-CsVoiceRoute</strong></p></td>
</tr>
<tr class="odd">
<td><p>PSTN-Verwendung</p></td>
<td><p><strong>Get-CsPstnUsage</strong></p></td>
</tr>
<tr class="even">
<td><p>URLs</p></td>
<td><p><strong>Get-CsSimpleUrlConfiguration</strong></p></td>
</tr>
<tr class="odd">
<td><p>Richtlinien für externen Zugriff</p></td>
<td><p><strong>Get-CsExternalAccessPolicy</strong></p></td>
</tr>
<tr class="even">
<td><p>Archivierungsrichtlinie</p></td>
<td><p><strong>Get-CsArchivingPolicy</strong></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

