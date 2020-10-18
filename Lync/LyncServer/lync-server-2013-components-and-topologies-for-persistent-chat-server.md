---
title: 'Lync Server 2013: Komponenten und Topologien für den Server für beständigen Chat'
description: 'Lync Server 2013: Komponenten und Topologien für den Server für beständigen Chat.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for Persistent Chat Server
ms:assetid: 6a0a14a0-baad-44e9-b26e-4d192c0a0e70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398500(v=OCS.15)
ms:contentKeyID: 48184420
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 937b3d6f2716d9471e61cffd651847f6de9d83f1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576811"
---
# <a name="components-and-topologies-for-persistent-chat-server-in-lync-server-2013"></a>Komponenten und Topologien für den Server für beständigen Chat in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-05_

Der Server für beständigen Chat unterstützt Konfigurationen mit einem einzelnen Server und Konfigurationen mit mehreren Servern. Der Server für beständigen Chat kann auch auf einem lync Server 2013 Standard Edition-Server ausgeführt werden. Diese Konfigurationen bestehen aus den folgenden Server Komponenten und Topologien für beständigen Chat.

<div>

## <a name="persistent-chat-server-components"></a>Server Komponenten für beständigen Chat

Für die Installation der neuesten Version des Servers für beständigen Chat sind die folgenden Komponenten erforderlich:

  - Mindestens ein Computer, auf dem der Server für beständigen Chat läuft und die folgenden Dienste bereitstellt:
    
      - Beständiger Chat Dienst
    
      - Kompatibilitätsdienst, der eingeschaltet wird, wenn Kompatibilität aktiviert ist
    
    <div>
    

    > [!IMPORTANT]  
    > In lync Server 2013 ist der beständige Chat Webdienste für das Hochladen/Herunterladen von Dateien nun mit lync Server 2013 &nbsp; Front-End-Server verbunden.<BR>Die Webdienste für den beständigen Chat für die chatroomverwaltung wird auch mit lync Server 2013 Front-End-Server zusammengefasst &nbsp; .

    
    </div>

  - Server (mehrere Server, wenn die Spiegelung verwendet wird), die die SQL Server-Back-End-Datenbank zum Hosten der Inhaltsdatenbank für beständigen Chat hosten, in der Chatroom-Inhalte,-Räume und-Kategorien gespeichert werden.
    
    <div>
    

    > [!NOTE]  
    > In der Back-End-Datenbank werden Chatverlaufs Daten gespeichert, einschließlich Informationen zu Kategorien und beständigen Chatrooms, die erstellt werden.

    
    </div>

  - Wenn die Kompatibilität aktiviert wurde, werden (mehrere Server, wenn die Spiegelung verwendet wird) die SQL Server-Back-End-Datenbank zum Hosten der Kompatibilitätsdatenbank für beständigen Chat, in der kompatibilitätsereignisse und Chat Inhalte für die Zwecke der Compliance gespeichert werden.

Verwenden Sie die lync Server-Systemsteuerung auf dem Computer, um den Server für beständigen Chat von einem separaten Computer aus zu verwalten (beispielsweise eine Verwaltungskonsole). Dieser Computer muss dann in einer Active Directory-Domänendienste Domäne bereitgestellt werden, wobei mindestens ein globaler Katalogserver im Gesamtstrukturstamm vorhanden ist.

Ausführliche Informationen zu Hardware-und Softwareanforderungen für den Server für beständigen Chat finden Sie unter [Technische Anforderungen für den Server für beständigen Chat in lync Server 2013](lync-server-2013-technical-requirements-for-persistent-chat-server.md), [Unterstützte Hardware für lync Server 2013](lync-server-2013-supported-hardware.md)sowie [Server Software und Infrastrukturunterstützung in lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) in der Unterstützungsdokumentation.

</div>

<div>

## <a name="supported-collocation"></a>Unterstützte Zusammenstellungen

Lync Server 2013 unterstützt eine Vielzahl von Zusammenstellungs Szenarien, die Ihnen die Flexibilität bieten, Hardwarekosten zu sparen, indem Sie mehrere Komponenten auf einem Server ausführen (wenn Sie eine kleine Organisation haben) oder einzelne Komponenten auf unterschiedlichen Servern ausführen (wenn Sie über eine größere Organisation verfügen, die Skalierbarkeit und Leistung benötigt). Skalierbarkeits Faktoren sollten sicherlich berücksichtigt werden, bevor Sie entscheiden, ob Sie Komponenten collocate.

Der Kompatibilitätsdienst für beständigen Chat, falls die Kompatibilität aktiviert ist, wird mit dem lync Server 2013 Front-End-Server zusammengefasst.

Der Server für beständigen Chat kann im Standard Edition-Server bereitgestellt werden. Der Server für den Back-End-Server für beständigen Chat und die Kompatibilitätsdatenbank für beständigen Chat können auf dem Standard Edition-Server auf dem lokalen SQL Server Express Back-End-Server zusammengefasst werden. Ausführliche Informationen zu den Komponenten, die dort zusammengefasst werden können, finden Sie unter [unterstützte Server](lync-server-2013-supported-server-collocation.md) Zusammenstellungen in lync Server 2013 in der Unterstützungsdokumentation.

Für lync Server 2013 Enterprise Edition können persistent Chat Server nicht auf dem Enterprise Edition-Server zusammengefasst werden. Die SQL Server Datenbank für den Server für beständigen Chat kann mit der Datenbank des Back-End-Servers eines Enterprise Edition-Front-End-Pool zusammengefasst werden. Die SQL Server-Datenbank für die Compliance für beständigen Chat kann auch mit der Back-End-Server-Datenbank eines Enterprise Edition-Pools zusammengefasst werden.

<div>


> [!IMPORTANT]  
> Der Server, der die Datenbank für beständigen Chat hostet, kann andere Datenbanken hosten. Wenn Sie jedoch die Datenbank für beständigen Chat mit anderen Datenbanken abstimmen, sollten Sie beachten, dass der von der Datenbank für beständigen Chat benötigte Speicherplatz sehr groß sein kann, wenn Sie die Nachrichten von mehreren Benutzern speichern. Aus diesem Grund wird die abstimmen der Datenbank für beständigen Chat nicht mit der Back-End-Datenbank empfohlen.



</div>

Wenn Sie die Datenbank für beständigen Chat mit der Back-End-Datenbank collocate, können Sie entweder eine einzelne Instanz von SQL Server für eine oder alle Datenbanken verwenden, oder Sie können eine separate Instanz von SQL Server für jede Datenbank verwenden, wobei die folgende Einschränkung gilt:

  - Jede Instanz von SQL Server kann nur eine einzige Back-End-Datenbank und eine einzelne Datenbank für beständigen Chat enthalten.

Ausführliche Informationen zur gemeinsamen Nutzung aller Serverrollen und Datenbanken finden Sie unter [Supported Server Colocation in lync Server 2013](lync-server-2013-supported-server-collocation.md) in der Unterstützungsdokumentation.

</div>

<div>

## <a name="persistent-chat-server-topologies"></a>Server Topologien für beständigen Chat

Der Server für beständigen Chat unterstützt die folgenden Topologien:

  - Lync Server 2013 Server für den beständigen Server für die Enterprise Edition Front-End-Server

  - Lync Server 2013 Server für beständigen Chat auf mehreren Servern Front-End-Server

  - Lync Server 2013 Standard Edition-Server mit SQL Server Express

  - Lync Server 2013 Standard Edition-Server-und beständiger Chat Server auf einem separaten Server mit Standard Edition-Server als nächster Hop-Server.

Sie können den Server für beständigen Chat mit dem Topologie-Generator zu ihrer lync Server 2013-Bereitstellung hinzufügen. Sie können Ihrer Topologie einen einzelnen Server oder einen Serverpool für beständigen Chat mit mehreren Servern hinzufügen.

<div>


> [!IMPORTANT]  
> Nachdem Sie einen Serverpool für beständigen Chat mit einem einzelnen Server mithilfe des Topologie-Generators erstellt haben, können Sie dem Pool keine weiteren Server hinzufügen.



</div>

<div>

## <a name="single-server-topology"></a>Einzelservertopologie

Die minimale Konfiguration und die einfachste Bereitstellung für den Server für beständigen Chat ist ein einzelner Server für beständigen Chat Front-End-Server Topologie. Für diese Bereitstellung ist ein einzelner Server erforderlich, auf dem der Server für beständigen Chat ausgeführt wird (optional wird der Kompatibilitätsdienst ausgeführt, wenn die Kompatibilität aktiviert ist), ein Server, der sowohl die SQL Server Datenbank hostet, als auch die erforderliche Kompatibilität, die SQL Server Datenbank zum Speichern der Kompatibilitätsdaten.

<div>


> [!IMPORTANT]  
> Sie können keinem Serverpool für beständigen Chat, der als Einzel Server Bereitstellung im Topologie-Generator gestartet wird, keine weiteren Server hinzufügen. Daher sollten Sie auch dann, wenn Sie nur einen einzigen Server haben, die Multiserver-Pool-Topologie verwenden, da Sie dann später weitere Server hinzufügen können, falls erforderlich.



</div>

Die folgende Abbildung zeigt alle erforderlichen und optionalen Komponenten einer Topologie für einen einzelnen Server für beständigen Chat Front-End-Server mit Compliance.

**Einzelner dauerhafter Chatserver**

![Topologie mit einem Server mit Kompatibilitätsdienst](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Topologie mit einem Server mit Kompatibilitätsdienst")

</div>

<div>

## <a name="multiple-server-topology"></a>Topologie mit mehreren Servern

Um eine höhere Kapazität und Zuverlässigkeit zu bieten, können Sie eine Topologie mit mehreren Servern bereitstellen, wie unter [Planning for persistent Chat Server in lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md)beschrieben. Die Topologie mit mehreren Servern kann bis zu vier aktive Computer mit persistent Chat Server umfassen (Hochverfügbarkeit und Notfall Wiederherstellungs Konfigurationen ermöglichen bis zu acht, aber nur vier können aktiv sein und die restlichen vier im Standbymodus). Jeder Server kann bis zu 20.000 gleichzeitige Benutzer unterstützen, für insgesamt 80.000 gleichzeitige Benutzer, die mit einem Serverpool für beständigen Chat mit 4 Servern verbunden sind. Eine Topologie mit mehreren Servern ist identisch mit der Einzelservertopologie, mit dem Unterschied, dass mehrere Server den Server für beständigen Chat hosten und höher skalieren können. Mehrere Computer mit persistent Chat Server sollten sich in derselben Active Directory-Domänendienste Domäne wie lync Server und dem Kompatibilitätsdienst befinden.

Die folgende Abbildung zeigt alle Komponenten einer Topologie mit mehreren Servern mit mehreren Computern, auf denen der Server für beständigen Chat, der optionale Kompatibilitätsdienst und eine separate Kompatibilitätsdatenbank läuft.

**Mehrere dauerhafte Chatserver**

![Topologie mit mehreren Servern](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Topologie mit mehreren Servern")

Topologien mit mehreren Servern ermöglichen es, Serverfunktionen zu einem Pool zusammenzufassen. In einem Serverpool kommunizieren die Dienste für beständigen Chat und teilen Daten. So ist beispielsweise der Chatverlauf, der ursprünglich für einen beständigen Chatdienst bereitgestellt wurde, in jedem persistent Chat-Dienst im System verfügbar. Auf eine Datei, die über einen beständigen Chatdienst hochgeladen wird, kann jeder beständige Chatdienst zugreifen. Benutzer können mit verschiedenen Front-End-Servern für beständigen Chat Server verbunden werden und können miteinander chatten und kommunizieren.

Der Standardport von TCP 8011 verbindet einen Server mit einem Serverpool und wird vom beständigen Chat Dienst verwendet, um zwischen sich selbst oder zu administrativen Zwecken zu kommunizieren.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

