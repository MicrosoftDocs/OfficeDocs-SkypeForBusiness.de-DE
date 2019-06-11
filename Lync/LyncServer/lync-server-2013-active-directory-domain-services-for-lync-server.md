---
title: 'Lync Server 2013: Active Directory-Domänendienste für lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Active Directory Domain Services for Lync Server 2013
ms:assetid: 5483afd5-d8af-4825-ae95-a82dbe941dbf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481129(v=OCS.15)
ms:contentKeyID: 59893871
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9a7dd0a5d5c6d8323abab3a8abfbc5f1025379e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839963"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-domain-services-for-lync-server-2013"></a>Active Directory-Domänendienste für lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-11-13_

Active Directory-Domänendienste fungiert als Verzeichnisdienst für Windows Server 2003, Windows Server 2008, Windows Server 2012 und Windows Server 2012 R2-Netzwerke. Active Directory-Domänendienste dient auch als Grundlage für die Erstellung der Microsoft lync Server 2013-Sicherheitsinfrastruktur. In diesem Abschnitt wird beschrieben, wie lync Server 2013 die Active Directory-Domänendienste zum Erstellen einer vertrauenswürdigen Umgebung für Chats, Webkonferenzen, Medien und Sprachanrufe verwendet. Details zu den lync-Server Erweiterungen für Active Directory-Domänendienste und zum Vorbereiten Ihrer Umgebung für Active Directory-Domänendienste finden Sie unter [Vorbereiten der Active Directory-Domänendienste für lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in der Bereitstellung. Dokumentation. Details zur Rolle der Active Directory-Domänendienste in Windows Server-Netzwerken finden Sie in der Dokumentation zur Version des verwendeten Betriebssystems.

Lync Server 2013 verwendet die Active Directory-Domänendienste zum Speichern von:

  - Globale Einstellungen, die auf allen Servern mit lync Server 2013 in einer Gesamtstruktur erforderlich sind.

  - Dienstinformationen, die die Rollen aller Server mit lync Server 2013 in einer Gesamtstruktur identifizieren.

  - Einige Benutzereinstellungen

<div>

## <a name="active-directory-infrastructure"></a>Active Directory-Infrastruktur

Zu den Infrastrukturanforderungen für Active Directory gehören die folgenden:

  - Betriebssystemanforderungen für Domänencontroller

  - Anforderungen für die Domänen- und Gesamtstrukturfunktionsebene

  - Anforderungen für die globale Katalogdomäne

Ausführliche Informationen finden Sie unter Anforderungen an die [Active Directory-Infrastruktur für lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) in der Bereitstellungsdokumentation.

</div>

<div>

## <a name="active-directory-domain-services-preparation"></a>Vorbereitung der Active Directory-Domänendienste

<div>


> [!NOTE]  
> Wir empfehlen, dass Sie die globalen Einstellungen für den Konfigurationscontainer anstelle des System Containers bereitstellen. Dies verbessert nicht die Sicherheit, kann aber zu Verbesserungen bei der Skalierbarkeit einiger Active Directory-Domänendienste-Topologien führen. Wenn Sie von Microsoft Office Communications Server 2007 migrieren und den Systemcontainer verwendet haben, aber den Konfigurationscontainer verwenden möchten, müssen Sie die Einstellungen im Systemcontainer verschieben, bevor Sie ein Upgrade vorbereiten. Informationen zum Migrieren der System Container Einstellungen zum Konfigurationscontainer finden Sie unter Office Communications Server 2007-Migrations Tool für <A href="http://go.microsoft.com/fwlink/p/?linkid=145236">http://go.microsoft.com/fwlink/p/?LinkId=145236</A>globale Einstellungen unter.



</div>

Beim Bereitstellen von lync Server 2013 besteht der erste Schritt darin, Active Directory-Domänendienste vorzubereiten. Das Vorbereiten der Active Directory-Domänendienste für lync Server 2013 umfasst die folgenden drei Schritte:

  - **Schema vorbereiten**. Mit dieser Aufgabe wird das Schema in den Active Directory-Domänendiensten so erweitert, dass es Klassen und Attribute enthält, die für lync Server 2013 spezifisch sind. Details zum Vorbereiten des Schemas finden Sie unter [Ausführen der Active Directory-Schemavorbereitung in lync Server 2013](lync-server-2013-running-schema-preparation.md) in der Bereitstellungsdokumentation. Weitere Informationen finden Sie unter [Migration von Office Communications Server 2007 R2 zu lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md).

  - **Vorbereiten der Gesamtstruktur** Mit dieser Aufgabe werden globale Einstellungen und Objekte in der Gesamtstruktur-Stammdomäne sowie der universelle Dienst und administrative Gruppen erstellt, die den Zugriff auf diese Einstellungen und Objekte Regeln. Details zum Vorbereiten der Gesamtstruktur finden Sie unter [Ausführen der Gesamtstrukturvorbereitung für lync Server 2013](lync-server-2013-running-forest-preparation.md) in der Bereitstellungsdokumentation.

  - **Domäne vorbereiten**. Mit dieser Aufgabe werden universelle Gruppen, die Berechtigungen zum Hosten und Verwalten von Benutzern innerhalb der Domäne erteilen, die erforderlichen Zugriffssteuerungseinträge (ACEs) hinzugefügt. Diese Aufgabe muss in allen Domänen ausgeführt werden, in denen Sie Server mit lync Server 2013 und alle Domänen bereitstellen möchten, in denen sich Ihre lync Server-Benutzer befinden. Details zum Vorbereiten der Domäne finden Sie unter [Ausführen der Domänenvorbereitung für lync Server 2013](lync-server-2013-running-domain-preparation.md) in der Bereitstellungsdokumentation.

Eine Übersicht über den vollständigen Prozess zum Vorbereiten von Active Directory sowie über die für die einzelnen Schritte erforderlichen Rechte und Berechtigungen finden Sie unter [Active Directory Infrastructure Requirements for lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) in der Bereitstellungsdokumentation.

</div>

<div>

## <a name="universal-groups"></a>Universelle Gruppen

Während der Vorbereitung der Gesamtstruktur erstellt lync Server 2013 verschiedene universelle Gruppen in Active Directory-Domänendiensten, die über die Berechtigung zum Zugriff auf und Verwalten globaler Einstellungen und Dienste verfügen. Zu diesen Gruppen zählen die folgenden:

  - **Administrative Gruppen:** Diese Gruppen definieren die grundlegenden Administratorrollen für ein lync Server-Netzwerk. Während der Gesamtstrukturvorbereitung werden diese Administratorgruppen den lync Server-Infrastrukturgruppen hinzugefügt.

  - **Dienstgruppen:** Diese Gruppen sind Dienstkonten, die für den Zugriff auf verschiedene Dienste erforderlich sind, die von lync Server bereitgestellt werden.

  - **Infrastrukturgruppen:** Diese Gruppen bieten die Berechtigung für den Zugriff auf bestimmte Bereiche der lync Server-Infrastruktur. Sie dienen als Komponenten von administrativen Gruppen und Sie sollten sie weder ändern noch ihnen direkt Nutzer hinzufügen. Während der Gesamtstrukturvorbereitung werden den entsprechenden Infrastrukturgruppen bestimmte Dienst- und Administrationsgruppen hinzugefügt.

Details zu den spezifischen universellen Gruppen, die beim Vorbereiten von AD für lync Server erstellt wurden, sowie zu den Dienst-und Verwaltungsgruppen, die den Infrastrukturgruppen hinzugefügt werden, finden Sie unter [Änderungen der Gesamtstrukturvorbereitung in lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) im Bereitstellungsdokumentation

<div>


> [!NOTE]  
> Lync Server 2013 unterstützt die universellen Gruppen in Windows Server 2012 für Server, auf denen lync Server 2013 ausgeführt wird, sowie Windows Server 2003-Betriebssysteme für Domänencontroller. Mitglieder universeller Gruppen können andere Gruppen und Konten aus beliebigen Domänen in der Domänen- oder Gesamtstruktur umfassen und über Berechtigungen für beliebige Domänen in der Domänen- oder Gesamtstruktur verfügen. Die Unterstützung für universelle Gruppen in Verbindung mit der Administrator Delegierung vereinfacht die Verwaltung einer lync Server-Bereitstellung. Beispielsweise ist es nicht erforderlich, eine Domäne einer anderen hinzuzufügen, um einem Administrator die Verwaltung beider Domänen zu ermöglichen.



</div>

</div>

<div>

## <a name="role-based-access-control"></a>Rollenbasierte Zugriffssteuerung

Zusätzlich zum Erstellen von Gruppen für universelle Dienste und Administratoren sowie zum Hinzufügen von Dienst-und Verwaltungsgruppen zu den entsprechenden universellen Gruppen erstellt die Gesamtstrukturvorbereitung auch Rollenbasierte Zugriffssteuerungsgruppen. Details zu den von der Gesamtstrukturvorbereitung erstellten speziellen RBAC-Gruppen finden Sie unter Änderungen, die [von der Gesamtstrukturvorbereitung in lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) in der Bereitstellungsdokumentation vorgenommen wurden. Weitere Informationen zu RBAC-Gruppen finden Sie unter [rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC) für lync Server 2013](lync-server-2013-role-based-access-control-rbac.md).

</div>

<div>

## <a name="access-control-entries-aces-and-inheritance"></a>Zugriffssteuerungseinträge (Access Control Entries,ACEs) und Vererbung

Bei der Gesamtstrukturvorbereitung werden sowohl private als auch öffentliche ACEs erstellt und ACEs zu den erstellten universellen Gruppen hinzugefügt. Es werden bestimmte private ACEs im Container für globale Einstellungen erstellt, der von lync Server verwendet wird. Dieser Container wird nur von lync Server verwendet und befindet sich entweder im Konfigurationscontainer oder im System Container in der Stammdomäne, je nachdem, wo Sie die globalen Einstellungen speichern.

Beim Schritt zur Domänenvorbereitung werden universellen Gruppen die erforderlichen ACEs (Access Control Entries, Zugriffssteuerungseinträge) hinzugefügt, über die Berechtigungen zum Hosten und Verwalten von Benutzern in der Domäne gewährt werden. Bei der Domänenvorbereitung werden ACEs im Domänenstamm und in drei integrierten Containern erstellt: für Benutzer, Computer und Domänencontroller.

Details zu den öffentlichen ACEs, die von der Gesamtstrukturvorbereitung und Domänenvorbereitung erstellt und hinzugefügt wurden, finden Sie unter [Änderungen der Gesamtstrukturvorbereitung in lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) und Änderungen, die [von der Domänenvorbereitung in lync Server 2013](lync-server-2013-changes-made-by-domain-preparation.md) in der Bereitstellung vorgenommen wurden. Dokumentation.

Organisationen Sperren häufig Active Directory-Domänendienste (AD DS), um Sicherheitsrisiken zu minimieren. Eine gesperrte Active Directory-Umgebung kann jedoch die von lync Server 2013 erforderlichen Berechtigungen einschränken. Dazu kann das Entfernen von ACEs aus Containern und Organisationseinheiten und das Deaktivieren der Vererbung von Berechtigungen für Nutzer-, Kontakt-, InetOrgPerson- oder Computerobjekten gehören. In einer gesperrten Active Directory-Umgebung müssen Berechtigungen für Container und OUs, für die Sie erforderlich sind, manuell festgelegt werden. Ausführliche Informationen finden Sie unter [Vorbereiten einer gesperrten Active Directory-Domänendienste in lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) in der Bereitstellungsdokumentation.

</div>

<div>

## <a name="server-information"></a>Serverinformationen

Während der Aktivierung veröffentlicht lync Server 2013 Server Informationen an den drei folgenden Speicherorten in den Active Directory-Domänendiensten:

  - Einen Dienstverbindungspunkt (Service Connection Point, SCP) für jedes Active Directory-Computerobjekt, das einem physikalischen Computer entspricht, auf dem lync Server 2013 installiert ist.

  - Serverobjekte, die im Container der Klasse **msRTCSIP-Pools** erstellt wurden

  - Im Topologie-Generator angegebene vertrauenswürdige Server.

</div>

<div>

## <a name="service-connection-points"></a>Dienstverbindungspunkte

Jedes lync Server 2013-Objekt in den Active Directory-Domänendiensten verfügt über einen SCP namens RTC Services, der wiederum eine Reihe von Attributen enthält, die jeden Computer identifizieren und die bereitgestellten Dienste angeben. Zu den wichtigeren Attributen der Dienstverbindungspunkte zählen *serviceDNSName *, *serviceDNSNameType*, *serviceClassname* und *serviceBindingInformation *. Asset Management-Anwendungen von Drittanbietern können Serverinformationen bereitstellungsübergreifend abrufen, indem sie diese und andere Attribute von Dienstverbindungspunkten anfragen.

</div>

<div>

## <a name="active-directory-server-objects"></a>Active Directory-Server Objekte

Jede lync Server 2013-Serverrolle verfügt über ein entsprechendes Active Directory-Objekt, dessen Attribute die von dieser Rolle bereitgestellten Dienste definieren. Wenn ein Standard Edition-Server aktiviert ist oder wenn ein Enterprise Edition-Pool erstellt wird, erstellt lync Server 2013 ein neues **Attribut msRTCSIP-** Objekt im Container **Attribut msRTCSIP-Pools** . Die **msRTCSIP-Pool**-Klasse gibt den vollständig qualifizierten Domänennamen (FQDN) des Pools sowie die Verbindung zwischen den Front-End- und Back-End-Komponenten des Pools an. (Ein Standard Edition-Server wird als logischer Pool angesehen, dessen Front-und Back-Ends auf einem einzelnen Computer angeordnet sind.)

</div>

<div>

## <a name="trusted-servers"></a>Vertrauenswürdige Server

In lync Server 2013 sind vertrauenswürdige Server diejenigen, die beim Ausführen des Topologie-Generators und Veröffentlichen Ihrer Topologie angegeben werden. Die veröffentlichte Topologie wird einschließlich aller Serverinformationen im zentralen Verwaltungsspeicher gespeichert. Nur die im zentralen Verwaltungsspeicher definierten Server sind vertrauenswürdig. In lync Server 2013 ist ein vertrauenswürdiger Server einer, der die folgenden Kriterien erfüllt:

  - Der FQDN des Servers ist in der im zentralen Verwaltungsspeicher gespeicherten Topologie enthalten.

  - Der Server verfügt über ein gültiges Zertifikat von einer vertrauenswürdigen Zertifizierungsstelle. Ausführliche Informationen finden Sie unter Anforderungen an die [Zertifikatinfrastruktur für lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md).

Wird eins dieser Kriterien nicht erfüllt, ist der Server nicht vertrauenswürdig, und die Verbindung mit ihm wird abgelehnt. Diese doppelte Anforderung verhindert einen möglichen, wenn auch unwahrscheinlichen, Angriff, bei dem ein nicht autorisierter Server versucht, den FQDN eines gültigen Servers zu übernehmen.

Damit Microsoft Office Communications Server 2007 R2 und Microsoft Office Communications Server 2007-Bereitstellungen mit lync Server 2013-Servern kommunizieren können, erstellt lync Server 2013 Container während der Gesamtstrukturvorbereitung für das halten von Listen von vertrauenswürdige Server für frühere Versionen. In der folgenden Tabelle sind die für die Kompatibilität mit früheren Bereitstellungen erstellten Container beschrieben.

### <a name="trusted-server-lists-and-their-active-directory-containers-for-compatibility-with-previous-releases"></a>Vertrauenswürdige Server Listen und deren Active Directory-Container zur Kompatibilität mit früheren Versionen

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
<td><p>Lync Server 2013 unterstützt keine Abwärtskompatibilität für Proxy Server</p></td>
</tr>
</tbody>
</table>


Zur Unterstützung von vertrauenswürdigen Servern vorheriger Versionen müssen Sie das Tool bewährte Methoden Analyzer ausführen. Details zum Ausführen des Best Practices Analyzer finden Sie [http://go.microsoft.com/fwlink/p/?LinkId=330633](http://go.microsoft.com/fwlink/p/?linkid=330633)unter.

</div>

</div>

<span> </span>

</div>

</div>

</div>

