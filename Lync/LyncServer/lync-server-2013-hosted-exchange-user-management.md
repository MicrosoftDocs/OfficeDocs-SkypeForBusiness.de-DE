---
title: 'Lync Server 2013: Benutzerverwaltung für gehostete Exchange-Dienste'
TOCTitle: Benutzerverwaltung für gehostete Exchange-Dienste
ms:assetid: e8723af5-0604-4d7d-bad2-463a9832efb4
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg399037(v=OCS.15)
ms:contentKeyID: 49295756
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Benutzerverwaltung für gehostete Exchange-Dienste in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Zur Bereitstellung von Voicemaildiensten für Lync Server 2013-Benutzer, deren Postfächer sich in einem gehosteten Exchange-Dienst befinden, müssen Sie die Benutzerkonten für gehostete Voicemail aktivieren.


> [!NOTE]
> Bevor ein Lync Server 2013-Benutzerkonto für gehostete Voicemail aktiviert werden kann, muss eine Richtlinie für gehostete Voicemail bereitgestellt werden, die auf das entsprechende Benutzerkonto angewendet wird. Diese Richtlinie kann auf globaler, Standort- oder Benutzerebene eingerichtet werden, solange sie auf das Benutzerkonto angewendet wird, das Sie aktivieren möchten. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-hosted-voice-mail-policies.md">Richtlinien für gehostete Voicemail in Lync Server 2013</A>.



## Das Attribut "msExchUCVoiceMailSettings"

Lync Server 2013 stellt das neue Benutzerattribut **msExchUCVoiceMailSettings** bereit, das im Rahmen der Active Directory-Schemavorbereitung in Lync Server 2013 erstellt wird. Dieses mehrwertige Attribut enthält Voicemaileinstellungen, die von Lync Server 2013 und dem gehosteten Exchange-Dienst gemeinsam genutzt werden.

Der gehostete Exchange-Dienst kann in einigen Fällen während der Aktivierung von Exchange UM oder während der Übertragung von Postfächern auf einen gehosteten Exchange-Server den Wert des Attributs "msExchUCVoiceMailSettings" festlegen. Wenn das Attribut nicht durch Exchange festgelegt wird, muss der Lync Server 2013-Administrator es mithilfe des Cmdlets "Set-CsUser" festlegen, wie weiter oben in diesem Thema beschrieben.

Die folgende Tabelle zeigt die Schlüssel/Wert-Paare und ihren Ursprung.

### Schlüssel/Wert-Paare des Attributs "msExchUCVoiceMailSettings"

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Wert</th>
<th>Ursprung</th>
<th>Bedeutung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ExchangeHostedVoiceMail=1</p></td>
<td><p>Exchange</p></td>
<td><p>Benutzerkonto wurde durch Exchange Server für den Zugriff auf den gehosteten UM-Dienst aktiviert. Die Exchange UM-Routinganwendung sucht in der Richtlinie für gehostete Voicemail des Benutzers nach Routinginformationen.</p></td>
</tr>
<tr class="even">
<td><p>ExchangeHostedVoiceMail=0</p></td>
<td><p>Exchange</p></td>
<td><p>Benutzerkonto wurde durch Exchange Server für den Zugriff auf den gehosteten UM-Dienst deaktiviert.</p></td>
</tr>
<tr class="odd">
<td><p>CsHostedVoiceMail=1</p></td>
<td><p>Lync Server</p></td>
<td><p>Benutzerkonto wurde durch Lync Server 2013 für den Zugriff auf den gehosteten UM-Dienst aktiviert. Die Lync Server 2013 ExUM-Routinganwendung sucht in der Richtlinie für gehostete Voicemail des Benutzers nach Routinginformationen.</p></td>
</tr>
<tr class="even">
<td><p>CsHostedVoiceMail=0</p></td>
<td><p>Lync Server</p></td>
<td><p>Benutzerkonto wurde durch Lync Server 2013 für den Zugriff auf den gehosteten UM-Dienst deaktiviert.</p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> Wenn das Attribut bereits andere Werte als eines der Lync Server 2013-Schlüssel/Wert-Paare (CSHostedVoiceMail=0 oder CSHostedVoiceMail=1) enthält, weist eine Warnung darauf hin, dass das Attribut möglicherweise durch eine andere Anwendung verwaltet wird. Beispielsweise wird eine Warnung angezeigt, wenn das Schlüssel/Wert-Paar ExchangeHostedVoiceMail=0 oder ExchangeHostedVoiceMail=1 bereits vorhanden ist. In diesem Fall können Sie den Wert in Active Directory bearbeiten oder mit dem folgenden Cmdlet auf "null" setzen:<BR>Set-CsUser -identity user -HostedVoicemail $null



## Aktivieren von Benutzerkonten für gehostete Voicemail

Damit die Voicemailanrufe eines Benutzers zum gehosteten Exchange UM-Dienst geroutet werden können, müssen Sie mit dem Cmdlet "Set-CsUser" den Wert des Parameters *HostedVoiceMail* festlegen. Dieser Parameter weist Lync Server 2013 auch an, die Anzeige "Voicemail anrufen" zu aktivieren.

  - Im folgenden Beispiel wird das Benutzerkonto von Pilar Ackerman für gehostete Voicemail aktiviert:
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $True
    
    Das Cmdlet stellt sicher, dass auf diesen Benutzer eine Richtlinie für gehostete Voicemail (auf globaler, Standort- oder Benutzerebene) angewendet wird. Wenn keine Richtlinie angewendet werden kann, tritt bei der Ausführung des Cmdlets ein Fehler auf.

  - Im folgenden Beispiel wird das Benutzerkonto von Pilar Ackerman für gehostete Voicemail deaktiviert:
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $False
    
    Das Cmdlet stellt sicher, dass für diesen Benutzer keine Richtlinie für gehostete Voicemail (auf globaler, Standort- oder Benutzerebene) angewendet wird. Wenn eine Richtlinie angewendet wird, tritt bei der Ausführung des Cmdlets ein Fehler auf.

Ausführliche Informationen zur Verwendung des Cmdlets "Set-CsUser" finden Sie in der Dokumentation zur Lync Server-Verwaltungsshell.

