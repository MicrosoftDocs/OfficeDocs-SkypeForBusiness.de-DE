---
title: 'Lync Server 2013: Erstellen von DNS-Einträgen für Reverse-Proxy Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create DNS records for reverse proxy servers
ms:assetid: b3513339-e49b-4665-80f1-b5a1c81a0e2e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429719(v=OCS.15)
ms:contentKeyID: 48185181
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 117b13802b79a66c7078f8dcd9ca92a14f390a17
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152007"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-dns-records-for-reverse-proxy-servers-in-lync-server-2013"></a>Erstellen von DNS-Einträgen für Reverse-Proxy Server in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-03-29_

Erstellen Sie externe DNS-A-Einträge, die auf die öffentliche externe Schnittstelle des ISA (Microsoft Internet Security and Acceleration Server) 2006 SP1, Forefront Threat Management Gateway 2010-Servers oder des Internet Information Server-Anwendungs Anforderungs Routings, wie unter [configure DNS for Edge Support in lync Server 2013](lync-server-2013-configure-dns-for-edge-support.md)beschrieben, verweist. Sie benötigen DNS-Einträge für die FQDN des externen Webdiensts für jeden Pool, den Director (oder Directorpool) und jede einfache URL.

Für die minimalen DNS-Einträge für die Clientauflösung für Reverseproxy müssen die folgenden Einträge erstellt werden:

  - Host (A)-Eintrag (e), der die veröffentlichten externen Webdienste für Directors und Director-Pools definiert (beispielsweise **webdirext.contoso.com**)

  - Host (A)-Eintrag (e), der die veröffentlichten externen Webdienste für externe Webdienste definiert, die in allen Front-End-Pools und Standard Edition-Server Rollen gehostet werden (beispielsweise **Webext.contoso.com**)

  - Host (A)-Einträge für einfache URLs (beispielsweise **dialin.contoso.com** und **meet.contoso.com**)

  - Host (A)-Eintrag für den externen lync Discover-Eintrag und bietet auch einen Zeiger auf die AutoErmittlung für alle Webanwendungen, einschließlich lync Web App, Scheduler und Mobilität (beispielsweise **lyncdiscover.contoso.com**)

  - Host Einträge (A) für die Office-webapps-Server-URL (beispielsweise **officewebapp01.contoso.com**)

Ausführliche Informationen finden Sie unter [DNS Summary-Reverse Proxy in lync Server 2013](lync-server-2013-dns-summary-reverse-proxy.md).

</div>

<span> </span>

</div>

</div>

</div>

