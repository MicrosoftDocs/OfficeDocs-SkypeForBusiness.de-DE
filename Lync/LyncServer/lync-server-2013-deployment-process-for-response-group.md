---
title: 'Lync Server 2013: Bereitstellungsprozess für die Reaktionsgruppe'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment process for Response Group
ms:assetid: d390c8a1-dc6e-44d8-b386-2be1fca9877c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205270(v=OCS.15)
ms:contentKeyID: 48185437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2151532b31f3c1660be98d11ac9d9c337ffecb64
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832458"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-response-group-in-lync-server-2013"></a>Bereitstellungsprozess für die Reaktionsgruppe in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-27_

Dieser Abschnitt enthält eine Übersicht über die Phasen und Schritte, die beim Bereitstellen der reaktionsgruppenanwendung erforderlich sind.

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
<td><p>Installieren der reaktionsgruppenanwendung</p></td>
<td><p>Die reaktionsgruppenanwendung wird standardmäßig installiert und aktiviert, wenn Sie Enterprise-VoIP bereitstellen.</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploying-enterprise-voice.md">Bereitstellen von Enterprise-VoIP in lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Komponenten für Reaktionsgruppe installieren</p></td>
<td><p>Lync Server-Cmdlets, die lync Server-Systemsteuerung, das Reaktionsgruppen-Konfigurations Tool, die Anmelde-und Abmelde Konsole des Agents und der Client-Webdienst für Reaktionsgruppen werden als Teil von Webdiensten installiert. Webdienste werden installiert, wenn Sie einen Enterprise Edition-Pool oder einen Standard Edition-Server bereitstellen.</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploying-lync-server.md">Bereitstellen von Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Aktivieren von Benutzern für lync 2013 und für Enterprise-VoIP</p></td>
<td><p>Aktivieren Sie Benutzer, die Agents für lync Server und Enterprise-VoIP sein sollen. Benutzer müssen aktiviert sein, damit sie Agentgruppen hinzugefügt werden können. In der Regel sind Benutzer während der Enterprise Edition-oder Standard Edition-Server Bereitstellung für lync Server aktiviert. Benutzer sind während der Enterprise-VoIP-Bereitstellung für Enterprise-VoIP aktiviert.</p></td>
<td><p>RTCUniversalUserAdmins</p>
<p>CsUserAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Deaktivieren oder erneutes Aktivieren des Benutzerkontos für lync Server 2013</a></p>
<p><a href="lync-server-2013-enable-users-for-enterprise-voice.md">Aktivieren von Benutzern für Enterprise-VoIP in lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Erstellen und Konfigurieren von Reaktionsgruppen, die aus Agentgruppen, Warteschlangen und Workflows bestehen</p></td>
<td><ol>
<li><p>Verwenden Sie die lync Server-Systemsteuerung oder die lync Server-Verwaltungsshell, um folgende Aktionen auszuführen:</p>
<ol>
<li><p>Erstellen und Konfigurieren von Agentgruppen</p></li>
<li><p>Erstellen und Konfigurieren von Warteschlangen</p></li>
</ol></li>
<li><p>Optional können Sie mithilfe der lync Server-Verwaltungsshell vordefinierte Geschäftszeiten und Feiertage in der Reaktionsgruppe erstellen.</p></li>
<li><p>Verwenden Sie das Reaktionsgruppen-Konfigurations Tool oder die lync Server-Verwaltungsshell zum Erstellen von Workflows (Sammelanschlüsse oder IVR-Anruf Bewegungen (Interactive Voice Response), einschließlich benutzerdefinierter Reaktionsgruppen-Geschäftszeiten und-Feiertage.</p>
<div>

> [!NOTE]  
> Sie können über die lync Server-Systemsteuerung auf das Tool für die Reaktionsgruppen Konfiguration zugreifen.


</div></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p>
<p>CsResponseGroupManager</p></td>
<td><p><a href="lync-server-2013-create-response-group-agent-groups.md">Erstellen von Agent-Gruppen für Reaktionsgruppen Lync Server 2013</a></p>
<p><a href="lync-server-2013-create-response-group-queues.md">Erstellen von Warteschleifen für Reaktionsgruppen in Lync Server 2013</a></p>
<p><a href="lync-server-2013-optional-define-response-group-business-hours.md">Optional Definieren der Geschäftszeiten der Reaktionsgruppe in lync Server 2013</a></p>
<p><a href="lync-server-2013-optional-define-response-group-holiday-sets.md">Optional Definieren von Feiertagssätzen für Reaktionsgruppen in lync Server 2013</a></p>
<p><a href="lync-server-2013-create-or-modify-a-workflow.md">Erstellen oder Ändern eines Workflows in lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>(Optional) Anpassen der Einstellungen auf Anwendungsebene</p></td>
<td><p>Verwenden Sie die lync Server-Verwaltungsshell zum Anpassen der standardmäßigen Music-on-halten-Konfiguration, der standardmäßigen Music-on-halten-Audiodatei, des Kulanzzeitraums für den Rückruf des Agenten und der Konfiguration des Anruf Kontexts.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-managing-application-level-response-group-settings.md">Verwalten von Reaktionsgruppeneinstellungen auf Anwendungsebene in lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>(Optional) Delegieren der Verwaltung von Reaktionsgruppen</p></td>
<td><p>Weisen Sie Benutzern die CsResponseGroupManager-Rolle zu, um die Konfiguration von Reaktionsgruppen zu delegieren. Die Antwortgruppen-Manager können dann die Ihnen zugewiesenen Antwortgruppen konfigurieren.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-planning-for-role-based-access-control.md">Planen für die rollenbasierte Zugriffssteuerung in Lync Server 2013</a></p></td>
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

