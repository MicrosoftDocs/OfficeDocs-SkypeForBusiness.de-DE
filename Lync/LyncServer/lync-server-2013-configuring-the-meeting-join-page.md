---
title: 'Lync Server 2013: Konfigurieren der Seite für den Besprechungsbeitritt'
TOCTitle: Konfigurieren der Seite für den Besprechungsbeitritt
ms:assetid: 45880423-47f4-49af-b825-cbd8e3fc1046
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204861(v=OCS.15)
ms:contentKeyID: 49293861
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren der Seite für den Besprechungsbeitritt in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Wenn ein Benutzer auf einen Besprechungslink in einer Besprechungsanfrage klickt, ermittelt die Seite für den Besprechungsbeitritt, ob bereits ein Lync 2013-Client auf dem Computer des Benutzers installiert ist. Wenn bereits ein Client installiert ist, wird dieser geöffnet und tritt der Besprechung bei. Wenn noch kein Client installiert ist, wird standardmäßig die 2013er-Version von Lync Web App geöffnet.

Wenn Sie möchten, dass sich Benutzer mit Office Communicator 2007 R2 oder Lync 2010-Vermittlung Besprechungen anschließen können, können Sie das Verhalten der Seite für den Besprechungsbeitritt ändern. Diese Konfigurationsoptionen wurden aus Systemsteuerung für Lync Server 2013 entfernt. Sie können die entsprechende Konfiguration jedoch mithilfe des Cmdlets Set-CsWebServiceConfiguration durchführen.

### Set-CsWebServiceConfiguration-Parameter der Seite für den Besprechungsbeitritt

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Set-CsWebServiceConfiguration-Parameter</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ShowJoinUsingLegacyClientLink</p></td>
<td><p>Wenn dieser Parameter auf &quot;True&quot; festgelegt ist, können Benutzer, die einer Besprechung mit einer anderen Clientanwendung als Lync beizutreten versuchen, der Besprechung mit Office Communicator 2007 R2 beitreten. Der Standardwert ist &quot;False&quot;.</p></td>
</tr>
<tr class="even">
<td><p>ShowAlternateJoinOptionsExpanded</p></td>
<td><p>Bei Festlegung auf &quot;True&quot; werden automatisch Alternativoptionen für den Onlinekonferenzbeitritt (beispielsweise Office Communicator 2007 R2) erweitert und den Benutzern angezeigt. Bei Festlegung auf den Standardwert &quot;False&quot; sind diese Optionen zwar ebenfalls verfügbar, müssen vom Benutzer aber manuell angezeigt werden.</p></td>
</tr>
</tbody>
</table>


## So konfigurieren Sie die Seite für den Besprechungsbeitritt mithilfe der Verwaltungsshell für Lync Server 2013

1.  Starten Sie die Verwaltungsshell für Lync Server 2013: Klicken Sie auf **Start** , klicken Sie auf **Alle Programme** , klicken Sie auf **Microsoft Lync Server 2013**, und klicken Sie dann auf **Lync Server-Verwaltungsshell**.

2.  Führen Sie das folgende Cmdlet aus, um die Konfigurationseinstellungen des Webdiensts anzuzeigen:
    
        Get-CsWebServiceConfiguration

3.  Führen Sie den folgenden Befehl aus und legen Sie die Parameter je nach Wunsch auf "True" oder "False" fest (ausführliche Informationen zu den Parametern für dieses Cmdlet finden Sie unter [Set-CsWebServiceConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsWebServiceConfiguration) in der Dokumentation zur Verwaltungsshell für Lync Server 2013):
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

## Siehe auch

#### Weitere Ressourcen

[Set-CsWebServiceConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsWebServiceConfiguration)

