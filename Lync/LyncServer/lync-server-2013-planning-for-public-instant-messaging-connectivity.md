---
title: 'Lync Server 2013: Planen der öffentlichen Instant Messaging-Konnektivität'
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
ms.openlocfilehash: b7885d17e708f2073006131862f06d93d9057fb3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725235"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-public-instant-messaging-connectivity-in-lync-server-2013"></a>Planen der öffentlichen Instant Messaging-Konnektivität in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-10-07_

Die öffentliche Instant Messaging-Konnektivität ist eine Klasse des Föderations-und ist so konfiguriert, dass Ihre internen und externen lync Server 2013-Benutzer Kontakte aus einem der folgenden hinzufügen können:

  - Messenger-Kontakte

  - Yahoo\! Kontakte

  - America Online (AOL)-Kontakte

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>Ab dem 1. September, 2012, ist die Microsoft lync Public Chat-Benutzerabonnementlizenz (PIC USL) nicht mehr für den Kauf für neue oder erneuernde Vereinbarungen verfügbar. Kunden mit aktiven Lizenzen sind in der Lage, weiterhin mit Yahoo! zu verbünden Messenger bis zum Shutdown-Datum des Diensts. Datum des Endes des Lebenszyklus von Juni 2014 für AOL und Yahoo! wurde angekündigt. Ausführliche Informationen finden Sie <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">unter Unterstützung für öffentliche Instant Messenger-Konnektivität in lync Server 2013</A>.</P>
> <LI>
> <P>Bei der PIC-USL handelt es sich um eine pro Benutzer/Monat-Abonnementlizenz, die für lync Server oder Office Communications Server für die Föderation mit Yahoo! erforderlich ist. Messenger. Die Möglichkeit von Microsoft, diesen Dienst bereitzustellen, war von der Unterstützung durch Yahoo! abhängig, deren zugrunde liegende Vereinbarung nicht verlängert werden sollte.</P>
> <LI>
> <P>Lync ist mehr denn je ein leistungsfähiges Tool für die Verbindung zwischen Organisationen und Personen in der ganzen Welt. Für den Verbund mit Windows Live Messenger sind keine zusätzlichen Benutzer-und Gerätelizenzen außerhalb der lync-Standard CAL erforderlich. Skype Federation wird dieser Liste hinzugefügt und ermöglicht es lync-Benutzern, Hunderte von Millionen von Personen über Chat und Sprache zu erreichen.</P></LI></UL>



</div>

Für diese Föderations Klasse sind die folgenden Planungsüberlegungen erforderlich:

  - Benutzer von Windows Live Messenger können neben Instant Messaging auch eine Peer-to-Peer-Audio/visuelle Kommunikation mit lync Server 2013-Benutzern führen. Ihre Edgeserver müssen bestimmte Port-und Protokollanforderungen erfüllen. Ausführliche Informationen finden Sie unter [ermitteln externer A/V-Firewall-und Portanforderungen für lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).

  - Yahoo Instant Messaging hat keine eindeutigen Anforderungen, außer denen, die normalerweise bei der Planung und Bereitstellung des typischen Edgeserver verwendet werden, der Föderation bereitstellt.

  - Für America Online ist es erforderlich, dass Ihr Edge-Server-Zertifikat, das dem Access-Edgedienst zugewiesen ist, über eine erweiterte Client-Schlüsselverwendung verfügt.

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Zertifikats Zusammenfassung – öffentliche Instant Messaging-Konnektivität in lync Server 2013](lync-server-2013-certificate-summary-public-instant-messaging-connectivity.md)

  - [Port Zusammenfassung – öffentliche Instant Messaging-Konnektivität in lync Server 2013](lync-server-2013-port-summary-public-instant-messaging-connectivity.md)

  - [DNS-Zusammenfassung – öffentliche Instant Messaging-Konnektivität in lync Server 2013](https://technet.microsoft.com/en-us/library/jj618375\(v=ocs.15\))

</div>

</div>

<span> </span>

</div>

</div>

</div>

