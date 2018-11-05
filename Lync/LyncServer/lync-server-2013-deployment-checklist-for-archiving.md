---
title: 'Lync Server 2013: Prüfliste zur Bereitstellung für die Archivierung'
TOCTitle: Prüfliste zur Bereitstellung für die Archivierung
ms:assetid: 7479734d-be01-40d9-ad82-320a09d19d04
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205009(v=OCS.15)
ms:contentKeyID: 49294403
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Prüfliste zur Bereitstellung für die Archivierung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Die Archivierung wird automatisch auf den einzelnen Front-End-Servern in Ihrer Lync Server 2013-Bereitstellung installiert, Sie müssen die Archivierung jedoch einrichten, bevor Sie sie verwenden können. Die in diesem Abschnitt zusammengefassten Schritte, die für die Einrichtung erforderlich sind, umfassen die Bereitstellung der Archivierung.

## Bereitstellungsreihenfolge

Die Einrichtung der Archivierung ist abhängig von der jeweiligen Speicheroption:

  - Wenn Sie eine Microsoft Exchange-Integration für alle Benutzer in Ihrer Bereitstellung verwenden, müssen Sie für Ihre Benutzer keine Lync Server 2013-Archivierungsrichtlinien konfigurieren. Stattdessen müssen Sie Ihre Exchange-Compliance-Archiv-Richtlinien so konfigurieren, dass diese die Archivierung für Benutzer unterstützen, die unter Exchange 2013 verwaltet werden und deren Postfächer sich im Compliance-Archiv befinden. Ausführliche Informationen zur Konfiguration dieser Richtlinien finden Sie in der Produktdokumentation zu Exchange 2013.

  - Wenn Sie keine Microsoft Exchange-Integration für die Benutzer in Ihrer Bereitstellung verwenden, müssen Sie Ihrer Topologie Lync Server-Archivierungsdatenbanken ( SQL Server-Datenbanken) hinzufügen, und diese Topologie veröffentlichen. Darüber hinaus müssen Sie Richtlinien und Einstellungen für Ihre Benutzer konfigurieren, bevor Sie Daten für diese Benutzer archivieren können. Sie können Archivierungsdatenbanken gleichzeitig mit Ihrer anfänglichen Topologie oder nach der Bereitstellung von mindestens einem Front-End-Pool oder Standard Edition-Server bereitstellen. Im vorliegenden Dokument wird beschrieben, wie Sie Archivierungsdatenbanken bereitstellen, indem Sie sie einer vorhandenen Bereitstellung hinzufügen.

Wenn Sie die Archivierung in einem Front-End-Pool oder auf einem Standard Edition-Server aktivieren, sollten Sie sie für alle weiteren Front-End-Pools und Standard Edition-Server in Ihrer Bereitstellung ebenfalls aktivieren. Auf diese Weise können Benutzer, deren Kommunikation archiviert werden muss, zu Sofortnachrichten-Gruppenunterhaltungen oder Besprechungen eingeladen werden, die in einem anderen Pool gehostet werden. Wenn im Pool, der die Unterhaltung oder Besprechung hostet, die Archivierung nicht aktiviert wurde, kann möglicherweise die gesamte Sitzung nicht archiviert werden. In diesen Fällen können Sofortnachrichten mit archivierungsfähigen Benutzern trotzdem archiviert werden. Für Konferenzinhaltdateien sowie für den Beitritt bzw. das Verlassen einer Konferenz ist dies jedoch nicht möglich.


> [!IMPORTANT]
> Wenn die Archivierung in Ihrer Organisation aus Gründen der Einhaltung von Bestimmungen wichtig ist, müssen Sie einen Archivierungsserver bereitstellen, Richtlinien und weitere Optionen auf der entsprechenden Ebene konfigurieren und die Archivierung für alle gewünschten Benutzer aktivieren, bevor Sie diese Benutzer für Lync Server 2013 aktivieren.



## Archivierungsbereitstellungsprozess

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
<td><p><strong>Erforderliche Hardware und Software installieren</strong></p></td>
<td><ul>
<li><p>Wenn Sie eine Microsoft Exchange-Integration (Verwendung von Exchange 2013 als Archivierungsspeicher für einen oder alle Benutzer) verwenden möchten, benötigen Sie eine bestehende Exchange 2013-Bereitstellung.</p></li>
<li><p>Wenn Sie separate Archivierungsdatenbanken (Verwendung von SQL Server-Datenbanken) als Archivierungsspeicher für einige oder alle Benutzer verwenden möchten, muss SQL Server auf dem Server ausgeführt werden, auf dem die Archivierungsdaten gespeichert werden.</p></li>
</ul>
<div>

> [!NOTE]
> Die Archivierung wird auf Front-End-Servern in einem Enterprise-Pool und Standard Edition-Servern ausgeführt. Abgesehen von den herkömmlichen Anforderungen zur Installation dieser Server bestehen keine zusätzlichen Hardware- oder Softwareanforderungen.


</div></td>
<td><p>Domänenbenutzer, der Mitglied der lokalen Administratorgruppe ist.</p></td>
<td><p><a href="lync-server-2013-supported-hardware.md">Unterstützte Hardware für Lync Server 2013</a> in der Unterstützungsdokumentation</p>
<p><a href="lync-server-2013-server-software-and-infrastructure-support.md">Serversoftware- und Infrastrukturunterstützung in Lync Server 2013</a> in der Unterstützungsdokumentation</p>
<p><a href="lync-server-2013-technical-requirements-for-archiving.md">Technische Anforderungen für die Archivierung in Lync Server 2013</a> in der Planungsdokumentation</p>
<p><a href="lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md">Einrichten der Systeme und Infrastruktur für die Archivierung</a> in der Bereitstellungsdokumentation</p>
<p><a href="lync-server-2013-exchange-and-sharepoint-integration-support.md">Unterstützung der Integration von Exchange Server und SharePoint in Lync Server 2013</a> in der Unterstützungsdokumentation</p></td>
</tr>
<tr class="even">
<td><p><strong>Erstellen der geeigneten internen Topologie zur Unterstützung der Archivierung (nur, wenn keine Microsoft Exchange-Integration für die Benutzer in der Bereitstellung verwendet wird)</strong></p></td>
<td><p>Führen Sie den Topologie-Generator aus, um der Topologie Lync Server 2013-Archivierungsdatenbanken ( SQL Server-Datenbanken) hinzuzufügen und die Topologie dann zu veröffentlichen.</p></td>
<td><p>Zum Definieren einer Topologie für die Einbindung von Archivierungsdatenbanken; ein Konto, das Mitglied der Gruppe der lokalen Benutzer ist.</p>
<p>Zum Veröffentlichen der Topologie; Konto, das Mitglied der Gruppen „Domänen-Admins“ und „RTCUniversalServerAdmins“ ist und über Vollzugriff (Lesen/Schreiben/Ändern) für die Dateifreigabe verfügt, die als Lync Server 2013-Dateispeicher verwendet wird (damit der Topologie-Generator die erforderlichen DACLs konfigurieren kann).</p></td>
<td><p><a href="lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md">Hinzufügen von Archivierungsdatenbanken zu einer vorhandenen Lync Server 2013-Bereitstellung</a> in der Bereitstellungsdokumentation</p></td>
</tr>
<tr class="odd">
<td><p><strong>Konfigurieren einer Server-zu-Server-Authentifizierung (nur bei Verwendung einer Microsoft Exchange-Integration)</strong></p></td>
<td><p>Konfigurieren Sie die Server so, dass eine Authentifizierung zwischen Lync Server 2013 und Exchange 2013 erfolgt. Wir empfehlen die Ausführung von <strong>Test-CsExchangeStorageConnectivity testuser_sipUri -Folder Dumpster</strong>, um die Exchange-Archivierungsspeicherkonnektivität zu überprüfen, bevor Sie die Archivierung aktivieren.</p></td>
<td><p>Ein Konto mit den entsprechenden Berechtigungen zum Verwalten von Zertifikaten auf den Servern.</p></td>
<td><p><a href="lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md">Verwalten von Server-zu-Server-Authentifizierung (OAuth) und Partneranwendungen</a> in der Bereitstellungs- oder Betriebsdokumentation.</p></td>
</tr>
<tr class="even">
<td><p><strong>Konfigurieren von Archivierungsrichtlinien und -konfigurationen</strong></p></td>
<td><p>Konfigurieren Sie die Archivierung, einschließlich der Option, ob eine Microsoft Exchange-Integration verwendet werden soll, und einschließlich der globalen Richtlinie und aller Standort- und Benutzerrichtlinien (wenn keine Microsoft Exchange-Integration für die Datenspeicher erfolgt) sowie spezifischer Archivierungsoptionen, z. B. den kritischen Modus sowie Datenexport und -löschung.</p>
<p>Wenn Sie eine Microsoft Exchange-Integration verwenden, konfigurieren Sie ggf. Exchange-Compliance-Archiv-Richtlinien.</p></td>
<td><p>Gruppe „RTCUniversalServerAdmins“ (nur Windows PowerShell) oder Zuweisung von Benutzern zur Rolle „CSArchivingAdministrator“ oder „CSAdministrator“</p></td>
<td><p><a href="lync-server-2013-configuring-support-for-archiving.md">Konfigurieren der Unterstützung für die Archivierung</a> in der Bereitstellungsdokumentation</p>
<p>Exchange-Produktdokumentation (bei Verwendung der Microsoft Exchange-Integration).</p></td>
</tr>
</tbody>
</table>


## Bereitstellen von Lync Server und Microsoft Exchange in unterschiedlichen Gesamtstrukturen

Wenn Microsoft Exchange Server nicht in derselben Gesamtstruktur wie Lync Server bereitgestellt wird, müssen Sie sicherstellen, dass die folgenden Exchange Active Directory-Attribute mit der Gesamtstruktur synchronisiert sind, in der Lync Server bereitgestellt wird:

1.  msExchUserHoldPolicies

2.  proxyAddresses

Dies ist ein mehrwertiges Attribut. Bei der Synchronisierung dieses Attributs müssen Sie die Werte zusammenführen, nicht ersetzen, um sicherzustellen, dass die vorhandenen Werte nicht verloren gehen.

