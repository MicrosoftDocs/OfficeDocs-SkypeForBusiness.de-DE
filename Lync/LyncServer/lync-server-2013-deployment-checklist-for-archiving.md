---
title: 'Lync Server 2013: Prüfliste zur Bereitstellung für die Archivierung'
description: 'Lync Server 2013: Prüfliste zur Bereitstellung für die Archivierung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for Archiving
ms:assetid: 7479734d-be01-40d9-ad82-320a09d19d04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205009(v=OCS.15)
ms:contentKeyID: 48184516
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e9fb3085950aa1e8a750d36a0aeb8592bc18113
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557711"
---
# <a name="deployment-checklist-for-archiving-in-lync-server-2013"></a>Prüfliste zur Bereitstellung für die Archivierung in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-18_

Die Archivierung wird automatisch auf jedem Front-End-Server in ihrer lync Server 2013-Bereitstellung installiert, Sie müssen Sie jedoch noch einrichten, bevor Sie Sie verwenden können. Die in diesem Abschnitt zusammengefassten Schritte, die für die Einrichtung erforderlich sind, umfassen die Bereitstellung der Archivierung.

<div>

## <a name="deployment-sequence"></a>Bereitstellungsreihenfolge

Die Einrichtung der Archivierung ist abhängig von der jeweiligen Speicheroption:

  - Wenn Sie Microsoft Exchange Integration für alle Benutzer in Ihrer Bereitstellung verwenden, müssen Sie lync Server 2013 Archivierungsrichtlinien für Ihre Benutzer nicht konfigurieren. Konfigurieren Sie stattdessen Ihre Exchange In-Place Hold-Richtlinien zur Unterstützung der Archivierung für Benutzer, die in Exchange 2013 verwaltet werden und deren Postfächer In-Place aufbewahrt werden. Ausführliche Informationen zum Konfigurieren dieser Richtlinien finden Sie in der Exchange 2013-Produktdokumentation.

  - Wenn Sie Microsoft Exchange Integration nicht für alle Benutzer in Ihrer Bereitstellung verwenden, müssen Sie lync Server Archivierungsdatenbanken (SQL Server Datenbanken) zu Ihrer Topologie hinzufügen und diese dann veröffentlichen sowie Richtlinien und Einstellungen für Ihre Benutzer konfigurieren, bevor Sie Daten für diese Benutzer archivieren können. Sie können Archivierungsdatenbanken gleichzeitig bereitstellen, wenn Sie die anfängliche Topologie bereitstellen oder nachdem Sie mindestens eine Front-End-Pool oder Standard Edition-Server bereitgestellt haben. In diesem Dokument wird beschrieben, wie Sie Archivierungsdatenbanken bereitstellen, indem Sie Sie einer vorhandenen Bereitstellung hinzufügen.

Wenn Sie die Archivierung in einem Front-End-Pool oder auf einem Standard Edition-Server aktivieren, sollten Sie sie für alle weiteren Front-End-Pools und Standard Edition-Server in Ihrer Bereitstellung ebenfalls aktivieren. Auf diese Weise können Benutzer, deren Kommunikation archiviert werden muss, zu Sofortnachrichten-Gruppenunterhaltungen oder Besprechungen eingeladen werden, die in einem anderen Pool gehostet werden. Wenn im Pool, der die Unterhaltung oder Besprechung hostet, die Archivierung nicht aktiviert wurde, kann möglicherweise die gesamte Sitzung nicht archiviert werden. In diesen Fällen können Sofortnachrichten mit archivierungsfähigen Benutzern trotzdem archiviert werden. Für Konferenzinhaltdateien sowie für den Beitritt bzw. das Verlassen einer Konferenz ist dies jedoch nicht möglich.

<div>


> [!IMPORTANT]  
> Wenn die Archivierung aus Kompatibilitätsgründen in Ihrer Organisation kritisch ist, müssen Sie die Archivierung bereitstellen, Richtlinien und andere Optionen auf der entsprechenden Ebene konfigurieren und diese für alle entsprechenden Benutzer aktivieren, bevor Sie diese Benutzer für lync Server 2013 aktivieren.



</div>

</div>

<div>

## <a name="archiving-deployment-process"></a>Archivierungsbereitstellungsprozess

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
<li><p>Wenn Sie Microsoft Exchange Integration (mithilfe von Exchange 2013 für Archivierungsspeicher für einige oder alle Benutzer) verwenden möchten, benötigen Sie eine vorhandene Exchange 2013-Bereitstellung.</p></li>
<li><p>Wenn Sie separate Archivierungsdatenbanken (Verwendung von SQL Server-Datenbanken) als Archivierungsspeicher für einige oder alle Benutzer verwenden möchten, muss SQL Server auf dem Server ausgeführt werden, auf dem die Archivierungsdaten gespeichert werden.</p></li>
</ul>
<div>

> [!NOTE]  
> Die Archivierung wird auf Front-End-Servern in einem Enterprise-Pool und Standard Edition-Servern ausgeführt. Abgesehen von den herkömmlichen Anforderungen zur Installation dieser Server bestehen keine zusätzlichen Hardware- oder Softwareanforderungen.


</div></td>
<td><p>Domänenbenutzer, der Mitglied der lokalen Administratorgruppe ist.</p></td>
<td><p><a href="lync-server-2013-supported-hardware.md">Unterstützte Hardware für lync Server 2013</a> in der Unterstützungsdokumentation.</p>
<p><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server Software und Infrastrukturunterstützung in lync Server 2013</a> in der Unterstützungsdokumentation.</p>
<p><a href="lync-server-2013-technical-requirements-for-archiving.md">Technische Voraussetzungen für die Archivierung in lync Server 2013</a> in der Planungsdokumentation.</p>
<p><a href="lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md">Einrichten von Systemen und Infrastruktur für die Archivierung in lync Server 2013</a> in der Bereitstellungsdokumentation.</p>
<p><a href="lync-server-2013-exchange-and-sharepoint-integration-support.md">Unterstützung von Exchange Server und SharePoint-Integration in lync Server 2013</a> in der Unterstützungsdokumentation.</p></td>
</tr>
<tr class="even">
<td><p><strong>Erstellen der geeigneten internen Topologie zur Unterstützung der Archivierung (nur, wenn keine Microsoft Exchange Integration für alle Benutzer in Ihrer Bereitstellung verwendet wird)</strong></p></td>
<td><p>Führen Sie den Topologie-Generator aus, um der Topologie lync Server 2013 Archivierungsdatenbanken (SQL Server-Datenbanken) hinzuzufügen, und veröffentlichen Sie dann die Topologie.</p></td>
<td><p>Zum Definieren einer Topologie für die Einbindung von Archivierungsdatenbanken; ein Konto, das Mitglied der Gruppe der lokalen Benutzer ist.</p>
<p>So veröffentlichen Sie die Topologie, ein Konto, das Mitglied der Gruppe "Domänen-Admins" und der RTCUniversalServerAdmins-Gruppe ist und die über die Berechtigung "Vollzugriff" (Lesen/Schreiben/ändern) für die Dateifreigabe verfügt, die für den lync Server 2013 Dateispeicher verwendet werden soll (damit der Topologie-Generator die erforderlichen DACLs konfigurieren kann).</p></td>
<td><p><a href="lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md">Hinzufügen von Archivierungsdatenbanken zu einer vorhandenen lync Server 2013-Bereitstellung</a> in der Bereitstellungsdokumentation.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Konfigurieren der Server-zu-Server-Authentifizierung (nur bei Verwendung Microsoft Exchange Integration)</strong></p></td>
<td><p>Konfigurieren von Servern, um die Authentifizierung zwischen lync Server 2013 und Exchange 2013 zu ermöglichen. Es wird empfohlen, die Exchange-Archivierungsspeicher Konnektivität vor dem Aktivieren der Archivierung mit <strong>Test-CsExchangeStorageConnectivity testuser_sipUri – Folder Container</strong> zu validieren.</p></td>
<td><p>Ein Konto mit den entsprechenden Berechtigungen zum Verwalten von Zertifikaten auf den Servern.</p></td>
<td><p><a href="lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md">Verwalten der Server-zu-Server-Authentifizierung (OAuth) und der Partneranwendungen in lync Server 2013</a> in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.</p></td>
</tr>
<tr class="even">
<td><p><strong>Konfigurieren von Archivierungsrichtlinien und -konfigurationen</strong></p></td>
<td><p>Konfigurieren Sie die Archivierung, einschließlich der Frage, ob Sie Microsoft Exchange Integration, die globale Richtlinie und alle Standort-und Benutzerrichtlinien verwenden möchten (wenn Sie nicht die Microsoft Exchange Integration für alle Datenspeicher verwenden), sowie bestimmte Archivierungsoptionen, beispielsweise den kritischen Modus und den Datenexport und das Löschen.</p>
<p>Wenn Sie Microsoft Exchange Integration verwenden, konfigurieren Sie die Exchange In-Place-Aufbewahrungsrichtlinien entsprechend.</p></td>
<td><p>Gruppe „RTCUniversalServerAdmins“ (nur Windows PowerShell) oder Zuweisung von Benutzern zur Rolle „CSArchivingAdministrator“ oder „CSAdministrator“</p></td>
<td><p><a href="lync-server-2013-configuring-support-for-archiving.md">Konfigurieren der Unterstützung für die Archivierung in lync Server 2013</a> in der Bereitstellungsdokumentation.</p>
<p>Exchange-Produktdokumentation (bei Verwendung Microsoft Exchange Integration).</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="deploying-lync-server-and-microsoft-exchange-in-different-forests"></a>Bereitstellen von lync Server und Microsoft Exchange in unterschiedlichen Gesamtstrukturen

Wenn Exchange Server nicht in derselben Gesamtstruktur wie lync Server bereitgestellt wird, müssen Sie sicherstellen, dass die folgenden Exchange Active Directory-Attribute mit der Gesamtstruktur synchronisiert sind, in der lync Server bereitgestellt wird:

1.  msExchUserHoldPolicies

2.  proxyAddresses

Dies ist ein mehrwertiges Attribut. Bei der Synchronisierung dieses Attributs müssen Sie die Werte zusammenführen, nicht ersetzen, um sicherzustellen, dass die vorhandenen Werte nicht verloren gehen.

</div>

</div>

<span> </span>

</div>

</div>

</div>

