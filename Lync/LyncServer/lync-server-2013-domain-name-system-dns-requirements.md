---
title: 'Lync Server 2013: DNS-Anforderungen (Domain Name System)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Domain Name System (DNS) requirements
ms:assetid: 586cf18e-0080-4eb1-aee5-56843277fdfc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398386(v=OCS.15)
ms:contentKeyID: 48184194
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 771bf78f8477008345422cc61f63202c58fcdd14
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832335"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="domain-name-system-dns-requirements-for-lync-server-2013"></a>DNS-Anforderungen (Domain Name System) für lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-06-18_

Zum Bereitstellen von lync Server müssen Sie DNS-Einträge (Domain Name System) erstellen, die die Ermittlung von Clients und Servern ermöglichen, und optional die Unterstützung für die automatische Clientanmeldung, wenn Ihre Organisation Sie unterstützen möchte.

Lync Server verwendet DNS wie folgt:

  - Ermitteln interner Server oder Pools für die Server-zu-Server-Kommunikation.

  - Damit Clients den Front-End-Pool oder den Standard Edition-Server ermitteln können, der für verschiedene SIP-Transaktionen verwendet wird.

  - Wenn Sie Unified Communications-Geräten (UC) zulassen möchten, die nicht angemeldet sind, um den Front-End-Pool oder den Standard Edition-Server mit dem Geräte Update-Webdienst zu entdecken, beziehen Sie Updates, und senden Sie Protokolle.

  - Damit externe Server und Clients eine Verbindung mit Edgeserver oder dem HTTP-Reverseproxy für Sofortnachrichten (im) oder Konferenzen herstellen können.

  - So ermöglichen Sie externen UC-Geräten das Herstellen einer Verbindung mit dem Geräte Update-Webdienst über Edgeserver oder den HTTP-Reverseproxy und Abrufen von Updates

  - Damit Mobile Clients automatisch Webdienste-Ressourcen ermitteln können, ohne dass die Benutzer URLs in den Geräteeinstellungen manuell eingeben müssen.

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Ermitteln von DNS-Anforderungen für Lync Server 2013](lync-server-2013-determine-dns-requirements.md)

  - [DNS-Anforderungen für Front-End-Pools in lync Server 2013](lync-server-2013-dns-requirements-for-front-end-pools.md)

  - [DNS-Anforderungen für Standard Edition-Server in lync Server 2013](lync-server-2013-dns-requirements-for-standard-edition-servers.md)

  - [DNS-Anforderungen für einfache URLs in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [DNS-Anforderungen für die automatische Clientanmeldung in lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)

  - [DNS-Anforderungen für Mobilität mit lync Server 2013](lync-server-2013-dns-requirements-for-mobility.md)

  - [DNS-Lastenausgleich in lync Server 2013](lync-server-2013-dns-load-balancing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

