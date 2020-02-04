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
ms.openlocfilehash: 6d033621382587367630d9119c2176e976cb2c2d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739155"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-automatic-client-sign-in-in-lync-server-2013"></a>DNS-Anforderungen für die automatische Clientanmeldung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-06-19_

In diesem Abschnitt werden die DNS-Einträge (Domain Name System) erläutert, die für die automatische Clientanmeldung erforderlich sind. Wenn Sie Ihre Standard Edition-Server oder Front-End-Pools bereitstellen, können Sie Ihre Clients so konfigurieren, dass die automatische Ermittlung für die Anmeldung beim entsprechenden Standard Edition-Server oder Front-End-Pool verwendet wird. Wenn Sie planen, dass Ihre Clients eine Verbindung mit lync Server 2013 manuell herstellen müssen, können Sie dieses Thema überspringen.

Um die automatische Clientanmeldung zu unterstützen, müssen Sie Folgendes ausführen:

  - Festlegen eines einzelnen Servers oder Pools zum Verteilen und Authentifizieren von Clientanmeldeanforderungen Hierbei kann es sich um einen vorhandenen Server oder Pool in Ihrer Organisation handeln, der Benutzer hostet, oder Sie können einen dedizierten Server oder Pool für diesen Zweck festlegen, der keine Benutzer hostet. Für eine höhere Verfügbarkeit empfehlen wir, einen Front-End-Pool für diese Funktion festzulegen.

  - Erstellen Sie einen internen DNS-SRV-Eintrag, um die automatische Clientanmeldung für diesen Server oder Pool zu unterstützen.
    
    <div>
    

    > [!NOTE]  
    > In den folgenden Daten Satz Anforderungen bezieht sich die SIP-Domäne auf den Hostbereich der SIP-URIs, die Benutzern zugewiesen sind. Wenn beispielsweise SIP-URIs die Form * @contoso. com aufweisen, ist contoso.com die SIP-Domäne. Die SIP-Domäne unterscheidet sich häufig von der internen Active Directory-Domäne. Eine Organisation kann auch mehrere SIP-Domänen unterstützen.

    
    </div>

Wenn Sie die automatische Konfiguration für Ihre Clients aktivieren möchten, müssen Sie einen internen DNS-SRV-Eintrag erstellen, der einen der folgenden Einträge dem vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Front-End-Pools oder Standard Edition-Servers zuordnet, der Anmeldeanforderungen von lync verteilt. Clients

  - \_sipinternaltls. \_TCP. \<Domäne\> – für interne TLS-Verbindungen

Sie müssen nur einen einzelnen SRV-Eintrag für den Front-End-Pool oder Standard Edition-Server erstellen oder die Anmeldeanforderungen verteilen.

In der folgenden Tabelle sind einige Beispieldatensätze aufgeführt, die für das fiktive Unternehmen Contoso erforderlich sind, das SIP-Domänen von contoso.com und Retail.contoso.com unterstützt.

### <a name="example-of-dns-records-required-for-automatic-client-sign-in-with-multiple-sip-domains"></a>Beispiel für DNS-Einträge, die für die automatische Client Anmeldung mit mehreren SIP-Domänen erforderlich sind

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>FQDN des Front-End-Pools, der zum Verteilen von Anmeldeanforderungen verwendet wird</th>
<th>SIP-Domäne</th>
<th>DNS-SRV-Eintrag</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>pool01.contoso.com</p></td>
<td><p>contoso.com</p></td>
<td><p>Ein SRV-Eintrag für _sipinternaltls _tcp. contoso. com-Domäne über Port 5061, der pool01.contoso.com zugeordnet ist</p></td>
</tr>
<tr class="even">
<td><p>pool01.contoso.com</p></td>
<td><p>retail.contoso.com</p></td>
<td><p>Ein SRV-Eintrag für _sipinternaltls. _tcp. Retail. contoso. com-Domäne über Port 5061, der pool01.contoso.com zugeordnet ist</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Standardmäßig befolgen Abfragen für DNS-Einträge den strikten Domänennamen Abgleich zwischen der Domäne im Benutzernamen und dem SRV-Eintrag. Wenn Sie es vorziehen, dass Client-DNS-Abfragen stattdessen Suffix-Abgleich verwenden, können Sie die DisableStrictDNSNaming-Gruppenrichtlinie konfigurieren. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-planning-for-clients-and-devices.md">Planen von Clients und Geräten in lync Server 2013</A> in der Planungsdokumentation.



</div>

<div>

## <a name="example-of-the-certificates-and-dns-records-required-for-automatic-client-sign-in"></a>Beispiel für die für die automatische Client Anmeldung erforderlichen Zertifikate und DNS-Einträge

In diesem Beispiel werden die gleichen Beispiel Namen in der vorhergehenden Tabelle verwendet. Die Contoso-Organisation unterstützt die SIP-Domänen von contoso.com und Retail.contoso.com, und alle Benutzer verfügen über einen SIP-URI in einem der folgenden Formate:

  - \<Benutzer\>@Retail. contoso.com

  - \<Benutzer\>@contoso. com

</div>

</div>

<span> </span>

</div>

</div>

</div>

