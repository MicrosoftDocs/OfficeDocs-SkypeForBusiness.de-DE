---
title: 'Lync Server 2013: Prüfliste zur Bereitstellung für die Archivierung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment checklist for Archiving
ms:assetid: 7479734d-be01-40d9-ad82-320a09d19d04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205009(v=OCS.15)
ms:contentKeyID: 48184516
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51c556dd288ff3539bbf2f4de816eab3a544b847
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832519"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-archiving-in-lync-server-2013"></a>Prüfliste zur Bereitstellung für die Archivierung in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-18_

Die Archivierung wird automatisch auf jedem Front-End-Server in ihrer lync Server 2013-Bereitstellung installiert, Sie müssen Sie aber noch einrichten, bevor Sie Sie verwenden können. Die erforderlichen Schritte zum Einrichten, wie in diesem Abschnitt zusammengefasst, stellen die Bereitstellung der Archivierung dar.

<div>

## <a name="deployment-sequence"></a>Bereitstellungssequenz

Wie Sie die Archivierung einrichten, hängt davon ab, welche Speicheroption Sie auswählen:

  - Wenn Sie die Microsoft Exchange-Integration für alle Benutzer in Ihrer Bereitstellung verwenden, müssen Sie die lync Server 2013-Archivierungsrichtlinien für Ihre Benutzer nicht konfigurieren. Konfigurieren Sie stattdessen Ihre Exchange-in-situ-Speicherrichtlinien, um die Archivierung für Benutzer in Exchange 2013 zu unterstützen, wobei ihre Postfächer in-situ-Speicher abgelegt werden. Details zum Konfigurieren dieser Richtlinien finden Sie in der Exchange 2013-Produktdokumentation.

  - Wenn Sie die Microsoft Exchange-Integration nicht für alle Benutzer in Ihrer Bereitstellung verwenden, müssen Sie Ihrer Topologie lync Server-Archivierungsdatenbanken (SQL Server-Datenbanken) hinzufügen und dann veröffentlichen sowie Richtlinien und Einstellungen für Ihre Benutzer konfigurieren, bevor Sie Archivieren Sie Daten für diese Benutzer. Sie können Archivierungsdatenbanken zur gleichen Zeit bereitstellen, in der Sie Ihre anfängliche Topologie bereitstellen, oder nachdem Sie mindestens einen Front-End-Pool oder Standard Edition-Server bereitgestellt haben. In diesem Dokument wird beschrieben, wie Archivierungsdatenbanken bereitgestellt werden, indem Sie einer vorhandenen Bereitstellung hinzugefügt werden.

Wenn Sie die Archivierung in einem Front-End-Pool oder Standard Edition-Server aktivieren, sollten Sie Sie für alle anderen Front-End-Pools und Standard Edition-Server in Ihrer Bereitstellung aktivieren. Dies liegt daran, dass Benutzer, deren Kommunikation archiviert werden muss, zu einer Gruppenunterhaltung oder Besprechungen eingeladen werden können, die in einem anderen Pool gehostet werden. Wenn die Archivierung in dem Pool, in dem die Unterhaltung oder Besprechung gehostet wird, nicht aktiviert ist, wird die vollständige Sitzung möglicherweise nicht archiviert. In diesen Fällen können IMS mit Archivierungs fähigen Benutzern weiterhin archiviert werden, jedoch nicht für Konferenz Inhaltsdateien und Konferenzteilnahme-oder Leave-Ereignisse.

<div>


> [!IMPORTANT]  
> Wenn die Archivierung aus Kompatibilitätsgründen für Ihre Organisation wichtig ist, stellen Sie sicher, dass Sie die Archivierung bereitstellen, Richtlinien und andere Optionen auf der entsprechenden Ebene konfigurieren und für alle entsprechenden Benutzer aktivieren, bevor Sie diese Benutzer für lync Server 2013 aktivieren.



</div>

</div>

<div>

## <a name="archiving-deployment-process"></a>Archivierungs Bereitstellungsprozess

Die folgende Tabelle bietet einen Überblick über die erforderlichen Schritte zur Bereitstellung einer Archivierung in einer vorhandenen Topologie.


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
<th>Rollen und Gruppenmitgliedschaften</th>
<th>Dokumentation</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Installieren der erforderlichen Hardware und Software</strong></p></td>
<td><ul>
<li><p>Wenn Sie die Microsoft Exchange-Integration (mit Exchange 2013 für die Archivierung von Speicher für einige oder alle Benutzer) verwenden möchten, benötigen Sie eine vorhandene Exchange 2013-Bereitstellung.</p></li>
<li><p>So verwenden Sie separate Archivierungsdatenbanken (mithilfe von SQL Server-Datenbanken) zum Archivieren von Speicher für einige oder alle Benutzer, SQL Server auf dem Server, auf dem Archivierungsdaten gespeichert werden.</p></li>
</ul>
<div>

> [!NOTE]  
> Die Archivierung wird auf Front-End-Servern eines Enterprise-Pools und von Standard Edition-Servern ausgeführt. Abgesehen von den herkömmlichen Anforderungen zur Installation dieser Server bestehen keine zusätzlichen Hardware- oder Softwareanforderungen.


</div></td>
<td><p>Domänenbenutzer, der Mitglied der lokalen Administratorgruppe ist.</p></td>
<td><p><a href="lync-server-2013-supported-hardware.md">Unterstützte Hardware für lync Server 2013</a> in der Dokumentation zur Unterstützung.</p>
<p><a href="lync-server-2013-server-software-and-infrastructure-support.md">Unterstützung für Server Software und-Infrastruktur in lync Server 2013</a> in der Dokumentation zur Unterstützung.</p>
<p><a href="lync-server-2013-technical-requirements-for-archiving.md">Technische Voraussetzungen für die Archivierung in lync Server 2013</a> in der Planungsdokumentation.</p>
<p><a href="lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md">Einrichten von Systemen und Infrastruktur für die Archivierung in lync Server 2013</a> in der Bereitstellungsdokumentation</p>
<p><a href="lync-server-2013-exchange-and-sharepoint-integration-support.md">Unterstützung für Exchange Server und SharePoint-Integration in lync Server 2013</a> in der Dokumentation zur Unterstützung.</p></td>
</tr>
<tr class="even">
<td><p><strong>Erstellen der geeigneten internen Topologie zur Unterstützung der Archivierung (nur, wenn Sie nicht die Microsoft Exchange-Integration für alle Benutzer in Ihrer Bereitstellung verwenden)</strong></p></td>
<td><p>Führen Sie den Topologie-Generator aus, um der Topologie lync Server 2013-Archivierungsdatenbanken (SQL Server-Datenbanken) hinzuzufügen, und veröffentlichen Sie dann die Topologie.</p></td>
<td><p>So definieren Sie eine Topologie für die Integration von Archivierungsdatenbanken: ein Konto, das ein Mitglied der lokalen Benutzergruppe ist.</p>
<p>So veröffentlichen Sie die Topologie: ein Konto, das ein Mitglied der Gruppe "Domänen-Admins" und der RTCUniversalServerAdmins-Gruppe ist und das Vollzugriffsberechtigungen (Lesen/Schreiben/ändern) für die Dateifreigabe hat, die für den lync Server 2013-Dateispeicher verwendet werden soll (damit der Topologie-Generator Konfigurieren Sie die erforderlichen DACLs).</p></td>
<td><p><a href="lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md">Hinzufügen von Archivierungsdatenbanken zu einer vorhandenen lync Server 2013-Bereitstellung</a> in der Bereitstellungsdokumentation</p></td>
</tr>
<tr class="odd">
<td><p><strong>Konfigurieren der Server-zu-Server-Authentifizierung (nur bei Verwendung der Microsoft Exchange-Integration)</strong></p></td>
<td><p>Konfigurieren Sie Server, um die Authentifizierung zwischen lync Server 2013 und Exchange 2013 zu ermöglichen. Wir empfehlen die Ausführung von <strong>Test-CsExchangeStorageConnectivity testuser_sipUri – Folder Container</strong> , um die Exchange-Archivierungsspeicher Konnektivität zu überprüfen, bevor Sie die Archivierung aktivieren.</p></td>
<td><p>Ein Konto mit den entsprechenden Berechtigungen zum Verwalten von Zertifikaten auf den Servern.</p></td>
<td><p><a href="lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md">Verwalten der Server-zu-Server-Authentifizierung (OAuth) und der Partneranwendungen in lync Server 2013</a> in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.</p></td>
</tr>
<tr class="even">
<td><p><strong>Konfigurieren von Archivierungsrichtlinien und-Konfigurationen</strong></p></td>
<td><p>Konfigurieren Sie die Archivierung, einschließlich der Frage, ob Sie die Microsoft Exchange-Integration, die globale Richtlinie und alle Website-und Benutzerrichtlinien verwenden möchten (wenn Sie die Microsoft Exchange-Integration nicht für alle Datenspeicher verwenden), und bestimmte Archivierungsoptionen wie kritischer Modus und Daten Exportieren und bereinigen.</p>
<p>Wenn Sie die Microsoft Exchange-Integration verwenden, konfigurieren Sie Exchange-in-situ-Speicherrichtlinien nach Bedarf.</p></td>
<td><p>Gruppe „RTCUniversalServerAdmins“ (nur Windows PowerShell) oder Zuweisung von Benutzern zur Rolle „CSArchivingAdministrator“ oder „CSAdministrator“</p></td>
<td><p><a href="lync-server-2013-configuring-support-for-archiving.md">Konfigurieren der Unterstützung für die Archivierung in lync Server 2013</a> in der Bereitstellungsdokumentation</p>
<p>Exchange-Produktdokumentation (bei Verwendung der Microsoft Exchange-Integration).</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="deploying-lync-server-and-microsoft-exchange-in-different-forests"></a>Bereitstellen von lync Server und Microsoft Exchange in verschiedenen Gesamtstrukturen

Wenn Microsoft Exchange Server nicht in derselben Gesamtstruktur wie lync Server bereitgestellt wird, müssen Sie sicherstellen, dass die folgenden Exchange Active Directory-Attribute mit der Gesamtstruktur synchronisiert werden, in der lync Server bereitgestellt wird:

1.  msExchUserHoldPolicies

2.  proxyAddresses

Dies ist ein mehrwertiges Attribut. Bei der Synchronisierung dieses Attributs müssen Sie die Werte zusammenführen und nicht ersetzen, um sicherzustellen, dass die vorhandenen Werte nicht verloren gehen.

</div>

</div>

<span> </span>

</div>

</div>

</div>

