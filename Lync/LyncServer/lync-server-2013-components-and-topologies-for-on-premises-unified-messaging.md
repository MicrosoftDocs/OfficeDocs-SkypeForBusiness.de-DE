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
ms.openlocfilehash: 94a22348ca5b0f17415edf0a4f259d5c58d473a9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007985"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-on-premises-unified-messaging-in-lync-server-2013"></a>Komponenten und Topologien für lokale Unified Messaging in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-25_

In diesem Thema werden die Microsoft Exchange Server 2013 Komponenten beschrieben, die zum Bereitstellen von Exchange Unified Messaging (um) Funktionen für lync Server 2013 Bereitstellung erforderlich sind. Außerdem werden die unterstützten Topologien für die lokale Exchange um Integration beschrieben.

<div>

## <a name="exchange-server-components"></a>Exchange Server-Komponenten

Um die in den [Features integrierter Unified Messaging und lync Server 2013](lync-server-2013-features-of-integrated-unified-messaging.md) für Enterprise-VoIP-Benutzer in Ihrer Organisation beschriebenen Exchange um Features und Dienste bereitzustellen, müssen Sie einen Microsoft Exchange Postfachserver und Client Zugriffsserver bereitstellen, der Benutzerpostfächer hostet und einen einzelnen Speicherort für e-Mail und Voicemail bereitstellt. Exchange um wird auf Exchange-Postfach-und Client Zugriffsservern als Dienst ausgeführt.

Ausführliche Informationen zu Exchange um Komponenten in Microsoft Exchange Server 2007 und Microsoft Exchange Server 2010 finden Sie unter [Deploying on-premises Exchange um to bereitstellen lync Server 2013 Voice Mail](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md) in der Bereitstellungsdokumentation.

</div>

<div>

## <a name="supported-topologies"></a>Unterstützte Topologien

Sie können lync Server 2013 und Exchange Unified Messaging (um) in derselben Gesamtstruktur oder in mehreren Gesamtstrukturen bereitstellen. Wenn die Bereitstellung mehrere Gesamtstrukturen umfasst, müssen Sie die Exchange-Integrationsschritte für jede Exchange um Gesamtstruktur ausführen. Darüber hinaus müssen Sie jede Microsoft Exchange Gesamtstruktur so konfigurieren, dass Sie der lync Server 2013-Gesamtstruktur und der lync Server 2013-Gesamtstruktur vertraut, um jeder Exchange um Gesamtstruktur zu vertrauen. Zusätzlich zu dieser Gesamtstrukturvertrauensstellung müssen die Exchange um Einstellungen für alle Benutzer für die Benutzerobjekte in der lync Server 2013 Gesamtstruktur festgelegt werden.

Lync Server 2013 unterstützt die folgenden Topologien für die Exchange um Integration:

  - Einzelne Gesamtstruktur

  - Einzelne Domäne (also eine einzelne Gesamtstruktur mit einer einzigen Domäne). Lync Server 2013, Microsoft Exchange und Benutzer befinden sich alle in derselben Domäne.

  - Mehrere Domänen (also eine Stammdomäne mit einer oder mehreren untergeordneten Domänen). Lync Server 2013 und Microsoft Exchange Server werden in verschiedenen Domänen aus der Domäne bereitgestellt, in der Sie Benutzer erstellen. Exchange um Server können in verschiedenen Domänen aus dem lync Server 2013-Pool bereitgestellt werden, den Sie unterstützen.

  - Mehrere Gesamtstrukturen (also Ressourcengesamtstruktur). Lync Server 2013 wird in einer einzelnen Gesamtstruktur bereitgestellt, und die Benutzer werden dann über mehrere Gesamtstrukturen verteilt. Die Exchange um Attribute der Benutzer müssen in die lync Server 2013 Gesamtstruktur repliziert werden.
    
    <div>
    

    > [!NOTE]  
    > Exchange kann in mehreren Gesamtstrukturen bereitgestellt werden. Jede Exchange-Organisation kann Ihren Benutzern Exchange um bereitstellen, oder Exchange um können in derselben Gesamtstruktur wie lync Server 2013 bereitgestellt werden.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

