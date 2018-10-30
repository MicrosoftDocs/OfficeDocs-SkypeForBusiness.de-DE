---
title: 'Lync Server 2013: Unterstützte Topologien'
TOCTitle: Unterstützte Topologien
ms:assetid: 3475d430-0394-491b-a09b-ba85bd62be70
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425833(v=OCS.15)
ms:contentKeyID: 49293635
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Unterstützte Topologien in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2014-01-14_

Lync Server 2013 unterstützt die lokale Bereitstellung von Standorten in einer Organisation und die Integration lokaler Bereitstellungen in Skype for Business Online-Bereitstellungen. Dies wird als Hybridbereitstellung bezeichnet. In einer Hybridbereitstellung werden einige Benutzer lokal und andere online verwaltet.

Für lokale Bereitstellungen unterstützt Lync Server 2013 die Bereitstellung eines oder mehrerer Standorte, die so skaliert werden können, dass sie die Anforderungen an hohe Verfügbarkeit und die Standortanforderungen erfüllen. Diese Standorte und ihre Komponenten können Sie so strukturieren, dass sie den Anforderungen Ihrer Organisation hinsichtlich Zugriff und Ausfallsicherheit entsprechen.

Eine lokale Lync Server 2013-Bereitstellung umfasst Folgendes:

  - Ihre Bereitstellung muss mindestens einen zentralen Standort aufweisen (auch als Datencenter bezeichnet). Jeder zentrale Standort muss mindestens einen Front-End-Pool der Enterprise Edition oder einen Server der Standard Edition enthalten. Diese Komponenten sind folgendermaßen zusammengesetzt:
    
      - Der Front-End-Pool der Enterprise Edition umfasst einen oder mehrere Front-End-Server (aus Gründen der Skalierbarkeit typischerweise mindestens zwei Front-End-Server) sowie einen separaten Back-End-Server. Ein Front-End-Pool kann höchstens zwölf Front-End-Server enthalten. Für mehrere Front-End-Server ist ein Lastenausgleich erforderlich. Für SIP-Datenverkehr wird der DNS-Lastenausgleich empfohlen, es werden jedoch auch Hardwaregeräte zum Lastenausgleich unterstützt. Auch wenn Sie den DNS-Lastenausgleich für SIP-Datenverkehr einsetzen, benötigen Sie außerdem ein Hardwaregerät zum Lastenausgleich für HTTP-Datenverkehr. Um bei Datenbanken eine hohe Verfügbarkeit sicherzustellen, wird eine SQL Server-Spiegelung empfohlen. Die Back-End-Datenbank erfordert eine separate Instanz, aber Sie können die Archivierungsdatenbank, Überwachungsdatenbank, Datenbank für beständigen Chat und Konformitätsdatenbank für beständigen Chat mit der Back-End-Datenbank verbinden. Lync Server 2013 unterstützt die Verwendung eines freigegebenen Clusters für die Dateifreigaben in Ihrer Bereitstellung. Detaillierte Informationen zu den Datenbankspeicheranforderungen finden Sie unter [Unterstützte Datenbanksoftware in Lync Server 2013](lync-server-2013-database-software-support.md). Detaillierte Informationen zu den Dateispeicheranforderungen finden Sie unter [Dateispeicherunterstützung in Lync Server 2013](lync-server-2013-file-storage-support.md).
        

        > [!IMPORTANT]
        > Wenn Sie Lync Server-Datenbanken verbinden, wird dringend empfohlen, alle Faktoren einzubeziehen, die sich ggf. auf die Verfügbarkeit und Leistung auswirken. Zum Überprüfen der Failoverkapazitäten wird empfohlen, alle Failoverszenarien zu testen.

    
      - Server der Standard Edition, der eine verbundene SQL Server Express-Datenbank enthält.

  - In Ihrer Bereitstellung können mehrere Zweigstellen einem zentralen Standort zugeordnet werden.

In diesem Abschnitt werden die Standorte und Komponenten einer Lync Server 2013-Bereitstellung beschrieben. Ausführliche Informationen zur Planung von Lync Server 2013-Standorten, -Topologien und -Komponenten finden Sie unter [Topologiegrundlagen, die Sie vor der Planung für Lync Server 2013 kennen sollten](lync-server-2013-topology-basics-you-must-know-before-planning.md) und [Referenztopologien in Lync Server 2013](lync-server-2013-reference-topologies.md) in der Planungsdokumentation. Ausführliche Informationen zur Integration von Komponenten mit einer vorherigen Version finden Sie unter [Unterstützte Migrationspfade und Koexistenzszenarien in Lync Server 2013](lync-server-2013-supported-migration-paths-and-coexistence-scenarios.md).


> [!NOTE]
> Erweiterte Pools werden für die Serverrollen Front-End, Edge, Mediation und Director nicht unterstützt.



## Topologien und Komponenten des zentralen Standorts (lokal)

Auch wenn die Topologie eines zentralen Standorts einen Front-End-Pool oder einen Server der Standard Edition umfassen muss, kann jeder zentrale Standort auch folgende Komponenten enthalten:

  - Mehrere Front-End-Pools, die sich in derselben oder in verschiedenen Domänen befinden können. Alle Front-End-Server in einem Front-End-Pool und der Back-End-Server für den entsprechenden Pool müssen sich jedoch in derselben Domäne befinden.

  - Mehrere Server der Standard Edition.

  - Office Web Apps-Server, der mit Office-Webanwendungen in Lync Server 2013 verwendet wird, um die Freigabe und das Rendern von Microsoft PowerPoint-Präsentationen zu behandeln.

  - Edgeserver oder Edgepool in Ihrem Umkreisnetzwerk, wenn die Bereitstellung Verbundpartner, Verbindungen mit öffentlichen Chatdiensten, XMPP-Gateway, Remotebenutzerzugriff, die Teilnahme anonymer Benutzer an Besprechungen oder Exchange Unified Messaging (UM)unterstützen soll. Mit einem Edgeserver kann keine weitere Serverrolle verbunden werden. Der DNS-Lastenausgleich wird nach Bedarf empfohlen, es werden jedoch auch Hardwaregeräte zum Lastenausgleich unterstützt. Für die interne Edgeschnittstelle und die externe Edgeschnittstelle muss derselbe Typ von Lastenausgleich verwendet werden. Es ist nicht möglich, für eine Edgeschnittstelle den DNS-Lastenausgleich und für die andere Edgeschnittstelle ein Hardwaregerät zum Lastenausgleich zu verwenden. Ausführliche Informationen zu den Anforderungen und zur Unterstützung des Lastenausgleichs finden Sie unter [Planen des Zugriffs externer Benutzer in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in der Planungsdokumentation und unter [Bereitstellen des Zugriffs durch externe Benutzer in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in der Bereitstellungsdokumentation.

  - Vermittlungsserver oder -pool, wenn Sie Enterprise-VoIP oder Einwahlkonferenzen in einem Front-End-Pool am zentralen Standort unterstützen möchten. Je nach der Bereitstellung der Enterprise-VoIP-Unterstützung können Sie den Vermittlungsserver in einem Front-End-Pool (Standardeinstellung) verbinden oder einen eigenständigen Vermittlungsserver oder -pool bereitstellen. Sie können (je nach Situation) den DNS-Lastenausgleich, ein Hardwaregerät zum Lastenausgleich oder einen Anwendungslastenausgleich einsetzen, um den Datenverkehr von einem Gatewaypeer des Vermittlungsserverpools zu verteilen. Hierzu zählen PSTN-Gateway, IP-Nebenstellenanlage oder SIP-Trunk-SBC (Session Border Control). Ausführliche Informationen zum Planen der entsprechenden Vermittlungsservertopologie finden Sie unter [Richtlinien für die Vermittlungsserverbereitstellung in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) in der Planungsdokumentation.

  - Server für beständigen Chat, wenn Sie möchten, dass Benutzer an themenorientierten Unterhaltungen mit mehreren Parteien teilnehmen können, die beständig gespeichert werden. Für eine höhere Kapazität und bessere Zuverlässigkeit kann Ihre Topologie mehrere Computer mit Server für beständigen Chat umfassen. Sie können den Server für beständigen Chat mit anderen Servern in einem Enterprise-Pool verbinden. Sie können jedoch keinen Server für beständigen Chat mit einem Standard Edition-Server verbinden. Für den beständigen Chat ist eine Datenbank erforderlich. Wenn Sie Konformität für beständigen Chat implementieren, ist zudem eine Konformitätsdatenbank für beständigen Chat erforderlich, die mit der Archivierungsdatenbank, Überwachungsdatenbank oder dem Back-End-Server eines Enterprise Edition-Front-End-Pools verbunden werden kann. Ausführliche Informationen zur Planung der entsprechenden Server für beständigen Chat-Topologie finden Sie unter [Planen für den Server für beständigen Chat in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in der Planungsdokumentation.

  - Überwachung, wenn Sie die Erfassung der Audio/Video-QoE-Daten (Quality of Experience) und die Aufzeichnung von Kommunikationsdatensätzen (KDS) für Enterprise-VoIP und A/V-Konferenzen in Ihrer Bereitstellung unterstützen möchten. Optional können Sie Microsoft System Center Operations Manager (früher Microsoft Operations Manager) installieren. Diese Software generiert mithilfe der KDS-Überwachung und QoE-Daten annähernd Echtzeitwarnungen zur Anrufzuverlässigkeit und zur Medienqualität. Die Überwachung wird, sofern bereitgestellt, mit den Front-End-Servern oder einem Standard Edition-Server verbunden. Für die Überwachung ist eine Datenbank erforderlich, die jedoch mit der Archivierungsdatenbank, der Datenbank für beständigen Chat oder der Konformitätsdatenbank für beständigen Chat verbunden verbunden oder auf dem Back-End-Server eines Enterprise Edition-Front-End-Pools angeordnet werden kann.

  - Archivierung, wenn Sie die Chatkommunikation und Besprechungsinhalte (zur Einhaltung von Bestimmungen) in Ihrer Bereitstellung archivieren möchten. Die Archivierung, sofern bereitgestellt, wird mit Front-End-Servern oder einem Standard-Edition-Server verbunden. Für den Archivierungsspeicher ist entweder die Bereitstellung einer Archivierungsdatenbank oder die Integration in den Exchange 2013-Speicher erforderlich. Wenn Sie beides verwenden (als *gemischter Modus* bezeichnet), wird Exchange 2013-Speicher verwendet, um Archivdaten für Benutzer zu speichern, die unter Exchange 2013 verwaltet werden, und die Archivierungsdatenbank wird zum Archivieren der Daten für alle anderen Benutzer in der Bereitstellung verwendet. Wenn Sie eine Archivierungsdatenbank benötigen, kann die Datenbank mit der Überwachungsdatenbank, Datenbank für beständigen Chat, Konformitätsdatenbank für beständigen Chat oder dem Back-End-Server eines Front-End-Pool verbunden werden. Ausführliche Informationen zum Planen der entsprechenden Archivierungstopologie finden Sie unter [Planen der Archivierung in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in der Planungsdokumentation.

  - Director oder Directorpool, wenn Sie die Ausfallsicherheit und die Umleitung von Lync Server 2013-Benutzeranfragen zum Home-Pool des Benutzers vereinfachen möchten. Bei diesem kann es sich entweder um einen Front-End-Pool der Enterprise Edition oder um einen Server der Standard Edition handeln. Es empfiehlt sich, einen Director oder Directorpool an jedem zentralen Standort bereitzustellen, der den Zugriff durch externe Benutzer unterstützt, sowie an jedem zentralen Standort, in dem ein oder mehrere Front-End-Pools bereitgestellt werden. Jeder Directorpool kann höchstens zehn Directors enthalten. Ein Director kann nicht mit einer anderen Serverrolle kombiniert werden. Ausführliche Informationen zur Planung der Directortopologie finden Sie unter [Szenarien für den Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) in der Planungsdokumentation.

  - Reverseproxy, der zwar keine Lync Server 2013-Komponente ist, aber benötigt wird, wenn die Freigabe von Webinhalten für Partnerbenutzer oder der Mobilitätsdatenverkehr unterstützt werden soll. Sie können einen Reverseproxyserver nicht mit einer Lync Server 2013-Serverrolle verbinden. Allerdings können Sie Reverseproxyunterstützung für eine Lync Server 2013-Bereitstellung implementieren, indem Sie die Unterstützung auf einem vorhandenen Reverseproxyserver in Ihrer Organisation konfigurieren, der für andere Anwendungen genutzt wird. Ausführliche Informationen zu Reverseproxyservern finden Sie unter [Einrichten von Reverseproxyservern für Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) in der Bereitstellungsdokumentation.


> [!NOTE]
> In Lync Server 2013 werden A/V-Konferenzfunktion, Überwachung und Archivierung auf Front-End-Servern ausgeführt. Es handelt sich hierbei nicht mehr um separate Serverrollen.



Alle am zentralen Standort bereitgestellten Front-End-Pools und Server der Standard Edition nutzen folgende Komponenten gemeinsam, wenn Sie diese für den zentralen Standort bereitstellen:

  - Director oder Director-Pool

  - Eigenständiger Vermittlungsserver oder -pool

  - Office Web Apps-Server

  - Edgeserver oder Edgepool

  - Server für beständigen Chat oder Pool

  - Monitoring

  - Archiving


> [!NOTE]
> Ein Exchange UM-Server kann mit der Lync Server 2013-Bereitstellung implementiert werden, wenn Sie die Integration von Exchange 2013 Unified Messaging unterstützen möchten, ist aber keine Komponente des Lync Server 2013-Standorts.



Mehrere zentrale Standorte können außerdem folgende Komponenten gemeinsam nutzen, die Sie an einem zentralen Standort bereitstellen:

  - Eigenständiger Vermittlungsserver oder -pool

  - Edgeserver oder Edgepool

  - Server für beständigen Chat oder Pool

  - Archiving

  - Monitoring


> [!NOTE]
> Ein Exchange UM-Server kann in Ihrer Lync Server 2013-Bereitstellung implementiert und von mehreren zentralen Standorten gemeinsam genutzt werden, es handelt sich jedoch nicht um eine Komponente des Lync Server 2013-Standorts.



Ausführliche Informationen zu Lync Server 2013-Serverrollen und -Funktionen finden Sie unter [Serverrollen in Lync Server 2013](lync-server-2013-server-roles.md) in der Planungsdokumentation.

Eine Übersicht darüber, welche Lync Server 2013-Server verbunden werden können, finden Sie unter [Unterstützte Serverzusammenstellungen in Lync Server 2013](lync-server-2013-supported-server-collocation.md).

Neben den zuvor in diesem Abschnitt erläuterten Serverrollen und Funktionen verfügt Lync Server 2013 über zusätzliche Komponenten und Optionen. Hierzu gehören unter anderem:

  - Firewalls

  - PSTN-Gateways (bei Bereitstellung von Enterprise-VoIP)

  - Exchange UM-Server

  - DNS-Lastenausgleich

  - Hardwaregeräte zum Lastenausgleich

  - SQL Server-Datenbanken

  - Dateifreigaben

Ausführliche Informationen zu allen Lync Server 2013-Features, -Komponenten und -Optionen finden Sie in der Planungsdokumentation.

## Topologien und Komponenten von Zweigstellen (lokal)

Eine Zweigstelle ist einem zentralen Standort zugeordnet, und jede Survivable Branch Appliance an einem Zweigstellenstandort ist einem Front-End-Pool der Enterprise Edition oder einem Server der Standard Edition am entsprechenden zentralen Standort zugeordnet. Der Großteil der Funktionalität an Zweigstellenstandorten ist vom zentralen Standort abhängig, daher umfassen Zweigstellenstandorte nur folgende Komponenten:

  - Eine Survivable Branch-Anwendung, welche ein PSTN-Gateway (Public Switched Telephone Network) mit Lync Server-Funktionalität kombiniert. Ein Vermittlungsserver kann mit der Instanz der Registrierungsstelle in der Survivable Branch-Anwendung kombiniert werden, und Sie können einen eigenständigen Vermittlungsserver oder einen Pool mit Vermittlungsservern bereitstellen.

  - Survivable Branch Server: Dies ist ein Windows Server-Server, auf dem die Lync Server 2013-Registrierungsstellen- und -Vermittlungsserversoftware installiert ist.

  - Ein eigenständiges PSTN-Gateway (kein Bestandteil der Survivable Branch Appliance) und einen eigenständigen Vermittlungsserver.

Die Anforderungen für Survivable Branch Server stimmen mit den Anforderungen aller Lync Server 2013-Serverrollen überein.

