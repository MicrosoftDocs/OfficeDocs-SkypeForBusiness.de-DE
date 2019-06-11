---
title: 'Lync Server 2013: Definieren zusätzlicher Trunks im Topologie-Generator'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define additional trunks in Topology Builder
ms:assetid: e68b8377-50a2-452a-bf5c-910929e34236
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721915(v=OCS.15)
ms:contentKeyID: 49733849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b18d12762566258051d5fe0e7c71921b9fff160c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832722"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-additional-trunks-in-topology-builder-in-lync-server-2013"></a>Definieren zusätzlicher Trunks im Topologie-Generator in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-04_

Führen Sie die folgenden Schritte aus, um mithilfe des Topologie-Generators einen zusätzlichen trunk zu definieren, dem Sie einen *Peer* einem Vermittlungs Server zuordnen können. Ein Peer bietet Benutzern, die für Enterprise-VoIP aktiviert sind, Verbindungen mit dem öffentlich geschalteten Telefonnetz (PSTN). Bei einem Peer kann es sich um ein PSTN-Gateway, eine IP-Nebenstellenanlage oder einen Session Border Controller (SBC) für einen Anbieter von Internettelefoniediensten handeln. Der trunk definiert diese Verbindung zwischen dem Vermittlungs Server und dem Peer. Pro Vermittlungs Server können mehrere Trunks definiert werden. Ein Vermittlungs Server kann mehreren Peers zugeordnet werden.

Ein trunk ist eine logische Verbindung zwischen einem Vermittlungs Server und einem vom Tupel eindeutig identifizierten Gateway:

{Vermittlungsserver-FQDN, Abhör Port für Mediationsserver (TLS oder TCP): Gateway-IP und-FQDN, Gateway-Überwachungs Port}

<div>


> [!NOTE]  
> In diesem Thema wird davon ausgegangen, dass Sie ein PSTN-Gateway und einen Stamm Stamm mit mindestens einem zusammengefassten oder eigenständigen Vermittlungs Server oder-Pool eingerichtet haben, wie unter <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">Definieren eines Gateways im Topologie-Generator in lync Server 2013</A> in der Bereitstellungsdokumentation beschrieben.



</div>

<div>


> [!NOTE]  
> In diesem Thema wird davon ausgegangen, dass Sie mindestens einen Front-End-Pool oder Standard Edition-Server an mindestens einem zentralen Standort eingerichtet haben, wie unter <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">definieren und Konfigurieren eines Front-End-Pools oder Standard Edition-Servers in lync Server 2013</A> und <A href="lync-server-2013-publish-the-topology.md">Veröffentlichen der Topologie in lync beschrieben ist. Server 2013</A> in der Bereitstellungsdokumentation.



</div>

<div>

## <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a>So definieren Sie einen zusätzlichen trunk zwischen einem Vermittlungs Server und einem Gateway-Peer

1.  Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topology Builder**.

2.  Klicken Sie unter lync Server 2013, ihren Websitenamen, **freigegebene Komponenten**, mit der rechten Maustaste auf den Knoten **Trunks** , und klicken Sie dann auf **neuer trunk**.
    
    ![Bildschirm der Dateistruktur für lync Server Topology Builder] (images/JJ721915.90d5b349-aa1e-407a-87ed-fa112f478560(OCS.15).png "Bildschirm der Dateistruktur für lync Server Topology Builder")

3.  Geben Sie in **Neuen Trunk definieren** einen Anzeigenamen ein, um den Trunk eindeutig zu identifizieren. Zwei Trunks mit demselben Namen sind nicht zulässig.
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie TLS (Transport Layer Security) als Transporttyp angeben, müssen Sie anstelle der IP-Adresse des Peers des Vermittlungsservers den FQDN angeben.

    
    </div>

4.  Wählen Sie unter **Zugeordnetes PSTN-Gateway** den PSTN-Gatewaypeer aus, der diesem Trunk zugeordnet werden soll.
    
    ![Eigenschafteneinstellungen für PSTN-Gateway-Peer für trunk] (images/JJ721915.7c3fe8ee-8f4c-4413-8462-8347228e61bb(OCS.15).png "Eigenschafteneinstellungen für PSTN-Gateway-Peer für trunk")

5.  Geben Sie unter **Abhör-Port für PSTN-Gateway**den Abhör-Port ein, mit dem der Peer (PSTN-Gateway, IP-PBX oder SBC) SIP-Nachrichten vom Vermittlungs Server empfängt, der diesem trunk zugeordnet werden soll. Die standardmäßigen Peerports sind 5066 für TCP (Transmission Control Protocol) und 5067 für TLS (Transport Layer Security). Die Standardanschlüsse für Survivable Branch-Appliances sind 5081 für TCP und 5082 für TLS.

6.  Klicken Sie unter **SIP-Transportprotokoll** auf den vom Peer verwendeten Transporttyp.
    
    <div>
    

    > [!NOTE]  
    > Aus Sicherheitsgründen empfehlen wir dringend, einen Peer auf dem Vermittlungs Server bereitzustellen, der TLS verwenden kann.

    
    </div>

7.  Wählen Sie unter **zugeordneter Vermittlungsserver**den vermittlungsserverpool aus, der dem Stamm Stamm dieses Peers zugeordnet werden soll.

8.  Geben Sie unter **zugeordneter Vermittlungsserver-Port**den Abhör-Port ein, auf dem der Vermittlungsserver SIP-Nachrichten vom Peer empfängt.
    
    <div>
    

    > [!NOTE]  
    > Mit mehreren trunk-Unterstützung in lync Server 2013 können zwei Trunks mit unterschiedlichen trunk-Namen nicht mit dem gleichen <STRONG>zugeordneten Vermittlungs Server-Port</STRONG> und dem <STRONG>Überwachungs-Port für das IP/PSTN-Gateway</STRONG> konfiguriert werden.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Mit mehreren trunk-Unterstützung in lync Server 2013 können mehrere SIP-Signalisierungs Anschlüsse auf dem Vermittlungsserver für die Kommunikation mit mehreren Peers definiert werden. Wenn Sie einen trunk definieren, muss sich die <STRONG>zugeordnete Vermittlungsserver-Port</STRONG> Nummer innerhalb des Bereichs der Abhör Anschlüsse für das jeweilige vom Vermittlungsserver zugelassene Protokoll befinden. Dieser Portbereich ist unter lync Server 2013 und Mediation Server Pools definiert. Klicken Sie mit der rechten Maustaste auf den entsprechenden Vermittlungs Server Pool, und wählen Sie <STRONG>Eigenschaften bearbeiten</STRONG>aus. Specify the port range in the <STRONG>Listening ports</STRONG> field.

    
    </div>

9.  Klicken Sie anschließend auf **OK**.

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

