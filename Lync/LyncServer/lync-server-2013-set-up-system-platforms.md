---
title: 'Lync Server 2013: Einrichten von Systemplattformen'
TOCTitle: Einrichten von Systemplattformen
ms:assetid: 2e72e49d-2737-4b5b-8c0a-60f6ecb15bf1
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204783(v=OCS.15)
ms:contentKeyID: 49293545
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Einrichten von Systemplattformen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

Bevor Sie mit der Server für beständigen Chat-Bereitstellung beginnen, müssen Sie das erforderliche Betriebssystem auf Hardware installieren, die den Systemanforderungen der Server entspricht:

Ausführliche Informationen zur unterstützten Hardware für Lync Server 2013-Server, Datenbankserver und Dateiserver finden Sie unter [Unterstützte Hardware für Lync Server 2013](lync-server-2013-supported-hardware.md) in der Unterstützungsdokumentation. Ausführliche Informationen zu den unterstützten Betriebssystemen und Datenbankanwendungen finden Sie unter [Serversoftware- und Infrastrukturunterstützung in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) in der Unterstützungsdokumentation. Ausführliche Informationen zu Windows-Updateanforderungen finden Sie unter [Zusätzliche Serverunterstützung und Anforderungen in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md) in der Unterstützungsdokumentation.

Der Front-End-Server für Server für beständigen Chat, **PersistentChatService**, kann auf einem oder mehreren eigenständigen Computern in einem Lync Server 2013- Enterprise Edition-Pool bereitgestellt werden. Sie können nicht auf dem Lync ServerEnterprise Edition- Front-End-Servern angeordnet werden. Der Server für beständigen Chat kann, wie jede andere Lync Server-Rolle, vom Bootstrapper bereitgestellt werden. Die **Beständiger Chat-Webdienste für den Dateiupload/-download** und die **Beständiger Chat-Webdienste für die Chatroomverwaltung** sind Webkomponenten, die auf den Lync Server 2013- Front-End-Servern bereitgestellt werden.

Ein einzelner Front-End-Server für Server für beständigen Chat kann bis zu 20.000 aktive Benutzer unterstützen. Sie können einen Serverpool für beständigen Chat mit bis zu 4 aktiven Front-End-Servern verwenden, die insgesamt 80.000 gleichzeitige Benutzer unterstützen. Auf dem Back-End-Server für Beständiger Chat, **PersistentChatStore**, werden die Chatrooms und -kategorien gespeichert. Es wird empfohlen, den **PersistentChatStore** auf einem dedizierten SQL Server- Back-End-Server in Ihrem Enterprise Edition-Pool zu installieren, obwohl die Anordnung des Lync Server 2013- Back-End-Servers und von **PersistentChatStore** in derselben SQL Server-Instanz unterstützt werden.

Falls in Ihrer Organisation Konformitätsunterstützung erforderlich ist, können Sie diese mit dem Topologie-Generator installieren. Der Server für beständigen Chat-Konformitätsdienst wird auf demselben Computer wie der Server für beständigen Chat- Front-End-Server installiert. Für die Konformität ist eine separate Datenbank erforderlich. Ausführliche Informationen zu den Konformitätsanforderungen für Server für beständigen Chat finden Sie unter [Planen für den Server für beständigen Chat in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in der Planungsdokumentation.

Die Mindestanforderung für jede Topologie ist ein Server mit Lync Server 2013-Installation und ein Server mit installierter SQL Server-Datenbanksoftware. Topologie-Generator unterstützt mehrere Serverpools für beständigen Chat. Folgen Sie für die Bereitstellung mehrerer Serverpools für beständigen Chat denselben Bereitstellungsanforderungen wie für jeden Pool unter [Bereitstellen von Lync Server 2013](lync-server-2013-deploying-lync-server.md) in der Bereitstellungsdokumentation.

Sie können auch Server für beständigen Chat mit Lync Server 2013- Standard Edition bereitstellen. In diesem Fall ist der **PersistentChatService**- Front-End-Server auf dem Standard Edition-Server angeordnet, und Sie können den **PersistentChatStore**- Back-End-Server in der lokalen SQL Server Express-Instanz bereitstellen.


> [!IMPORTANT]
> Server für beständigen ChatStandard Edition wird für hohe Verfügbarkeit nicht unterstützt. Leistung und Skalierung sind eingeschränkt. Zudem werden nur neue Server für beständigen Chat- Standard Edition-Server-Bereitstellungen unterstützt. Ein Upgrade von einem Lync Server 2010- Gruppenchatserver auf einen Lync Server 2013- Server für beständigen ChatStandard Edition wird nicht unterstützt.



## Siehe auch

#### Konzepte

[Zusätzliche Serverunterstützung und Anforderungen in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md)  

#### Weitere Ressourcen

[Unterstützte Hardware für Lync Server 2013](lync-server-2013-supported-hardware.md)  
[Serversoftware- und Infrastrukturunterstützung in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md)  
[Planen für den Server für beständigen Chat in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md)  
[Bereitstellen von Lync Server 2013](lync-server-2013-deploying-lync-server.md)

