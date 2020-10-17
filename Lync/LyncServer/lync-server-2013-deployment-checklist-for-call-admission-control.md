---
title: 'Lync Server 2013: Prüfliste für die Bereitstellung der Anrufsteuerung'
description: 'Lync Server 2013: Prüfliste für die Bereitstellung der Anrufsteuerung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for call admission control
ms:assetid: 7e56a169-3e63-44ab-bf28-1fdeb52381c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398631(v=OCS.15)
ms:contentKeyID: 48184621
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea5b16d41228faf01637e7e0d78f5ce56f950a19
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557691"
---
# <a name="deployment-checklist-for-call-admission-control-in-lync-server-2013"></a>Prüfliste für die Bereitstellung der Anrufsteuerung in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-08_

Für eine effektive Planung der Anrufsteuerung müssen die folgenden Aspekte berücksichtigt werden:

  - Voraussetzungen für die Bereitstellung der Anrufsteuerung

  - Erforderliche Informationen für die Anrufsteuerung und erforderliche Entscheidungen zur Konfiguration, bevor Sie mit der Bereitstellung beginnen.

<div>

## <a name="deployment-prerequisites-for-call-admission-control"></a>Voraussetzungen für die Bereitstellung der Anrufsteuerung

Bevor Sie die Anrufsteuerung bereitstellen, müssen Sie Ihre lync Server 2013 internen Server bereits bereitgestellt haben, einschließlich einer Front-End-Pool oder einer Standard Edition-Server.

</div>

<div>

## <a name="information-requirements-for-call-admission-control"></a>Erforderliche Informationen für die Anrufsteuerung

In der folgenden Tabelle sind die erforderlichen Informationen für die Bereitstellung der Anrufsteuerung zusammengefasst.

### <a name="information-requirements-for-call-admission-control-deployment"></a>Erforderliche Informationen für die Bereitstellung der Anrufsteuerung

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Informationen</th>
<th>Zusammenfassung der erforderlichen Informationen</th>
<th>Dokumentation</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server von Ihrer Organisation benötigten Funktionen</p></td>
<td><ul>
<li><p>Funktionen, die von Ihrer Organisation unterstützt werden sollen</p></li>
<li><p>Funktionen, die für einzelne Benutzer aktiviert werden sollen</p></li>
</ul></td>
<td><p><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Definieren der Anforderungen für die Anrufsteuerung in lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Topologien und Komponenten, die bereitgestellt werden sollen</p></td>
<td><ul>
<li><p>Zugehörige Komponenten im Zusammenhang mit der Anrufsteuerung werden automatisch im Rahmen von lync Server 2013 installiert</p></li>
</ul></td>
<td><p><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Definieren der Anforderungen für die Anrufsteuerung in lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Systemanforderungen</p></td>
<td><ul>
<li><p>Hardwareanforderungen</p></li>
<li><p>Softwareanforderungen</p></li>
<li><p>Anforderungen für die gemeinsame Ausführung</p></li>
</ul></td>
<td><p><a href="lync-server-2013-determining-your-system-requirements.md">Bestimmen der Systemanforderungen für lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Infrastrukturanforderungen</p></td>
<td><ul>
<li><p>Für die Anrufsteuerung liegen keine besonderen Infrastrukturanforderungen vor</p></li>
</ul></td>
<td><p><a href="lync-server-2013-infrastructure-requirements-for-call-admission-control.md">Infrastrukturanforderungen für die Anrufsteuerung in lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Netzwerkschnittstellenanforderungen</p></td>
<td><ul>
<li><p>Informationen zu internen und externen Schnittstellen</p></li>
<li><p>Routing Informationen (einschließlich Informationen im NextHop-Blog unter <a href="https://go.microsoft.com/fwlink/p/?linkid=203149">https://go.microsoft.com/fwlink/p/?LinkId=203149</a> , Microsoft lync Server Team Kundenantwort Kanal)</p></li>
</ul></td>
<td><p><a href="lync-server-2013-deploying-external-user-access.md">Bereitstellen von externem Benutzer Zugriff in lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Bereitstellungsstrategie</p></td>
<td><ul>
<li><p>Bereitstellungsreihenfolge</p></li>
<li><p>Arbeitsgruppe oder Domäne</p></li>
<li><p>Sicherheit</p></li>
<li><p>Überwachung und Prüfung</p></li>
<li><p>Überlegungen zur Hardware</p></li>
</ul></td>
<td><p><a href="lync-server-2013-best-practices-for-call-admission-control.md">Bewährte Methoden für die Anrufsteuerung in lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Bereitstellungsprozess</p></td>
<td><ul>
<li><p>Voraussetzungen</p></li>
<li><p>Erforderliche Informationen</p></li>
<li><p>Prozess und Verfahren</p></li>
</ul></td>
<td><p><a href="lync-server-2013-configure-call-admission-control.md">Konfigurieren der Anrufsteuerung in lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

