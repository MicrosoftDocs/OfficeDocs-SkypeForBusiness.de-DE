---
title: 'Lync Server 2013: Definieren zusätzlicher Trunks im Topologie-Generator'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define additional trunks in Topology Builder
ms:assetid: e68b8377-50a2-452a-bf5c-910929e34236
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721915(v=OCS.15)
ms:contentKeyID: 49733849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e8e5650492cc51b024b03cc0c92f64ff46d818b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504642"
---
# <a name="define-additional-trunks-in-topology-builder-in-lync-server-2013"></a>Definieren zusätzlicher Trunks im Topologie-Generator in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-04_

Führen Sie die folgenden Schritte aus, um den Topologie-Generator zum Definieren eines zusätzlichen Trunks zu verwenden, dem Sie einen *Peer* einem Vermittlungsserver zuordnen können. Ein Peer stellt für Enterprise-VoIP aktivierte Benutzer Verbindungen mit dem Telefon Festnetz (Public Switched Telephone Network, PSTN) bereit. Bei dem Peer kann es sich um ein PSTN-Gateway, eine IP-Nebenstellenanlage oder einen Session Border Controller (SBC) für einen Anbieter von Internettelefoniediensten handeln. Der trunk definiert diese Verbindung zwischen dem Vermittlungsserver und dem Peer. Pro Vermittlungsserver können mehrere Trunks definiert werden. Ein Vermittlungsserver kann mehreren Peers zugeordnet werden.

Ein trunk ist eine logische Verbindung zwischen einem Vermittlungsserver und einem Gateway, das durch das Tupel eindeutig identifiziert wird:

{Vermittlungsserver FQDN, Vermittlungsserver Abhör Port (TLS oder TCP): Gateway-IP und FQDN, Gateway-Abhör Port}

<div>


> [!NOTE]  
> In diesem Thema wird davon ausgegangen, dass Sie ein PSTN-Gateway und einen Stamm trunk mit mindestens einem verbundenen oder eigenständigen Vermittlungsserver oder Pool eingerichtet haben, wie unter <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">define a Gateway in Topology Builder in lync Server 2013</A> in der Bereitstellungsdokumentation beschrieben.



</div>

<div>


> [!NOTE]  
> In diesem Thema wird davon ausgegangen, dass Sie mindestens einen Front-End-Pool oder Standard Edition-Server an mindestens einem zentralen Standort eingerichtet haben, wie unter <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">define and configure a Front-End-Pool or Standard Edition-Server in lync Server 2013</A> und <A href="lync-server-2013-publish-the-topology.md">Veröffentlichen der Topologie in lync Server 2013</A> in der Bereitstellungsdokumentation beschrieben.



</div>

<div>

## <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a>So definieren Sie einen zusätzlichen trunk zwischen einem Vermittlungsserver und einem Gateway-Peer

1.  Starten Sie den Topologie-Generator: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topologie-Generator**.

2.  Klicken Sie unter lync Server 2013, Name Ihrer Website, **freigegebene Komponenten**mit der rechten Maustaste auf den Knoten **Trunks** , und klicken Sie dann auf **neuer trunk**.
    
    ![Dateistruktur Bildschirm für lync Server Topologie-Generator](images/JJ721915.90d5b349-aa1e-407a-87ed-fa112f478560(OCS.15).png "Dateistruktur Bildschirm für lync Server Topologie-Generator")

3.  Geben Sie in **Neuen Trunk definieren** einen Anzeigenamen ein, um den Trunk eindeutig zu identifizieren. Zwei Trunks mit demselben Namen sind nicht zulässig.
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie TLS (Transport Layer Security) als Transporttyp angeben, müssen Sie anstelle der IP-Adresse des Peers des Vermittlungsserver den FQDN angeben.

    
    </div>

4.  Wählen Sie unter **Zugeordnetes PSTN-Gateway** den PSTN-Gatewaypeer aus, der diesem Trunk zugeordnet werden soll.
    
    ![Eigenschafteneinstellungen für PSTN-Gateway-Peer für trunk](images/JJ721915.7c3fe8ee-8f4c-4413-8462-8347228e61bb(OCS.15).png "Eigenschafteneinstellungen für PSTN-Gateway-Peer für trunk")

5.  Geben Sie unter **Abhör Port für PSTN-Gateway**den Abhör Port ein, den der Peer (PSTN-Gateway, IP-PBX oder SBC) SIP-Nachrichten von dem Vermittlungsserver empfängt, der diesem trunk zugeordnet werden soll. Die standardmäßigen Peer Ports sind 5066 für TCP (Transmission Control Protocol) und 5067 für TLS (Transport Layer Security). Die Standard Survivable Branch Appliance Ports sind 5081 für TCP und 5082 für TLS.

6.  Klicken Sie unter **SIP-Transportprotokoll** auf den vom Peer verwendeten Transporttyp.
    
    <div>
    

    > [!NOTE]  
    > Aus Sicherheitsgründen wird dringend empfohlen, einen Peer für den Vermittlungsserver bereitzustellen, der TLS verwenden kann.

    
    </div>

7.  Wählen Sie unter **zugeordnete Vermittlungsserver**den Vermittlungsserver-Pool aus, der dem Stamm trunk dieses Peers zugeordnet werden soll.

8.  Geben Sie unter **zugeordneter Vermittlungsserver Port**den Abhör Port ein, über den der Vermittlungsserver SIP-Nachrichten vom Peer empfängt.
    
    <div>
    

    > [!NOTE]  
    > Bei mehreren trunk-Unterstützung in lync Server 2013 können zwei Trunks mit unterschiedlichen trunk Namen nicht mit dem gleichen <STRONG>zugeordneten Vermittlungsserver-Port</STRONG> und dem <STRONG>Überwachungs Port für IP/PSTN-Gateway</STRONG> konfiguriert werden.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Bei mehreren trunk Unterstützung in lync Server 2013 können mehrere SIP-Signalisierungs Ports für die Vermittlungsserver für die Kommunikation mit mehreren Peers definiert werden. Beim Definieren eines Trunks muss sich die <STRONG>zugeordnete Vermittlungsserver Port</STRONG> Nummer innerhalb des Bereichs der Überwachungs Ports für das jeweilige vom Vermittlungsserver zugelassene Protokoll befinden. Dieser Portbereich ist unter lync Server 2013-und Vermittlungsserver-Pools definiert. Klicken Sie mit der rechten Maustaste auf den betreffenden Vermittlungsserver Pool, und wählen Sie <STRONG>Eigenschaften bearbeiten</STRONG>aus. Geben Sie den Portbereich im Feld <STRONG>Überwachungsports</STRONG> an.

    
    </div>

9.  Klicken Sie auf **OK**.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Ändern eines Trunks im Topologie-Generator in lync Server 2013](lync-server-2013-modify-a-trunk-in-topology-builder.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

