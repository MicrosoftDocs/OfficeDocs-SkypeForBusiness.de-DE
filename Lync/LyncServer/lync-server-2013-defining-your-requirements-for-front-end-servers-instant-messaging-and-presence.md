---
title: 'Lync Server 2013: Definieren der Anforderungen für Front-End-Server, Chat und Anwesenheit'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining your requirements for Front End Servers, instant messaging, and presence
ms:assetid: c21198bc-520c-4d17-8b84-7ff1475b9b0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412956(v=OCS.15)
ms:contentKeyID: 48185319
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 176b73f6d82c03e3bcdb0f2b0066752cd68f307c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832688"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a>Definieren der Anforderungen für Front-End-Server, Chat und Anwesenheit in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-10-07_

Die wichtigste Aufgabe bei der Planung von Instant Messaging (im) und Anwesenheitsfunktionen besteht darin, sicherzustellen, dass Sie über genügend Front-End-Server für Ihre Benutzer verfügen.

<div>

## <a name="enabling-communication-with-external-users"></a>Aktivieren der Kommunikation mit externen Benutzern

Sie können die Vorteile Ihrer Investition in lync Server erheblich steigern, indem Sie es Ihren Benutzern ermöglichen, mit externen Benutzern zu kommunizieren. Bei externen Benutzern sind unter anderem folgende Kategorien möglich:

  - **Remote Benutzer**   die eigenen Benutzer Ihrer Organisation, wenn Sie außerhalb Ihrer Firewalls arbeiten und ihre Laptops oder andere lync Server-Geräte verwenden.

  - **Benutzer von Verbundbenutzern**   aus Unternehmen, mit denen Sie zusammenarbeiten, die ebenfalls lync Server ausführen. Damit Ihre Benutzer problemlos Kontakt zu diesen Benutzern aufnehmen können, erstellen Sie Partnerverbundbeziehungen mit diesen Unternehmen.

  - **Öffentliche Benutzer**   von öffentlichen Chat Diensten wie Chat Dienste, die vom Windows Live-Netzwerk von Internet Diensten, Yahoo\!und AOL bereitgestellt werden, sowie Benutzer von Anbietern und Servern, die das Extensible Messaging and Presence Protocol (XMPP) verwenden, wie etwa Google Talk.
    
    <div>
    

    > [!NOTE]  
    > Beachten Sie, dass für öffentliche Chat Verbindungen mit Windows Live, AOL und Yahoo! möglicherweise eine separate Lizenz erforderlich ist.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P>Ab dem 1. September, 2012, ist die Microsoft lync Public im Connectivity-Benutzerabonnementlizenz ("PIC USL") nicht mehr für den Kauf von neuen oder erneuernden Vereinbarungen verfügbar. Kunden mit aktiven Lizenzen sind in der Lage, weiterhin mit Yahoo! zu verbünden Messenger, bis der Dienst das Datum beendet hat. Datum des Endes des Lebenszyklus von Juni 2014 für AOL und Yahoo! wurde angekündigt. Ausführliche Informationen finden Sie <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">unter Unterstützung für öffentliche Instant Messenger-Konnektivität in lync Server 2013</A>.</P>
    > <LI>
    > <P>Bei der PIC-USL handelt es sich um eine Abonnementlizenz pro Benutzer pro Monat, die für die Föderation von lync Server oder Office Communications Server mit Yahoo! erforderlich ist. Messenger. Die Möglichkeit von Microsoft, diesen Dienst bereitzustellen, war von der Unterstützung durch Yahoo! abhängig, deren zugrunde liegende Vereinbarung abgewickelt wird.</P>
    > <LI>
    > <P>Lync ist mehr denn je ein leistungsfähiges Tool für die Verbindung zwischen Organisationen und Personen in der ganzen Welt. Für den Verbund mit Windows Live Messenger sind keine zusätzlichen Benutzer-und Gerätelizenzen außerhalb der lync-Standard CAL erforderlich. Skype Federation wird dieser Liste hinzugefügt und ermöglicht es lync-Benutzern, Hunderte von Millionen von Personen mit Chat und Sprache zu erreichen.</P></LI></UL>

    
    </div>

Wenn Sie ein oder alle dieser Szenarien aktivieren möchten, müssen Sie einen Edgeserver bereitstellen, um die sichere Kommunikation zwischen Ihrer lync Server-Bereitstellung und externen Benutzern zu ermöglichen. Remotebenutzer Ihrer Organisation und Benutzer in Partnerorganisationen können ihre Anwesenheitsinformationen sehen und über Chat miteinander kommunizieren. Details zum Aktivieren der Kommunikation mit externen Benutzern finden Sie unter [Planen des Zugriffs externer Benutzer in lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in der Planungsdokumentation.

</div>

<div>

## <a name="archiving-im-content"></a>Archivieren von Chat Inhalten

Lync Server bietet Funktionen, die Sie verwenden können, wenn Ihre Organisation Konformitätsrichtlinien beachten muss. Mithilfe der Archivierung können Sie Chatinhalte für alle Benutzer in Ihrer Organisation oder nur für bestimmte Benutzer archivieren. Ausführliche Informationen finden Sie unter [Planen der Archivierung in lync Server 2013](lync-server-2013-planning-for-archiving.md) in der Planungsdokumentation.

Wenn Sie auch Microsoft Exchange Server 2013 bereitgestellt haben, können Sie die Archivierung von Exchange-Daten mit der Archivierung von lync Server-Daten integrieren und ein einzelnes Tool verwenden, um beide Arten von archivierten Daten zu durchsuchen. Weitere Informationen finden Sie unter [Konfigurieren von Microsoft lync Server 2013 für die Verwendung von Microsoft Exchange Server 2013-Archivierung](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

