---
title: 'Lync Server 2013: Planen der Verbindung mit öffentlichen Instant Messaging-Diensten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for public instant messaging connectivity
ms:assetid: e75e8884-05c7-414a-8014-bc9aa8126fb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205349(v=OCS.15)
ms:contentKeyID: 48185698
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06b650b277e10214be35414568f2c539f8dd21b3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139326"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-public-instant-messaging-connectivity-in-lync-server-2013"></a>Planen der Verbindung mit öffentlichen Instant Messaging-Diensten in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-10-07_

Die Verbindung mit öffentlichen Instant Messaging-Diensten ist eine Klasse von Verbund und wird so konfiguriert, dass Ihre internen und externen lync Server 2013-Benutzer Kontakte aus einem der folgenden Elemente hinzufügen können:

  - Messenger-Kontakte

  - Yahoo\! contacts

  - America Online (AOL)-Kontakte

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>Seit dem 1. September 2012 ist die Microsoft lync Public Chat Connectivity User Subscription License (PIC USL) nicht mehr für den Kauf für neue oder erneuerte Verträge verfügbar. Kunden mit aktiven Lizenzen können weiterhin mit Yahoo! zusammenarbeiten. Messenger bis zum Datum der Beendigung des Diensts. Ein End-of-Life-Datum vom Juni 2014 für AOL und Yahoo! wurde angekündigt. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for Public Instant Messenger Connectivity in lync Server 2013</A>.</P>
> <LI>
> <P>Bei der PIC-USL handelt es sich um eine Abonnementlizenz pro Benutzer pro Monat, die für lync Server oder Office Communications Server erforderlich ist, um mit Yahoo! zu verbünden. Messenger. Die Fähigkeit von Microsoft, diesen Dienst bereitzustellen, wurde von der Unterstützung von Yahoo! abhängig gemacht, die zugrunde liegende Vereinbarung, für die nicht erneuert wird.</P>
> <LI>
> <P>Lync ist mehr denn je ein leistungsfähiges Tool für die Verbindung zwischen verschiedenen Organisationen und mit Einzelpersonen auf der ganzen Welt. Für den Verbund mit Windows Live Messenger sind keine zusätzlichen Benutzer-/Gerätelizenzen außerhalb der lync-Standard-CAL erforderlich. Skype Federation wird dieser Liste hinzugefügt, sodass lync-Benutzer über Chat und Voice Hunderte von Millionen von Benutzern erreichen können.</P></LI></UL>



</div>

Für diese Partnerverbundklasse sind die folgenden Planungsüberlegungen erforderlich:

  - Windows Live Messenger-Benutzer können über Peer-to-Peer-Audio/visuelle Kommunikation mit lync Server 2013-Benutzern sowie Chatnachrichten verfügen. Ihre Edgeserver müssen bestimmte Port-und Protokollanforderungen erfüllen. Ausführliche Informationen finden Sie unter [bestimmen der externen A/V-Firewall und Portanforderungen für lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).

  - Yahoo Instant Messaging hat keine eindeutigen Anforderungen, außer denen, die in der Regel für die Planung und Bereitstellung der typischen Edgeserver verwendet werden, die den Verbund bereitstellt.

  - Für America Online ist es erforderlich, dass Ihr Edgeserver Zertifikat, das dem Zugriffs-Edgedienst zugewiesen ist, über eine verstärkte Schlüsselverwendung für Clients verfügt (EKU).

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Zertifikatzusammenfassung für die Verbindung mit öffentlichen Instant Messaging-Diensten in lync Server 2013](lync-server-2013-certificate-summary-public-instant-messaging-connectivity.md)

  - [Port Zusammenfassung – Verbindung mit öffentlichen Instant Messaging-Diensten in lync Server 2013](lync-server-2013-port-summary-public-instant-messaging-connectivity.md)

  - [DNS-Zusammenfassung – Verbindung mit öffentlichen Instant Messaging-Diensten in lync Server 2013](https://technet.microsoft.com/library/jj618375\(v=ocs.15\))

</div>

</div>

<span> </span>

</div>

</div>

</div>

