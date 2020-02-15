---
title: 'Lync Server 2013: DNS-Anforderungen für die automatische Clientanmeldung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for automatic client sign-in
ms:assetid: 3bcd4bb3-a022-4ffa-b005-1a95ad2b1796
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425884(v=OCS.15)
ms:contentKeyID: 48183873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b022d9780d1498f70fd5918894a1412996731004
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031239"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-automatic-client-sign-in-in-lync-server-2013"></a>DNS-Anforderungen für die automatische Clientanmeldung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-06-19_

In diesem Abschnitt wird erläutert, welche DNS-Einträge (Domain Name System) für die automatische Clientanmeldung erforderlich sind. Wenn Sie Standard Edition-Server oder Front-End-Pools bereitstellen, können Sie Ihre Clients zur automatischen Ermittlung von und Anmeldung am geeigneten Standard Edition-Server oder Front-End-Pool konfigurieren. Wenn Sie planen, dass Ihre Clients manuell mit lync Server 2013 eine Verbindung herstellen müssen, können Sie dieses Thema überspringen.

Zur Unterstützung der automatischen Clientanmeldung müssen Sie folgende Aufgaben ausführen:

  - Legen Sie einen einzelnen Server oder Pool für die Verteilung und Authentifizierung von Clientanmeldeanforderungen fest. Hierbei kann es sich um einen vorhandenen Server oder Pool handeln, der Benutzer hostet, oder Sie können zu diesem Zweck einen dedizierten Server oder Pool zuweisen, der keine Benutzer hostet. Um eine hohe Verfügbarkeit sicherzustellen, wird empfohlen, einen Front-End-Pool für diese Funktion zuzuweisen.

  - Erstellen Sie einen internen DNS-SRV-Eintrag zur Unterstützung der automatischen Clientanmeldung für diesen Server oder Pool.
    
    <div>
    

    > [!NOTE]  
    > In den folgenden Eintragsanforderungen bezieht sich die SIP-Domäne auf den Hostabschnitt der SIP-URIs, die Benutzern zugewiesen sind. Wenn die SIP-URIs beispielsweise das Format "*@contoso.com" aufweisen, bezeichnet "contoso.com" die SIP-Domäne. Die SIP-Domäne unterscheidet sich häufig von der internen Active Directory-Domäne. In einer Organisation können auch mehrere SIP-Domänen unterstützt werden.

    
    </div>

Um die automatische Konfiguration für Ihre Clients zu aktivieren, müssen Sie einen internen DNS-SRV-Eintrag erstellen, der einen der folgenden Einträge dem vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Front-End-Pool oder Standard Edition-Server zuordnet, der Anmeldeanforderungen von lync verteilt. Clients

  - \_sipinternaltls. \_TCP. \<Domäne\> – für interne TLS-Verbindungen

Sie müssen für den Front-End-Pool oder Standard Edition-Server, der die Anmeldeanforderungen verteilt, nur einen einzigen SRV-Eintrag erstellen.

Die folgende Tabelle enthält einige der erforderlichen Beispieleinträge für das fiktive Unternehmen Contoso, das die SIP-Domänen "contoso.com" und "retail.contoso.com" unterstützt.

### <a name="example-of-dns-records-required-for-automatic-client-sign-in-with-multiple-sip-domains"></a>Beispiele für erforderliche DNS-Einträge für die automatische Clientanmeldung bei mehreren SIP-Domänen

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>FQDN des Front-End-Pools für die Verteilung von Anmeldeanforderungen</th>
<th>SIP-Domäne</th>
<th>DNS-SRV-Eintrag</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>pool01.contoso.com</p></td>
<td><p>contoso.com</p></td>
<td><p>Ein SRV-Eintrag für die Domäne "_sipinternaltls._tcp.contoso.com" über Port 5061, der "pool01.contoso.com" zugeordnet ist</p></td>
</tr>
<tr class="even">
<td><p>pool01.contoso.com</p></td>
<td><p>retail.contoso.com</p></td>
<td><p>Ein SRV-Eintrag für die Domäne "_sipinternaltls._tcp.retail.contoso.com" über Port 5061, der "pool01.contoso.com" zugeordnet ist</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> In der Standardeinstellung müssen bei Abfragen für DNS-Einträge die Domänennamen im Benutzernamen und im SRV-Eintrag genau übereinstimmen. Wenn bei DNS-Abfragen des Clients stattdessen die Suffixe verglichen werden sollen, können Sie die Gruppenrichtlinie "DisableStrictDNSNaming" konfigurieren. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-planning-for-clients-and-devices.md">Planning for Clients and Devices in lync Server 2013</A> in der Planungsdokumentation.



</div>

<div>

## <a name="example-of-the-certificates-and-dns-records-required-for-automatic-client-sign-in"></a>Beispiele für erforderliche Zertifikate und DNS-Einträge für die automatische Clientanmeldung

In diesem Beispiel werden dieselben Beispiele wie in der oben gezeigten Tabelle verwendet. Das Unternehmen Contoso unterstützt die SIP-Domänen "contoso.com" und "retail.contoso.com", und alle Benutzer des Unternehmens verfügen über einen SIP-URI in einem der folgenden Formate:

  - \<Benutzer\>@Retail. contoso.com

  - \<Benutzer\>@contoso. com

</div>

</div>

<span> </span>

</div>

</div>

</div>

