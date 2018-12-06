---
title: Active Directory-Domänendienste für Lync Server 2013
TOCTitle: Active Directory-Domänendienste für Lync Server 2013
ms:assetid: 5483afd5-d8af-4825-ae95-a82dbe941dbf
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Dn481129(v=OCS.15)
ms:contentKeyID: 59679131
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Active Directory-Domänendienste für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Active Directory-Domänendienste dient als Verzeichnisdienst für Windows Server 2003, Windows Server 2008-, Windows Server 2012- und Windows Server 2012 R2-Netzwerke. Active Directory-Domänendienste ist auch die Grundlage, auf der die Microsoft Lync Server 2013-Sicherheitsinfrastruktur aufgebaut ist. In diesem Abschnitt wird beschrieben, wie Lync Server 2013Active Directory-Domänendienste verwendet, um eine vertrauenswürdige Umgebung für Chat, Webkonferenzen, Media und Sprache zu erstellen. Details zu Lync Server-Erweiterungen für Active Directory-Domänendienste und zum Vorbereiten Ihrer Umgebung für Active Directory-Domänendienste finden Sie unter [Vorbereiten der Active Directory-Domänendienste für Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in der Bereitstellungsdokumentation. Details zur Rolle von Active Directory-Domänendienste in Windows Server-Netzwerken finden Sie in der Dokumentation zu Ihrer verwendeten Betriebssystemversion.

Lync Server 2013 verwendet Active Directory-Domänendienste zum Speichern der folgenden Komponenten:

  - Globale Einstellungen, die für alle Server mit Lync Server 2013 in einer Gesamtstruktur erforderlich sind

  - Dienstinformationen, mit denen die Rollen aller Server mit Lync Server 2013 in einer Gesamtstruktur identifiziert werden

  - Einige Benutzereinstellungen

## Active Directory-Infrastruktur

Zu den Infrastrukturanforderungen für Active Directory zählen die folgenden:

  - Betriebssystemanforderungen für Domänencontroller

  - Anforderungen für die Domänen- und Gesamtstrukturfunktionsebene

  - Anforderungen für die globale Katalogdomäne

Ausführliche Informationen hierzu finden Sie in der Bereitstellungsdokumentation unter [Active Directory-Infrastrukturanforderungen für Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md).

## Vorbereitung für Active Directory-Domänendienste


> [!NOTE]
> Wir empfehlen Ihnen, globale Einstellungen an den Konfigurationscontainer statt an den Systemcontainer bereitstellen. Damit wird die Sicherheit nicht verbessert, es kann aber zu Skalierbarkeitsverbesserungen für einige Active Directory-Domänendienste-Topologien führen. Wenn Sie von Microsoft Office Communications Server&nbsp;2007 migrieren und den Systemcontainer verwendet haben, aber die Verwendung des Konfigurationscontainers planen, MÜSSEN Sie die Einstellungen im Systemcontainer verschieben, BEVOR Sie Upgradevorbereitungen treffen. Informationen zum Migrieren Ihrer Systemcontainereinstellungen zum Konfigurationscontainer finden Sie unter Office Communications Server 2007 Global Settings Migration Tool unter <A href="http://go.microsoft.com/fwlink/p/?linkid=145236">http://go.microsoft.com/fwlink/p/?LinkId=145236</A>.



Der erste Schritt in der Bereitstellung von Lync Server 2013 ist die Vorbereitung von Active Directory-Domänendienste. Die Vorbereitung von Active Directory-Domänendienste für Lync Server 2013 umfasst die folgenden drei Schritte:

  - **Vorbereiten des Schemas:** Mit dieser Aufgabe wird das Schema in Active Directory-Domänendienste erweitert, damit es für Lync Server 2013 spezifische Klassen und Attribute enthält. Ausführliche Informationen zum Vorbereiten des Schemas finden Sie in der Bereitstellungsdokumentation unter [Ausführen der Active Directory-Schemavorbereitung in Lync Server 2013](lync-server-2013-running-schema-preparation.md). Weitere Informationen finden Sie unter [Migration von Office Communications Server 2007 R2 zu Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md).

  - **Vorbereiten der Gesamtstruktur:** Mit dieser Aufgabe werden globale Einstellungen und Objekte in der Stammdomäne der Gesamtstruktur zusammen mit den universellen Dienst- und administrativen Gruppen erstellt, die den Zugriff auf diese Einstellungen und Objekte regeln. Ausführliche Informationen zum Vorbereiten der Gesamtstruktur finden Sie in der Bereitstellungsdokumentation unter [Ausführen der Gesamtstrukturvorbereitung für Lync Server 2013](lync-server-2013-running-forest-preparation.md).

  - **Vorbereiten der Domäne:** Mit dieser Aufgabe werden universellen Gruppen die erforderlichen ACEs (Access Control Entries, Zugriffssteuerungseinträge) hinzugefügt, über die Berechtigungen zum Hosten und Verwalten von Benutzern in der Domäne gewährt werden. Diese Aufgabe muss in allen Domänen durchgeführt werden, in denen Sie Server mit Lync Server 2013 bereitstellen wollen, und in allen Domänen, in denen sich Ihre Lync Server-Benutzer befinden. Ausführliche Informationen zum Vorbereiten der Domäne finden Sie in der Bereitstellungsdokumentation unter [Ausführen der Domänenvorbereitung für Lync Server 2013](lync-server-2013-running-domain-preparation.md).

Eine Übersicht über den vollständigen Vorgang zur Vorbereitung von Active Directory sowie die für die Durchführung jedes Schritts erforderlichen Rechte und Berechtigungen finden Sie in der Bereitstellungsdokumentation unter [Active Directory-Infrastrukturanforderungen für Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md).

## Universelle Gruppen

Während der Vorbereitung der Gesamtstruktur erstellt Lync Server 2013 verschiedene universelle Gruppen in Active Directory-Domänendienste, die Berechtigungen für den Zugriff auf globale Einstellungen und Dienste und deren Verwaltung haben. Zu diesen Gruppen zählen die folgenden:

  - **Administrative Gruppen:** Mit diesen Gruppen werden die grundlegenden Administratorrollen für ein Lync Server-Netzwerk definiert. Während der Gesamtstrukturvorbereitung werden diese Administratorgruppen zu Lync Server-Infrastrukturgruppen hinzugefügt.

  - **Dienstgruppen:** Diese Gruppen sind Dienstkonten, die für den Zugriff auf verschiedene von Lync Server bereitgestellte Dienste benötigt werden.

  - **Infrastrukturgruppen:** Diese Gruppen stellen die Berechtigung für den Zugriff auf bestimmte Bereiche der Lync Server-Infrastruktur bereit. Sie dienen als Komponenten von administrativen Gruppen, und Sie sollten sie weder ändern noch ihnen direkt Benutzer hinzufügen. Während der Gesamtstrukturvorbereitung werden den entsprechenden Infrastrukturgruppen bestimmte Dienst- und Administrationsgruppen hinzugefügt.

Ausführliche Informationen zu den bestimmten universellen Gruppen, die während der Vorbereitung von AD für Lync Server erstellt werden, sowie den Dienst- und Administrationgruppen, die den Infrastrukturgruppen hinzugefügt werden, finden Sie in der Bereitstellungsdokumentation unter [Änderungen bei der Gesamtstrukturvorbereitung in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md).


> [!NOTE]
> Lync Server 2013 unterstützt die universellen Gruppen in den Betriebssystemen Windows Server 2012 für Server mit Lync Server 2013 und Windows Server 2003 für Domänencontroller. Mitglieder universeller Gruppen können andere Gruppen und Konten aus beliebigen Domänen in der Domänen- oder Gesamtstruktur umfassen und über Berechtigungen für beliebige Domänen in der Domänen- oder Gesamtstruktur verfügen. Durch die Unterstützung universeller Gruppen in Verbindung mit der Delegierung administrativer Aufgaben wird die Verwaltung einer Lync Server-Bereitstellung vereinfacht. Beispielsweise ist es nicht erforderlich, eine Domäne einer anderen hinzuzufügen, um einem Administrator die Verwaltung beider Domänen zu ermöglichen.



## Rollenbasierte Zugriffssteuerung

Zusätzlich zum Erstellen von universellen Dienst- und Administrationsgruppen und Hinzufügen von Dienst- und Administrationsgruppen zu den entsprechenden universellen Gruppen werden bei der Gesamtstrukturvorbereitung auch rollenbasierte Zugriffssteuerungsgruppen (RBAC-Gruppen) erstellt. Ausführliche Informationen zu bestimmten bei der Gesamtstrukturvorbereitung erstellten RBAC-Gruppen finden Sie in der Bereitstellungsdokumentation unter [Änderungen bei der Gesamtstrukturvorbereitung in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) Weitere Informationen zu RBAC-Gruppen finden Sie unter [Rollenbasierte Zugriffskontrolle (RBAC) für Lync Server 2013](lync-server-2013-role-based-access-control-rbac.md).

## Zugriffssteuerungseinträge (Access Control Entries,ACEs) und Vererbung

Bei der Gesamtstrukturvorbereitung werden sowohl private als auch öffentliche ACEs erstellt und ACEs zu den erstellten universellen Gruppen hinzugefügt. Bestimmte private ACEs werden im Container mit den globalen Einstellungen erstellt, der von Lync Server verwendet wird. Dieser Container wird ausschließlich von Lync Server verwendet und befindet sich entweder im Konfigurationscontainer oder im Systemcontainer der Stammdomäne (abhängig davon, wo Sie die globalen Einstellungen speichern).

Beim Schritt zur Domänenvorbereitung werden universellen Gruppen die erforderlichen ACEs (Access Control Entries, Zugriffssteuerungseinträge) hinzugefügt, über die Berechtigungen zum Hosten und Verwalten von Benutzern in der Domäne gewährt werden. Bei der Domänenvorbereitung werden ACEs im Domänenstamm und in drei integrierten Containern erstellt: für Benutzer, Computer und Domänencontroller.

Ausführliche Informationen zu den öffentlichen ACEs, die bei der Gesamtstruktur- und Domänenvorbereitung erstellt und hinzugefügt werden, finden Sie in der Bereitstellungsdokumentation unter [Änderungen bei der Gesamtstrukturvorbereitung in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) und [Änderungen bei der Domänenvorbereitung in Lync Server 2013](lync-server-2013-changes-made-by-domain-preparation.md).

Unternehmen sperren Active Directory-Domänendienste (AD DS) oft, um Sicherheitsrisiken zu mindern. Aber in einer gesperrten Active Directory-Umgebung können die Berechtigungen begrenzt sein, die für Lync Server 2013 erforderlich sind. Dazu kann das Entfernen von ACEs aus Containern und Organisationseinheiten und das Deaktivieren der Vererbung von Berechtigungen für Benutzer-, Kontakt-, InetOrgPerson- oder Computerobjekten gehören. In einer gesperrten Active Directory-Umgebung müssen Berechtigungen für Container und Organisationseinheiten, die diese benötigen, manuell festgelegt werden. Ausführliche Informationen finden Sie in der Bereitstellungsdokumentation unter [Vorbereiten gesperrter Active Directory-Domänendienste in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).

## Serverinformationen

Während der Aktivierung veröffentlicht Lync Server 2013 Serverinformationen an die folgenden drei Standorte in Active Directory-Domänendienste:

  - Einen Dienstverbindungspunkt in jedem Active Directory-Computerobjekt, das einem physischen Computer entspricht, auf dem Lync Server 2013 installiert ist

  - Serverobjekte, die im Container der Klasse **msRTCSIP-Pools** erstellt wurde

  - Vertrauenswürdige Server, die in Topologie-Generator angegeben sind

## Dienstverbindungspunkte

Jedes Lync Server 2013-Objekt in Active Directory-Domänendienste hat einen Dienstverbindungspunkt namens RTC Services, der wiederum eine Reihe von Attributen enthält, die jeden Computer identifizieren und die Dienste angeben, die dieser bereitstellt. Zu den wichtigeren Attributen der Dienstverbindungspunkte zählen *serviceDNSName*, *serviceDNSNameType*, *serviceClassname* und *serviceBindingInformation*. Asset Management-Anwendungen von Drittanbietern können Serverinformationen bereitstellungsübergreifend abrufen, indem sie diese und andere Attribute von Dienstverbindungspunkten anfragen.

## Active Directory Serverobjekte

Jede Lync Server 2013-Serverrolle hat ein entsprechendes Active Directory-Objekt, dessen Attribute die von dieser Rolle bereitgestellten Dienste definieren. Wenn ein Standard Edition-Server aktiviert oder ein Enterprise Edition-Pool erstellt wird, erstellt Lync Server 2013 zudem ein neues Objekt **msRTCSIP-Pool** im Container **msRTCSIP-Pools**. Die Klasse **msRTCSIP-Pool** gibt den vollständig qualifizierten Domänennamen (FQDN) des Pools sowie die Verbindung zwischen den Front-End- und Back-End-Komponenten des Pools an. (Ein Standard Edition-Server wird als ein logischer Pool betrachtet, dessen Front- und Back-Ends auf einem einzigen Computer verbunden sind.)

## Vertrauenswürdige Server

In Lync Server 2013 sind vertrauenswürdige Server die Server, die angegeben werden, wenn Sie Topologie-Generator ausführen und Ihre Topologie veröffentlichen. Die veröffentlichte Topologie wird, einschließlich aller Serverinformationen, im zentralen Verwaltungsspeicher gespeichert. Nur die im zentralen Verwaltungsspeicher definierten Server sind vertrauenswürdig. In Lync Server 2013 muss ein vertrauenswürdiger Server die folgenden Kriterien erfüllen:

  - Der FQDN des Servers ist in der im zentralen Verwaltungsspeicher gespeicherten Topologie enthalten.

  - Der Server verfügt über ein gültiges Zertifikat von einer vertrauenswürdigen Zertifizierungsstelle. Ausführliche Informationen finden Sie unter [Anforderungen in Bezug auf die Zertifikatinfrastruktur für Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md).

Wird eins dieser Kriterien nicht erfüllt, ist der Server nicht vertrauenswürdig, und die Verbindung mit ihm wird abgelehnt. Diese doppelte Anforderung verhindert einen möglichen, wenn auch unwahrscheinlichen, Angriff, bei dem ein nicht autorisierter Server versucht, den FQDN eines gültigen Servers zu übernehmen.

Damit Microsoft Office Communications Server 2007 R2- und Microsoft Office Communications Server 2007-Bereitstellungen mit Lync Server 2013-Servern kommunizieren können, erstellt Lync Server 2013 außerdem während der Gesamtstrukturvorbereitung Container zum Speichern von Listen vertrauenswürdiger Server für frühere Versionen. In der folgenden Tabelle sind die für die Kompatibilität mit früheren Bereitstellungen erstellten Container beschrieben.

### Liste vertrauenswürdiger Server und ihre Active Directory-Container für Kompatibilität mit früheren Versionen

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Liste vertrauenswürdiger Server</th>
<th>Active Directory-Container</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Standard Edition-Server und Enterprise-Pool-Front-End-Server</p></td>
<td><p>RTC Service/Global Settings</p></td>
</tr>
<tr class="even">
<td><p>Konferenzserver</p></td>
<td><p>RTC Service/Trusted MCUs</p></td>
</tr>
<tr class="odd">
<td><p>Webkomponentenserver</p></td>
<td><p>RTC Service/TrustedWebComponentsServers</p></td>
</tr>
<tr class="even">
<td><p>Vermittlungsservers und Communicator Web Access-Server, Anwendungsserver, Registrierung mit QoE, A/V-Konferenzdienst (auch SIP-Server von Drittanbietern)</p></td>
<td><p>RTC Service/Trusted Services</p></td>
</tr>
<tr class="odd">
<td><p>Proxyserver</p></td>
<td><p>Lync Server 2013 unterstützt keine Rückwärtskompatibilität für Proxyserver.</p></td>
</tr>
</tbody>
</table>


Um vertrauenswürdige Server aus früheren Versionen zu unterstützen, müssen Sie das Best Practices Analyzer-Tool ausführen. Ausführliche Informationen zum Ausführen von Best Practices Analyzer finden Sie unter [http://go.microsoft.com/fwlink/p/?LinkId=330633](http://go.microsoft.com/fwlink/p/?linkid=330633).

