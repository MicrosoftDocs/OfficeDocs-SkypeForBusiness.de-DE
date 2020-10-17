---
title: 'Lync Server 2013: Definieren der Anforderungen für Front-End-Server, Instant Messaging und Anwesenheit'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your requirements for Front End Servers, instant messaging, and presence
ms:assetid: c21198bc-520c-4d17-8b84-7ff1475b9b0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412956(v=OCS.15)
ms:contentKeyID: 48185319
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54629a270fcba5f6237deaaa1146108e16bafef7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504332"
---
# <a name="defining-your-requirements-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a>Definieren der Anforderungen für Front-End-Server, Instant Messaging und Anwesenheitsinformationen in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-10-07_

Die Hauptaufgabe bei der Planung von Instant Messaging (Sofortnachrichten) und Anwesenheit besteht darin, dass Sie über genügend Front-End-Server für Ihre Benutzer verfügen.

<div>

## <a name="enabling-communication-with-external-users"></a>Aktivieren der Kommunikation mit externen Benutzern

Sie können die Vorteile Ihrer Investition in lync Server erheblich verbessern, indem Sie Ihren Benutzern die Kommunikation mit externen Benutzern ermöglichen. Externe Benutzer können Folgendes umfassen:

  - **Remote Benutzer**     Die eigenen Benutzer Ihrer Organisation, wenn Sie außerhalb Ihrer Firewalls arbeiten und ihre Laptops oder andere lync Server Geräte verwenden.

  - Partner **Verbundbenutzer**     Benutzer aus Unternehmen, mit denen Sie zusammenarbeiten und die auch lync Server ausführen. Damit Ihre Benutzer diese Benutzer problemlos kontaktieren können, erstellen Sie Partnerverbundbeziehungen mit diesen Unternehmen.

  - **Öffentliche Benutzer**     Benutzer von öffentlichen Sofortnachrichtendiensten wie Chat Dienste, die von dem Windows Live-Netzwerk von Internet Diensten, Yahoo \! und AOL bereitgestellt werden, sowie Benutzer von Anbietern und Servern, die XMPP (Extensible Messaging and Presence Protocol) verwenden, wie etwa Google Talk.
    
    <div>
    

    > [!NOTE]  
    > Beachten Sie, dass für Verbindungen mit öffentlichen Instant Messaging-Diensten wie Windows Live, AOL und Yahoo! möglicherweise eine separate Lizenz erforderlich ist.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P>Seit dem 1. September 2012 ist die Microsoft lync Public Chat Connectivity-Benutzerabonnementlizenz ("PIC USL") nicht mehr für neue oder erneuerte Verträge verfügbar. Kunden mit aktiven Lizenzen können weiterhin mit Yahoo! zusammenarbeiten. Messenger, bis der Dienst das Datum heruntergefahren hat. Ein End-of-Life-Datum vom Juni 2014 für AOL und Yahoo! wurde angekündigt. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for Public Instant Messenger Connectivity in lync Server 2013</A>.</P>
    > <LI>
    > <P>Bei der PIC-USL handelt es sich um eine Abonnementlizenz pro Benutzer pro Monat, die für lync Server oder Office Communications Server für die Zusammensetzung mit Yahoo! erforderlich ist. Messenger. Die Fähigkeit von Microsoft, diesen Dienst bereitzustellen, wurde von der Unterstützung von Yahoo! abhängig gemacht, die zugrunde liegende Vereinbarung, für die die Rückabwicklung erfolgt.</P>
    > <LI>
    > <P>Lync ist mehr denn je ein leistungsfähiges Tool für die Verbindung zwischen verschiedenen Organisationen und mit Einzelpersonen auf der ganzen Welt. Für den Verbund mit Windows Live Messenger sind keine zusätzlichen Benutzer-/Gerätelizenzen außerhalb der lync-Standard-CAL erforderlich. Skype Federation wird dieser Liste hinzugefügt, sodass lync-Benutzer Hunderte Millionen von Benutzern mit Chat und VoIP erreichen können.</P></LI></UL>

    
    </div>

Zum Aktivieren eines oder aller dieser Szenarien müssen Sie eine Edgeserver bereitstellen, die die sichere Kommunikation zwischen Ihrer lync Server-Bereitstellung und externen Benutzern unterstützt. Remotebenutzer Ihrer Organisation und Benutzer in Partnerorganisationen können ihre Anwesenheitsinformationen ansehen und über Instant Messaging miteinander kommunizieren. Ausführliche Informationen zum Aktivieren der Kommunikation mit externen Benutzern finden Sie unter [Planning for external User Access in lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in der Planungsdokumentation.

</div>

<div>

## <a name="archiving-im-content"></a>Archivieren von Sofortnachrichteninhalten

Lync Server bietet Funktionen, die Sie verwenden können, wenn Ihre Organisation den Compliance-Vorschriften folgen muss. Sie können die Archivierung verwenden, um den Inhalt von Chatnachrichten für alle Benutzer in Ihrer Organisation oder nur für bestimmte Benutzer, die Sie angeben, zu archivieren. Ausführliche Informationen finden Sie unter [Planning for Archiving in lync Server 2013](lync-server-2013-planning-for-archiving.md) in der Planungsdokumentation.

Wenn Sie auch Microsoft Exchange Server 2013 bereitgestellt haben, können Sie die Archivierung von Exchange-Daten mit der Archivierung von lync Server Daten integrieren und ein einzelnes Tool verwenden, um beide Arten archivierter Daten zu durchsuchen. Weitere Informationen finden Sie unter [Konfigurieren von Microsoft lync Server 2013 für die Verwendung Microsoft Exchange Server 2013 Archivierung](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

