---
title: Lync Server 2013 Unterstützung für gehostete Exchange um Integration
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Support for hosted Exchange UM integration
ms:assetid: c7573ec3-013c-48d9-b59b-2a5427e6da35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398821(v=OCS.15)
ms:contentKeyID: 48185376
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 89c87de9c57abaf4938b350aa40e8deea1150d22
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208291"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="support-for-hosted-exchange-um-integration-in-lync-server-2013"></a>Unterstützung für gehostete Exchange um Integration in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-21_

Die lync Server 2013 ExUM-Routing Anwendung unterstützt die Integration in Exchange Unified Messaging (um) in einer lokalen Umgebung, in der lync Server 2013 und Exchange um sowohl lokal in Ihrem Unternehmen installiert sind, als auch in mit Exchange um Hosted by a Dienstanbieter, wie im folgenden Diagramm dargestellt.

![Lokale lync Server Exchange um-Bereitstellung](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "Lokale lync Server Exchange um-Bereitstellung")

Die folgenden Modi werden unterstützt:

  - ****   Der lokale Modus lync Server 2013 und Exchange um werden auf lokalen Servern innerhalb Ihres Unternehmens bereitgestellt.

  - **Standortübergreifender Modus**   lync Server 2013 wird auf lokalen Servern innerhalb Ihres Unternehmens bereitgestellt, und Exchange um wird in der Einrichtung eines Onlinedienstanbieters gehostet, beispielsweise in einem Microsoft Exchange Online-Rechenzentrum.

  - **Gemischter Modus**   bei ihrer lync Server 2013-Bereitstellung befinden sich einige Benutzerpostfächer auf lokalen Servern, auf denen Exchange Server in Ihrem Unternehmen ausgeführt wird, sowie einige Postfächer, die in einem gehosteten Exchange-Dienst Datencenter verwaltet werden
    
    <div>
    

    > [!NOTE]  
    > Der gemischte Modus kann als Übergangslösung bei der Evaluierung und schrittweisen Migration von Benutzern zu gehosteten Exchange um oder als dauerhafte Lösung verwendet werden, wenn Sie sich dafür entscheiden, einige Benutzer Exchange um Dienste lokal zu halten, nachdem Sie andere Personen migriert haben.

    
    </div>

Um lync Server 2013 mit gehosteten Exchange um zu integrieren, müssen Sie einen *freigegebenen SIP-Adressraum* konfigurieren (auch als *geteilte Domäne*bezeichnet). In dieser Konfiguration können sowohl lync Server 2013 als auch der von einem Drittanbieter gehostete Exchange um-Dienstanbieter auf denselben Adressraum für die SIP-Domäne zugreifen. Ausführliche Informationen finden Sie unter [Hosted Exchange um Integration Architecture in lync Server 2013](lync-server-2013-hosted-exchange-um-integration-architecture.md) in der Planungsdokumentation.

</div>

<span> </span>

</div>

</div>

</div>

