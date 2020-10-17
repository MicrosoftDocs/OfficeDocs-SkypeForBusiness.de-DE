---
title: 'Lync Server 2013: Planen des ausgehenden VoIP-Routings'
description: 'Lync Server 2013: Planen des ausgehenden VoIP-Routings.'
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
ms.openlocfilehash: 057f81b995e231c2025a9fcb07e675086a662efe
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563981"
---
# <a name="planning-outbound-voice-routing-in-lync-server-2013"></a>Planen der ausgehenden VoIP-Weiterleitung in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-21_

Das Routing ausgehender Anrufe wird auf Anrufe angewendet, die an ein PSTN-Gateway (Public Switched Telephone Network) , einen Trunk oder eine Nebenstellenanlage gerichtet sind. Wenn ein Benutzer einen Anruf tätigt, normalisiert der Server die Rufnummer ggf., indem er diese in das E.164-Format übersetzt und versucht, sie einem SIP-URI zuzuordnen. Ermittelt der Server keine Übereinstimmung, wird die Routinglogik für ausgehende Anrufe basierend auf der bereitgestellten Wählzeichenfolge angewendet. Sie können diese Logik durch Konfigurieren der Servereinstellungen definieren, die in der folgenden Tabelle beschrieben werden.

### <a name="lync-server-outbound-call-routing-settings"></a>Einstellungen für das Routing ausgehender Anrufe in Lync Server

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
<td><p>Wähleinstellungen</p></td>
<td><p>Wähleinstellungen sind benannte Sätze aus Normalisierungsregeln, mit deren Hilfe Telefonnummern als Bestandteil der Telefonautorisierung und Anrufweiterleitung für einen benannten Standort, einzelne Benutzer oder Kontaktobjekte in ein einzelnes Standardformat (E.164) übersetzt werden.</p></td>
</tr>
<tr class="even">
<td><p>Normalisierungsregel</p></td>
<td><p>Normalisierungsregeln definieren das Routing von Rufnummern in unterschiedlichen Formaten für den benannten Standort, Benutzer oder das Kontaktobjekt. Ein und dieselbe Wählzeichenfolge kann je nach Standort, an dem sie gewählt wurde, und je nach Person oder Kontaktobjekt, die bzw. das den Anruf tätigt, unterschiedlich interpretiert und übersetzt werden. Eine Gruppe von Normalisierungsregeln, die einem bestimmten Standort zugeordnet sind, bildet einen Satz mit Wähleinstellungen.</p></td>
</tr>
<tr class="odd">
<td><p>VoIP-Richtlinie</p></td>
<td><p>Eine VoIP-Richtlinie ordnet einem Benutzer oder einer Benutzergruppe mindestens einen PSTN-Verwendungsdatensatz zu. Eine VoIP-Richtlinie stellt darüber hinaus eine Liste der Anruffunktionen bereit, die Sie aktivieren oder deaktivieren können.</p></td>
</tr>
<tr class="even">
<td><p>PSTN-Verwendungsdatensatz</p></td>
<td><p>Ein PSTN-Verwendungsdatensatz gibt eine Anrufklasse (z. B. interne Anrufe, Ortsgespräche oder Ferngespräche) an, die von bestimmten Benutzern oder Benutzergruppen in einer Organisation getätigt werden dürfen.</p></td>
</tr>
<tr class="odd">
<td><p>Anrufroute</p></td>
<td><p>Eine Anrufroute ordnet Zielrufnummern bestimmte Trunks und PSTN-Verwendungseinträge zu. Ein PSTN-Gateway wird als Trunk angesehen.</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a>In diesem Abschnitt

In diesem Abschnitt werden Richtlinien zum Konfigurieren der folgenden Servereinstellungen für das Ausgangsrouting bereitgestellt:

  - <span></span>  
    [Wählpläne und Normalisierungsregeln in lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md)

  - <span></span>  
    [VoIP-Richtlinien in lync Server 2013](lync-server-2013-voice-policies.md)

  - <span></span>  
    [PSTN-Verwendungsdaten Sätze in lync Server 2013](lync-server-2013-pstn-usage-records.md)

  - <span></span>  
    [VoIP-Routen in lync Server 2013](lync-server-2013-voice-routes.md)

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

