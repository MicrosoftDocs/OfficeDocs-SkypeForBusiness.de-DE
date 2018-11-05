---
title: Konfigurieren der Seite für den Besprechungsbeitritt
TOCTitle: Konfigurieren der Seite für den Besprechungsbeitritt
ms:assetid: 036c9d03-ad95-4d63-a3d8-6cae1a8ad530
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204635(v=OCS.15)
ms:contentKeyID: 49293013
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren der Seite für den Besprechungsbeitritt

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Wenn ein Benutzer auf einen Besprechungslink in einer Besprechungsanfrage klickt, ermittelt die Seite für den Besprechungsbeitritt, ob bereits ein Lync 2013-Client auf dem Computer des Benutzers installiert ist. Wenn bereits ein Client installiert ist, öffnet dieser Client die Besprechung, und er tritt ihr bei. Ist kein Client installiert, wird standardmäßig die Version 2013 von Lync Web App geöffnet.

Sie können das Verhalten der Seite für den Besprechungsbetritt ändern, wenn Sie Benutzern den Besprechungsbeitritt mit Office Communicator 2007 R2 oder Lync 2010-Vermittlung ermöglichen möchten. Diese Konfigurationsoptionen wurden zwar aus der Systemsteuerung für Lync Server 2013 entfernt, Sie können sie jedocht mithilfe des Cmdlets "CsWebServiceConfiguration" konfigurieren.

### Parameter "CsWebServiceConfiguration" der Besprechungsbeitrittsseite

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Parameter &quot;CsWebServiceConfiguration&quot;</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ShowJoinUsingLegacyClientLink</p></td>
<td><p>Bei Festlegung auf &quot;True&quot; wird Benutzern, die einer Besprechung mithilfe einer anderen Clientanwendung als Lync beitreten, die Möglichkeit gegeben, mithilfe von Office Communicator 2007 R2 an der Besprechung teilzunehmen. Der Standardwert lautet &quot;False&quot;.</p></td>
</tr>
<tr class="even">
<td><p>ShowAlternateJoinOptionsExpanded</p></td>
<td><p>Bei Festlegung auf &quot;True&quot; werden automatisch Alternativoptionen für den Onlinekonferenzbeitritt (beispielsweise Office Communicator 2007 R2) erweitert und den Benutzern angezeigt. Bei Festlegung auf den Standardwert &quot;False&quot; sind diese Optionen zwar ebenfalls verfügbar, müssen vom Benutzer aber manuell angezeigt werden.</p></td>
</tr>
</tbody>
</table>


## So konfigurieren Sie die Seite für den Besprechungsbeitritt mithilfe der Verwaltungsshell für Lync Server 2013

1.  Starten Sie die Verwaltungsshell für Lync Server 2013: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft Lync Server 2013** und klicken Sie dann auf **Lync Server-Verwaltungsshell**.

2.  Führen Sie das folgende Cmdlet aus:
    
        Get-CsWebServiceConfiguration
    
    Dieses Cmdlet gibt die Konfigurationseinstellungen für den Webdienst zurück.

3.  Führen Sie den folgenden Befehl aus und legen Sie die Parameter je nach Wunsch auf "True" oder "False" fest (ausführliche Informationen zu den Parametern für dieses Cmdlet finden Sie in der Dokumentation zur Verwaltungsshell für Lync Server 2013):
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

