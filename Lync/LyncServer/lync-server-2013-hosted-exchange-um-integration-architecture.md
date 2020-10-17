---
title: 'Lync Server 2013: Hosted Exchange um Integration Architecture'
description: 'Lync Server 2013: Hosted Exchange um Integration Architecture.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange UM integration architecture
ms:assetid: 0094d5dc-1836-441c-b6e2-f88e35203a8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398067(v=OCS.15)
ms:contentKeyID: 48183222
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2399fa421b59a5ea1fd83b1a86225fc12de1f2ca
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552461"
---
# <a name="hosted-exchange-um-integration-architecture-in-lync-server-2013"></a>Gehostete Exchange um Integrationsarchitektur in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-25_

Die lync Server 2013 ExUM-Routing Anwendung unterstützt die Integration in eine lokale Exchange Unified Messaging (um)-Bereitstellung, wobei Exchange um von einem Dienstanbieter gehostet wird, oder mit einer Kombination aus beiden. Im nachfolgenden Diagramm werden alle drei Möglichkeiten dargestellt.

**Integration in eine Umgebung mit lokaler Exchange UM-Bereitstellung und zwei Anbietern für gehostete Exchange-Dienste**

![Lokale lync Server Exchange um-Bereitstellung](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "Lokale lync Server Exchange um-Bereitstellung")

Die folgenden Modi werden unterstützt:

  - **Lokale Bereitstellung:** Lync Server 2013 und Exchange um werden auf lokalen Servern innerhalb Ihres Unternehmens bereitgestellt.

  - **Standortübergreifende Bereitstellung:** Lync Server 2013 wird auf lokalen Servern innerhalb Ihres Unternehmens bereitgestellt, und Exchange um wird in der Einrichtung eines Onlinedienstanbieters gehostet, beispielsweise in einem Microsoft Exchange Online-Rechenzentrum.

  - **Gemischte Bereitstellung:** Bei ihrer lync Server 2013-Bereitstellung befinden sich einige Benutzerpostfächer auf lokalen Exchange-Servern innerhalb Ihres Unternehmens und einige Postfächer, die in einem gehosteten Exchange-Dienst Datencenter verwaltet werden.
    
    <div>
    

    > [!NOTE]  
    > Die gemischte Bereitstellung kann als Übergangslösung bei der Evaluierung und bei einer in Phasen durchgeführten Migration von Benutzern zu gehosteten Exchange UM-Diensten oder als dauerhafte Lösung eingesetzt werden, wenn Sie einige Exchange UM-Dienste nach der Migration weiterhin lokal verwalten möchten.

    
    </div>

<div>

## <a name="shared-sip-address-space"></a>Freigegebener SIP-Adressraum

Zum Integrieren von lync Server 2013 in eine lokale Exchange um-Bereitstellung erteilen Sie lync Server 2013 Berechtigung zum Lesen Exchange um Active Directory-Domänendienste-Objekten. Diese Vorgehensweise funktioniert jedoch nicht für die Integration in gehostete Exchange um, da lync Server 2013 und Exchange um in getrennten Gesamtstrukturen installiert werden, ohne dass diese vertrauenswürdig sind.

Um lync Server 2013 mit gehosteten Exchange um zu integrieren, müssen Sie einen *freigegebenen SIP-Adressraum*konfigurieren. In dieser Konfiguration ist derselbe SIP-Domänen Adressraum sowohl für lync Server 2013 als auch für den gehosteten Exchange um Dienstanbieter verfügbar.

<div>


> [!NOTE]  
> Die Verwendung des freigegebenen SIP-Adressraums ähnelt dem in einer standortübergreifenden lync Server 2013 Umgebung verwendeten Ansatz, bei dem einige Benutzer in der lokalen Bereitstellung verwaltet werden und einige in einer gehosteten Bereitstellung (beispielsweise lync Online) verwaltet werden. Die SIP-Domäne wird zwischen den Umgebungen aufgeteilt. Wenn Sie lync Server 2013 mit gehosteten Exchange um integrieren, stellen Sie sicher, dass Sie den Exchange um Dienstanbieter in den freigegebenen SIP-Adressraum einschließen.



</div>

Zum Konfigurieren des freigegebenen SIP-Adressraums für die Integration in eine Umgebung mit einem Exchange UM-Dienstanbieter müssen Sie Ihren Edgeserver folgendermaßen konfigurieren:

1.  Konfigurieren Sie den Edgeserver für den Partnerverbund, indem Sie mit dem **Set-CsAccessEdgeConfiguration**-Cmdlet die folgenden Parameter festlegen:
    
      - **UseDnsSrvRouting** gibt an, dass Edgeserver beim Senden und Empfangen von Partnerverbundanforderungen auf DNS-SRV-Einträge zurückgreifen.
    
      - **AllowFederatedUsers** gibt an, ob interne Benutzer mit Benutzern aus Partnerdomänen kommunizieren dürfen. Diese Eigenschaft legt außerdem fest, ob interne Benutzer mit Benutzern in einem Szenario mit getrennten Domänen kommunizieren können.
    
      - **EnablePartnerDiscovery** gibt an, ob lync Server 2013 DNS-Einträge verwenden, um Partnerdomänen zu ermitteln, die nicht in der Liste zugelassene Domänen Active Directory aufgeführt werden. Wenn false, werden lync Server 2013 nur mit Domänen zusammenfassen, die in der Liste zugelassene Domänen gefunden werden. Dieser Parameter ist für die Verwendung von DNS-Dienstrouting erforderlich. In den meisten Bereitstellungen ist der Wert auf "False" gesetzt, um einen Partnerverbund mit allen Partnern zu vermeiden.

2.  Replizieren Sie den zentralen Verwaltungsspeicher in den Edgeserver, und überprüfen Sie die Replikation. Ausführliche Informationen finden Sie unter [Exportieren Ihrer lync Server 2013 Topologie und Kopieren dieser auf externe Medien für die Edge-Installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) in der Bereitstellungsdokumentation.

3.  Konfigurieren Sie einen *Hostinganbieter* auf dem Edgeserver, indem Sie mit dem Cmdlet **New-CsHostingProvider** die folgenden Parameter festlegen:
    
      - **Identity** gibt einen eindeutigen Zeichenfolgenwert für den Hostinganbieter an, den Sie erstellen, beispielsweise **Hosted Exchange UM**.
    
      - **Enabled** gibt an, ob die Netzwerkverbindung zwischen Ihrer Domäne und dem Hostinganbieter aktiviert ist. Dieser Parameter muss auf **True** festgelegt werden.
    
      - **EnabledSharedAddressSpace** gibt an, ob der Hostinganbieter in einem Szenario mit freigegebenem SIP-Adressraum verwendet wird. Dieser Parameter muss auf **True** festgelegt werden.
    
      - **HostsOCSUsers** gibt an, ob der Hostinganbieter zum Hosten von lync Server 2013 Konten verwendet wird. Dieser Parameter muss auf **False** festgelegt werden.
    
      - **ProxyFQDN** gibt den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des vom Hostinganbieter verwendeten Proxyservers an, z. B. **proxyserver.fabrikam.com**. Sie erhalten diese Information von Ihrem Hostinganbieter. Dieser Wert kann nicht geändert werden. Wenn der Hostinganbieter seinen Proxyserver ändert, muss der Eintrag für diesen Anbieter gelöscht und neu erstellt werden.
    
      - **IsLocal** gibt an, ob der vom Hostinganbieter verwendete Proxy Server in ihrer lync Server 2013 Topologie enthalten ist. Dieser Parameter muss auf **False** festgelegt werden.

</div>

</div>

<span> </span>

</div>

</div>

</div>

