---
title: 'Lync Server 2013: Active Directory-Domänendienste für lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory Domain Services for Lync Server 2013
ms:assetid: 5483afd5-d8af-4825-ae95-a82dbe941dbf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481129(v=OCS.15)
ms:contentKeyID: 59893871
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a5a4e548f68f68a65ac4ecfb2e4ddc532b5f337c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529712"
---
# <a name="active-directory-domain-services-for-lync-server-2013"></a>Active Directory-Domänendienste für lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-11-13_

Active Directory-Domänendienste fungiert als Verzeichnisdienst für Windows Server 2003-, Windows Server 2008-, Windows Server 2012-und Windows Server 2012 R2-Netzwerke. Active Directory-Domänendienste dient auch als Grundlage, auf der die Microsoft lync Server 2013 Sicherheitsinfrastruktur aufgebaut ist. In diesem Abschnitt wird beschrieben, wie lync Server 2013 Active Directory-Domänendienste verwendet, um eine vertrauenswürdige Umgebung für Chat, Webkonferenzen, Medien und VoIP zu erstellen. Ausführliche Informationen zu lync Server Erweiterungen für Active Directory-Domänendienste und zur Vorbereitung Ihrer Umgebung auf Active Directory-Domänendienste finden Sie unter [vorbereiten Active Directory-Domänendienste für lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in der Bereitstellungsdokumentation. Ausführliche Informationen zur Rolle der Active Directory-Domänendienste in Windows Server-Netzwerken finden Sie in der Dokumentation für die Version des von Ihnen verwendeten Betriebssystems.

Lync Server 2013 verwendet Active Directory-Domänendienste zum Speichern von:

  - Globale Einstellungen, die alle lync Server 2013 in einer Gesamtstruktur ausgeführten Server benötigen.

  - Dienstinformationen, mit denen die Rollen aller Server identifiziert werden, auf denen lync Server 2013 in einer Gesamtstruktur ausführt.

  - Einige Benutzereinstellungen

<div>

## <a name="active-directory-infrastructure"></a>Active Directory-Infrastruktur

Für Active Directory gelten die folgenden Infrastrukturanforderungen:

  - Betriebssystemanforderungen für Domänencontroller

  - Anforderungen bezüglich der Funktionsebene der Domäne und der Gesamtstruktur

  - Domänenanforderungen bezüglich des globalen Katalogs

Ausführliche Informationen finden Sie unter [Active Directory Infrastrukturanforderungen für lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) in der Bereitstellungsdokumentation.

</div>

<div>

## <a name="active-directory-domain-services-preparation"></a>Vorbereiten der Active Directory-Domänendienste

<div>


> [!NOTE]  
> Es wird empfohlen, globale Einstellungen nicht im Systemcontainer, sondern im Konfigurationscontainer bereitzustellen. Dadurch wird zwar die Sicherheit nicht optimiert, aber es kann zu Verbesserungen bei der Skalierbarkeit für einige Topologien der Active Directory-Domänendienste führen. Wenn Sie von Microsoft Office Communications Server 2007 migrieren und den Systemcontainer verwendet haben, aber den Konfigurationscontainer verwenden möchten, müssen Sie die Einstellungen im Systemcontainer verschieben, bevor Sie ein Upgrade vorbereiten. Informationen zum Migrieren der System Container Einstellungen zum Konfigurationscontainer finden Sie unter Office Communications Server 2007 Migration Tool Global Settings unter <A href="https://go.microsoft.com/fwlink/p/?linkid=145236">https://go.microsoft.com/fwlink/p/?LinkId=145236</A> .



</div>

Bei der Bereitstellung von lync Server 2013 besteht der erste Schritt darin, Active Directory-Domänendienste vorzubereiten. Das Vorbereiten Active Directory-Domänendienste für lync Server 2013 umfasst die folgenden drei Schritte:

  - **Vorbereiten des Schemas**. Diese Aufgabe erweitert das Schema in Active Directory-Domänendienste auf Klassen und Attribute, die spezifisch für lync Server 2013 sind. Ausführliche Informationen zum Vorbereiten des Schemas finden Sie unter [Running Active Directory Schema Preparation in lync Server 2013](lync-server-2013-running-schema-preparation.md) in der Bereitstellungsdokumentation. Weitere Informationen finden Sie unter [Migration from Office Communications Server 2007 R2 to lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md).

  - **Vorbereiten der Gesamtstruktur** Mit dieser Aufgabe werden globale Einstellungen und Objekte in der Gesamtstruktur-Stammdomäne sowie der universelle Dienst und administrative Gruppen erstellt, die den Zugriff auf diese Einstellungen und Objekte steuern. Ausführliche Informationen zum Vorbereiten der Gesamtstruktur finden Sie unter [Ausführung der Gesamtstrukturvorbereitung für lync Server 2013](lync-server-2013-running-forest-preparation.md) in der Bereitstellungsdokumentation.

  - **Vorbereiten der Domäne**. Diese Aufgabe fügt universelle Gruppen die erforderlichen Zugriffssteuerungseinträge (Access Control Entries, ACEs) hinzu, die Berechtigungen zum Hosten und Verwalten von Benutzern in der Domäne erteilen. Diese Aufgabe muss in allen Domänen abgeschlossen sein, in denen Sie Server mit lync Server 2013 und Domänen bereitstellen möchten, in denen sich Ihre lync Server Benutzer befinden. Ausführliche Informationen zum Vorbereiten der Domäne finden Sie unter [Ausführung der Domänenvorbereitung für lync Server 2013](lync-server-2013-running-domain-preparation.md) in der Bereitstellungsdokumentation.

Eine Übersicht über den vollständigen Prozess für die Vorbereitung Active Directory und die erforderlichen Rechte und Berechtigungen zum Ausführen der einzelnen Schritte finden Sie unter [Active Directory Infrastrukturanforderungen für lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) in der Bereitstellungsdokumentation.

</div>

<div>

## <a name="universal-groups"></a>Universelle Gruppen

Während der Vorbereitung der Gesamtstruktur erstellt lync Server 2013 verschiedene universelle Gruppen in Active Directory-Domänendienste, die über die Berechtigung zum Zugreifen auf und Verwalten globaler Einstellungen und Dienste verfügen. Dazu gehören folgende universelle Gruppen:

  - **Administrative Gruppen**. Diese Gruppen definieren die grundlegenden Administratorrollen für ein lync Server Netzwerk. Während der Gesamtstrukturvorbereitung werden diese Administratorgruppen zu lync Server-Infrastrukturgruppen hinzugefügt.

  - **Dienstgruppen**. Diese Gruppen sind Dienstkonten, die für den Zugriff auf verschiedene von lync Server bereitgestellte Dienste erforderlich sind.

  - **Infrastrukturgruppen**. Diese Gruppen bieten die Berechtigung für den Zugriff auf bestimmte Bereiche der lync Server Infrastruktur. Es sollten keine Infrastrukturgruppen geändert oder Benutzer direkt zu ihnen hinzugefügt werden. Während der Gesamtstrukturvorbereitung werden bestimmte Dienst-und Verwaltungsgruppen zu den entsprechenden Infrastrukturgruppen hinzugefügt.

Ausführliche Informationen zu den spezifischen universellen Gruppen, die beim Vorbereiten von AD für lync Server erstellt werden, sowie zu den Dienst-und Verwaltungsgruppen, die den Infrastrukturgruppen hinzugefügt werden, finden Sie unter Änderungen, die [von der Gesamtstrukturvorbereitung in lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) in der Bereitstellungsdokumentation vorgenommen wurden.

<div>


> [!NOTE]  
> Lync Server 2013 unterstützt die universellen Gruppen im Windows Server 2012 für Server, auf denen lync Server 2013 läuft, sowie Windows Server 2003 Betriebssysteme für Domänencontroller. Mitglieder universeller Gruppen können andere Gruppen und Konten aus beliebigen Domänen in der Domänen- oder Gesamtstruktur umfassen und über Berechtigungen für beliebige Domänen in der Domänen- oder Gesamtstruktur verfügen. Die universelle Gruppenunterstützung in Kombination mit der Administrator Delegierung vereinfacht die Verwaltung einer lync Server-Bereitstellung. Beispielsweise ist es nicht erforderlich, eine Domäne einer anderen Domäne hinzuzufügen, um einem Administrator die Verwaltung beider Domänen zu ermöglichen.



</div>

</div>

<div>

## <a name="role-based-access-control"></a>Rollenbasierte Zugriffssteuerung

Neben dem Erstellen von universellen Dienst-und Verwaltungsgruppen und dem Hinzufügen von Dienst-und Verwaltungsgruppen zu den entsprechenden universellen Gruppen erstellt die Gesamtstrukturvorbereitung auch Role-Based Zugriffssteuerungsgruppen (RBAC). Ausführliche Informationen zu den spezifischen RBAC-Gruppen, die von der Gesamtstrukturvorbereitung erstellt werden, finden Sie unter Änderungen bei der [Gesamtstrukturvorbereitung in lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) in der Bereitstellungsdokumentation. Weitere Informationen zu RBAC-Gruppen finden Sie unter [Role-Based Access Control (RBAC) für lync Server 2013](lync-server-2013-role-based-access-control-rbac.md).

</div>

<div>

## <a name="access-control-entries-aces-and-inheritance"></a>Zugriffssteuerungseinträge und Vererbung

Bei der Gesamtstrukturvorbereitung werden sowohl private als auch öffentliche Zugriffssteuerungseinträge (Access Control Entries, ACEs) erstellt sowie ACEs für die erstellten universellen Gruppen hinzugefügt. Es werden bestimmte private ACEs im Container "globale Einstellungen" erstellt, der von lync Server verwendet wird. Dieser Container wird nur von lync Server verwendet und befindet sich in Abhängigkeit davon, wo Sie globale Einstellungen speichern, entweder im Konfigurationscontainer oder im System Container in der Stammdomäne.

Beim Schritt zur Domänenvorbereitung werden universellen Gruppen die erforderlichen Zugriffssteuerungseinträge (Access Control Entries, ACEs) hinzugefügt, über die Berechtigungen zum Hosten und Verwalten von Benutzern in der Domäne gewährt werden. Bei der Domänenvorbereitung werden ACEs im Domänenstamm und in drei integrierten Containern erstellt: für Benutzer, Computer und Domänencontroller.

Ausführliche Informationen zu den öffentlichen ACEs, die von der Gesamtstrukturvorbereitung und der Domänenvorbereitung erstellt und hinzugefügt wurden, finden Sie unter Änderungen bei der [Gesamtstrukturvorbereitung in lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) und Änderungen, die [von der Domänenvorbereitung in lync Server 2013](lync-server-2013-changes-made-by-domain-preparation.md) in der Bereitstellungsdokumentation vorgenommen wurden.

In Organisationen werden die Active Directory-Domänendienste (Active Directory Domain Services, AD DS) häufig gesperrt, um Sicherheitsrisiken nach Möglichkeit auszuschließen. Eine gesperrte Active Directory Umgebung kann jedoch die Berechtigungen einschränken, die lync Server 2013 erfordert. Dies kann das Entfernen von ACEs aus Containern und Organisationseinheiten (Organizational Units, OUs) und das Deaktivieren der Vererbung von Berechtigungen für Benutzer-, Kontakt-, InetOrgPerson- oder Computerobjekte beinhalten. In einer gesperrten Active Directory-Umgebung müssen Berechtigungen manuell für die entsprechenden Container und Organisationseinheiten festgelegt werden. Ausführliche Informationen finden Sie unter [Vorbereiten einer gesperrten Active Directory-Domänendienste in lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) in der Bereitstellungsdokumentation.

</div>

<div>

## <a name="server-information"></a>Serverinformationen

Während der Aktivierung veröffentlicht lync Server 2013 Server Informationen an den drei folgenden Speicherorten in Active Directory-Domänendienste:

  - Einen Dienstverbindungspunkt (Service Connection Points, SCP) auf jedem Active Directory Computerobjekt, das einem physischen Computer entspricht, auf dem lync Server 2013 installiert ist.

  - Serverobjekte, die im Container der **msRTCSIP-Pools**-Klasse erstellt wurden

  - Im Topologie-Generator angegebene vertrauenswürdige Server.

</div>

<div>

## <a name="service-connection-points"></a>Dienstverbindungspunkte

Jedes lync Server 2013-Objekt in Active Directory-Domänendienste verfügt über einen SCP namens RTC Services, der wiederum eine Reihe von Attributen enthält, mit denen jeder Computer identifiziert und die bereitgestellten Dienste angegeben werden. Zu den wichtigsten SCP-Attributen gehören *servicednsname*, *serviceDNSNameType*, *serviceClassName*und *serviceBindingInformation*. Asset Management-Anwendungen von Drittanbietern können Server Informationen in einer Bereitstellung abrufen, indem Sie diese und andere SCP-Attribute Abfragen.

</div>

<div>

## <a name="active-directory-server-objects"></a>Active Directory-Serverobjekte

Jede lync Server 2013 Server Rolle verfügt über ein entsprechendes Active Directory-Objekt, dessen Attribute die von dieser Rolle bereitgestellten Dienste definieren. Wenn ein Standard Edition-Server aktiviert wird oder ein Enterprise Edition-Pool erstellt wird, erstellt lync Server 2013 außerdem ein neues **msRTCSIP-** Objekt im **msRTCSIP-Pool-** Container. In der **msRTCSIP-Pool**-Klasse werden der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des Pools und die Zuordnung zwischen Front-End- und Back-End-Komponenten des Pools festgelegt. (Ein Standard Edition-Server wird als logischer Pool betrachtet, dessen Front- und Back-Ends gemeinsam auf einem einzigen Computer ausgeführt werden.)

</div>

<div>

## <a name="trusted-servers"></a>Vertrauenswürdige Server

In lync Server 2013 sind vertrauenswürdige Server diejenigen, die beim Ausführen des Topologie-Generators und Veröffentlichen Ihrer Topologie angegeben werden. Die veröffentlichte Topologie, einschließlich aller Serverinformationen, wird im zentralen Verwaltungsspeicher gespeichert. Nur im zentralen Verwaltungsspeicher definierte Server sind vertrauenswürdig. In lync Server 2013 ist ein vertrauenswürdiger Server einer, der die folgenden Kriterien erfüllt:

  - Der vollqualifizierte Domänenname (FQDN) des Servers ist in der im zentralen Verwaltungsspeicher gespeicherten Topologie vorhanden.

  - Der Server verfügt über ein gültiges Zertifikat von einer vertrauenswürdigen Zertifizierungsstelle. Ausführliche Informationen finden Sie unter [Certificate Infrastructure Requirements for lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md).

Wenn eines dieser Kriterien nicht zutrifft, gilt der Server nicht als vertrauenswürdig und es wird keine Verbindung damit hergestellt. Diese doppelte Anforderung soll einen möglichen, wenn auch unwahrscheinlichen Angriff ausschließen, bei dem ein nicht autorisierter Server versucht, den FQDN eines gültigen Servers zu übernehmen.

Um Microsoft Office Communications Server 2007 R2-und Microsoft Office Communications Server 2007-Bereitstellungen mit lync Server 2013-Servern zu kommunizieren, erstellt lync Server 2013 außerdem Container während der Gesamtstrukturvorbereitung für die Aufbewahrung von Listen vertrauenswürdiger Server für frühere Versionen. In der folgenden Tabelle werden die Container beschrieben, die erstellt werden, um die Kompatibilität mit früheren Bereitstellungen zu ermöglichen.

### <a name="trusted-server-lists-and-their-active-directory-containers-for-compatibility-with-previous-releases"></a>Listen mit vertrauenswürdigen Servern und ihre entsprechenden Active Directory-Container für die Kompatibilität mit vorherigen Versionen

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Listen mit vertrauenswürdigen Servern</th>
<th>Active Directory-Container</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Standard Edition-Server und Front End-Server von Enterprise-Pools</p></td>
<td><p>RTC-Dienst/Globale Einstellungen</p></td>
</tr>
<tr class="even">
<td><p>Konferenzserver</p></td>
<td><p>RTC-Dienst/Vertrauenswürdige MCUs</p></td>
</tr>
<tr class="odd">
<td><p>Webkomponentenserver</p></td>
<td><p>RTC-Dienst/TrustedWebComponentsServers</p></td>
</tr>
<tr class="even">
<td><p>Vermittlungsserver und Communicator Web Access-Server, Anwendungsserver, Registrierungsstelle mit QoE, A/V-Konferenzdienst (auch SIP-Server von Drittanbietern)</p></td>
<td><p>RTC-Dienst/Vertrauenswürdige Dienste</p></td>
</tr>
<tr class="odd">
<td><p>Proxyserver</p></td>
<td><p>Lync Server 2013 unterstützt keine Abwärtskompatibilität für Proxy Server</p></td>
</tr>
</tbody>
</table>


Um vertrauenswürdige Server früherer Versionen zu unterstützen, müssen Sie das Tool Best Practices Analyzer ausführen. Ausführliche Informationen zum Durchführen von Best Practices Analyzer finden Sie unter [https://go.microsoft.com/fwlink/p/?LinkId=330633](https://go.microsoft.com/fwlink/p/?linkid=330633) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

