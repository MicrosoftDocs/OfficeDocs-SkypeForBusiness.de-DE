---
title: 'Lync Server 2013: Komponenten und Topologien für beständigen Chat Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components and topologies for Persistent Chat Server
ms:assetid: 6a0a14a0-baad-44e9-b26e-4d192c0a0e70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398500(v=OCS.15)
ms:contentKeyID: 48184420
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14ae22b2afed27109fb6e2c514211293cef42a46
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839526"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-persistent-chat-server-in-lync-server-2013"></a>Komponenten und Topologien für den Server für beständigen Chat in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-05_

Der beständige Chat Server unterstützt Konfigurationen mit einem Server sowie Konfigurationen mit mehreren Servern. Der Server für beständigen Chat kann auch auf einem lync Server 2013 Standard Edition-Server ausgeführt werden. Diese Konfigurationen bestehen aus den folgenden beständigen Chat Server-Komponenten und-Topologien.

<div>

## <a name="persistent-chat-server-components"></a>Server Komponenten für beständigen Chat

Zum Installieren der neuesten Version des beständigen Chat Servers sind die folgenden Komponenten erforderlich:

  - Auf einem oder mehreren Computern, auf denen der beständige Chat Server ausgeführt wird und die folgenden Dienste bereitstellen:
    
      - Beständiger Chat Dienst
    
      - Kompatibilitätsdienst, der eingeschaltet wird, wenn Kompatibilität aktiviert ist
    
    <div>
    

    > [!IMPORTANT]  
    > In lync Server 2013 sind die beständigen Chat-Webdienste für Datei Upload/-Download jetzt mit&nbsp;dem lync Server 2013-Front-End-Server eingerichtet.<BR>Die beständigen Chat-Webdienste für die chatroomverwaltung sind ebenfalls mit&nbsp;dem lync Server 2013-Front-End-Server eingerichtet.

    
    </div>

  - Server (mehrere Server, wenn Spiegelung verwendet wird), die die SQL Server-Back-End-Datenbank für das Hosten der Inhaltsdatenbank für beständigen Chat hosten, in der Chatroom-Inhalte,-Räume und-Kategorien gespeichert sind.
    
    <div>
    

    > [!NOTE]  
    > Die Back-End-Datenbank speichert Chatverlaufs Daten, einschließlich Informationen zu Kategorien und beständigen Chatrooms, die erstellt werden.

    
    </div>

  - Wenn Compliance aktiviert war, wird ein Server (mehrere Server, wenn Spiegelung verwendet wird) bereitgestellt, der die SQL Server-Back-End-Datenbank zum Hosten der beständigen Chat-Kompatibilitätsdatenbank hostet, in dem Compliance-Ereignisse und Chat Inhalte zum Zwecke der Compliance gespeichert werden.

Verwenden Sie die lync Server-Systemsteuerung auf dem Computer, um den Server für beständigen Chat von einem separaten Computer (beispielsweise einer Verwaltungskonsole) zu verwalten. Dieser Computer muss dann in einer Active Directory-Domänendienst Domäne mit mindestens einem globalen Katalogserver im Gesamtstrukturstamm bereitgestellt werden.

Details zu den Hardware-und Softwareanforderungen für den Server für beständigen Chat finden Sie unter [Technische Voraussetzungen für den Server für beständigen Chat in lync Server 2013](lync-server-2013-technical-requirements-for-persistent-chat-server.md), [Unterstützte Hardware für lync Server 2013](lync-server-2013-supported-hardware.md)und [Server Software und-Infrastruktur. Unterstützung in lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) in der Dokumentation zur Unterstützung.

</div>

<div>

## <a name="supported-collocation"></a>Unterstützte Anordnung

Lync Server 2013 unterstützt eine Vielzahl von Szenarien für die Zusammenstellung, die Ihnen die Flexibilität bieten, Hardwarekosten zu sparen, indem Sie mehrere Komponenten auf einem Server ausführen (wenn Sie über eine kleine Organisation verfügen) oder einzelne Komponenten auf unterschiedlichen Servern ausführen (wenn Sie über eine größere Organisation, die Skalierbarkeit und Leistung benötigt). Skalierbarkeits Faktoren sollten sicherlich berücksichtigt werden, bevor Sie entscheiden, ob Sie Komponenten collocate.

Der beständige Chat-Kompatibilitätsdienst, wenn die Kompatibilität aktiviert ist, wird mit dem lync Server 2013-Front-End-Server kombiniert.

Der Server für beständigen Chat kann auf dem Standard Edition-Server bereitgestellt werden. Der beständige Chat Server-Back-End-Server und die Compliance-Datenbank für beständigen Chat können auf dem Standard Edition-Server auf dem lokalen SQL Server Express-Back-End-Server installiert werden. Details zu den Komponenten, die sich dort befinden können, finden Sie unter [unterstützte Server Zusammenstellung in lync Server 2013](lync-server-2013-supported-server-collocation.md) in der Dokumentation zur Unterstützung.

Bei lync Server 2013 Enterprise Edition können persistente Chat Server nicht auf dem Enterprise Edition-Server zusammengestellt werden. Die SQL Server-Datenbank für beständigen Chat Server kann mit der Back-End-Server-Datenbank eines Enterprise Edition-Front-End-Pools zusammengestellt werden. Die SQL Server-Datenbank für die beständige Chat-Kompatibilität kann auch mit der Back-End-Server-Datenbank eines Enterprise Edition-Pools zusammengestellt werden.

<div>


> [!IMPORTANT]  
> Der Server, auf dem die persistente Chat-Datenbank gehostet wird, kann andere Datenbanken hosten. Wenn Sie jedoch die persistente Chat-Datenbank mit anderen Datenbanken abstimmen, sollten Sie beachten, dass der von der persistenten Chat Datenbank benötigte Speicherplatz sehr groß werden kann, wenn Sie die Nachrichten von mehr als wenigen Benutzern speichern. Aus diesem Grund empfehlen wir, die Datenbank für persistente Chats nicht mit der Back-End-Datenbank abstimmen.



</div>

Wenn Sie die Datenbank für beständigen Chat mit der Back-End-Datenbank collocate, können Sie entweder eine einzelne Instanz von SQL Server für eine oder alle Datenbanken verwenden, oder Sie können für jede Datenbank eine separate Instanz von SQL Server verwenden, mit der folgenden Einschränkung:

  - Jede Instanz von SQL Server kann nur eine einzige Back-End-Datenbank und eine einzelne persistente Chat-Datenbank enthalten.

Ausführliche Informationen zur Anordnung aller Serverrollen und Datenbanken finden Sie unter unterstützte Server [in lync Server 2013](lync-server-2013-supported-server-collocation.md) in der Dokumentation zur Unterstützung.

</div>

<div>

## <a name="persistent-chat-server-topologies"></a>Server-Topologien für beständigen Chat

Der beständige Chat Server unterstützt die folgenden Topologien:

  - Lync Server 2013 Enterprise Edition-Front-End-Server für beständigen Chat Server

  - Lync Server 2013 Enterprise Edition, beständiger Chat Server-Front-End-Server für mehrere Server

  - Lync Server 2013 Standard Edition-Server mit SQL Server Express

  - Lync Server 2013 Standard Edition-Server und beständiger Chat Server auf einem separaten Server mit Standard Edition-Server als nächster Hop-Server.

Mithilfe des Topologie-Generators können Sie Ihrer lync Server 2013-Bereitstellung einen beständigen Chat Server hinzufügen. Sie können Ihrer Topologie einen einzelnen Server oder einen Serverpool für beständigen Chat mit mehreren Servern hinzufügen.

<div>


> [!IMPORTANT]  
> Nachdem Sie einen Serverpool für beständigen Chat mit einem einzelnen Server mithilfe des Topologie-Generators erstellt haben, können Sie dem Pool keine weiteren Server hinzufügen.



</div>

<div>

## <a name="single-server-topology"></a>Topologie mit einem Server

Die Mindestkonfiguration und einfachste Bereitstellung für beständigen Chat Server ist eine einzelne Front-End-Server Topologie des beständigen Chat Servers. Für diese Bereitstellung ist ein einzelner Server erforderlich, auf dem der beständige Chat Server ausgeführt wird (wobei optional der Kompatibilitätsdienst ausgeführt wird, wenn die Kompatibilität aktiviert ist), ein Server, der sowohl die SQL Server-Datenbank hostet, als auch die SQL Server-Datenbank zum Speichern des Kompatibilitätsdaten.

<div>


> [!IMPORTANT]  
> Sie können einem beständigen Chat Serverpool, der als Einzel Server Bereitstellung im Topologie-Generator gestartet wird, keine weiteren Server hinzufügen. Wir empfehlen die Verwendung der Pooltopologie mit mehreren Servern, auch wenn Sie einen einzelnen Server verwenden, sodass Sie bei Bedarf später weitere Server hinzufügen können.



</div>

Die folgende Abbildung zeigt alle erforderlichen und optionalen Komponenten einer Topologie für einen einzelnen beständigen Chat Server-Front-End-Server mit Compliance.

**Einzelner beständiger Chat Server**

![Topologie mit einem Server mit Kompatibilitätsdienst] (images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Topologie mit einem Server mit Kompatibilitätsdienst")

</div>

<div>

## <a name="multiple-server-topology"></a>Topologie mit mehreren Servern

Um eine größere Kapazität und Zuverlässigkeit bereitzustellen, können Sie eine Topologie mit mehreren Servern bereitstellen, wie unter [Planen des beständigen Chat Servers in lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md)beschrieben. Die Topologie mit mehreren Servern kann bis zu vier aktive Computer umfassen, auf denen der beständige Chat Server ausgeführt wird (für hoch Verfügbarkeits-und Disaster Recovery-Konfigurationen sind bis zu acht möglich, aber nur vier können aktiv sein und die restlichen vier im Standbymodus). Jeder Server kann bis zu 20.000 gleichzeitige Benutzer unterstützen, für insgesamt 80.000 gleichzeitige Benutzer, die mit einem beständigen Chat Serverpool mit 4 Servern verbunden sind. Eine Topologie mit mehreren Servern entspricht der Topologie mit einem Server, mit der Ausnahme, dass mehrere Server den persistenten Chat Server hosten und höher skalieren können. Mehrere Computer, auf denen der beständige Chat Server ausgeführt wird, sollten sich in derselben Active Directory-Domänendienst Domäne wie lync Server und dem Kompatibilitätsdienst befinden.

Die folgende Abbildung zeigt alle Komponenten einer Topologie mit mehreren Servern mit mehreren Computern, auf denen der beständige Chat Server, der optionale Kompatibilitätsdienst und eine separate Kompatibilitätsdatenbank ausgeführt werden.

**Mehrere beständige Chat Server**

![Topologie mit mehreren Servern] (images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Topologie mit mehreren Servern")

Topologien mit mehreren Servern ermöglichen es, Serverfunktionen zu einem Pool zusammenzufassen. In einem Serverpool kommunizieren die beständigen Chat Dienste und geben Daten frei. So kann beispielsweise der Chatverlauf, der ursprünglich in einem beständigen Chatdienst gepostet wurde, von jedem beständigen Chatdienst im System zur Verfügung gestellt werden. Auf eine Datei, die über einen beständigen Chatdienst hochgeladen wird, kann von jedem beständigen Chatdienst zugegriffen werden. Benutzer können mit unterschiedlichen Front-End-Servern für beständigen Chat Server verbunden werden und können chatten und miteinander kommunizieren.

Der Standardport von TCP 8011 verbindet einen Server mit einem Serverpool und wird vom beständigen Chat Dienst für die Kommunikation zwischen sich selbst oder für administrative Zwecke verwendet.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

