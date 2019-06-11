---
title: 'Lync Server 2013: Unterstützung für die Integration gehosteter Exchange UM-Dienste'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Support for hosted Exchange UM integration
ms:assetid: c7573ec3-013c-48d9-b59b-2a5427e6da35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398821(v=OCS.15)
ms:contentKeyID: 48185376
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56ba107c9a782acb15ccd8d57f82cf567f2b75e1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847702"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="support-for-hosted-exchange-um-integration-in-lync-server-2013"></a>Unterstützung für die Integration gehosteter Exchange UM-Dienste in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

Die lync Server 2013 ExUM-Routing Anwendung unterstützt die Integration in Exchange Unified Messaging (um) in einer lokalen Umgebung, in der lync Server 2013 und Exchange um sowohl lokal innerhalb Ihres Unternehmens installiert sind, als auch in Exchange um von einer Dienstanbieter, wie in der folgenden Abbildung dargestellt.

![Lokale lync Server Exchange um-Bereitstellung] (images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "Lokale lync Server Exchange um-Bereitstellung")

Die folgenden Modi werden unterstützt:

  - **Der lokale Modus**   lync Server 2013 und Exchange um werden auf lokalen Servern innerhalb Ihres Unternehmens bereitgestellt.

  - ****   Standortübergreifender Modus lync Server 2013 wird auf lokalen Servern innerhalb Ihres Unternehmens bereitgestellt, und Exchange um wird in der Einrichtung eines Onlinedienstanbieters wie einem Microsoft Exchange Online-Rechenzentrum gehostet.

  - **Gemischter Modus**   ihre lync Server 2013-Bereitstellung enthält einige Benutzerpostfächer, die sich auf lokalen Servern mit Microsoft Exchange Server innerhalb Ihres Unternehmens und einigen Postfächern befinden, die in einem gehosteten Exchange-Dienst-Rechenzentrum verwaltet werden.
    
    <div>
    

    > [!NOTE]  
    > Der gemischte Modus kann während der Evaluierung und schrittweisen Migration von Benutzern zu Hosted Exchange um als Übergangslösung verwendet werden, oder als dauerhafte Lösung, wenn Sie sich entscheiden, die Exchange um-Dienste einiger Benutzer nach der Migration anderer Personen lokal zu verwalten.

    
    </div>

Zum Integrieren von lync Server 2013 in gehostete Exchange um müssen Sie einen *freigegebenen SIP-Adressraum* (auch als geteilte *Domäne*bezeichnet) konfigurieren. In dieser Konfiguration können sowohl lync Server 2013 als auch der von einem Drittanbieter gehostete Exchange um-Dienstanbieter auf denselben SIP-Domänen Adressraum zugreifen. Ausführliche Informationen finden Sie unter [Hosted Exchange um-Integrationsarchitektur in lync Server 2013](lync-server-2013-hosted-exchange-um-integration-architecture.md) in der Planungsdokumentation.

</div>

<span> </span>

</div>

</div>

</div>

