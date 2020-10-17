---
title: Lync Server 2013 Referenztopologie für kleine Organisationen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reference topology for small organizations
ms:assetid: 0453aeee-c41f-44e6-a6e0-aaace526ca08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398095(v=OCS.15)
ms:contentKeyID: 48183272
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68163756f2c2153d1e164999532bc6265400ac5b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536732"
---
# <a name="reference-topology-for-lync-server-2013-in-small-organizations"></a>Referenztopologie für lync Server 2013 in kleinen Organisationen

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-10-07_

Die Referenztopologie für kleine Organisationen zeigt, wie Sie eine stabile, hoch verfügbare Lösung bereitstellen können, indem Sie nur drei Server mit lync Server bereitstellen.

**Referenztopologie für kleine Organisationen**

![Referenztopologie Bereitstellen von drei Server Diagrammen](images/Gg398095.25196d0d-dd07-451b-83ba-94c0ddf59030(OCS.15).jpg "Referenztopologie Bereitstellen von drei Server Diagrammen")

  - **Paar von Standard Edition-Servern, die bereitgestellt werden**     Diese Organisation verfügt über 4.000 Benutzer am zentralen Standort. Die Organisation hat zwei Standard Edition-Server bereitgestellt und kombiniert, um hohe Verfügbarkeit und Notfallwiederherstellung zu ermöglichen. Jeder Server Homes 2.000 Benutzer, aber Informationen zu allen Benutzern werden zwischen den beiden Servern synchronisiert. Wenn eine ausfällt, kann ein Administrator ein Failover für diese Benutzer durchführen, um von dem anderen Server bedient zu werden, mit einem Minimum an Unterbrechungen für die Benutzer. Weitere Informationen zu Funktionen für hohe Verfügbarkeit und Notfallwiederherstellung in lync Server 2013 finden Sie unter [Planning for High Availability and Disaster Recovery in lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

  - **Edgeserver Bereitstellung wird empfohlen.**     Obwohl die Bereitstellungeines Edgeserver für interne Sofortnachrichten, Anwesenheitsinformationen und Konferenzen nicht erforderlich ist, wird dies auch für kleine Bereitstellungen empfohlen. Sie können Ihre lync Server Investition maximieren, indem Sie eine Edgeserver bereitstellen, um die Dienste für Benutzer bereitzustellen, die sich derzeit außerhalb der Firewalls Ihrer Organisation befinden. Hierdurch bieten sich folgende Vorteile:
    
      - Die eigenen Benutzer Ihrer Organisation können lync Server Funktionalität verwenden, wenn Sie von zu Hause aus arbeiten oder unterwegs sind.
    
      - Ihre Benutzer können externe Benutzer zur Teilnahme an Besprechungen einladen.
    
      - Wenn Sie über einen Partner, einen Anbieter oder eine Kundenorganisation verfügen, die auch lync Server verwendet, können Sie eine *Verbundbeziehung* mit dieser Organisation bilden. Ihre lync Server-Bereitstellung würde dann Benutzer aus dieser Verbundorganisation erkennen, was zu einer besseren Zusammenarbeit führt.
    
      - Ihre Benutzer können Sofortnachrichten mit Benutzern von öffentlichen Instant Messaging-Diensten austauschen, einschließlich einer oder aller der folgenden: Windows Live, AOL, Yahoo \! und Google Talk. Für öffentliche Chat Verbindungen mit diesen Diensten ist möglicherweise eine separate Lizenz erforderlich.
        
        <div>
        

        > [!IMPORTANT]  
        > <UL>
        > <LI>
        > <P>Seit dem 1. September 2012 ist die Microsoft lync Public Chat Connectivity-Benutzerabonnementlizenz ("PIC USL") nicht mehr für neue oder erneuerte Verträge verfügbar. Kunden mit aktiven Lizenzen können weiterhin mit Yahoo! zusammenarbeiten. Messenger, bis der Dienst das Datum heruntergefahren hat. Ein End-of-Life-Datum vom Juni 2014 für AOL und Yahoo! wurde angekündigt. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for Public Instant Messenger Connectivity in lync Server 2013</A>.</P>
        > <LI>
        > <P>Bei der PIC-USL handelt es sich um eine Abonnementlizenz pro Benutzer pro Monat, die für lync Server oder Office Communications Server für die Zusammensetzung mit Yahoo! erforderlich ist. Messenger. Die Fähigkeit von Microsoft, diesen Dienst bereitzustellen, wurde von der Unterstützung von Yahoo! abhängig gemacht, die zugrunde liegende Vereinbarung, für die die Rückabwicklung erfolgt.</P>
        > <LI>
        > <P>Lync ist mehr denn je ein leistungsfähiges Tool für die Verbindung zwischen verschiedenen Organisationen und mit Einzelpersonen auf der ganzen Welt. Für den Verbund mit Windows Live Messenger sind keine zusätzlichen Benutzer-/Gerätelizenzen außerhalb der lync-Standard-CAL erforderlich. Skype Federation wird dieser Liste hinzugefügt, sodass lync-Benutzer Hunderte Millionen von Benutzern mit Chat und VoIP erreichen können.</P></LI></UL>

        
        </div>

  - Überlebensfähigkeit von **Zweigstellen Websites.**     In dieser Organisation wird ein Pilotprogramm der Enterprise-VoIP-Funktion von lync Server durchführen. Einige Benutzer verwenden lync Server als einzige Sprachlösung. Einige dieser VoIP-Pilotbenutzer befinden sich am Zweigstellenstandort. Der Zweigstellenstandort verfügt nicht über eine zuverlässige WAN-Verbindung (Wide Area Network) mit dem zentralen Standort, sodass ein Survivable Branch Appliance dort bereitgestellt wird. Wenn die WAN-Verbindung ausfällt, können Benutzer am Zweigstellenstandort weiterhin Anrufe tätigen und empfangen (beide Anrufe innerhalb der Organisation und PSTN-Anrufe), über Voicemailfunktionen verfügen und mit Instant Messaging (Sofortnachrichten) mit zwei Teilnehmern kommunizieren. Benutzer können darüber hinaus auch dann authentifiziert werden, wenn die WAN-Verbindung nicht verfügbar ist.

  - **Exchange UM-Bereitstellung.** Diese Referenztopologie umfasst einen Exchange Unified Messaging (um) Server, der Exchange Server und nicht lync Server ausführt.
    
    Ausführliche Informationen zu Exchange um finden Sie unter [Planning for Exchange Unified Messagingintegration in lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) and [Hosted Exchange Unified Messagingintegration in lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) in der Planungsdokumentation.

  - **Office Web Apps Server.** Wir empfehlen die Bereitstellung eines Office Web Apps Servers oder einer Office Web Apps Server-Farm in allen Organisation, die Webkonferenzen unterstützen. Office-webapps-Server ermöglicht die Präsentation von PowerPoint-Folien in Webkonferenzen. Weitere Informationen finden Sie unter [Konfigurieren der Integration mit Office-webapps Server und lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

</div>

<span> </span>

</div>

</div>

</div>

