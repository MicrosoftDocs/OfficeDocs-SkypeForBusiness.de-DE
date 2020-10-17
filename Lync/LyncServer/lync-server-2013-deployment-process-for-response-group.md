---
title: 'Lync Server 2013: Bereitstellungsprozess für Reaktionsgruppen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Response Group
ms:assetid: d390c8a1-dc6e-44d8-b386-2be1fca9877c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205270(v=OCS.15)
ms:contentKeyID: 48185437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54335e8f70753a77f937819f896135ec1fe67b93
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526892"
---
# <a name="deployment-process-for-response-group-in-lync-server-2013"></a>Bereitstellungsprozess für die Reaktionsgruppe in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-27_

Dieser Abschnitt enthält eine Übersicht über die Phasen und Schritte bei der Bereitstellung des Reaktionsgruppenanwendung.

### <a name="response-group-deployment-process"></a>Prozess zur Bereitstellung von Reaktionsgruppen

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Phase</th>
<th>Schritte</th>
<th>Berechtigungen</th>
<th>Bereitstellungsdokumentation</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Installieren des Reaktionsgruppenanwendung</p></td>
<td><p>Das Reaktionsgruppenanwendung wird bei der Bereitstellung von Enterprise-VoIP standardmäßig installiert und aktiviert.</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploying-enterprise-voice.md">Bereitstellen von Enterprise-VoIP in lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Installieren von Komponenten für Reaktionsgruppen</p></td>
<td><p>Lync Server-Cmdlets, das lync Server-Systemsteuerung, das Reaktionsgruppen-Konfigurations Tool, die Anmelde-und Abmelde Konsole des Agents und der Client-Webdienst der Reaktionsgruppe werden als Teil von Webdienste installiert. Webdienste wird installiert, wenn Sie einen Enterprise Edition-Pool oder ein Standard Edition-Server bereitstellen.</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploying-lync-server.md">Bereitstellen von Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Aktivieren von Benutzern für lync 2013 und für Enterprise-VoIP</p></td>
<td><p>Aktivieren Sie Benutzer, die Agents für lync Server und Enterprise-VoIP sein sollen. Benutzer müssen aktiviert sein, bevor Sie Sie zu Agentgruppen hinzufügen können. In der Regel werden Benutzer während der Enterprise Edition-oder Standard Edition-Server-Bereitstellung für lync Server aktiviert. Benutzer sind während der Enterprise-VoIP-Bereitstellung für Enterprise-VoIP aktiviert.</p></td>
<td><p>RTCUniversalUserAdmins</p>
<p>CsUserAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Deaktivieren oder erneutes Aktivieren des Benutzerkontos für lync Server 2013</a></p>
<p><a href="lync-server-2013-enable-users-for-enterprise-voice.md">Aktivieren von Benutzern für Enterprise-VoIP in lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Erstellen und Konfigurieren von Reaktionsgruppen, die aus Agentgruppen, Warteschlangen und Workflows bestehen</p></td>
<td><ol>
<li><p>Verwenden Sie die lync Server-Systemsteuerung oder lync Server-Verwaltungsshell, um Folgendes zu tun:</p>
<ol>
<li><p>Erstellen und Konfigurieren von Agentgruppen</p></li>
<li><p>Erstellen und Konfigurieren von Warteschlangen</p></li>
</ol></li>
<li><p>Verwenden Sie optional lync Server-Verwaltungsshell, um vordefinierte Reaktionsgruppen-Geschäftszeiten und Feiertage zu erstellen.</p></li>
<li><p>Verwenden Sie das Reaktionsgruppen-Konfigurations Tool oder lync Server-Verwaltungsshell, um Workflows (Sammelanschlüsse oder interaktive Sprachantwort-Anruf Flüsse) zu erstellen, einschließlich benutzerdefinierter Reaktionsgruppen-Geschäftszeiten und Feiertage.</p>
<div>

> [!NOTE]  
> Sie können über lync Server-Systemsteuerung auf das Tool für die Reaktionsgruppen Konfiguration zugreifen.


</div></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p>
<p>Rolle csresponsegroupmanager</p></td>
<td><p><a href="lync-server-2013-create-response-group-agent-groups.md">Erstellen von Gruppen für Reaktionsgruppen-Agents lync Server 2013</a></p>
<p><a href="lync-server-2013-create-response-group-queues.md">Erstellen von Warteschlangen für Reaktionsgruppen in lync Server 2013</a></p>
<p><a href="lync-server-2013-optional-define-response-group-business-hours.md">Optional Definieren von Geschäftszeiten für Reaktionsgruppen in lync Server 2013</a></p>
<p><a href="lync-server-2013-optional-define-response-group-holiday-sets.md">Optional Definieren von Feiertagssätzen für Reaktionsgruppen in lync Server 2013</a></p>
<p><a href="lync-server-2013-create-or-modify-a-workflow.md">Erstellen oder Ändern eines Workflows in lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>(Optional) Anpassen der Einstellungen auf Anwendungsebene</p></td>
<td><p>Verwenden Sie lync Server-Verwaltungsshell zum Anpassen der standardmäßigen Music-on-Hold-Konfiguration, der standardmäßigen Music-on-Hold-Audiodatei, der Kulanzfrist für den Agent-Rückruf und der Anrufkontext Konfiguration.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-managing-application-level-response-group-settings.md">Verwalten von Reaktionsgruppeneinstellungen auf Anwendungsebene in lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>(Optional) Delegieren der Verwaltung von Reaktionsgruppen</p></td>
<td><p>Weisen Sie Benutzern die Rolle csresponsegroupmanager-Rolle zu, um die Konfiguration von Reaktionsgruppen zu delegieren. Reaktionsgruppen-Manager können dann die Ihnen zugewiesenen Reaktionsgruppen konfigurieren.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-planning-for-role-based-access-control.md">Planen der rollenbasierten Zugriffssteuerung in lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Überprüfen der Reaktionsgruppenbereitstellung</p></td>
<td><p>Führen Sie Testanrufe bei den Sammelanschlüssen und IVR-Workflows durch, um sicherzustellen, dass die Konfiguration wie erwartet funktioniert.</p></td>
<td><p>-</p></td>
<td><p>-</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

