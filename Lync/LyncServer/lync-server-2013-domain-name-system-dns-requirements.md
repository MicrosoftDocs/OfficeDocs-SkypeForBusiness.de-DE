---
title: 'Lync Server 2013: Domain Name System (DNS) Anforderungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Domain Name System (DNS) requirements
ms:assetid: 586cf18e-0080-4eb1-aee5-56843277fdfc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398386(v=OCS.15)
ms:contentKeyID: 48184194
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7ddbab6e4d0b1a0654c91027cbf0676ad6445f1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501132"
---
# <a name="domain-name-system-dns-requirements-for-lync-server-2013"></a>Domain Name System (DNS) Anforderungen für lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-06-18_

Um lync Server bereitzustellen, müssen Sie Domain Name System (DNS) Datensätze erstellen, die die Ermittlung von Clients und Servern ermöglichen, und optional die Unterstützung für die automatische Clientanmeldung, wenn Ihre Organisation Sie unterstützen möchte.

Lync Server verwendet DNS auf folgende Weise:

  - Zum Erkennen interner Server oder Pools für die Kommunikation zwischen Servern.

  - Damit Clients die Front-End-Pool oder Standard Edition-Server finden, die für verschiedene SIP-Transaktionen verwendet werden.

  - Wenn Sie UC-Geräte (Unified Communications) zulassen möchten, die nicht angemeldet sind, können Sie die Front-End-Pool oder Standard Edition-Server ausgeführten Geräte Update-Webdienst ermitteln, Updates abrufen und Protokolle senden.

  - Damit externe Server und Clients eine Verbindung mit Edgeserver oder dem HTTP-Reverseproxy für Instant Messaging (Sofortnachrichten) oder Konferenzen herstellen können.

  - Damit externe UC-Geräte über Edgeserver oder den HTTP-Reverseproxy eine Verbindung mit dem Geräte Update-Webdienst herstellen und Updates abrufen können.

  - Damit mobile Clients automatisch Webdienstressourcen ermitteln können, ohne dass Benutzer in den Geräteeinstellungen manuell URLs eingeben müssen.

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Bestimmen der DNS-Anforderungen für lync Server 2013](lync-server-2013-determine-dns-requirements.md)

  - [DNS-Anforderungen für Front-End-Pools in lync Server 2013](lync-server-2013-dns-requirements-for-front-end-pools.md)

  - [DNS-Anforderungen für Standard Edition-Server in lync Server 2013](lync-server-2013-dns-requirements-for-standard-edition-servers.md)

  - [DNS-Anforderungen für einfache URLs in lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [DNS-Anforderungen für die automatische Clientanmeldung in lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)

  - [DNS-Anforderungen für die Mobilität mit lync Server 2013](lync-server-2013-dns-requirements-for-mobility.md)

  - [DNS-Lastenausgleich in lync Server 2013](lync-server-2013-dns-load-balancing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

