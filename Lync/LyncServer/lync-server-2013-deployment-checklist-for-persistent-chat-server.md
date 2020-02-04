---
title: 'Lync Server 2013: Prüfliste zur Bereitstellung für den Server für beständigen Chat'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for Persistent Chat Server
ms:assetid: b1108f8f-88a2-4660-8086-d25ba76f7239
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412851(v=OCS.15)
ms:contentKeyID: 48185155
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d80122534739d443dedaeeb203ab09da94cb0067
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762703"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-persistent-chat-server-in-lync-server-2013"></a>Prüfliste zur Bereitstellung für den Server für beständigen Chat in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-16_

Bereitstellung von lync Server 2013 erfordert der beständige Chat Server, dass Sie ihn in der richtigen Reihenfolge bereitstellen und alle erforderlichen Bereitstellungsschritte ausführen.

<div>

## <a name="deployment-sequence"></a>Bereitstellungssequenz

Sie können beständigen Chat Server bereitstellen, nachdem Sie Ihre anfängliche Topologie bereitgestellt haben, einschließlich mindestens eines lync Server 2013, Front-End-Pools oder eines lync Server 2013, Standard Edition-Servers. In diesem Thema wird beschrieben, wie Sie den Server für beständigen Chat bereitstellen, indem Sie ihn einer vorhandenen Bereitstellung hinzufügen.

</div>

<div>

## <a name="deployment-process"></a>Bereitstellungsprozess

In der folgenden Tabelle sind die grundlegenden Schritte zum Bereitstellen des beständigen Chat Servers sowie Links für weitere Details aufgelistet.

### <a name="persistent-chat-server-deployment-process"></a>Bereitstellungsprozess für beständigen Chat Server

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Aufgabe</th>
<th>Schritte</th>
<th>Erforderliche Rollen und Gruppenmitgliedschaften</th>
<th>Verwandte Themen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Installieren der erforderlichen Hardware und Software</strong></p></td>
<td><p>Installieren Sie die folgenden Komponenten auf einem Hardwaresystem, das die Systemanforderungen erfüllt:</p>
<ul>
<li><p>Auf den beständigen Chat Server-Front-End-Servern:</p></li>
</ul>
<ul>
<li><p>Ein Betriebssystem, das die Systemanforderungen erfüllt</p></li>
<li><p>Software Voraussetzungen für Computer mit lync Server 2013</p></li>
<li><p>SQL Server auf dem Server, auf dem die persistente Chat Server-Datenbank gehostet wird</p></li>
</ul>
<p>Wenn die beständige Chat Server-Kompatibilität erforderlich ist:</p>
<ul>
<li><p>SQL Server auf dem Server, auf dem die Compliance-Datenbank des beständigen Chat Servers gehostet wird</p></li>
</ul></td>
<td><p>Jeder Benutzer, der Mitglied der lokalen Gruppe „Administratoren“ ist.</p></td>
<td><p><a href="lync-server-2013-supported-hardware.md">Unterstützte Hardware für lync Server 2013</a> in der Dokumentation zur Unterstützung</p>
<p><a href="lync-server-2013-server-software-and-infrastructure-support.md">Unterstützung für Server Software und-Infrastruktur in lync Server 2013</a> in der Dokumentation zur Unterstützung</p>
<p><a href="lync-server-2013-determining-your-system-requirements.md">Ermitteln Ihrer Systemanforderungen für Lync Server 2013</a></p>
<p><a href="lync-server-2013-technical-requirements-for-persistent-chat-server.md">Technische Anforderungen für den Server für beständigen Chat in lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><strong>Erstellen der geeigneten internen Topologie zur Unterstützung des beständigen Chat Servers (und optional die Compliance für beständigen Chat)</strong></p></td>
<td><p>Führen Sie den Topologie-Generator aus, um Ihrer Topologie einen beständigen Chat Server Pool hinzuzufügen:</p>
<ul>
<li><p>Hinzufügen von persistenten Chat Server-Komponenten zur Topologie</p></li>
<li><p>Erstellen einer SQL Server-Datenbank für den beständigen Chat Server Speicher (und ein Backup SQL Server für Disaster Recovery)</p></li>
<li><p>Definieren eines neuen lync-Dateispeichers oder Verwenden eines vorhandenen lync-Dateispeichers für persistente Chat Server Dateien</p></li>
<li><p>Zuordnen des lync Server 2013-Pools, der Anforderungen an diesen beständigen Chat Serverpool weiterleiten kann</p></li>
</ul>
<p>Wenn die Kompatibilität für den beständigen Chat erforderlich ist:</p>
<ul>
<li><p>Kompatibilitäts Speicher für beständigen Chat hinzufügen</p></li>
<li><p>Aktivieren Sie das Kontrollkästchen Definition des beständigen Chat Server Pools, um die Kompatibilität zu aktivieren</p></li>
<li><p>Veröffentlichen der Topologie</p></li>
</ul>
<p>Wenn Sie den Server für beständigen Chat auf Standard Edition installieren, muss der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des beständigen Chat Server Pools mit dem Standard Edition-Server übereinstimmen, und die SQL Server-Datenbanken sind auf der SQL Server Express-Instanz auf dem Standard Edition-Server</p></td>
<td><p>Zum Definieren einer Topologie. Ein Konto, das Mitglieder der lokalen Gruppe „Benutzer“ ist.</p>
<p>Um die Topologie zu veröffentlichen, muss ein Konto, das ein Mitglied der Gruppe "Domänen-Admins" und der RTCUniversalServerAdmins-Gruppe ist, und der Benutzer auch über die Berechtigung "Vollzugriff" (Lesen/Schreiben/ändern) im lync-Dateispeicher für persistente Chat Server Dateien verfügen (damit der Topologie-Generator die erforderlichen DACLs konfigurieren kann).</p></td>
<td><p><a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Hinzufügen von beständigem Chat Server zu Ihrer Bereitstellung in lync Server 2013</a> in der Bereitstellungsdokumentation</p></td>
</tr>
<tr class="odd">
<td><p><strong>Bereitstellen des Servers für beständigen Chat</strong></p></td>
<td><p>Führen Sie das lync Server-Setup auf allen Computern aus, auf denen der beständige Chat Server ausgeführt wird. Das Setup des beständigen Chat Servers ist in den lync Server 2013-Bereitstellungs-Assistenten integriert, in dem die folgenden Anweisungen enthalten sind:</p>
<ul>
<li><p>Den lokalen Verwaltungsspeicher bereitstellen</p></li>
<li><p>Installieren von beständigen Chat Server Diensten</p></li>
<li><p>Zertifikate anfordern und zuweisen</p></li>
<li><p>Dienste ausführen und starten</p></li>
</ul></td>
<td><p>Jeder Benutzer, der Mitglied der lokalen Gruppe „Administratoren“ ist.</p></td>
<td><p><a href="lync-server-2013-deploying-persistent-chat-server.md">Bereitstellen des beständigen Chat Servers in lync Server 2013</a> in der Bereitstellungsdokumentation</p></td>
</tr>
<tr class="even">
<td><p><strong>Erstellen eines Administrators für beständigen Chat</strong></p></td>
<td><p>Fügen Sie der Sicherheitsgruppe „CsPersistentChatAdministrator“ Benutzer hinzu.</p></td>
<td><p>Jeder Benutzer, der Mitglied der Domänenadministratoren ist.</p></td>
<td><p><a href="lync-server-2013-adding-a-persistent-chat-administrator.md">Hinzufügen eines Administrators für beständigen Chat in lync Server 2013</a> in der Bereitstellungsdokumentation</p></td>
</tr>
<tr class="odd">
<td><p><strong>Konfigurieren des Server für beständigen Chat</strong></p></td>
<td><p>Konfigurieren von Benutzern:</p>
<ul>
<li><p>Der Benutzer muss durch eine Richtlinie für den Zugriff auf beständigen Chat Server aktiviert sein. Die Richtlinie ist standardmäßig für alle Benutzer deaktiviert und kann auf globaler, Standort-, Pool- und Benutzerebene definiert werden.</p></li>
<li><p>Einstellungen konfigurieren</p></li>
</ul></td>
<td><p>Der Benutzer muss Mitglied von „CsPersistentChatAdministrator“ sein. Benutzer müssen sich zum Ändern der Richtlinie mindestens in „CsUserAdministrator“ befinden.</p></td>
<td><p><a href="lync-server-2013-configuring-persistent-chat-server.md">Konfigurieren des beständigen Chat Servers in lync Server 2013</a> in der Bereitstellungsdokumentation</p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> Sie können einen oder mehrere beständige Chat Server Pools bereitstellen. Wir unterstützen mehrere Server Pools für beständige Chats aus regulatorischen Gründen, wobei in einer bestimmten Region generierte Daten erforderlich sind, um in dieser Region zu bleiben. Wenn Sie beispielsweise einen Serverpool für beständigen Chat in Chicago und einen anderen in Zürich bereitstellen, um den Richtlinien für Daten in der Schweiz zu entsprechen, können Benutzer in den beständigen Chat Server Pools Verbindungen mit Chatrooms herstellen, vorausgesetzt, Sie haben Zugriff.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

