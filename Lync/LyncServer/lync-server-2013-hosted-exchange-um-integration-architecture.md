---
title: 'Lync Server 2013: Architektur für die Integration gehosteter Exchange UM-Dienste'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hosted Exchange UM integration architecture
ms:assetid: 0094d5dc-1836-441c-b6e2-f88e35203a8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398067(v=OCS.15)
ms:contentKeyID: 48183222
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2991bb35298534943d030b04c1cae7a438318c62
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832065"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-um-integration-architecture-in-lync-server-2013"></a>Architektur für die Integration gehosteter Exchange UM-Dienste in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-25_

Die lync Server 2013 ExUM-Routing Anwendung unterstützt die Integration in eine lokale Exchange Unified Messaging (um)-Bereitstellung, wobei Exchange um von einem Dienstanbieter gehostet wird oder mit einer Kombination der beiden. Das folgende Diagramm zeigt alle drei Möglichkeiten.

**Integration in eine lokale Exchange um-Bereitstellung und zwei gehostete Exchange-Anbieter**

![Lokale lync Server Exchange um-Bereitstellung] (images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "Lokale lync Server Exchange um-Bereitstellung")

Die folgenden Modi werden unterstützt:

  - **Lokale Bereitstellung:** Lync Server 2013 und Exchange um sind beide auf lokalen Servern innerhalb Ihres Unternehmens bereitgestellt.

  - **Standortübergreifende Bereitstellung:** Lync Server 2013 wird auf lokalen Servern innerhalb Ihres Unternehmens bereitgestellt, und Exchange um wird in der Einrichtung eines Onlinedienstanbieters, beispielsweise in einem Microsoft Exchange Online-Rechenzentrum, gehostet.

  - **Gemischte Bereitstellung:** In ihrer lync Server 2013-Bereitstellung sind einige Benutzerpostfächer auf lokalen Exchange-Servern innerhalb Ihres Unternehmens und einige Postfächer in einem gehosteten Exchange-Dienst-Rechenzentrum verwaltet.
    
    <div>
    

    > [!NOTE]  
    > Die gemischte Bereitstellung kann während der Evaluierung und der schrittweisen Migration von Benutzern zu Hosted Exchange um eine Übergangslösung sowie eine dauerhafte Lösung verwendet werden, wenn Sie sich entscheiden, die Exchange-um-Dienste einiger Benutzer nach der Übertragung anderer Personen lokal zu verwalten.

    
    </div>

<div>

## <a name="shared-sip-address-space"></a>Freigegebener SIP-Adressraum

Um lync Server 2013 in eine lokale Exchange um-Bereitstellung zu integrieren, erteilen Sie die lync Server 2013-Berechtigung zum Lesen von Exchange um-Active Directory-Domänendienste-Objekten. Dieser Ansatz funktioniert jedoch nicht für die Integration in Hosted Exchange um, da lync Server 2013 und Exchange um in getrennten Gesamtstrukturen installiert werden, die keine Vertrauensstellung zwischen Ihnen aufweisen.

Zum Integrieren von lync Server 2013 in gehostete Exchange um müssen Sie einen *freigegebenen SIP-Adressraum*konfigurieren. In dieser Konfiguration steht derselbe SIP-Domänen Adressraum sowohl für lync Server 2013 als auch für den gehosteten Exchange um-Dienstanbieter zur Verfügung.

<div>


> [!NOTE]  
> Die Verwendung des freigegebenen SIP-Adressraums ähnelt dem in einer standortübergreifenden lync Server 2013-Umgebung verwendeten Ansatz, bei dem einige Benutzer in der lokalen Bereitstellung verwaltet werden und einige in einer gehosteten Bereitstellung (wie lync Online) verwaltet werden. Die SIP-Domäne wird zwischen ihnen aufgeteilt. Wenn Sie lync Server 2013 mit Hosted Exchange um integrieren, stellen Sie sicher, dass Sie den Exchange um-Dienstanbieter in den freigegebenen SIP-Adressraum einbeziehen.



</div>

Wenn Sie den freigegebenen SIP-Adressraum für die Integration in einen Exchange um-Dienstanbieter konfigurieren möchten, müssen Sie den Edgeserver wie folgt konfigurieren:

1.  Konfigurieren Sie den Edgeserver für Federation, indem Sie das Cmdlet " **festlegen-csaccessedgeconfiguration nicht angeben** " ausführen, um die folgenden Parameter einzurichten:
    
      - **UseDnsSrvRouting** gibt an, dass Edgeserver beim Senden und Empfangen von Partnerverbundanforderungen auf DNS-SRV-Einträge zurückgreifen.
    
      - **AllowFederatedUsers** gibt an, ob interne Benutzer mit Benutzern aus Partnerdomänen kommunizieren dürfen. Diese Eigenschaft legt außerdem fest, ob interne Benutzer mit Benutzern in einem Szenario mit getrennten Domänen kommunizieren können.
    
      - **EnablePartnerDiscovery** gibt an, ob lync Server 2013 DNS-Einträge verwendet, um zu versuchen, Partnerdomänen zu finden, die nicht in der Liste der zulässigen Domänen für Active Directory aufgeführt sind. Ist der Wert false, wird lync Server 2013 nur mit Domänen zusammen, die in der Liste zugelassene Domänen gefunden werden. Dieser Parameter ist für die Verwendung von DNS-Dienstrouting erforderlich. In den meisten Bereitstellungen ist der Wert auf "False" gesetzt, um einen Partnerverbund mit allen Partnern zu vermeiden.

2.  Replizieren Sie den zentralen Verwaltungsspeicher auf den Edgeserver, und überprüfen Sie die Replikation. Ausführliche Informationen finden Sie unter [Exportieren Ihrer lync Server 2013-Topologie und Kopieren der Edge-Installation in externe Medien](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) in der Bereitstellungsdokumentation.

3.  Konfigurieren Sie einen *Hostinganbieter* auf dem Edgeserver, indem Sie das Cmdlet **New-CsHostingProvider** ausführen, um die folgenden Parameter einzurichten:
    
      - **Identity** gibt einen eindeutigen Zeichenfolgenwert Bezeichner für den Hostinganbieter an, den Sie erstellen, beispielsweise " **Hosted Exchange um**".
    
      - **Enabled** gibt an, ob die Netzwerkverbindung zwischen Ihrer Domäne und dem Hostinganbieter aktiviert ist. Muss auf " **true**" festgelegt werden.
    
      - **EnabledSharedAddressSpace** gibt an, ob der Hostinganbieter in einem Szenario mit freigegebenem SIP-Adressraum verwendet wird. Muss auf " **true**" festgelegt werden.
    
      - **HostsOCSUsers** gibt an, ob der Hostinganbieter zum Hosten von lync Server 2013-Konten verwendet wird. Muss auf " **false**" festgelegt sein.
    
      - **ProxyFQDN** gibt den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für den vom Hostinganbieter verwendeten Proxy Server an, beispielsweise **Proxyserver.fabrikam.com**. Wenden Sie sich für diese Informationen an Ihren Hostinganbieter. Dieser Wert kann nicht geändert werden. Wenn der Hostinganbieter seinen Proxy Server ändert, müssen Sie den Eintrag für diesen Anbieter löschen und dann erneut erstellen.
    
      - **IsLocal** gibt an, ob der vom Hostinganbieter verwendete Proxy Server in ihrer lync Server 2013-Topologie enthalten ist. Muss auf " **false**" festgelegt sein.

</div>

</div>

<span> </span>

</div>

</div>

</div>

