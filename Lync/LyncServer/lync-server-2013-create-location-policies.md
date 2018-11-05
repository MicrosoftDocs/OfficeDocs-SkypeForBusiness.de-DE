---
title: Erstellen von Ortungsrichtlinien in Lync Server 2013
TOCTitle: Erstellen von Ortungsrichtlinien in Lync Server 2013
ms:assetid: f1878194-c756-4794-8fa1-15dd2118b4b3
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg413006(v=OCS.15)
ms:contentKeyID: 49295865
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen von Ortungsrichtlinien in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Lync Server verwendet eine Ortungsrichtlinie, um Lync-Clients während der Clientregistrierung für E9-1-1 zu aktivieren. Eine Ortungsrichtlinie enthält die Einstellungen zur Definition der E9-1-1-Implementierung.

Sie können die globale Ortungsrichtlinie bearbeiten und bereichsspezifische Ortungsrichtlinien erstellen. Ein Client, der sich nicht in einem Subnetz mit zugeordneter Ortungsrichtlinie befindet oder dem nicht direkt eine Ortungsrichtlinie zugeordnet wurde, ruft eine globale Richtlinie ab. Bereichsspezifische Ortungsrichtlinien werden Subnetzen oder Benutzern zugewiesen.

Zum Erstellen einer Ortungsrichtlinie müssen Sie ein Konto verwenden, das Mitglied der Gruppe "RTCUniversalServerAdmins" oder der Administratorrolle "CsVoiceAdministrator" ist oder entsprechende Administratorrechte und -berechtigungen besitzt.

Eine vollständige Beschreibung von Ortungsrichtlinien finden Sie unter [Definieren der Standortrichtlinie für Lync Server 2013](lync-server-2013-defining-the-location-policy.md). Die Cmdlets in diesem Verfahren verwenden eine Ortungsrichtlinie, die mit den folgenden Werten definiert ist:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Element</th>
<th>Wert</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>EnhancedEmergencyServicesEnabled</p></td>
<td><p><strong>True</strong></p></td>
</tr>
<tr class="even">
<td><p>LocationRequired</p></td>
<td><p><strong>Disclaimer</strong></p></td>
</tr>
<tr class="odd">
<td><p>EnhancedEmergencyServiceDisclaimer</p></td>
<td><p>Die Unternehmensrichtlinie erfordert, dass Sie eine Ortung festlegen. Wenn Sie keine Ortung festlegen, können Sie im Ernstfall nicht von Notfalldiensten lokalisiert werden. Bitte legen Sie eine Ortung fest.</p></td>
</tr>
<tr class="even">
<td><p>UseLocationForE911Only</p></td>
<td><p><strong>False</strong></p></td>
</tr>
<tr class="odd">
<td><p>PstnUsage</p></td>
<td><p><strong>EmergencyUsage</strong></p></td>
</tr>
<tr class="even">
<td><p>EmergencyDialString</p></td>
<td><p><strong>911</strong></p></td>
</tr>
<tr class="odd">
<td><p>EmergencyDialMask</p></td>
<td><p><strong>112</strong></p></td>
</tr>
<tr class="even">
<td><p>NotificationUri</p></td>
<td><p><strong>sip:security@litwareinc.com</strong></p></td>
</tr>
<tr class="odd">
<td><p>ConferenceUri</p></td>
<td><p><strong>sip:+14255550123@litwareinc.com</strong></p></td>
</tr>
<tr class="even">
<td><p>ConferenceMode</p></td>
<td><p><strong>twoway</strong></p></td>
</tr>
<tr class="odd">
<td><p>LocationRefreshInterval</p></td>
<td><p><strong>2</strong></p></td>
</tr>
</tbody>
</table>


Ausführliche Informationen zum Arbeiten mit Ortungsrichtlinien finden Sie in der Dokumentation zur Lync Server-Verwaltungsshell-Verwaltungsshell für die folgenden Cmdlets:

  - New-CsLocationPolicy

  - Get-CsLocationPolicy

  - Set-CsLocationPolicy

  - Remove-CsLocationPolicy

  - Grant-CsLocationPolicy

## So erstellen Sie Ortungsrichtlinien

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.
    

    > [!NOTE]
    > Bei Ausführung von "CsLocationPolicy" tritt ein Fehler auf, wenn sich die Einstellung für <STRONG>PstnUsage</STRONG> nicht bereits in der globalen Liste "PstnUsages" befindet.



2.  Optional können Sie auch das folgende Cmdlet ausführen, um die globale Ortungsrichtlinie zu bearbeiten:
    
        Set-CsLocationPolicy -Identity Global -EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -PstnUsage "emergencyUsage" -EmergencyDialString "911" -ConferenceMode "twoway" -ConferenceUri "sip:+14255550123@litwareinc.com" -EmergencyDialMask "112" NotificationUri "sip:security@litwareinc.com" -UseLocationForE911Only $true -LocationRefreshInterval 2

3.  Führen Sie folgendes Cmdlet aus, um eine bereichsspezifische Ortungsrichtlinie zu erstellen.
    
        New-CsLocationPolicy -Identity Tag:Redmond - EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -UseLocationForE911Only $false -PstnUsage "EmergencyUsage" -EmergencyDialString "911" -EmergencyDialMask "112" -NotificationUri "sip:security@litwareinc.com" -ConferenceUri "sip:+14255550123@litwareinc.com" -ConferenceMode "twoway" -LocationRefreshInterval 2

4.  Führen Sie das folgende Cmdlet aus, um die in Schritt 3 erstellte bereichsspezifische Ortungsrichtlinie auf eine Benutzerrichtlinie anzuwenden.
    
        (Get-CsUser | where { $_.Name -match "UserName" }) | Grant-CsLocationPolicy -PolicyName Redmond

