---
title: 'Lync Server 2013: Prüfliste für die Bereitstellung der Anrufsteuerung'
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
ms.openlocfilehash: 0bf88529734530e70c4d0536d5337395ff0742d2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740745"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-call-admission-control-in-lync-server-2013"></a>Prüfliste für die Bereitstellung der Anrufsteuerung in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-08_

Damit Sie effektiv für die Anrufsteuerung (CAC) planen können, müssen Sie Folgendes in Frage stellen:

  - Voraussetzungen für die Bereitstellung von CAC.

  - Informationen, die für CAC-und Konfigurationsentscheidungen erforderlich sind, die Sie im Vorfeld der Bereitstellung vornehmen müssen.

<div>

## <a name="deployment-prerequisites-for-call-admission-control"></a>Voraussetzungen für die Bereitstellung der Anrufsteuerung

Bevor Sie die Anrufsteuerung bereitstellen, müssen Sie Ihre lync Server 2013-internen Server bereits bereitgestellt haben, einschließlich eines Front-End-Pools oder eines Standard Edition-Servers.

</div>

<div>

## <a name="information-requirements-for-call-admission-control"></a>Informationsanforderungen für die Anrufsteuerung

In der folgenden Tabelle sind die erforderlichen Informationen für die Bereitstellung der Anrufsteuerung zusammengefasst.

### <a name="information-requirements-for-call-admission-control-deployment"></a>Informationsanforderungen für die Bereitstellung von Anruf Zulassungs Steuerungen

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
<td><p>Für Ihre Organisation erforderliche lync Server-Funktionen</p></td>
<td><ul>
<li><p>Von Ihrer Organisation unterstützte Funktionen</p></li>
<li><p>Funktionen, die für einzelne Benutzer aktiviert werden können</p></li>
</ul></td>
<td><p><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Definieren der Anforderungen Ihrer Organisation für die Anrufsteuerung in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Topologien und Komponenten, die bereitgestellt werden sollen</p></td>
<td><ul>
<li><p>Mit CAC verknüpfte Komponenten werden automatisch als Teil von lync Server 2013 installiert</p></li>
</ul></td>
<td><p><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Definieren der Anforderungen Ihrer Organisation für die Anrufsteuerung in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Systemanforderungen</p></td>
<td><ul>
<li><p>Hardwareanforderungen</p></li>
<li><p>Softwareanforderungen</p></li>
<li><p>Anforderungen für die Übersetzung</p></li>
</ul></td>
<td><p><a href="lync-server-2013-determining-your-system-requirements.md">Ermitteln Ihrer Systemanforderungen für Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Infrastrukturanforderungen</p></td>
<td><ul>
<li><p>Für CAC sind keine spezifischen Infrastrukturanforderungen erforderlich</p></li>
</ul></td>
<td><p><a href="lync-server-2013-infrastructure-requirements-for-call-admission-control.md">Infrastrukturanforderungen für die Anrufsteuerung in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Netzwerkschnittstellen Anforderungen</p></td>
<td><ul>
<li><p>Interne und externe Schnittstelleninformationen</p></li>
<li><p>Routing Informationen (einschließlich Informationen im NextHop-Blog unter <a href="http://go.microsoft.com/fwlink/p/?linkid=203149">http://go.microsoft.com/fwlink/p/?LinkId=203149</a>dem Kundenantwort Kanal des Microsoft lync Server-Teams)</p></li>
</ul></td>
<td><p><a href="lync-server-2013-deploying-external-user-access.md">Bereitstellen des Zugriffs durch externe Benutzer in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Bereitstellungsstrategie</p></td>
<td><ul>
<li><p>Bereitstellungssequenz</p></li>
<li><p>Arbeitsgruppe oder Domäne</p></li>
<li><p>Sicherheit</p></li>
<li><p>Überwachen und überwachen</p></li>
<li><p>Hardware Überlegungen</p></li>
</ul></td>
<td><p><a href="lync-server-2013-best-practices-for-call-admission-control.md">Bewährte Methoden für die Anrufsteuerung in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Bereitstellungsprozess</p></td>
<td><ul>
<li><p>Voraussetzungen</p></li>
<li><p>Informationsanforderungen</p></li>
<li><p>Verfahren und Verfahren</p></li>
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

