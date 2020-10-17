---
title: 'Lync Server 2013: PSTN-Verwendungsdaten Sätze'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN usage records
ms:assetid: b5f624aa-abe8-455b-a8e3-c228be230463
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412878(v=OCS.15)
ms:contentKeyID: 48185188
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 74c9f6dda4112325d6a408cc1bbb543373e9de61
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512432"
---
# <a name="pstn-usage-records-in-lync-server-2013"></a>PSTN-Verwendungsdaten Sätze in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-23_

Die Planung von PSTN-Verwendungsdatensätzen besteht hauptsächlich darin, alle Anrufberechtigungen aufzulisten, die aktuell in Ihrer Organisation vorhanden sind, vom Firmenchef bis hin zu Personen mit befristeten Arbeitsverträgen, Beratern und Zeitarbeitern. Dieses Verfahren bietet außerdem die Gelegenheit, vorhandene Berechtigungen neu zu überprüfen und sie zu überarbeiten. Sie können PSTN-Verwendungsdatensätze ausschließlich für Berechtigungen erstellen, die sich auf Ihre vorgesehenen Enterprise-VoIP-Benutzer beziehen. Langfristig besteht eine bessere Lösung möglicherweise darin, PSTN-Verwendungsdatensätze einfach für alle Berechtigungen zu erstellen, und zwar unabhängig davon, ob einige davon derzeit nicht für die Gruppe der Benutzer gelten, für die Enterprise-VoIP aktiviert werden soll. Wenn Anrufberechtigungen geändert oder neue Benutzer mit abweichenden Abrufberechtigungen hinzugefügt werden, haben Sie die erforderlichen PSTN-Verwendungsdatensätze bereits erstellt.

Die folgende Tabelle stellt eine typische PSTN-Verwendungstabelle dar.

### <a name="pstn-usage-records"></a>PSTN-Verwendungsdatensätze

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Telefonattribut</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lokal</p></td>
<td><p>Ortsgespräche</p></td>
</tr>
<tr class="even">
<td><p>Long-Distance</p></td>
<td><p>Ferngespräche</p></td>
</tr>
<tr class="odd">
<td><p>International</p></td>
<td><p>Auslandsgespräche</p></td>
</tr>
<tr class="even">
<td><p>Delhi</p></td>
<td><p>Vollzeitmitarbeiter in Delhi</p></td>
</tr>
<tr class="odd">
<td><p>Redmond</p></td>
<td><p>Vollzeitmitarbeiter in Redmond</p></td>
</tr>
<tr class="even">
<td><p>RedmondTemps</p></td>
<td><p>Zeitarbeiter in Redmond</p></td>
</tr>
<tr class="odd">
<td><p>Zürich</p></td>
<td><p>Vollzeitmitarbeiter in Zürich</p></td>
</tr>
</tbody>
</table>


PSTN-Verwendungsdatensätze alleine führen keine Aktionen aus. Um sie verwenden zu können, müssen Sie sie mit Folgendem verknüpfen:

  - VoIP-Richtlinien, die Benutzern zugewiesen sind

  - Routen, die Rufnummern zugewiesen sind

Ausführliche Informationen zu VoIP-Richtlinien und-Routen finden Sie unter [VoIP-Richtlinien in lync Server 2013](lync-server-2013-voice-policies.md) und [VoIP-Routen in lync Server 2013](lync-server-2013-voice-routes.md). Ausführliche Informationen zum Erstellen und Konfigurieren dieser Informationen finden Sie unter [Konfigurieren von VoIP-Routen für ausgehende Anrufe in lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).

</div>

<span> </span>

</div>

</div>

</div>

