---
title: 'Lync Server 2013: Komponenten und Topologien für lokales Unified Messaging'
TOCTitle: Komponenten und Topologien für lokales Unified Messaging
ms:assetid: 22fc87cf-a7e5-4c8c-bb9b-101e5380cdcf
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425711(v=OCS.15)
ms:contentKeyID: 49293427
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Komponenten und Topologien für lokales Unified Messaging in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-25_

In diesem Thema werden die Microsoft Exchange Server 2013-Komponenten beschrieben, die zum Bereitstellen von Exchange Unified Messaging (UM)-Funktionen in der Lync Server 2013-Bereitstellung erforderlich sind. Außerdem werden die unterstützten Topologien für die lokale Exchange UM-Integration beschrieben.

## Exchange Server-Komponenten

Um die Exchange UM-Funktionen und -Dienste, die unter [Features von integriertem Unified Messaging und Lync Server 2013](lync-server-2013-features-of-integrated-unified-messaging.md) beschrieben sind, für Enterprise-VoIP-Benutzer in Ihrer Organisation zur Verfügung zu stellen, müssen Sie einen Microsoft Exchange-Postfachserver und Clientzugriffsserver bereitstellen, der Postfächer hostet und einen einzelnen Speicherort für E-Mail- und Voicemail-Nachrichten bietet. Exchange UM wird als ein Dienst auf dem Exchange-Postfachserver und dem Clientzugriffsserver ausgeführt.

Ausführliche Informationen zu Exchange UM-Komponenten in Microsoft Exchange Server 2007 und Microsoft Exchange Server 2010 finden Sie unter [Bereitstellen lokaler Exchange Unified Messaging-Dienste zur Unterstützung von Lync Server 2013-Voicemail](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md) in der Bereitstellungsdokumentation.

## Unterstützte Topologien

Sie können Lync Server 2013 und Exchange Unified Messaging (UM) in derselben Gesamtstruktur oder in mehreren Gesamtstrukturen bereitstellen. Wenn Ihre Bereitstellung mehrere Gesamtstrukturen einschließt, müssen Sie die Exchange-Integrationsschritte für jede Exchange UM-Gesamtstruktur durchführen. Darüber hinaus müssen Sie jede Microsoft Exchange-Gesamtstruktur so konfigurieren, dass eine Vertrauensbeziehung zur Lync Server 2013-Gesamtstruktur und eine Vertrauensbeziehung zwischen der Lync Server 2013-Gesamtstruktur und jeder Exchange UM-Gesamtstruktur besteht. Zusätzlich zu diesen Gesamtstruktur-Vertrauensstellungen müssen die Exchange UM-Einstellungen für alle Benutzer auf die Benutzerobjekte in der Lync Server 2013-Gesamtstruktur festgelegt werden.

Lync Server 2013 unterstützt die folgenden Topologien für die Exchange UM-Integration:

  - Einzelne Gesamtstruktur

  - Einzelne Domäne (also eine einzelne Gesamtstruktur mit einer einzigen Domäne). Lync Server 2013, Microsoft Exchange und Benutzer befinden sich alle in derselben Domäne.

  - Mehrere Domänen (also eine Stammdomäne mit einer oder mehreren untergeordneten Domänen). Lync Server 2013 und Microsoft Exchange-Server werden in anderen Domänen bereitgestellt als in der Domäne, in der Sie Benutzer erstellen. Exchange UM-Server können in anderen Domänen bereitgestellt werden als der Lync Server 2013-Pool, den sie unterstützen.

  - Mehrere Gesamtstrukturen (also Ressourcengesamtstruktur). Lync Server 2013 wird in einer einzigen Gesamtstruktur bereitgestellt, und die Benutzer werden anschließend auf mehrere Gesamtstrukturen verteilt. Die Exchange UM-Attribute der Benutzer müssen in der Lync Server 2013-Gesamtstruktur repliziert werden.
    

    > [!NOTE]
    > Exchange kann in mehreren Gesamtstrukturen bereitgestellt werden. Jede Exchange-Organisation kann Exchange UM für die Benutzer bereitstellen, oder Exchange UM kann in derselben Gesamtstruktur wie Lync Server 2013 bereitgestellt werden.


