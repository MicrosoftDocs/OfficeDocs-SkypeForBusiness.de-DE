---
title: 'Lync Server 2013: DNS-Zusammenfassung-Reverseproxy'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Reverse proxy
ms:assetid: 3073affa-4d92-4453-9974-3a82ca0c6445
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204781(v=OCS.15)
ms:contentKeyID: 48183755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13cecbc7e690302d9bc0fcad13a686f5514e3cf7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136372"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---reverse-proxy-in-lync-server-2013"></a>DNS-Zusammenfassung-Reverseproxy in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-03-22_

Sie können die zwei Netzwerkadapter auf Ihrem Reverseproxy folgendermaßen konfigurieren:

<div>

## <a name="reverse-proxy-network-adapter-requirements"></a>Netzwerkadapteranforderungen für Reverseproxy

  - Beispiel **Netzwerkadapter 1 (interne Schnittstelle)**
    
    Interne Schnittstelle mit zugewiesener Adresse 172.25.33.40.
    
    Es ist kein Standardgateway definiert.
    
    Stellen Sie sicher, dass es eine Route aus dem Netzwerk mit der internen Reverseproxy-Schnittstelle zu Netzwerken gibt, die lync Server Front-End-Pool-Server enthalten (beispielsweise von 172.25.33.0 zu 192.168.10.0).

  - Beispiel **Netzwerkadapter 2 (interne Schnittstelle)**
    
    Diesem Netzwerkadapter ist mindestens eine öffentliche IP-Adresse zugewiesen.
    
    Das Gateway ist so definiert, dass es auf den Router oder die integrierte Firewall in Ihrem äußeren Umkreis zeigt (10.45.16.1 in den Szenariobeispielen).

### <a name="dns-records-required-for-reverse-proxy"></a>Für Reverseproxy erforderliche DNS-Einträge

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Standort/Typ/Port</th>
<th>FQDN</th>
<th>IP-Adresse</th>
<th>Zugeordnet zu/Kommentar</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Externe DNS/A</p></td>
<td><p>webext.contoso.com</p></td>
<td><p>Zugewiesener Listener für extern veröffentlichte Ressourcen</p></td>
<td><p>Externe Webdienste aus der internen Bereitstellung. Zusätzliche Einträge können definiert und für alle Pools und einzelne Server für eine beliebige SIP-Domäne konfiguriert werden, die diesen Reverseproxy verwendet und für die externe Webdienste definiert sind.</p></td>
</tr>
<tr class="even">
<td><p>Externer DNS-Eintrag/A</p></td>
<td><p>webdirext.contoso.com</p></td>
<td><p>Zugewiesener Listener für extern veröffentlichte Ressourcen</p></td>
<td><p>Externe Webdienste für die Directors-oder Director-Pools in Ihrer Bereitstellung. Sie können beliebig viele Directors definieren, da es verschiedene Directors gibt, von denen möglicherweise anderen SIP-Domänen zugeordnet werden.</p>
<div>

> [!IMPORTANT]  
> Das Definieren der DNS-Einträge für und das Veröffentlichen der Directors ist weder die Front-End-Pool noch die Entscheidung des Direktors. Sie müssen sowohl die Director-als auch die Front-End-Pool externen Webdienste definieren und veröffentlichen, wenn Sie Directors verwenden. Bestimmte Datenverkehrstypen (für Authentifizierung und andere Zwecke) werden zuerst an den Director gesendet, wenn Sie in der Topologie definiert sind.


</div></td>
</tr>
<tr class="odd">
<td><p>Externe DNS/A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>Zugewiesener Listener für extern veröffentlichte Ressourcen</p></td>
<td><p>Extern veröffentlichte Einwahlkonferenzen</p></td>
</tr>
<tr class="even">
<td><p>Externe DNS/A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>Zugewiesener Listener für extern veröffentlichte Ressourcen</p></td>
<td><p>Extern veröffentlichte Konferenzen</p></td>
</tr>
<tr class="odd">
<td><p>Externe DNS/A</p></td>
<td><p>officewebapps01.contoso.com</p></td>
<td><p>Zugewiesener Listener für Office-webapps Server</p></td>
<td><p>Office-webapps-Server, der intern oder im Umkreis bereitgestellt und für den externen Clientzugriff veröffentlicht wurde</p></td>
</tr>
<tr class="even">
<td><p>Externer DNS-Eintrag/A</p></td>
<td><p>lyncdiscover.contoso.com</p></td>
<td><p>Zugewiesener Listener für extern veröffentlichte Ressourcen</p></td>
<td><p>Externer Eintrag für lync Discover für extern veröffentlichte AutoErmittlung und umfasst Mobility, Microsoft lync Web App und Scheduler-Webanwendung</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

