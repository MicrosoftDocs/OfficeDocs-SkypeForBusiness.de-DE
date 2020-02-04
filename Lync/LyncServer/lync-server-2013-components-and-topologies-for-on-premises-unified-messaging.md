---
title: 'Lync Server 2013: Komponenten und Topologien für lokales Unified Messaging'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for on-premises Unified Messaging
ms:assetid: 22fc87cf-a7e5-4c8c-bb9b-101e5380cdcf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425711(v=OCS.15)
ms:contentKeyID: 48183619
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1739dbb7d603f112af72c78032c46b94470302bb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742585"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-on-premises-unified-messaging-in-lync-server-2013"></a>Komponenten und Topologien für lokales Unified Messaging in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-25_

In diesem Thema werden die Microsoft Exchange Server 2013-Komponenten beschrieben, die für die Bereitstellung von Exchange Unified Messaging (um)-Features zur lync Server 2013-Bereitstellung erforderlich sind. Darüber hinaus werden die unterstützten Topologien für die lokale Exchange um-Integration beschrieben.

<div>

## <a name="exchange-server-components"></a>Exchange Server-Komponenten

Wenn Sie die Exchange um-Features und-Dienste bereitstellen möchten, die unter [Features von Integrated Unified Messaging und lync Server 2013](lync-server-2013-features-of-integrated-unified-messaging.md) für Enterprise-VoIP-Benutzer in Ihrer Organisation beschrieben sind, müssen Sie einen Microsoft Exchange-Postfachserver und Client Zugriffsserver bereitstellen, der Benutzerpostfächer hostet und einen einzelnen Speicherort für e-Mail und Voicemail bereitstellt. Exchange um wird als Dienst auf Exchange-Postfach-und-Client Zugriffsservern ausgeführt.

Details zu den Exchange um-Komponenten in Microsoft Exchange Server 2007 und Microsoft Exchange Server 2010 finden Sie unter [Bereitstellen von lokalen Exchange um zum Bereitstellen von lync Server 2013-Voicemail](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md) in der Bereitstellungsdokumentation.

</div>

<div>

## <a name="supported-topologies"></a>Unterstützte Topologien

Sie können lync Server 2013 und Exchange Unified Messaging (um) in derselben Gesamtstruktur oder in mehreren Gesamtstrukturen bereitstellen. Wenn die Bereitstellung mehrere Gesamtstrukturen umfasst, müssen Sie die Exchange-Integrationsschritte für jede Exchange um-Gesamtstruktur ausführen. Darüber hinaus müssen Sie die einzelnen Microsoft Exchange-Gesamtstrukturen so konfigurieren, dass Sie der lync Server 2013-Gesamtstruktur und der lync Server 2013-Gesamtstruktur vertrauen, um jeder Exchange um-Gesamtstruktur zu vertrauen. Zusätzlich zu dieser Gesamtstrukturvertrauensstellung müssen die Exchange um-Einstellungen für alle Benutzer für die Benutzerobjekte in der lync Server 2013-Gesamtstruktur eingerichtet werden.

Lync Server 2013 unterstützt die folgenden Topologien für die Exchange um-Integration:

  - Einzelne Gesamtstruktur

  - Einzelne Domäne (also eine einzelne Gesamtstruktur mit einer einzigen Domäne). Lync Server 2013, Microsoft Exchange und Benutzer befinden sich alle in der gleichen Domäne.

  - Mehrere Domänen (also eine Stammdomäne mit einer oder mehreren untergeordneten Domänen). Lync Server 2013 und Microsoft Exchange-Server werden in verschiedenen Domänen aus der Domäne bereitgestellt, in der Sie Benutzer erstellen. Exchange um-Server können in verschiedenen Domänen aus dem von Ihnen unterstützten lync Server 2013-Pool bereitgestellt werden.

  - Mehrere Gesamtstrukturen (also Ressourcengesamtstruktur). Lync Server 2013 wird in einer einzelnen Gesamtstruktur bereitgestellt, und dann werden Benutzer über mehrere Gesamtstrukturen verteilt. Die Exchange um-Attribute der Benutzer müssen in die lync Server 2013-Gesamtstruktur repliziert werden.
    
    <div>
    

    > [!NOTE]  
    > Exchange kann in mehreren Gesamtstrukturen bereitgestellt werden. Jede Exchange-Organisation kann Exchange um für Ihre Benutzer bereitstellen, oder Exchange um kann in derselben Gesamtstruktur wie lync Server 2013 bereitgestellt werden.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

