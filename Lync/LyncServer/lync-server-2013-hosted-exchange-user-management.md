---
title: 'Lync Server 2013: Benutzerverwaltung für gehostete Exchange-Dienste'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange user management
ms:assetid: e8723af5-0604-4d7d-bad2-463a9832efb4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399037(v=OCS.15)
ms:contentKeyID: 48185887
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 23289399e4eee4a654b41f2978191a6329739b4e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738985"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-user-management-in-lync-server-2013"></a>Benutzerverwaltung für gehostete Exchange-Dienste in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-18_

Wenn Sie Voicemail-Dienste für lync Server 2013-Benutzer bereitstellen möchten, deren Postfächer sich in einem gehosteten Exchange-Dienst befinden, müssen Sie deren Benutzerkonten für gehostete Voicemail aktivieren.

<div>


> [!NOTE]  
> Bevor ein lync Server 2013-Benutzer für gehostete Voicemail aktiviert werden kann, muss eine gehostete Voicemail-Richtlinie bereitgestellt werden, die für das entsprechende Benutzerkonto gilt. Die Richtlinie kann global, Site oder pro Benutzer im Umfang sein, sofern Sie für den Benutzer gilt, den Sie aktivieren möchten. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-hosted-voice-mail-policies.md">Richtlinien für gehostete Voicemail in lync Server 2013</A>.



</div>

<div>

## <a name="the-msexchucvoicemailsettings-attribute"></a>Das msExchUCVoiceMailSettings-Attribut

Lync Server 2013 führt ein neues Benutzerattribut mit dem Namen **msExchUCVoiceMailSettings**ein, das im Rahmen der Active Directory-Schemavorbereitung von lync Server 2013 erstellt wird. Dieses mehrwertige Attribut enthält Einstellungen für Voicemail, die von lync Server 2013 und dem gehosteten Exchange-Dienst freigegeben werden.

Der gehostete Exchange-Dienst kann in einigen Fällen den Wert des Attributs msExchUCVoiceMailSettings beim Aktivieren von Exchange um oder während des Prozesses der Übertragung von Postfächern auf einen gehosteten Exchange-Server einstellen. Wenn dieses Attribut nicht von Exchange gesetzt wird, muss der lync Server 2013-Administrator es durch Ausführen des Cmdlets "CsUser", wie weiter oben in diesem Thema beschrieben, einrichten.

Die Schlüssel-Wert-Paare des Attributs und deren Autoren sind in der folgenden Tabelle dargestellt.

### <a name="the-msexchucvoicemailsettings-attribute-keyvalue-pairs"></a>Schlüssel-Wert-Paare des msExchUCVoiceMailSettings-Attributs

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Wert</th>
<th>Autor</th>
<th>Bedeutung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ExchangeHostedVoiceMail = 1</p></td>
<td><p>Exchange</p></td>
<td><p>Der Benutzer wurde für den gehosteten um-Zugriff durch Exchange Server aktiviert. Die Exchange um-Routing Anwendung überprüft die Richtlinie des Benutzers für gehostete Voicemail auf Routing Details.</p></td>
</tr>
<tr class="even">
<td><p>ExchangeHostedVoiceMail = 0</p></td>
<td><p>Exchange</p></td>
<td><p>Der Benutzer wurde für den gehosteten um-Zugriff durch Exchange Server deaktiviert.</p></td>
</tr>
<tr class="odd">
<td><p>CsHostedVoiceMail = 1</p></td>
<td><p>Lync Server</p></td>
<td><p>Der Benutzer wurde für den gehosteten um-Zugriff von lync Server 2013 aktiviert. Die lync Server 2013 ExUM-Routing Anwendung überprüft die Richtlinie des Benutzers für gehostete Voicemail auf Routing Details.</p></td>
</tr>
<tr class="even">
<td><p>CsHostedVoiceMail = 0</p></td>
<td><p>Lync Server</p></td>
<td><p>Der Benutzer wurde für den gehosteten um-Zugriff von lync Server 2013 deaktiviert.</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Wenn das Attribut bereits Werte enthält, die nicht zu den Schlüssel-Wert-Paaren von lync Server 2013 (CSHostedVoiceMail = 0 oder CSHostedVoiceMail = 1) führen, wird eine Warnung angezeigt, die besagt, dass das Attribut von einer anderen Anwendung verwaltet werden kann. Beispielsweise wird eine Warnung angezeigt, wenn das Schlüssel-Wert-Paar ExchangeHostedVoiceMail = 0 oder ExchangeHostedVoiceMail = 1 bereits vorhanden ist. In diesem Fall können Sie den Wert ändern, indem Sie ihn in Active Directory bearbeiten, oder führen Sie das folgende Cmdlet aus, um den Wert auf NULL festzulegen:<BR>Satz-CsUser – Identity User – HostedVoicemail $NULL



</div>

</div>

<div>

## <a name="enabling-users-for-hosted-voice-mail"></a>Aktivieren von Benutzern für gehostete Voicemails

Damit die Voicemail-Anrufe eines Benutzers an den Hosted Exchange um weitergeleitet werden können, müssen Sie das Cmdlet "setCsUser" ausführen, um den Wert des *HostedVoiceMail* -Parameters festzulegen. Dieser Parameter signalisiert auch, dass lync Server 2013 den Indikator "Voicemail anrufen" aufleuchtet.

  - Im folgenden Beispiel wird das Benutzerkonto von Pilar Ackerman für gehostete Voicemail aktiviert:
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $True
    
    Das Cmdlet überprüft, ob eine gehostete Voicemail-Richtlinie (Global, Websiteebene oder pro Benutzer) für diesen Benutzer gilt. Wenn keine Richtlinie zutrifft, schlägt das Cmdlet fehl.

  - Im folgenden Beispiel wird das Benutzerkonto von Pilar Ackerman für gehostete Voicemail deaktiviert:
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $False
    
    Das Cmdlet überprüft, ob für diesen Benutzer keine gehostete Voicemail-Richtlinie (Global, Website-Ebene oder pro Benutzer) gilt. Wenn eine Richtlinie angewendet wird, schlägt das Cmdlet fehl.

Ausführliche Informationen zur Verwendung des Cmdlets "CsUser" finden Sie in der Dokumentation zur lync Server-Verwaltungsshell.

</div>

</div>

<span> </span>

</div>

</div>

</div>

