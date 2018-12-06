---
title: Überprüfen von Konfigurationseinstellungen
TOCTitle: Überprüfen von Konfigurationseinstellungen
ms:assetid: 41dbf91c-f2e1-4b9a-88cf-959575558cf2
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204848(v=OCS.15)
ms:contentKeyID: 49293809
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Überprüfen von Konfigurationseinstellungen

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Nach dem Zusammenführen der Topologie und dem Ausführen des **Import-CsLegacyConfiguration** -Cmdlets stellen Sie sicher, dass die Office Communications Server 2007 R2-Richtlinien und -Einstellungen in Lync Server 2013 importiert wurden. In der folgenden Tabelle werden die Richtlinien und Einstellungen aufgelistet, die Sie überprüfen sollten.

## Nach der Migration zu überprüfende Richtlinien und Einstellungen


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
<p>Wählpläne</p>
<p>PSTN-Verwendungseinstellungen</p></td>
</tr>
<tr class="even">
<td><p>Communicator Web Access</p></td>
<td><p>Einfache URLs</p></td>
</tr>
<tr class="odd">
<td><p>Externe Benutzer</p></td>
<td><p>Richtlinien für externen Zugriff</p></td>
</tr>
<tr class="even">
<td><p>Archiving</p></td>
<td><p>Archivierungsrichtlinie</p></td>
</tr>
</tbody>
</table>


## So überprüfen Sie Richtlinien und Einstellungen

1.  Notieren Sie in Ihrer Office Communications Server 2007 R2-Umgebung die Bezeichnungen für die Wähleinstellungen (ehemals als Standortprofile bezeichnet), Zugriffsnummern für die Einwahl (Zugriffstelefonnummern und Regionen der Konferenzzentrale), VoIP-Routen und die Richtlinien in der obenstehenden Tabelle. Notieren Sie außerdem die Communicator Web Access-URLs.

2.  Öffnen Sie auf dem Lync Server 2013-Front-End-Server Lync Server-Systemsteuerung.

3.  Zum Überprüfen der importierten Konferenzrichtlinien klicken Sie im linken Bereich auf **Konferenzen** , dann auf **Konferenzrichtlinie** und überprüfen anschließend, ob alle Konferenzrichtlinien in Ihrer Office Communications Server 2007 R2-Umgebung in der Liste enthalten sind.
    

    > [!NOTE]
    > Die <STRONG>Besprechungsrichtlinie</STRONG> aus früheren Versionen von Office Communications Server wird in Lync Server 2013 jetzt als "Konferenzrichtlinie" bezeichnet. Außerdem ist die Einstellung <STRONG>Anonyme Teilnehmer</STRONG> aus früheren Versionen von Office Communications Server jetzt eine Einstellung in der Lync Server 2013-Konferenzrichtlinie.

    

    > [!NOTE]
    > Wenn in Office Communications Server 2007 R2 für die Konferenzrichtlinie nicht die <STRONG>Option für einzelne Benutzer</STRONG> ausgewählt ist, werden nur globale Richtlinieneinstellungen importiert. In dieser Situation werden keine anderen Konferenzrichtlinien importiert.

    

    > [!NOTE]
    > Wenn in Ihrer Office Communications Server 2007 R2-Konferenzrichtlinie für <STRONG>Anonyme Teilnehmer</STRONG> die Option <STRONG>Pro Benutzer erzwingen</STRONG> ausgewählt ist, werden bei der Migration zwei Konferenzrichtlinien erstellt: In einer ist <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> auf <STRONG>True</STRONG> (Wahr) festgelegt, während in der zweiten <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> auf <STRONG>False</STRONG> (Falsch) festgelegt ist.



4.  Zum Überprüfen von migrierten Wählplänen klicken Sie auf **VoIP-Routing** und auf **Wählplan** , und stellen Sie dann sicher, dass alle Wählpläne in Ihrer Office Communicator 2007 R2-Umgebung in der Liste aufgeführt werden.
    

    > [!NOTE]
    > In Lync Server 2013 werden <STRONG>Standortprofile</STRONG> jetzt als <STRONG>Wähleinstellungen</STRONG> bezeichnet.



5.  Zum Überprüfen der importierten VoIP-Richtlinien klicken Sie auf **VoIP-Routing** , dann auf **VoIP-Richtlinie** , und überprüfen Sie anschließend, ob alle VoIP-Richtlinien in Ihrer Office Communicator 2007 R2-Umgebung in der Liste enthalten sind.
    

    > [!NOTE]
    > Wenn in Ihrer Office Communications Server 2007 R2-Umgebung für die VoIP-Richtlinien nicht die <STRONG>Option für einzelne Benutzer</STRONG> ausgewählt ist, werden nur globale Richtlinieneinstellungen importiert. In dieser Situation werden keine anderen VoIP-Richtlinien importiert.



6.  Zum Überprüfen von migrierten VoIP-Routen klicken Sie auf **VoIP-Routing** und dann auf **Route** , und stellen Sie sicher, dass alle VoIP-Routen in Ihrer Office Communicator 2007 R2-Umgebung in der Liste enthalten sind.

7.  Zum Überprüfen der importierten PSTN-Verwendungseinstellungen klicken Sie auf **VoIP-Routing** und auf **PSTN-Verwendung** , und stellen Sie dann sicher, dass die PSTN-Verwendungseinstellungen aus der Office Communicator 2007 R2-Umgebung in der Liste enthalten sind.

8.  Zum Überprüfen der importierten Richtlinien für externen Zugriff klicken Sie auf **Partnerverbund und externer Zugriff** und auf **Externe Zugriffsrichtlinie** , und stellen Sie dann sicher, dass alle Richtlinien für externen Zugriff in der Office Communicator 2007 R2-Umgebung in der Liste enthalten sind.

9.  Zum Überprüfen von Archivierungsrichtlinien klicken Sie auf **Überwachen und Archivieren** und dann auf **Archivierungsrichtlinie** , und stellen Sie sicher, dass alle Archivierungsrichtlinien in Ihrer Office Communications Server 2007 R2-Umgebung in der Liste enthalten sind.

10. Öffnen Sie die Lync Server-Verwaltungsshell.

11. Geben Sie zum Überprüfen der Anwesenheitsrichtlinien an der Befehlszeile Folgendes ein:
    
        Get-CsPresencePolicy
    
    Überprüfen Sie anhand des Namens im Parameter **Identität** , ob alle Anwesenheitsrichtlinien in Ihrer Office Communications Server 2007 R2-Umgebung importiert wurden.

## So überprüfen Sie Richtlinien und Einstellungen mithilfe von Cmdlets

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

