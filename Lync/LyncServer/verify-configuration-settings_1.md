---
title: Überprüfen der Konfigurationseinstellungen
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Verify configuration settings
ms:assetid: 41dbf91c-f2e1-4b9a-88cf-959575558cf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204848(v=OCS.15)
ms:contentKeyID: 48183997
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a20b78ac9275657461beb74a7325c0c46e4e40fd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846979"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-configuration-settings"></a>Überprüfen der Konfigurationseinstellungen

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-28_

Nachdem Sie die Topologie zusammengeführt und das Cmdlet " **Import-CsLegacyConfiguration** " ausgeführt haben, vergewissern Sie sich, dass Ihre Office Communications Server 2007 R2-Richtlinien und-Einstellungen in lync Server 2013 importiert wurden. In der folgenden Tabelle sind die Richtlinien und Einstellungen aufgeführt, die Sie überprüfen sollten.

<div>

## <a name="policies-and-settings-to-verify-after-migration"></a>Richtlinien und Einstellungen, die nach der Migration überprüft werden sollen


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Wenn Sie diese Arbeitsauslastung verwenden:</th>
<th>Überprüfen Sie diese Richtlinien und Einstellungen:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Instant Messaging (im) und Konferenzen</p></td>
<td><p>Anwesenheitsrichtlinie</p>
<p>Konferenzrichtlinie</p></td>
</tr>
<tr class="even">
<td><p>Einwahlkonferenzen</p></td>
<td><p>Einwahl-Zugriffsnummern</p>
<p>Wählpläne</p></td>
</tr>
<tr class="odd">
<td><p>Enterprise-VoIP</p></td>
<td><p>VoIP-Richtlinie</p>
<p>VoIP-Routen</p>
<p>Wählpläne</p>
<p>PSTN-Nutzungseinstellungen</p></td>
</tr>
<tr class="even">
<td><p>Communicator Web Access</p></td>
<td><p>Einfache URLs </p></td>
</tr>
<tr class="odd">
<td><p>Externe Benutzer</p></td>
<td><p>Richtlinien für den externen Zugriff</p></td>
</tr>
<tr class="even">
<td><p>Archiving</p></td>
<td><p>Archivierungsrichtlinie</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-verify-policies-and-settings"></a>So überprüfen Sie Richtlinien und Einstellungen

1.  Notieren Sie sich in Ihrer Office Communications Server 2007 R2-Umgebung die Namen von Wählplänen (vormals als Standortprofile bezeichnet), Einwahl Zugriffsnummern (Konferenzzentrale für den Zugriff auf Telefonnummern und Regionen), VoIP-Routen und die Richtlinien, die in der Liste obige Tabelle zusätzlich zu den URLs, die für Communicator Web Access verwendet werden.

2.  Öffnen Sie auf dem lync Server 2013-Front-End-Server die lync Server-Systemsteuerung.

3.  Um importierte Konferenzrichtlinien zu überprüfen, klicken Sie im linken Bereich auf **Konferenzen**, klicken Sie auf **konferenzrichtlinie**, und überprüfen Sie dann, ob alle Konferenzrichtlinien in Ihrer Office Communications Server 2007 R2-Umgebung in der Liste enthalten sind.
    
    <div>
    

    > [!NOTE]  
    > Die <STRONG>Besprechungs</STRONG> Richtlinie aus früheren Versionen von Office Communications Server wird jetzt als konferenzrichtlinie in lync Server 2013 bezeichnet. Darüber hinaus ist die Einstellung für <STRONG>Anonyme Teilnehmern</STRONG> aus früheren Versionen von Office Communications Server jetzt eine Einstellung in der lync Server 2013-konferenzrichtlinie.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Wenn in Office Communications Server 2007 R2 die konferenzrichtlinie nicht auf <STRONG>pro Benutzer verwenden</STRONG>eingestellt ist, werden nur globale Richtlinieneinstellungen importiert. In dieser Situation werden keine weiteren Konferenzrichtlinien importiert.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Wenn für <STRONG>Anonyme Teilnehmer</STRONG> in Ihrer Office Communications Server 2007 R2-konferenzrichtlinie die <STRONG>Erzwingung pro Benutzer</STRONG> eingerichtet ist, werden während der Migration zwei Konferenzrichtlinien erstellt: eine mit <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> auf <STRONG>True</STRONG> und eins, wobei <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> auf <STRONG>false</STRONG>festgelegt ist.

    
    </div>

4.  Klicken Sie zum Überprüfen von importierten Wählplänen auf **VoIP-Routing**, klicken Sie auf **Wählplan**, und überprüfen Sie, ob alle Wählpläne in Ihrer Office Communicator 2007 R2-Umgebung in der Liste enthalten sind.
    
    <div>
    

    > [!NOTE]  
    > In lync Server 2013 werden <STRONG>Standortprofile</STRONG> nun als Wählpläne bezeichnet <STRONG></STRONG>.

    
    </div>

5.  Um importierte VoIP-Richtlinien zu überprüfen, klicken Sie auf **VoIP-Routing**, klicken Sie auf **VoIP-Richtlinie**, und überprüfen Sie dann, ob alle VoIP-Richtlinien in Ihrer Office Communicator 2007 R2-Umgebung in der Liste enthalten sind.
    
    <div>
    

    > [!NOTE]  
    > Wenn für die VoIP-Richtlinie nicht die <STRONG>Verwendung pro Benutzer</STRONG> in Ihrer Office Communications Server 2007 R2-Umgebung eingestellt ist, werden nur globale Richtlinieneinstellungen importiert. In dieser Situation werden keine anderen VoIP-Richtlinien importiert.

    
    </div>

6.  Um importierte VoIP-Routen zu überprüfen, klicken Sie auf **VoIP-Routing**, klicken Sie auf **Route**, und stellen Sie dann sicher, dass alle VoIP-Routen in Ihrer Office Communicator 2007 R2-Umgebung in der Liste enthalten sind.

7.  Um die importierten PSTN-Nutzungseinstellungen zu überprüfen, klicken Sie auf **VoIP-Routing**, klicken Sie auf **PSTN-Nutzung**, und überprüfen Sie, ob die PSTN-Verwendungseinstellungen aus Ihrer Office Communicator 2007 R2-Umgebung in der Liste enthalten sind.

8.  Um importierte Richtlinien für den externen Zugriff zu überprüfen, klicken Sie auf **Föderation und externer Zugriff**, klicken Sie auf **Richtlinie für den externen Zugriff**, und überprüfen Sie, ob alle Richtlinien für den externen Zugriff in Ihrer Office Communicator 2007 R2-Umgebung in der Liste enthalten sind

9.  Klicken Sie zum Überprüfen von Archivierungsrichtlinien auf **Überwachung und Archivierung**, klicken Sie auf **Archivierungsrichtlinie**, und überprüfen Sie dann, ob alle Archivierungsrichtlinien in Ihrer Office Communications Server 2007 R2-Umgebung in der Liste enthalten sind.

10. Öffnen Sie die lync Server-Verwaltungsshell.

11. Zum Überprüfen von Anwesenheitsrichtlinien geben Sie in der Befehlszeile Folgendes ein:
    
        Get-CsPresencePolicy
    
    Überprüfen Sie den Namen im Parameter **Identity** , und stellen Sie sicher, dass alle Anwesenheitsrichtlinien in Ihrer Office Communications Server 2007 R2-Umgebung importiert wurden.

</div>

<div>

## <a name="to-verify-policies-and-settings-by-using-cmdlets"></a>So überprüfen Sie Richtlinien und Einstellungen mithilfe von Cmdlets

1.  Öffnen Sie die lync Server-Verwaltungsshell.

2.  Führen Sie die Cmdlets in der folgenden Tabelle aus, um Richtlinien und Einstellungen zu überprüfen.
    
    Die Syntax dieser Cmdlets ist wie im folgenden Beispiel dargestellt:
    
        Get-CsConferencingPolicy
    
    Details zu diesen Cmdlets finden Sie unter:
    
        Get-Help <cmdlet name> -Detailed


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Für diese Richtlinie oder Einstellung:</th>
<th>Verwenden Sie dieses Cmdlet:</th>
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
<td><p>Einwahl-Zugriffsnummern</p></td>
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
<td><p>Richtlinien für den externen Zugriff</p></td>
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

