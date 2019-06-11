---
title: 'Lync Server 2013: DNS-Zusammenfassung für Reverseproxy'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - Reverse proxy
ms:assetid: 3073affa-4d92-4453-9974-3a82ca0c6445
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204781(v=OCS.15)
ms:contentKeyID: 48183755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47606fe71b271e01cc7fbefbcf319a2efe93f478
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832348"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---reverse-proxy-in-lync-server-2013"></a>DNS-Zusammenfassung für Reverseproxy in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-03-22_

Sie konfigurieren zwei Netzwerkadapter in Ihrem Reverse-Proxy wie folgt:

<div>

## <a name="reverse-proxy-network-adapter-requirements"></a>Anforderungen des Reverse Proxy-Netzwerkadapters

  - Beispiel für **einen Netzwerkadapter 1 (interne Schnittstelle)**
    
    Interne Schnittstelle mit zugewiesenem 172.25.33.40
    
    Es wurde kein Standardgateway definiert.
    
    Stellen Sie sicher, dass eine Route aus dem Netzwerk mit der internen Reverse Proxy-Schnittstelle zu allen Netzwerken vorhanden ist, die lync Server-Front-End-Pool Server enthalten (beispielsweise von 172.25.33.0 zu 192.168.10.0).

  - Beispiel für **Netzwerkadapter 2 (externe Schnittstelle)**
    
    Diesem Netzwerkadapter wird mindestens eine öffentliche IP-Adresse zugewiesen.
    
    Gateway wird definiert, um auf den Router oder die integrierte Firewall im äußeren Umkreis zu verweisen. (10.45.16.1 in den Szenario-Beispielen)

### <a name="dns-records-required-for-reverse-proxy"></a>Für Reverse-Proxy erforderliche DNS-Einträge

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Ort/Typ/Port</th>
<th>FQDN</th>
<th>IP-Adresse</th>
<th>Karten/Kommentare</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Externer DNS/A</p></td>
<td><p>Webext.contoso.com</p></td>
<td><p>Zugewiesener Listener für extern veröffentlichte Ressourcen</p></td>
<td><p>Externe Webdienste aus der internen Bereitstellung. Zusätzliche Datensätze können für alle Pools und Einzelserver für alle SIP-Domänen definiert und erstellt werden, die diesen Reverseproxy verwenden, und hat externe Webdienste definiert.</p></td>
</tr>
<tr class="even">
<td><p>Externer DNS/A</p></td>
<td><p>webdirext.contoso.com</p></td>
<td><p>Zugewiesener Listener für extern veröffentlichte Ressourcen</p></td>
<td><p>Externe Webdienste für die Directors-oder Director-Pools in Ihrer Bereitstellung. Sie können beliebig viele Directors definieren, da es verschiedene Directors gibt, die möglicherweise anderen SIP-Domänen zugeordnet sind.</p>
<div>

> [!IMPORTANT]  
> Das Definieren der DNS-Einträge für und die Veröffentlichung der Directors ist weder der Front-End-Pool noch die Entscheidung des Regisseurs. Sie müssen sowohl den Director als auch den Front-End-Pool externer Webdienste definieren und veröffentlichen, wenn Sie Directors verwenden. Bestimmte Datenverkehrstypen (für Authentifizierung und andere Verwendungszwecke) werden zuerst an den Director gesendet, wenn er in der Topologie definiert ist.


</div></td>
</tr>
<tr class="odd">
<td><p>Externer DNS/A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>Zugewiesener Listener für extern veröffentlichte Ressourcen</p></td>
<td><p>Extern veröffentlichte Einwahlkonferenzen</p></td>
</tr>
<tr class="even">
<td><p>Externer DNS/A</p></td>
<td><p>Meet.contoso.com</p></td>
<td><p>Zugewiesener Listener für extern veröffentlichte Ressourcen</p></td>
<td><p>Extern veröffentlichte Konferenzen</p></td>
</tr>
<tr class="odd">
<td><p>Externer DNS/A</p></td>
<td><p>officewebapps01.contoso.com</p></td>
<td><p>Zugeordneter Listener für Office Web Apps Server</p></td>
<td><p>Office Web Apps Server wird intern oder im Umkreis bereitgestellt und für den Zugriff auf externe Clients veröffentlicht</p></td>
</tr>
<tr class="even">
<td><p>Externer DNS/A</p></td>
<td><p>lyncdiscover.contoso.com</p></td>
<td><p>Zugewiesener Listener für extern veröffentlichte Ressourcen</p></td>
<td><p>Lync erkennt externen Eintrag für extern veröffentlichte AutoErmittlung und umfasst Mobilität, Microsoft lync Web App und Scheduler Web App</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

