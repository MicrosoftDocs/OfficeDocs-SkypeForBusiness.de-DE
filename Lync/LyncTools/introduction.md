---
title: Einführung
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Introduction
ms:assetid: 276395be-93df-4a16-97e2-cb468cd0f2e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945588(v=OCS.15)
ms:contentKeyID: 51541414
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 354f28948578be528787928fd4e0874f6ff8e5fa
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755459"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="introduction"></a>Einführung

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-24_

Das lync Server 2013 Stress and Performance-Tool (als LyncPerfTool bezeichnet) kann die Benutzerlast der folgenden Typen simulieren:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Instant Messaging und Anwesenheit</p></td>
<td><p>Audiokonferenz</p></td>
</tr>
<tr class="even">
<td><p>Anwendungsfreigabe</p></td>
<td><p>VoIP (Voice over IP), einschließlich PSTN-Simulation (Public Switched Telephone Network)</p></td>
</tr>
<tr class="odd">
<td><p>Webzugriffs-Client Konferenzen</p></td>
<td><p>Microsoft lync 2013 Attendant</p></td>
</tr>
<tr class="even">
<td><p>Reaktionsgruppen</p></td>
<td><p>Verteilerlistenerweiterung</p></td>
</tr>
<tr class="odd">
<td><p>Adressbuch Download und Adressbuch Abfrage</p></td>
<td><p>Enhanced 9-1-1 (E9-1-1) Anrufe und Standortprofil (Wählplan)</p></td>
</tr>
<tr class="even">
<td><p>MultiView</p></td>
<td><p>Anzeigen mehrerer Datenströme aus einer Konferenz</p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
</tbody>
</table>


Das Tool für die lync Server 2013 Spannung und Leistung unterstützt die Generierung und den Verbund von Pool Lasten über erweiterte Konfigurationen.

Das Tool simuliert außerdem keine Benutzerlast für die folgenden Clients:

  - Office Live Meeting 2007

  - Lync 2013 beständiger Chat

Daher unterstützt das lync Server 2013 Stress and Performance-Tool nicht das Testen der folgenden Komponenten:

  - Lync 2013 beständiger Chat

  - Exchange-Integrationsszenarien

<div>

## <a name="applications-and-files-included-with-the-lync-server-2013-stress-and-performance-tool"></a>Im lync Server 2013 Stress and Performance Tool enthaltene Anwendungen und Dateien

Die folgenden Anwendungen sind im lync Server 2013 Stress and Performance Tool enthalten:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tool</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>UserProvisioningTool.exe</p></td>
<td><p>Das lync Server 2013 Benutzer ProTools. Dieses Tool wird zum Erstellen von Benutzern und Kontakten verwendet.</p></td>
</tr>
<tr class="even">
<td><p>UserProfileGenerator.exe</p></td>
<td><p>Das lync Server 2013 Lade Konfigurations Tool. Dieses Tool dient zum Konfigurieren der Merkmale der Benutzerlast, die simuliert werden soll.</p></td>
</tr>
<tr class="odd">
<td><p>LyncPerfTool.exe</p></td>
<td><p>Das Tool für die lync Server 2013 Spannung und Leistung. LyncPerfTool ist das Tool, mit dem die Benutzerlast simuliert wird.</p></td>
</tr>
<tr class="even">
<td><p>Standard. TMX</p></td>
<td><p>Standard. TMX ist für die Verwendung des lync Server 2013-Protokollierungstools erforderlich.</p></td>
</tr>
<tr class="odd">
<td><p>Beispielskripts für die Skriptverarbeitung</p></td>
<td><p>Diese Beispiele werden verwendet, um die Topologie für das Durchführen von Auslastungstests basierend auf bestimmten Szenarien zu konfigurieren.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

