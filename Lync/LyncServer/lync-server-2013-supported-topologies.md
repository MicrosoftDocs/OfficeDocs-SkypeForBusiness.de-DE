---
title: Lync Server 2013 unterstützten Topologien
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported topologies
ms:assetid: 3475d430-0394-491b-a09b-ba85bd62be70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425833(v=OCS.15)
ms:contentKeyID: 48183832
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f0e6ad0307674ce5e540445c48b6ab9aff767e40
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142341"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="supported-topologies-in-lync-server-2013"></a>Unterstützte Topologien in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-01-14_

Lync Server 2013 unterstützt die Bereitstellung von Websites in einer Organisation und Integration von lokalen Bereitstellungen mit lync Online-Bereitstellungen, die als hybridbereitstellung bezeichnet wird. In einer hybridbereitstellung werden einige Benutzer lokal verwaltet, und einige Benutzer werden online verwaltet.

Für lokale Bereitstellungen unterstützt lync Server 2013 die Bereitstellungeines oder mehrerer Standorte, die skaliert werden können, um hohe Verfügbarkeit und Standortanforderungen zu erfüllen. Diese Standorte und ihre Komponenten können Sie so strukturieren, dass sie den Anforderungen Ihrer Organisation hinsichtlich Zugriff und Ausfallsicherheit entsprechen.

Eine lync Server 2013 lokale Bereitstellung umfasst Folgendes:

  - Ihre Bereitstellung muss mindestens einen zentralen Standort aufweisen (auch als Datencenter bezeichnet). Jeder zentrale Standort muss mindestens einen Front-End-Pool der Enterprise Edition oder einen Server der Standard Edition enthalten. Diese Komponenten sind folgendermaßen zusammengesetzt:
    
      - Der Front-End-Pool der Enterprise Edition umfasst einen oder mehrere Front-End-Server (aus Gründen der Skalierbarkeit typischerweise mindestens zwei Front-End-Server) sowie einen separaten Back-End-Server. Ein Front-End-Pool kann maximal zwölf Front-End-Server enthalten. Für mehrere Front-End-Server ist ein Lastenausgleich erforderlich. Für SIP-Datenverkehr wird der DNS-Lastenausgleich empfohlen, es werden jedoch auch Hardwaregeräte zum Lastenausgleich unterstützt. Auch wenn Sie den DNS-Lastenausgleich für SIP-Datenverkehr einsetzen, benötigen Sie außerdem ein Hardwaregerät zum Lastenausgleich für HTTP-Datenverkehr. Es wird empfohlen, SQL Server Spiegelung für eine hohe Verfügbarkeit von Datenbanken zu sichern. Die Back-End-Datenbank erfordert eine separate Instanz, aber Sie können die Archivierungsdatenbank, Überwachungsdatenbank, Datenbank für beständigen Chat und Konformitätsdatenbank für beständigen Chat mit der Back-End-Datenbank verbinden. Lync Server 2013 unterstützt die Verwendung eines freigegebenen Clusters für die Dateifreigaben in Ihrer Bereitstellung. Ausführliche Informationen zu den Anforderungen an den Datenbankspeicher finden Sie unter [Database Software Support in lync Server 2013](lync-server-2013-database-software-support.md). Ausführliche Informationen zu den Dateispeicheranforderungen finden Sie unter [File Storage Support in lync Server 2013](lync-server-2013-file-storage-support.md).
        
        <div>
        

        > [!IMPORTANT]  
        > Wenn Sie lync Server Datenbanken collocate, wird dringend empfohlen, alle Faktoren zu bewerten, die sich auf die Verfügbarkeit und Leistung auswirken können. Zum Überprüfen der Failoverfunktionen wird empfohlen, alle Failover-Szenarien zu testen.

        
        </div>
    
      - Server der Standard Edition, der eine verbundene SQL Server Express-Datenbank enthält.

  - In Ihrer Bereitstellung können mehrere Zweigstellen einem zentralen Standort zugeordnet werden.

In diesem Abschnitt werden die Websites und Komponenten einer lync Server 2013-Bereitstellung beschrieben. Ausführliche Informationen zur Planung lync Server 2013 Standorts, der Topologie und der Komponenten finden Sie unter [Topologie Grundlagen, die Sie vor der Planung von lync Server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md) und [Referenz Topologien in lync Server 2013](lync-server-2013-reference-topologies.md) in der Planungsdokumentation kennen müssen. Ausführliche Informationen zur Integration von Komponenten früherer Versionen finden Sie unter [Supported Migration Paths and Koexistenz Scenarios in lync Server 2013](lync-server-2013-supported-migration-paths-and-coexistence-scenarios.md).

<div>


> [!NOTE]  
> Gestreckte Pools werden für die Serverrollen Front End, Edge, Mediation und Director nicht unterstützt.



</div>

<div>

## <a name="central-site-topologies-and-components-on-premises"></a>Topologien und Komponenten des zentralen Standorts (lokal)

Auch wenn die Topologie eines zentralen Standorts einen Front-End-Pool oder einen Server der Standard Edition umfassen muss, kann jeder zentrale Standort auch folgende Komponenten enthalten:

  - Mehrere Front-End-Pools, die sich in derselben oder in verschiedenen Domänen befinden können. Alle Front-End-Server in einem Front-End-Pool und der Back-End-Server für den entsprechenden Pool müssen sich jedoch in derselben Domäne befinden.

  - Mehrere Server der Standard Edition.

  - Office-webapps-Server, der mit Office-Webanwendungen in lync Server 2013 verwendet wird, um die Freigabe und das Rendern von Microsoft PowerPoint Präsentationen zu verarbeiten.

  - Edgeserver oder Edgepool in Ihrem Umkreisnetzwerk, wenn Ihre Bereitstellung Verbundpartner, öffentliche Instant Messaging-Verbindungen, ein XMPP-Gateway (Extensible Messaging and Presence Protocol), Remotebenutzerzugriff, Teilnahme anonymer Benutzer an Besprechungen unterstützen soll, oder Exchange Unified Messaging (um). Mit einem Edgeserver kann keine weitere Serverrolle verbunden werden. Der DNS-Lastenausgleich wird nach Bedarf empfohlen, es werden jedoch auch Hardwaregeräte zum Lastenausgleich unterstützt. Für die interne Edgeschnittstelle und die externe Edgeschnittstelle muss derselbe Typ von Lastenausgleich verwendet werden. Es ist nicht möglich, für eine Edgeschnittstelle den DNS-Lastenausgleich und für die andere Edgeschnittstelle ein Hardwaregerät zum Lastenausgleich zu verwenden. Ausführliche Informationen zu Lastenausgleichsanforderungen und-Unterstützung finden Sie unter [Planning for external User Access in lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in der Planungsdokumentation und [Bereitstellen des Zugriffs auf externe Benutzer in lync Server 2013](lync-server-2013-deploying-external-user-access.md) in der Bereitstellungsdokumentation.

  - Vermittlungsserver oder Pool, wenn Sie Enterprise-VoIP oder Einwahlkonferenzen in einer Front-End-Pool am zentralen Standort unterstützen möchten. Je nachdem, wie Sie Enterprise-VoIP-Unterstützung bereitstellen, können Sie die Vermittlungsserver in einer Front-End-Pool (Standardeinstellung) collocate oder einen eigenständigen Vermittlungsserver oder Pool bereitstellen. Sie können DNS-, Hardware-oder Anwendungslasten Ausgleich (sofern zutreffend) verwenden, um Datenverkehr vom Gateway-Peer eines Vermittlungsserver Pools zu verteilen, einschließlich eines PSTN-Gateways, einer IP-Nebenstellenanlage oder eines SIP-Trunk-Sitzungs Rahmensteuerelements (SBC). Ausführliche Informationen zum Planen der entsprechenden Vermittlungsserver Topologie finden Sie unter [Deployment Guidelines for Vermittlungsserver in lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) in der Planungsdokumentation.

  - Server für beständigen Chat, wenn Sie möchten, dass Benutzer an mehrteiligen, themenbasierten Unterhaltungen teilnehmen können, die im Laufe der Zeit beibehalten werden. Um mehr Kapazität und höhere Zuverlässigkeit bereitzustellen, kann Ihre Topologie mehrere Computer mit persistent Chat Server umfassen. Sie können den Server für beständigen Chat nicht mit anderen Serverrollen in einem Enterprise-Pool collocate. Sie können den Server für beständigen Chat jedoch auf einem Standard Edition-Server collocate. Für beständigen Chat ist eine Datenbank erforderlich, und wenn Sie die Compliance für beständigen Chat implementieren, wird eine Kompatibilitätsdatenbank für beständigen Chat benötigt, aber die Datenbankenkönnen mit dem Archivierungsdatenbank, Überwachungsdatenbank oder auf dem Back-End-Server einer Enterprise Edition verbunden werden. Front-End-Pool. Ausführliche Informationen zum Planen der entsprechenden Server Topologie für beständigen Chat finden Sie unter [Planning for persistent Chat Server in lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in der Planungsdokumentation.

  - Überwachung, wenn Sie die Datensammlung für die Audio/Video Quality of Experience (QoE) und die Aufzeichnung von Kommunikationsdatensätzen (CDR) für Enterprise-VoIP und A/V-Konferenzen in Ihrer Bereitstellung unterstützen möchten. Optional können Sie Microsoft System Center Operations Manager (ehemals Microsoft Operations Manager) installieren, das die Überwachungs-KDS-und QoE-Daten verwendet, um in Echtzeit Warnungen zu generieren, die die Integrität von Anruf Zuverlässigkeit und Medienqualität anzeigen. Die Überwachung erfolgt bei der Bereitstellung auf Front-End-Servern oder einem Standard Edition-Server. Für die Überwachung ist eine Datenbank erforderlich, die Datenbank kann jedoch mit der Archivierungsdatenbank, der Datenbank für beständigen Chat, der Kompatibilitätsdatenbank für beständigen Chat oder dem Back-End-Server eines Enterprise Edition-Front-End-Pool verbunden werden.

  - Archivierung, wenn Sie die Chatkommunikation und Besprechungsinhalte (zur Einhaltung von Bestimmungen) in Ihrer Bereitstellung archivieren möchten. Die Archivierung, sofern bereitgestellt, wird mit Front-End-Servern oder einem Standard-Edition-Server verbunden. Der Archivierungsspeicher erfordert entweder die Bereitstellungeines Archivierungsdatenbank oder eine Integration in Exchange 2013 Speicher. Wenn Sie beide verwenden, was als *Gemischter Modus*bezeichnet wird, wird Exchange 2013 Speicher verwendet, um Archivdaten für Benutzer zu speichern, die in Exchange 2013 verwaltet werden, und die Archivierungsdatenbank dient zum Archivieren von Daten für alle anderen Benutzer in Ihrer Bereitstellung. Wenn Sie eine Archivierungsdatenbank benötigen, kann die Datenbank mit der Überwachungsdatenbank, Datenbank für beständigen Chat, Konformitätsdatenbank für beständigen Chat oder dem Back-End-Server eines Front-End-Pool verbunden werden. Ausführliche Informationen zum Planen der entsprechenden Archivierungs Topologie finden Sie unter [Planning for Archiving in lync Server 2013](lync-server-2013-planning-for-archiving.md) in der Planungsdokumentation.

  - Director oder Directorpool, wenn Sie die Ausfallsicherheit und die Umleitung von lync Server 2013 Benutzeranforderungen an den Home-Pool des Benutzers erleichtern möchten, bei dem es sich entweder um eine Enterprise Edition-Front-End-Pool oder eine Standard Edition-Server handeln kann. Es wird empfohlen, dass Sie einen Director oder Directorpool an jedem zentralen Standort bereitstellen, der den Zugriff durch externe Benutzer und an jedem zentralen Standort unterstützt, in dem Sie einen oder mehrere Front-End-Pools bereitstellen. Jeder Directorpool kann maximal zehn Directors enthalten. Ein Director kann nicht mit einer anderen Serverrolle verbunden werden. Ausführliche Informationen zum Planen der entsprechenden Director-Topologie finden Sie unter [Szenarien für den Director in lync Server 2013](lync-server-2013-scenarios-for-the-director.md) in der Planungsdokumentation.

  - Reverseproxy, bei dem es sich nicht um eine lync Server 2013 Komponente handelt, aber erforderlich ist, wenn Sie die Freigabe von Webinhalten für Verbundbenutzer unterstützen oder Mobilitäts Datenverkehr unterstützen möchten. Es ist nicht möglich, einen Reverseproxy-Server mit einer lync Server 2013 Serverrolle collocate, aber Sie können Reverse-Proxy Unterstützung für eine lync Server 2013-Bereitstellung implementieren, indem Sie die Unterstützung für einen vorhandenen Reverseproxy in Ihrer Organisation konfigurieren, der für andere verwendet wird. Anwendungen. Ausführliche Informationen zu Reverse-Proxyservern finden Sie unter [Einrichten von Reverse-Proxyservern für lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) in der Bereitstellungsdokumentation.

<div>


> [!NOTE]  
> In lync Server 2013 werden A/V-Konferenzen,-Überwachung und-Archivierung auf Front-End-Servern ausgeführt und sind keine separaten Server Rollen mehr.



</div>

Alle am zentralen Standort bereitgestellten Front-End-Pools und Server der Standard Edition nutzen folgende Komponenten gemeinsam, wenn Sie diese für den zentralen Standort bereitstellen:

  - Director oder Director-Pool

  - Eigenständiger Vermittlungsserver oder -pool

  - Office Web Apps-Server

  - Edgeserver oder Edgepool

  - Server für beständigen Chat oder Pool

  - Überwachung

  - Archivierung

<div>


> [!NOTE]  
> Ein Exchange um Server kann mit ihrer lync Server 2013-Bereitstellung implementiert werden, wenn Sie die Integration von Exchange 2013 Unified Messaging unterstützen möchten, aber es handelt sich nicht um eine Komponente des lync Server 2013-Standorts.



</div>

Mehrere zentrale Standorte können außerdem folgende Komponenten gemeinsam nutzen, die Sie an einem zentralen Standort bereitstellen:

  - Eigenständiger Vermittlungsserver oder -pool

  - Edgeserver oder Edgepool

  - Server für beständigen Chat oder Pool

  - Archivierung

  - Überwachung

<div>


> [!NOTE]  
> Ein Exchange um Server kann mit ihrer lync Server 2013-Bereitstellung implementiert und von mehreren zentralen Standorten gemeinsam genutzt werden, aber es handelt sich nicht um eine Komponente des lync Server 2013-Standorts.



</div>

Ausführliche Informationen zu lync Server 2013 Serverrollen und-Funktionen finden Sie unter [Serverrollen in lync Server 2013](lync-server-2013-server-roles.md) in der Planungsdokumentation.

Eine Zusammenfassung der unterstützten lync Server 2013 Server-Zusammenstellungs Unterstützung finden Sie unter [Supported Server recolocation in lync Server 2013](lync-server-2013-supported-server-collocation.md).

Zusätzlich zu den zuvor in diesem Abschnitt beschriebenen Serverrollen und Funktionen verfügt lync Server 2013 über zusätzliche Komponenten und Optionen, die einige oder alle der folgenden Elemente enthalten können:

  - Firewalls

  - PSTN-Gateways (bei Bereitstellung von Enterprise-VoIP)

  - Exchange um Server

  - DNS-Lastenausgleich

  - Hardwaregeräte zum Lastenausgleich

  - SQL Server-Datenbanken

  - Dateifreigaben

Ausführliche Informationen zu allen lync Server 2013-Features,-Komponenten und-Optionen finden Sie in der Planungsdokumentation.

</div>

<div>

## <a name="branch-site-topologies-and-components-on-premises"></a>Topologien und Komponenten von Zweigstellen (lokal)

Eine Zweigstelle ist einem zentralen Standort zugeordnet, und jede Survivable Branch Appliance an einem Zweigstellenstandort ist einem Front-End-Pool der Enterprise Edition oder einem Server der Standard Edition am entsprechenden zentralen Standort zugeordnet. Der Großteil der Funktionalität an Zweigstellenstandorten ist vom zentralen Standort abhängig, daher umfassen Zweigstellenstandorte nur folgende Komponenten:

  - Ein Survivable Branch Appliance, in dem ein PSTN-Gateway (Public Switched Telephone Network) mit einigen lync Server Funktionen kombiniert wird. Ein Vermittlungsserver kann mit der Instanz der Registrierungsstelle auf dem Survivable Branch Appliance zusammengestellt werden, und Sie können eine eigenständige Vermittlungsserver oder einen Pool von Vermittlungsservern bereitstellen.

  - Ein Survivable Branch Server, bei dem es sich um einen Server mit Windows Server handelt, auf dem lync Server 2013 Registrierungsstelle und Vermittlungsserver Software installiert ist.

  - Ein eigenständiges PSTN-Gateway (kein Bestandteil der Survivable Branch Appliance) und einen eigenständigen Vermittlungsserver.

Die Anforderungen für Survivable Branch Server entsprechen den Anforderungen für alle lync Server 2013 Server Rolle.

</div>

</div>

<span> </span>

</div>

</div>

</div>

