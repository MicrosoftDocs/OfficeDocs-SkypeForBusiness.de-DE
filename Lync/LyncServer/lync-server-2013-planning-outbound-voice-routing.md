---
title: 'Lync Server 2013: Planen des VoIP-Routings für ausgehende Anrufe'
TOCTitle: Planen des VoIP-Routings für ausgehende Anrufe
ms:assetid: 37c55fa4-175a-4190-b9e4-c2e5ac7b9261
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425853(v=OCS.15)
ms:contentKeyID: 49293683
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planen des VoIP-Routings für ausgehende Anrufe in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Das Routing ausgehender Anrufe wird auf Anrufe angewendet, die an ein PSTN-Gateway (Public Switched Telephone Network) , einen Trunk oder eine Nebenstellenanlage gerichtet sind. Wenn ein Benutzer einen Anruf tätigt, normalisiert der Server die Rufnummer ggf., indem er diese in das E.164-Format übersetzt und versucht, sie einem SIP-URI zuzuordnen. Ermittelt der Server keine Übereinstimmung, wird die Routinglogik für ausgehende Anrufe basierend auf der bereitgestellten Wählzeichenfolge angewendet. Sie können diese Logik durch Konfigurieren der Servereinstellungen definieren, die in der folgenden Tabelle beschrieben werden.

### Einstellungen für das Routing ausgehender Anrufe in Lync Server

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
<td><p>Ein Wählplan ist ein benannter Satz Normalisierungsregeln, mit deren Hilfe Telefonnummern als Bestandteil der Telefonautorisierung und Anrufweiterleitung für einen benannten Standort, einzelne Benutzer oder Kontaktobjekte in ein einzelnes Standardformat (E.164) übersetzt werden.</p></td>
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


## In diesem Abschnitt

In diesem Abschnitt werden Richtlinien zum Konfigurieren der folgenden Servereinstellungen für das Ausgangsrouting bereitgestellt:

  - [Wählpläne und Normalisierungsregeln in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md)

  - [VoIP-Richtlinien in Lync Server 2013](lync-server-2013-voice-policies.md)

  - [PSTN-Verwendungsdatensätze in Lync Server 2013](lync-server-2013-pstn-usage-records.md)

  - [VoIP-Routen in Lync Server 2013](lync-server-2013-voice-routes.md)

## Siehe auch

#### Konzepte

[SIP-Trunking in Lync Server 2013](lync-server-2013-sip-trunking.md)  
[Direkte SIP-Verbindungen in Lync Server 2013](lync-server-2013-direct-sip-connections.md)

