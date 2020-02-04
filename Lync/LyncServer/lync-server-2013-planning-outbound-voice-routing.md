---
title: 'Lync Server 2013: Planen des VoIP-Routings für ausgehende Anrufe'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning outbound voice routing
ms:assetid: 37c55fa4-175a-4190-b9e4-c2e5ac7b9261
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425853(v=OCS.15)
ms:contentKeyID: 48183835
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d33fbe8d15b78bed9dd651cd7facf35a8249f64
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747665"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-outbound-voice-routing-in-lync-server-2013"></a>Planen des VoIP-Routings für ausgehende Anrufe in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

Das Routing für ausgehende Anrufe bezieht sich auf Anrufe, die für ein öffentliches Switched Telephone Network (PSTN) Gateway, trunk oder Private Branch Exchange (PBX) bestimmt sind. Wenn ein Benutzer einen Anruf eingibt, normalisiert der Server die Telefonnummer bei Bedarf in das E. 164-Format und versucht, ihn mit einem SIP-URI zu vergleichen. Ermittelt der Server keine Übereinstimmung, wird die Routinglogik für ausgehende Anrufe basierend auf der bereitgestellten Wählzeichenfolge angewendet. Sie können diese Logik durch Konfigurieren der Servereinstellungen definieren, die in der folgenden Tabelle beschrieben sind.

### <a name="lync-server-outbound-call-routing-settings"></a>Ausgehende Anruf Routing Einstellungen für lync Server

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Objekt</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Wählplan</p></td>
<td><p>Ein Wählplan ist ein benannter Satz von Normalisierungsregeln, mit deren Hilfe Telefonnummern als Bestandteil der Telefonautorisierung und Anrufweiterleitung für einen benannten Standort, für einzelne Benutzer oder für Kontaktobjekte in ein einzelnes Standardformat (E.164) übersetzt werden.</p></td>
</tr>
<tr class="even">
<td><p>Normalisierungsregel</p></td>
<td><p>Normalisierungsregeln definieren das Routing von Rufnummern in unterschiedlichen Formaten für benannte Standorte, Benutzer oder Kontaktobjekte. Ein und dieselbe Wählzeichenfolge kann je nach dem Standort, an dem sie gewählt wurde, und je nach der anrufenden Person bzw. dem anrufenden Kontaktobjekt unterschiedlich interpretiert und übersetzt werden. Eine Gruppe von Normalisierungsregeln, die einem bestimmten Standort zugeordnet sind, bildet einen Wählplan.</p></td>
</tr>
<tr class="odd">
<td><p>VoIP-Richtlinie</p></td>
<td><p>Eine VoIP-Richtlinie ordnet einem Benutzer oder einer Benutzergruppe mindestens einen PSTN-Verwendungseintrag zu. Außerdem enthält eine VoIP-Richtlinie immer eine Liste der Anruffunktionen, die Sie aktivieren oder deaktivieren können.</p></td>
</tr>
<tr class="even">
<td><p>PSTN-Verwendungseintrag</p></td>
<td><p>Ein PSTN-Verwendungseintrag gibt eine Klasse von Anrufen an (z. B. interne Anrufe, Ortsgespräche oder Ferngespräche), die von bestimmten Benutzern oder Benutzergruppen in einer Organisation getätigt werden dürfen.</p></td>
</tr>
<tr class="odd">
<td><p>Anrufroute</p></td>
<td><p>Eine Anrufroute ordnet Zielrufnummern bestimmte Trunks und PSTN-Verwendungseinträge zu. Ein PSTN-Gateway wird als Trunk angesehen.</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a>In diesem Abschnitt

In diesem Abschnitt finden Sie Richtlinien für die Konfiguration der folgenden Routingserver Einstellungen für ausgehende Anrufe:

  - <span></span>  
    [Wählpläne und Normalisierungsregeln in lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md)

  - <span></span>  
    [VoIP-Richtlinien in Lync Server 2013](lync-server-2013-voice-policies.md)

  - <span></span>  
    [PSTN-Verwendungsdatensätze in Lync Server 2013](lync-server-2013-pstn-usage-records.md)

  - <span></span>  
    [VoIP-Routen in Lync Server 2013](lync-server-2013-voice-routes.md)

</div>

<div>

## <a name="see-also"></a>Siehe auch


[SIP-Trunking in lync Server 2013](lync-server-2013-sip-trunking.md)  
[Direkte SIP-Verbindungen in lync Server 2013](lync-server-2013-direct-sip-connections.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

