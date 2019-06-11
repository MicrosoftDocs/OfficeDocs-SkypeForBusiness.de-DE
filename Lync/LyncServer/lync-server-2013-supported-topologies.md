---
title: 'Lync Server 2013: Unterstützte Topologien'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supported topologies
ms:assetid: 3475d430-0394-491b-a09b-ba85bd62be70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425833(v=OCS.15)
ms:contentKeyID: 48183832
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 295d0cfc212fcf09b9752c43e918861f49ec7a88
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847685"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-topologies-in-lync-server-2013"></a>Unterstützte Topologien in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-01-14_

Lync Server 2013 unterstützt die Bereitstellung von Websites in einer Organisation und die Integration von lokalen Bereitstellungen mit lync Online-Bereitstellungen, die als hybridbereitstellung bezeichnet werden. In einer hybridbereitstellung sind einige Benutzer lokal verwaltet, und einige Benutzer sind online verwaltet.

Bei lokalen Bereitstellungen unterstützt lync Server 2013 die Bereitstellung von einem oder mehreren Websites, die skaliert werden können, um die Anforderungen an die Hochverfügbarkeit und den Standort zu erfüllen. Sie können diese Websites und ihre Komponenten so strukturieren, dass Sie den Zugriffs-und Widerstands Anforderungen Ihrer Organisation entsprechen.

Eine lokale lync Server 2013-Bereitstellung umfasst die folgenden:

  - Ihre Bereitstellung muss mindestens einen zentralen Standort (auch als Rechenzentrum bezeichnet) umfassen. Jeder zentrale Standort muss mindestens einen Enterprise Edition-Front-End-Pool oder einen Standard Edition-Server enthalten. Diese bestehen aus folgenden Themen:
    
      - Enterprise Edition-Front-End-Pool, der aus einem oder mehreren Front-End-Servern (in der Regel mindestens zwei Front-End-Servern für Skalierbarkeit) und einem separaten Back-End-Server besteht. Ein Front-End-Pool kann maximal zwölf Front-End-Server enthalten. Der Lastenausgleich ist für mehrere Front-End-Server erforderlich. Für SIP-Datenverkehr empfehlen wir den DNS-Lastenausgleich, aber auch der Hardwarelastenausgleich wird unterstützt. Wenn Sie den DNS-Lastenausgleich für den SIP-Datenverkehr verwenden, benötigen Sie weiterhin ein Hardware-Lastenausgleichsmodul für HTTP-Datenverkehr. Wir empfehlen die SQL Server-Spiegelung für eine höhere Verfügbarkeit von Datenbanken. Die Back-End-Datenbank erfordert eine separate Instanz, Sie können jedoch die Archivierungsdatenbank, die Überwachungsdatenbank, die Datenbank für beständigen Chat und die Datenbank für beständigen Chat collocate. Lync Server 2013 unterstützt die Verwendung eines freigegebenen Clusters für die Dateifreigaben in Ihrer Bereitstellung. Details zu den Datenbankspeicher Anforderungen finden Sie unter [Unterstützung der Datenbanksoftware in lync Server 2013](lync-server-2013-database-software-support.md). Ausführliche Informationen zu den Dateispeicheranforderungen finden Sie unter [Unterstützung von Dateispeicher in lync Server 2013](lync-server-2013-file-storage-support.md).
        
        <div>
        

        > [!IMPORTANT]  
        > Wenn Sie lync Server-Datenbanken collocate, empfehlen wir dringend, alle Faktoren zu bewerten, die sich auf die Verfügbarkeit und Leistung auswirken können. Zum Überprüfen von Failoverfunktionen empfiehlt es sich, alle Failover-Szenarien zu testen.

        
        </div>
    
      - Standard Edition-Server mit einer kombinierten SQL Server Express-Datenbank

  - Ihre Bereitstellung kann auch eine oder mehrere Verzweigungs Websites aufweisen, die einem zentralen Standort zugeordnet sind.

In diesem Abschnitt werden die Websites und Komponenten einer lync Server 2013-Bereitstellung beschrieben. Details zur Website-, Topologie-und Komponentenplanung von lync Server 2013 finden Sie unter [Topologie-Grundlagen, die Sie vor dem Planen der lync Server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md) -und Referenz Topologien [in lync Server 2013](lync-server-2013-reference-topologies.md) in der Planungsdokumentation wissen müssen. Details zur Integration von Komponenten vorheriger Versionen finden Sie unter [Unterstützte Migrationspfade und Koexistenz Szenarien in lync Server 2013](lync-server-2013-supported-migration-paths-and-coexistence-scenarios.md).

<div>


> [!NOTE]  
> Gestreckte Pools werden für die Serverrollen Front End, Edge, Mediation und Director nicht unterstützt.



</div>

<div>

## <a name="central-site-topologies-and-components-on-premises"></a>Zentrale Standort Topologien und-Komponenten (lokal)

Obwohl eine zentrale Standorttopologie einen Front-End-Pool oder einen Standard Edition-Server enthalten muss, kann jede zentrale Website auch Folgendes enthalten:

  - Mehrere Front-End-Pools, die sich in der gleichen Domäne oder in verschiedenen Domänen befinden können. Allerdings müssen sich alle Front-End-Server in einem Front-End-Pool und der Back-End-Server für diesen Pool in der gleichen Domäne befinden.

  - Mehrere Standard Edition-Server.

  - Office Web Apps Server, der mit Office Web Applications in lync Server 2013 verwendet wird, um die Freigabe und das Rendern von Microsoft PowerPoint-Präsentationen zu verarbeiten.

  - Edgeserver oder Edge-Pool in Ihrem Umkreisnetzwerk, wenn Sie möchten, dass Ihre Bereitstellung Föderationspartner, öffentliche Chat Verbindungen, ein Extensible Messaging and Presence Protocol (XMPP)-Gateway, Remotebenutzerzugriff, Teilnahme anonymer Benutzer in Besprechungen unterstützt oder Exchange Unified Messaging (um). Sie können keine andere Serverrolle mit einem Edgeserver collocate. Es wird empfohlen, den DNS-Lastenausgleich zu finden, wobei der Hardwarelastenausgleich ebenfalls unterstützt wird. Für die interne Edgeschnittstelle und die externe Edgeschnittstelle muss derselbe Typ von Lastenausgleich verwendet werden. Es ist nicht möglich, für eine Edgeschnittstelle den DNS-Lastenausgleich und für die andere Edgeschnittstelle ein Hardwaregerät zum Lastenausgleich zu verwenden. Ausführliche Informationen zu Lastenausgleichsanforderungen und-Support finden Sie unter [Planen des Zugriffs externer Benutzer in lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in der Planungsdokumentation und [Bereitstellen des Zugriffs externer Benutzer in lync Server 2013](lync-server-2013-deploying-external-user-access.md) in der Bereitstellungsdokumentation.

  - Vermittlungs Server oder-Pool, wenn Sie Enterprise-VoIP oder Einwahlkonferenzen in einem Front-End-Pool am zentralen Standort unterstützen möchten. Je nachdem, wie Sie den Enterprise-VoIP-Support bereitstellen, können Sie den Vermittlungsserver in einem Front-End-Pool (Standard) collocate oder einen eigenständigen Vermittlungsserver oder-Pool bereitstellen. Sie können DNS-, Hardware-oder Anwendungslastenausgleich verwenden (falls zutreffend), um den Datenverkehr vom Gateway-Peer eines Mediations Server-Pools zu verteilen, einschließlich eines PSTN-Gateways, einer IP-PBX-oder SIP-Trunk-Sitzung Border Control (SBC). Details zum Planen der entsprechenden Mediation Server-Topologie finden Sie unter [Bereitstellungsrichtlinien für Mediation Server in lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) in der Planungsdokumentation.

  - Server für beständigen Chat, wenn Sie möchten, dass Benutzer an mehrteiligen, themenbasierten Unterhaltungen teilnehmen können, die im Laufe der Zeit beibehalten werden. Zur Bereitstellung von mehr Kapazität und höherer Zuverlässigkeit kann Ihre Topologie mehrere Computer umfassen, auf denen der beständige Chat Server ausgeführt wird. Sie können keinen beständigen Chat Server mit anderen Serverrollen in einem Enterprise-Pool collocate. Sie können den Server für beständigen Chat jedoch auf einem Standard Edition-Server collocate. Beständiger Chat erfordert eine Datenbank und, wenn Sie die beständige Chat-Compliance implementieren, eine Datenbank für beständigen Chat, aber die Datenbankenkönnen mit der Archivierungsdatenbank, der Überwachungsdatenbank oder auf dem Back-End-Server einer Enterprise-Edition zusammengestellt werden. Front-End-Pool. Weitere Informationen zum Planen der entsprechenden Server Topologie für beständigen Chat finden Sie unter Planen des beständigen [Chat Servers in lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in der Planungsdokumentation.

  - Überwachung, wenn Sie die Datensammlung für die Audio/Video Quality of Experience (QoE) und die Anrufdetailaufzeichnung (CDR) für Enterprise-VoIP-und A/V-Konferenzen in Ihrer Bereitstellung unterstützen möchten. Optional können Sie den Microsoft System Center Operations Manager (vormals Microsoft Operations Manager) installieren, der mithilfe der Überwachung von CDR-und QoE-Daten nahezu in Echtzeit Warnungen generiert, die den Status der Anruf Zuverlässigkeit und Medienqualität anzeigen. Die Überwachung wird bei der Bereitstellung auf Front-End-Servern oder einem Standard Edition-Server bereitgestellt. Für die Überwachung ist eine Datenbank erforderlich, aber die Datenbank kann mit der Archivierungsdatenbank, der persistent Chat-Datenbank, der beständigen Chat-Kompatibilitätsdatenbank oder auf dem Back-End-Server eines Enterprise Edition-Front-End-Pools zusammengestellt werden.

  - Archivierung, wenn Sie Chatnachrichten und Besprechungsinhalte (aus Kompatibilitätsgründen) in Ihrer Bereitstellung archivieren möchten. Die Archivierung erfolgt bei der Bereitstellung auf Front-End-Servern oder einem Standard Edition-Server. Der Archivierungsspeicher erfordert entweder die Bereitstellung einer Archivierungsdatenbank oder die Integration in den Exchange 2013-Speicher. Wenn Sie beides verwenden, das als gemischter *Modus*bezeichnet wird, wird Exchange 2013-Speicher zum Speichern von Archivdaten für Benutzer verwendet, die sich in Exchange 2013 befinden, und die Archivierungsdatenbank wird verwendet, um Daten für alle anderen Benutzer in Ihrer Bereitstellung zu archivieren. Wenn Sie eine Archivierungsdatenbank benötigen, kann die Datenbank in der Überwachungsdatenbank, in der Datenbank für beständigen Chat, in der Kompatibilitätsdatenbank für beständigen Chat oder auf dem Back-End-Server eines Front-End-Pools zusammengestellt werden. Details zum Planen der entsprechenden Archivierungs Topologie finden Sie unter [Planen der Archivierung in lync Server 2013](lync-server-2013-planning-for-archiving.md) in der Planungsdokumentation.

  - Director-oder Director-Pool, wenn Sie die Widerstandsfähigkeit und Umleitung von lync Server 2013-Benutzeranforderungen an den Home-Pool des Benutzers erleichtern möchten, der entweder ein Enterprise Edition-Front-End-Pool oder ein Standard Edition-Server sein kann. Wir empfehlen, dass Sie einen Director-oder Director-Pool in jedem zentralen Standort bereitstellen, der den Zugriff durch externe Benutzer unterstützt, und an jedem zentralen Standort, an dem Sie ein oder mehrere Front-End-Pools bereitstellen. Jeder Director-Pool kann maximal zehn Directors enthalten. Ein Director kann nicht mit einer anderen Serverrolle kombiniert werden. Details zum Planen der entsprechenden Director-Topologie finden Sie unter [Szenarien für den Director in lync Server 2013](lync-server-2013-scenarios-for-the-director.md) in der Planungsdokumentation.

  - Reverse Proxy, bei dem es sich nicht um eine lync Server 2013-Komponente handelt, aber erforderlich ist, wenn Sie die Freigabe von Webinhalten für verbundene Benutzer unterstützen oder Mobilitäts Datenverkehr unterstützen möchten. Sie können keinen Reverse-Proxy Server mit einer beliebigen lync Server 2013-Serverrolle collocate, aber Sie können Reverse-Proxy-Unterstützung für eine lync Server 2013-Bereitstellung implementieren, indem Sie die Unterstützung für einen vorhandenen Reverse-Proxy Server in Ihrer Organisation konfigurieren, der für andere verwendet wird. Anwendungen. Details zu Reverse-Proxyservern finden Sie unter [Einrichten von Reverse-Proxyservern für lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) in der Bereitstellungsdokumentation.

<div>


> [!NOTE]  
> In lync Server 2013 werden A/V-Konferenzen,-Überwachung und-Archivierung auf Front-End-Servern ausgeführt und sind keine separaten Server Rollen mehr.



</div>

Alle Front-End-Pools und Standard Edition-Server, die Sie an einem zentralen Standort bereitstellen, geben eine der folgenden Optionen frei, die Sie für die zentrale Website bereitstellen:

  - Director-oder Director-Pool

  - Eigenständiger Vermittlungs Server oder Pool

  - Office Web Apps-Server

  - Edgeserver oder Edge-Pool

  - Server oder Pool für beständigen Chat

  - Überwachung

  - Archiving

<div>


> [!NOTE]  
> Wenn Sie die Integration von Exchange 2013 Unified Messaging unterstützen möchten, kann ein Exchange um-Server mit ihrer lync Server 2013-Bereitstellung implementiert werden, aber es handelt sich nicht um eine Komponente der lync Server 2013-Website.



</div>

Mehrere zentrale Websites können auch eine der folgenden Freigaben freigeben, die Sie auf einer zentralen Website bereitstellen:

  - Eigenständiger Vermittlungs Server oder Pool

  - Edgeserver oder Edge-Pool

  - Server oder Pool für beständigen Chat

  - Archiving

  - Überwachung

<div>


> [!NOTE]  
> Ein Exchange um-Server kann mit ihrer lync Server 2013-Bereitstellung implementiert und von mehreren zentralen Standorten freigegeben werden, ist aber keine Komponente der lync Server 2013-Website.



</div>

Details zu den Serverrollen und Funktionen von lync Server 2013 finden Sie unter [Serverrollen in lync Server 2013](lync-server-2013-server-roles.md) in der Planungsdokumentation.

Eine Zusammenfassung der Unterstützung von lync Server 2013 Server-Unterstützung finden Sie unter [unterstützte Server Zusammenstellung in lync Server 2013](lync-server-2013-supported-server-collocation.md).

Zusätzlich zu den zuvor in diesem Abschnitt beschriebenen Serverrollen und Funktionen enthält lync Server 2013 zusätzliche Komponenten und Optionen, die einige oder alle der folgenden Elemente enthalten können:

  - Firewalls

  - PSTN-Gateways (bei Bereitstellung von Enterprise-VoIP)

  - Exchange um-Server

  - DNS-Lastenausgleich

  - Hardwaregeräte zum Lastenausgleich

  - SQL Server-Datenbanken

  - Dateifreigaben

Ausführliche Informationen zu allen lync Server 2013-Features,-Komponenten und-Optionen finden Sie in der Planungsdokumentation.

</div>

<div>

## <a name="branch-site-topologies-and-components-on-premises"></a>Topologien und Komponenten von Verzweigungs Websites (lokal)

Eine Verzweigungs Website ist einem zentralen Standort zugeordnet, und jede überlebensfähige Verzweigungs-Appliance an einer Zweigstelle ist einem Enterprise Edition-Front-End-Pool oder einem Standard Edition-Server auf dem zugehörigen zentralen Standort zugeordnet. Zweigstellen Websites sind für den größten Teil ihrer Funktionalität vom zentralen Standort abhängig, sodass Komponenten an einer Zweigstelle nur die folgenden Elemente enthalten:

  - Eine Survivable Branch-Appliance, die ein PSTN-Gateway (Public Switched Telephone Network) mit einigen lync-Server Funktionen kombiniert. Ein Vermittlungsserver kann mit der Instanz der Registrierungsstelle auf der Survivable Branch-Appliance zusammengestellt werden, und Sie können einen eigenständigen Vermittlungsserver oder einen Pool von Vermittlungsservern bereitstellen.

  - Ein Survival-Branch-Server, bei dem es sich um einen Server mit Windows Server handelt, auf dem die lync Server 2013-Registrierungs-und Mediationsserver Software installiert ist.

  - Ein eigenständiges PSTN-Gateway (nicht Bestandteil der Survivable Branch-Appliance) und ein eigenständiger Vermittlungs Server.

Die Anforderungen für überlebensfähige Zweigstellenserver sind identisch mit den Anforderungen für eine beliebige lync Server 2013-Serverrolle.

</div>

</div>

<span> </span>

</div>

</div>

</div>

