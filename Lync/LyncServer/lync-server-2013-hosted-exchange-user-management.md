---
title: 'Lync Server 2013: Hosted Exchange User Management'
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
ms.openlocfilehash: 16b2716bee52902f55160e770df36801d18f1b78
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043247"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-user-management-in-lync-server-2013"></a>Gehostete Exchange-Benutzerverwaltung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-18_

Um Voicemail-Dienste für lync Server 2013 Benutzer bereitzustellen, deren Postfächer sich in einem gehosteten Exchange-Dienst befinden, müssen Sie Ihre Benutzerkonten für gehostete Voicemail aktivieren.

<div>


> [!NOTE]  
> Bevor ein lync Server 2013-Benutzer für gehostete Voicemail aktiviert werden kann, muss eine Richtlinie für gehostete Voicemail, die für das entsprechende Benutzerkonto gilt, bereitgestellt werden. Die Richtlinie kann global, Standort oder benutzerbezogen sein, solange Sie auf den Benutzer angewendet wird, den Sie aktivieren möchten. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted Voice Mail Policies in lync Server 2013</A>.



</div>

<div>

## <a name="the-msexchucvoicemailsettings-attribute"></a>Das "msexchucvoicemailsettings"-Attribut

Lync Server 2013 stellt ein neues Benutzerattribut namens **"msexchucvoicemailsettings"** vor, das im Rahmen der Vorbereitung des lync Server 2013 Active Directory Schemas erstellt wird. Dieses mehrwertige Attribut umfasst Voicemaileinstellungen, die von lync Server 2013 und dem gehosteten Exchange-Dienst gemeinsam verwendet werden.

Der gehostete Exchange-Dienst kann in einigen Fällen den Wert des "msexchucvoicemailsettings"-Attributs bei der Aktivierung von Exchange um oder beim Übertragen von Postfächern in einen gehosteten Exchange Server festlegen. Wenn dieses Attribut nicht von Exchange festgelegt wird, muss der lync Server 2013 Administrator es durch Ausführen des Cmdlets "CsUser" festlegen, wie weiter oben in diesem Thema beschrieben.

Die Schlüssel-Wert-Paare des Attributs und deren Autoren sind in der folgenden Tabelle dargestellt.

### <a name="the-msexchucvoicemailsettings-attribute-keyvalue-pairs"></a>Schlüssel-Wert-Paare des "msexchucvoicemailsettings"-Attributs

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
<td><p>ExchangeHostedVoiceMail = 1</p></td>
<td><p>Exchange</p></td>
<td><p>Der Benutzer wurde für den gehosteten um-Zugriff über Exchange Server aktiviert. Die Exchange um Routing Anwendung prüft die Richtlinie für gehostete Voicemail des Benutzers auf Routing Details.</p></td>
</tr>
<tr class="even">
<td><p>ExchangeHostedVoiceMail = 0</p></td>
<td><p>Exchange</p></td>
<td><p>Der Benutzer wurde für den gehosteten um-Zugriff mit Exchange Server deaktiviert.</p></td>
</tr>
<tr class="odd">
<td><p>CsHostedVoiceMail = 1</p></td>
<td><p>Lync Server</p></td>
<td><p>Der Benutzer wurde für den gehosteten um-Zugriff über lync Server 2013 aktiviert. Die lync Server 2013 ExUM-Routing Anwendung prüft die Richtlinie für gehostete Voicemail des Benutzers auf Routing Details.</p></td>
</tr>
<tr class="even">
<td><p>CsHostedVoiceMail = 0</p></td>
<td><p>Lync Server</p></td>
<td><p>Der Benutzer wurde für den gehosteten um-Zugriff mit lync Server 2013 deaktiviert.</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Wenn das Attribut bereits Werte enthält, die nicht zu den lync Server 2013 Schlüssel/Wert-Paaren (CSHostedVoiceMail = 0 oder CSHostedVoiceMail = 1), wird eine Warnung angezeigt, dass das Attribut von einer anderen Anwendung verwaltet werden kann. Beispielsweise wird eine Warnung angezeigt, wenn das Schlüssel/Wert-Paar ExchangeHostedVoiceMail = 0 oder ExchangeHostedVoiceMail = 1 bereits vorhanden ist. In diesem Fall können Sie den Wert ändern, indem Sie ihn im Active Directory bearbeiten oder das folgende Cmdlet ausführen, um den Wert auf NULL festzulegen:<BR>Gruppe-CsUser – Identity User – HostedVoicemail $NULL



</div>

</div>

<div>

## <a name="enabling-users-for-hosted-voice-mail"></a>Aktivieren von Benutzern für gehostete Voicemail

Um zu ermöglichen, dass die Voicemail-Anrufe eines Benutzers an gehostete Exchange um weitergeleitet werden, müssen Sie das Cmdlet "Cmdlet festlegen" ausführen, um den Wert des *HostedVoiceMail* -Parameters festzulegen. Dieser Parameter signalisiert auch lync Server 2013, das Symbol "Voicemail anrufen" aufzuhellen.

  - Im folgenden Beispiel wird das Benutzerkonto von Pilar Ackerman für gehostete Voicemail aktiviert:
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $True
    
    Das Cmdlet überprüft, ob eine Richtlinie für gehostete Voicemail (Global, Websiteebene oder pro Benutzer) auf diesen Benutzer angewendet wird. Wenn keine Richtlinie angewendet wird, schlägt das Cmdlet fehl.

  - Im folgenden Beispiel wird das Benutzerkonto von Pilar Ackerman für gehostete Voicemail deaktiviert:
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $False
    
    Das Cmdlet überprüft, ob für diesen Benutzer keine Richtlinie für gehostete Voicemails (Global, Websiteebene oder pro Benutzer) gilt. Wenn eine Richtlinie angewendet wird, schlägt das Cmdlet fehl.

Ausführliche Informationen zur Verwendung des Cmdlets "CsUser" finden Sie in der lync Server-Verwaltungsshell Dokumentation.

</div>

</div>

<span> </span>

</div>

</div>

</div>

