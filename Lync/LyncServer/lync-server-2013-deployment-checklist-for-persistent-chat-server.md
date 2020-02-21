---
title: 'Lync Server 2013: Prüfliste für die Bereitstellung für persistent Chat Server'
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
ms.openlocfilehash: a01d38cec8d03a75d5f295c61f6e591da43f4a61
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213814"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-persistent-chat-server-in-lync-server-2013"></a>Prüfliste für die Bereitstellung für persistent Chat Server in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-16_

Für die Bereitstellung von lync Server 2013 ist der Server für beständigen Chat erforderlich, dass Sie ihn in der richtigen Reihenfolge bereitstellen und alle erforderlichen Bereitstellungsschritte ausführen.

<div>

## <a name="deployment-sequence"></a>Bereitstellungsreihenfolge

Sie können den Server für beständigen Chat bereitstellen, nachdem Sie die anfängliche Topologie bereitgestellt haben, einschließlich mindestens einer lync Server 2013, Front-End-Pool oder einer lync Server 2013 Standard Edition-Server. In diesem Thema wird beschrieben, wie Sie den Server für beständigen Chat bereitstellen, indem Sie ihn einer vorhandenen Bereitstellung hinzufügen.

</div>

<div>

## <a name="deployment-process"></a>Bereitstellungsprozess

In der folgenden Tabelle sind die grundlegenden Schritte zum Bereitstellen des Servers für beständigen Chat und Links für weitere Details aufgeführt.

### <a name="persistent-chat-server-deployment-process"></a>Server Bereitstellungsprozess für beständigen Chat

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
<td><p><strong>Erforderliche Hardware und Software installieren</strong></p></td>
<td><p>Installieren Sie die folgenden Komponenten auf einem Hardwaresystem, das die Systemanforderungen erfüllt:</p>
<ul>
<li><p>Auf den Front-End-Servern für beständigen Chat Server:</p></li>
</ul>
<ul>
<li><p>Ein Betriebssystem, das die Systemanforderungen erfüllt</p></li>
<li><p>Software Voraussetzungen für Computer mit lync Server 2013</p></li>
<li><p>SQL Server auf dem Server, auf dem die Server Datenbank für beständigen Chat gehostet wird</p></li>
</ul>
<p>Wenn die Server Kompatibilität für beständigen Chat erforderlich ist:</p>
<ul>
<li><p>SQL Server auf dem Server, auf dem die Kompatibilitätsdatenbank für den Server für beständigen Chat gehostet wird</p></li>
</ul></td>
<td><p>Jeder Benutzer, der Mitglied der lokalen Administratorgruppe ist.</p></td>
<td><p><a href="lync-server-2013-supported-hardware.md">Unterstützte Hardware für lync Server 2013</a> in der Unterstützungsdokumentation</p>
<p><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server Software-und Infrastrukturunterstützung in lync Server 2013</a> in der Unterstützungsdokumentation</p>
<p><a href="lync-server-2013-determining-your-system-requirements.md">Bestimmen der Systemanforderungen für lync Server 2013</a></p>
<p><a href="lync-server-2013-technical-requirements-for-persistent-chat-server.md">Technische Anforderungen für den Server für beständigen Chat in lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><strong>Erstellen der geeigneten internen Topologie zur Unterstützung des Servers für beständigen Chat (und optional beständiger Chat – Compliance)</strong></p></td>
<td><p>Führen Sie den Topologie-Generator aus, um der Topologie einen Server Pool für beständigen Chat hinzuzufügen:</p>
<ul>
<li><p>Hinzufügen von Komponenten für beständigen Chat Server zur Topologie</p></li>
<li><p>Erstellen einer SQL Server Datenbank für den Server Speicher für beständigen Chat (und eine Sicherungs SQL Server für die Notfallwiederherstellung)</p></li>
<li><p>Definieren einer neuen lync-Dateispeicher oder Verwenden einer vorhandenen lync-Dateispeicher für Server Dateien für beständigen Chat</p></li>
<li><p>Zuordnen des lync Server 2013 Pools, der Anforderungen an diesen Server Pool für beständigen Chat weiterleiten kann</p></li>
</ul>
<p>Wenn die Compliance für beständigen Chat erforderlich ist:</p>
<ul>
<li><p>Kompatibilitäts Speicher für beständigen Chat hinzufügen</p></li>
<li><p>Aktivieren Sie das Kontrollkästchen Definition für den Server Pool für beständigen Chat zur Aktivierung der Kompatibilität</p></li>
<li><p>Veröffentlichen der Topologie</p></li>
</ul>
<p>Wenn Sie den Server für beständigen Chat auf Standard Edition installieren, muss der vollqualifizierte Domänenname (FQDN) des Server Pools für beständigen Chat mit dem Standard Edition-Server übereinstimmen, und die SQL Server Datenbanken befinden sich auf der SQL Server Express-Instanz auf dem Standard Edition-Server</p></td>
<td><p>Zum Definieren einer Topologie. Ein Konto, das Mitglieder der lokalen Gruppe "Benutzer" ist.</p>
<p>Um die Topologie zu veröffentlichen, muss ein Konto, das Mitglied der Gruppe "Domänen-Admins" und der RTCUniversalServerAdmins-Gruppe ist, sowie der Benutzer über die Berechtigung "Vollzugriff" (Lesen/Schreiben/ändern) für die lync-Dateispeicher für Server Dateien für beständigen Chat verfügen (damit der Topologie-Generator die erforderlichen DACLs konfigurieren kann).</p></td>
<td><p><a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Hinzufügen von persistent Chat Server zu Ihrer Bereitstellung in lync Server 2013</a> in der Bereitstellungsdokumentation</p></td>
</tr>
<tr class="odd">
<td><p><strong>Bereitstellen des Servers für beständigen Chat</strong></p></td>
<td><p>Führen Sie das lync Server-Setup auf allen Computern aus, auf denen persistent Chat Server ausgeführt wird. Das Setup für beständigen Chat Server ist in den lync Server 2013-Bereitstellungs-Assistenten integriert, der die folgenden Anweisungen bereitstellt:</p>
<ul>
<li><p>Den lokalen Verwaltungsspeicher bereitstellen</p></li>
<li><p>Installieren von Server Diensten für beständigen Chat</p></li>
<li><p>Zertifikate anfordern und zuweisen</p></li>
<li><p>Dienste ausführen und starten</p></li>
</ul></td>
<td><p>Jeder Benutzer, der Mitglied der lokalen Administratorgruppe ist.</p></td>
<td><p><a href="lync-server-2013-deploying-persistent-chat-server.md">Bereitstellen des Servers für beständigen Chat in lync Server 2013</a> in der Bereitstellungsdokumentation</p></td>
</tr>
<tr class="even">
<td><p><strong>Erstellen eines Administrators für beständigen Chat</strong></p></td>
<td><p>Fügen Sie der Sicherheitsgruppe "CsPersistentChatAdministrator" Benutzer hinzu.</p></td>
<td><p>Jeder Benutzer, der Mitglied der Domänenadministratoren ist.</p></td>
<td><p><a href="lync-server-2013-adding-a-persistent-chat-administrator.md">Hinzufügen eines Administrators für beständigen Chat in lync Server 2013</a> in der Bereitstellungsdokumentation</p></td>
</tr>
<tr class="odd">
<td><p><strong>Konfigurieren von Persistent Chat Server</strong></p></td>
<td><p>Konfigurieren von Benutzern:</p>
<ul>
<li><p>Der Benutzer muss durch eine Richtlinie aktiviert sein, um auf den Server für beständigen Chat zuzugreifen. Die Richtlinie ist standardmäßig für alle Benutzer deaktiviert und kann auf globaler, Standort-, Pool- und Benutzerebene definiert werden.</p></li>
<li><p>Einstellungen konfigurieren</p></li>
</ul></td>
<td><p>Der Benutzer muss Mitglied von "CsPersistentChatAdministrator" sein. Benutzer müssen sich zum Ändern der Richtlinie mindestens in "CsUserAdministrator" befinden.</p></td>
<td><p><a href="lync-server-2013-configuring-persistent-chat-server.md">Konfigurieren des Servers für beständigen Chat in lync Server 2013</a> in der Bereitstellungsdokumentation</p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> Sie können einen oder mehrere Server Pools für beständigen Chat bereitstellen. Wir unterstützen mehrere Server Pools für beständigen Chat aus regulatorischen Gründen, wobei Daten, die in einer bestimmten Region generiert werden, in dieser Region verbleiben müssen. Wenn Sie beispielsweise einen Serverpool für beständigen Chat in Chicago und einen anderen in Zürich bereitstellen, um die Vorschriften für Daten in der Schweiz einzuhalten, können Benutzer in den Server Pools für beständigen Chat auf Chatrooms zugreifen, vorausgesetzt, Sie verfügen über Zugriff.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

