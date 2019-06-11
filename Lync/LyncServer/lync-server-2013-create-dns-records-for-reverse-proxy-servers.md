---
title: 'Lync Server 2013: Erstellen von DNS-Einträgen für Reverseproxyserver'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create DNS records for reverse proxy servers
ms:assetid: b3513339-e49b-4665-80f1-b5a1c81a0e2e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429719(v=OCS.15)
ms:contentKeyID: 48185181
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5608e3dd851c943e890fe3f718a38c2df02c1c08
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832843"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-dns-records-for-reverse-proxy-servers-in-lync-server-2013"></a>Erstellen von DNS-Einträgen für Reverseproxyserver in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-03-29_

Erstellen Sie externe DNS-A-Datensätze, die auf die öffentliche externe Schnittstelle Ihres Microsoft Internet Security and Acceleration (ISA)-Servers 2006 SP1, Forefront Threat Management Gateway 2010 Server oder auf das Internet Information Server-Anwendungs Anforderungs Routing verweisen, wie in [Konfigurieren von DNS für Edge-Unterstützung in lync Server 2013](lync-server-2013-configure-dns-for-edge-support.md)beschrieben. Sie benötigen DNS-Einträge für die FQDNs des externen Webdiensts für jeden Pool, den Director-(oder Director-Pool) und jede einfache URL.

Die Mindest-DNS-Einträge für die Clientauflösung des Reverse-Proxys müssen die folgenden Einträge erstellt werden:

  - Host (A)-Datensätze, die die veröffentlichten externen Webdienste für Directors-und Director-Pools definieren (beispielsweise **webdirext.contoso.com**)

  - Host (A)-Datensätze, die die veröffentlichten externen Webdienste für externe Webdienste definieren, die auf allen Front-End-Pools und Standard Edition-Serverrollen gehostet werden (beispielsweise **Webext.contoso.com**)

  - Host (A)-Einträge für die einfachen URLs (beispielsweise **dialin.contoso.com** und **Meet.contoso.com**)

  - Host (A)-Eintrag für den lync-Ermittlungs externen Eintrag und bietet auch einen Zeiger auf die AutoErmittlung für alle Web-Apps, einschließlich lync Web App, Scheduler und Mobilität (beispielsweise **lyncdiscover.contoso.com**).

  - Host (A)-Einträge für die Office Web Apps-Server-URL (beispielsweise **officewebapp01.contoso.com**)

Ausführliche Informationen finden Sie unter [DNS Summary – Reverse Proxy in lync Server 2013](lync-server-2013-dns-summary-reverse-proxy.md).

</div>

<span> </span>

</div>

</div>

</div>

