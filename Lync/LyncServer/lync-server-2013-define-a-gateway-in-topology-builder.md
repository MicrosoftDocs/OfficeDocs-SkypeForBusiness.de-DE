---
title: 'Lync Server 2013: Definieren eines Gateways im Topologie-Generator'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a gateway in Topology Builder
ms:assetid: 456e5a96-d9f6-42a6-862c-a69464391628
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425945(v=OCS.15)
ms:contentKeyID: 48184036
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18f257648ba24930eaab0d314e34178ffd67a0c2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733655"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-gateway-in-topology-builder-in-lync-server-2013"></a>Definieren eines Gateways im Topologie-Generator in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-04_

Führen Sie die folgenden Schritte aus, um mithilfe des Topologie-Generators einen *Peer* zu definieren, dem Sie einen Vermittlungs Server zuordnen können, um Verbindungen mit dem öffentlichen Telefonnetz (PSTN) für Benutzer bereitzustellen, die für Enterprise-VoIP aktiviert sind. Ein Peer-to-Mediation-Server kann ein PSTN-Gateway, eine IP-Telefonanlage oder ein Session Border Controller (SBC) für einen Internet-Telefoniedienstanbieter (ITSP) sein, mit dem Sie eine Verbindung herstellen, indem Sie einen SIP-Trunk konfigurieren.

<div>


> [!NOTE]  
> In diesem Thema wird davon ausgegangen, dass Sie mindestens einen internen Front-End-Pool oder Standard Edition-Server an mindestens einem zentralen Standort mit einem zusammengefassten oder eigenständigen Vermittlungsserver eingerichtet haben, wie unter <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">definieren und Konfigurieren eines Front-End-Pools oder Standard Edition-Servers in lync Server 2013</A> beschrieben und <A href="lync-server-2013-publish-the-topology.md">Veröffentlichen der Topologie in lync Server 2013</A> in der Bereitstellungsdokumentation. In diesem Thema wird auch davon ausgegangen, dass Sie überprüft haben, dass Ihre Infrastruktur die Voraussetzungen erfüllt, die unter <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">Software Voraussetzungen für Enterprise-VoIP in lync Server 2013</A> und <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">Sicherheits-und Konfigurationsvoraussetzungen für Enterprise-VoIP in lync Server 2013</A>beschrieben sind.



</div>

<div>

## <a name="to-define-a-peer-for-the-mediation-server"></a>So definieren Sie einen Peer für den Vermittlungs Server

1.  Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topology Builder**.

2.  Klicken Sie unter lync Server 2013, ihren Websitenamen, freigegebene Komponenten, mit der rechten Maustaste auf den Knoten **PSTN-Gateways** , und klicken Sie dann auf **Neues PSTN-Gateway**.
    
    ![d898c3c1-8798-4b74-8f02-b994ef3db4c1](images/Gg425945.d898c3c1-8798-4b74-8f02-b994ef3db4c1(OCS.15).png "d898c3c1-8798-4b74-8f02-b994ef3db4c1")

3.  Geben Sie unter **Neues IP/PSTN-Gateway definieren** den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) oder die IP-Adresse des Peers ein und klicken Sie auf **Weiter**.
    
    ![8017ba5e-41bc-48d4-97d9-fd306cd322b8](images/Gg425945.8017ba5e-41bc-48d4-97d9-fd306cd322b8(OCS.15).png "8017ba5e-41bc-48d4-97d9-fd306cd322b8")
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie TLS (Transport Layer Security) als Transporttyp angeben, müssen Sie anstelle der IP-Adresse des Peers des Vermittlungsservers den FQDN angeben.

    
    </div>

4.  Definieren Sie den Überwachungsmodus (IPv4 oder IPv6) für die IP-Adresse Ihres neuen PSTN-Gateways und klicken Sie auf **Weiter**.
    
    ![c7fc0d12-adc8-45a7-aca1-b376e1d2fcec](images/Gg425945.c7fc0d12-adc8-45a7-aca1-b376e1d2fcec(OCS.15).png "c7fc0d12-adc8-45a7-aca1-b376e1d2fcec")

5.  Definieren Sie einen *Stammtrunk* für das PSTN-Gateway. Ein trunk ist eine logische Verbindung zwischen einem Vermittlungs Server und einem vom Tupel eindeutig identifizierten Gateway.
    
    {Vermittlungsserver-FQDN, Abhör Port für Mediationsserver (TLS oder TCP): Gateway-IP und-FQDN, Gateway-Überwachungs Port}
    
      - Wenn Sie ein PSTN-Gateway im Topologie-Generator definieren, müssen Sie einen Stamm Stamm definieren, um das PSTN-Gateway erfolgreich zu Ihrer Topologie hinzuzufügen.
    
      - Der Stammtrunk kann erst entfernt werden, nachdem das damit verbundene PSTN-Gateway entfernt wurde.
    
    ![3b030757-eb35-4616-bb6b-74ee67507e3d](images/Gg425945.3b030757-eb35-4616-bb6b-74ee67507e3d(OCS.15).png "3b030757-eb35-4616-bb6b-74ee67507e3d")

6.  Geben Sie unter **Abhör Port für IP/PSTN-Gateway**den Abhöranschluss ein, den das Gateway, die Telefonanlage oder SBC für SIP-Nachrichten vom Vermittlungs Server verwenden, die dem Stammverzeichnis des PSTN-Gateways zugeordnet werden. (In der Standardeinstellung ist für ein PSTN-Gateway, eine Nebenstellenanlage oder einen SBC Port 5066 für TCP (Transmission Control Protocol) und Port 5067 für TLS (Transport Layer Security) festgelegt. Bei einer Survivable Branch-Appliance an einer Zweigstelle sind die Standardanschlüsse 5081 für TCP und 5082 für TLS.)

7.  Klicken Sie unter **SIP-Transportprotokoll** auf das für den Peer zu verwendende Transportprotokoll und dann auf **OK**.
    
    <div>
    

    > [!NOTE]  
    > Aus Sicherheitsgründen empfehlen wir dringend, einen Peer auf dem Vermittlungs Server bereitzustellen, der TLS verwenden kann.

    
    </div>

8.  Wählen Sie unter **zugeordneter Vermittlungsserver**den vermittlungsserverpool aus, der dem Stamm Stamm dieses PSTN-Gateways zugeordnet werden soll.

9.  Geben Sie unter **zugeordneter Vermittlungsserver-Port**den Abhör Port ein, der vom Vermittlungsserver für SIP-Nachrichten vom Gateway verwendet wird.
    
    <div>
    

    > [!NOTE]  
    > Mit mehreren trunk-Unterstützung in lync Server 2013 können mehrere SIP-Signalisierungs Anschlüsse auf dem Vermittlungsserver definiert werden, um für die Kommunikation mit mehreren PSTN-Gateways verwendet zu werden. Wenn Sie einen trunk definieren, muss sich der <STRONG>zugeordnete Vermittlungsserver-Port</STRONG> innerhalb des Bereichs der Abhör Anschlüsse für das jeweilige vom Vermittlungsserver zugelassene Protokoll befinden. Dieser Portbereich wird unter lync Server 2013 und Mediations Pools definiert. Klicken Sie mit der rechten Maustaste auf den Interessenbereich des Mediation Server-Pools, und wählen Sie <STRONG>Eigenschaften bearbeiten</STRONG>aus. Geben Sie den Portbereich im Feld <STRONG>Abhör-Ports</STRONG> an.

    
    </div>

10. Klicken Sie auf **Fertig stellen**.

<div>


> [!IMPORTANT]  
> Bevor Sie diesen Schritt abgeschlossen haben, müssen Sie sicherstellen, dass der von Ihnen definierte Peer ausgeführt wird und den von Ihnen angegebenen FQDN oder die IP-Adresse verwendet.



</div>

Führen Sie als nächstes zum Hinzufügen des Peers zur Topologie die Verfahren unter [Veröffentlichen der Topologie in lync Server 2013](lync-server-2013-publish-the-topology.md) in der Bereitstellungsdokumentation aus. Sie müssen Ihre Topologie jedes Mal veröffentlichen, wenn Sie den Topologie-Generator verwenden, um Ihre Topologie zu erstellen oder zu ändern, damit die Daten zum Installieren der Dateien für Server verwendet werden können, auf denen lync Server ausgeführt wird.

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

