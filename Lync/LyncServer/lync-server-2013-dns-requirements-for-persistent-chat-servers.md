---
title: 'Lync Server 2013: DNS-Anforderungen für Server für beständigen Chat'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Persistent Chat Servers
ms:assetid: f7531374-d7ed-4b63-ae81-02294cb4496a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205391(v=OCS.15)
ms:contentKeyID: 48185857
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc401fa844c750e57c870ad64ebd919c9b673d0e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049697"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-persistent-chat-servers-in-lync-server-2013"></a>DNS-Anforderungen für Server für beständigen Chat in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-06-28_

In diesem Abschnitt werden die Domain Name System (DNS) Einträge beschrieben, die für die Bereitstellung von Servern für beständigen Chat erforderlich sind.

<div>

## <a name="dns-records-for-persistent-chat-servers"></a>DNS-Einträge für Server für beständigen Chat

In der folgenden Tabelle werden die DNS-Anforderungen für die Server Bereitstellung für beständigen Chat angegeben.

### <a name="dns-requirements-for-a-persistent-chat-server"></a>DNS-Anforderungen für einen Server für beständigen Chat

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Bereitstellungsszenario</th>
<th>DNS-Anforderung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Ein Server für beständigen Chat</p></td>
<td><p>Ein interner A-Eintrag, mit dem der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des Servers in die zugehörige IP-Adresse aufgelöst wird.</p></td>
</tr>
<tr class="even">
<td><p>Pool für beständigen Chat</p></td>
<td><p>Ein interner A-Eintrag, der den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) der Server in seine IP-Adresse auflöst.</p>
<p><strong>Beispiel</strong></p>
<p>PersistentChatServer01.contoso.com 10.10.10.1</p>
<p>PersistentChatServer02.contoso.com 10.10.10.2</p>
<p>Ein interner A-Eintrag, der den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) der Server in seine IP-Adresse auflöst.</p>
<p><strong>Beispiel</strong></p>
<p>PersistentChatPool.contoso.com 10.10.10.1</p>
<p>PersistentChatPool.contoso.com 10.10.10.2</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

