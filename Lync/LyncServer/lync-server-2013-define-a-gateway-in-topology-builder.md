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
ms.openlocfilehash: 23286d5bb6cd8b1a1b695776258ad5e131743b8d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044077"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-gateway-in-topology-builder-in-lync-server-2013"></a>Definieren eines Gateways im Topologie-Generator in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-04_

Führen Sie die folgenden Schritte aus, um mithilfe des Topologie-Generators einen *Peer* zu definieren, dem Sie eine Vermittlungsserver zuordnen können, um eine Verbindung mit dem PSTN (Public Switched Telephone Network) für für Enterprise-VoIP aktivierte Benutzer bereitzustellen. Ein Peer zum Vermittlungsserver kann ein PSTN-Gateway, eine IP-Nebenstellenanlage oder ein Session Border Controller (SBC) für einen Internet Telefonie-Dienstanbieter (ITSP) sein, zu dem Sie eine Verbindung herstellen, indem Sie einen SIP-Trunk konfigurieren.

<div>


> [!NOTE]  
> In diesem Thema wird davon ausgegangen, dass Sie mindestens einen internen Front-End-Pool oder Standard Edition-Server an mindestens einem zentralen Standort mit einer nebeneinander liegenden oder eigenständigen Vermittlungsserver eingerichtet haben, wie in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">definieren und Konfigurieren einer Front-End-Pool oder Standard Edition-Server in lync Server 2013</A> und <A href="lync-server-2013-publish-the-topology.md">Veröffentlichen der Topologie in lync Server 2013</A> in der Bereitstellungsdokumentation beschrieben. In diesem Thema wird auch davon ausgegangen, dass Sie überprüft haben, dass Ihre Infrastruktur die unter <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">Software Voraussetzungen für Enterprise-VoIP in lync Server 2013</A> und <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">Sicherheits-und Konfigurationsvoraussetzungen für Enterprise-VoIP in lync Server 2013</A>beschriebenen Voraussetzungen erfüllt sind.



</div>

<div>

## <a name="to-define-a-peer-for-the-mediation-server"></a>So definieren Sie einen Peer für den Vermittlungsserver

1.  Starten Sie den Topologie-Generator: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topologie-Generator**.

2.  Klicken Sie unter lync Server 2013, Name Ihrer Website, freigegebene Komponenten mit der rechten Maustaste auf den Knoten **PSTN-Gateways** , und klicken Sie dann auf **Neues PSTN-Gateway**.
    
    ![d898c3c1-8798-4b74-8f02-b994ef3db4c1](images/Gg425945.d898c3c1-8798-4b74-8f02-b994ef3db4c1(OCS.15).png "d898c3c1-8798-4b74-8f02-b994ef3db4c1")

3.  Geben Sie unter **Neues IP/PSTN-Gateway definieren** den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) oder die IP-Adresse des Peers ein, und klicken Sie auf **Weiter**.
    
    ![8017ba5e-41bc-48d4-97d9-fd306cd322b8](images/Gg425945.8017ba5e-41bc-48d4-97d9-fd306cd322b8(OCS.15).png "8017ba5e-41bc-48d4-97d9-fd306cd322b8")
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie TLS (Transport Layer Security) als Transporttyp angeben, müssen Sie anstelle der IP-Adresse des Peers des Vermittlungsserver den FQDN angeben.

    
    </div>

4.  Definieren Sie den Überwachungsmodus (IPv4 oder IPv6) für die IP-Adresse Ihres neuen PSTN-Gateway, und klicken Sie auf **Weiter**.
    
    ![c7fc0d12-adc8-45a7-aca1-b376e1d2fcec](images/Gg425945.c7fc0d12-adc8-45a7-aca1-b376e1d2fcec(OCS.15).png "c7fc0d12-adc8-45a7-aca1-b376e1d2fcec")

5.  Definieren Sie einen *Stammtrunk* für das PSTN-Gateway. Ein trunk ist eine logische Verbindung zwischen einem Vermittlungsserver und einem Gateway, das durch das Tupel eindeutig identifiziert wird.
    
    {Vermittlungsserver FQDN, Vermittlungsserver Abhör Port (TLS oder TCP): Gateway-IP und FQDN, Gateway-Abhör Port}
    
      - Beim Definieren eines PSTN-Gateways im Topologie-Generator müssen Sie einen Stamm trunk definieren, um das PSTN-Gateway erfolgreich zu Ihrer Topologie hinzuzufügen.
    
      - Der Stammtrunk kann erst entfernt werden, nachdem das damit verbundene PSTN-Gateway entfernt wurde.
    
    ![3b030757-eb35-4616-bb6b-74ee67507e3d](images/Gg425945.3b030757-eb35-4616-bb6b-74ee67507e3d(OCS.15).png "3b030757-eb35-4616-bb6b-74ee67507e3d")

6.  Geben Sie unter **Überwachungsport für IP/PSTN-Gateway**den Abhör Port ein, den das Gateway, die Nebenstellenanlage oder der SBC für SIP-Nachrichten von der Vermittlungsserver verwendet, die dem Stamm trunk des PSTN-Gateways zugeordnet werden. (In der Standardeinstellung ist für ein PSTN-Gateway, eine Nebenstellenanlage oder einen SBC Port 5066 für TCP (Transmission Control Protocol) und Port 5067 für TLS (Transport Layer Security) festgelegt. Bei einem Survivable Branch Appliance an einem Zweigstellenstandort sind die Standardports 5081 für TCP und 5082 für TLS.)

7.  Klicken Sie unter **SIP-Transportprotokoll** auf das für den Peer zu verwendende Transportprotokoll, und klicken Sie dann auf **OK**.
    
    <div>
    

    > [!NOTE]  
    > Aus Sicherheitsgründen wird dringend empfohlen, einen Peer für den Vermittlungsserver bereitzustellen, der TLS verwenden kann.

    
    </div>

8.  Wählen Sie unter **zugeordnete Vermittlungsserver**den Vermittlungsserver Pool aus, der dem Stamm trunk dieses PSTN-Gateways zugeordnet werden soll.

9.  Geben Sie unter **zugeordneter Vermittlungsserver Port**den Überwachungs Port ein, den der Vermittlungsserver für SIP-Nachrichten vom Gateway verwenden wird.
    
    <div>
    

    > [!NOTE]  
    > Bei mehreren trunk Unterstützung in lync Server 2013 können mehrere SIP-Signalisierungs Ports für die Vermittlungsserver definiert werden, die für die Kommunikation mit mehreren PSTN-Gateways verwendet werden sollen. Beim Definieren eines Trunks muss sich der <STRONG>zugeordnete Vermittlungsserver Port</STRONG> innerhalb des Bereichs der Überwachungs Ports für das jeweilige vom Vermittlungsserver zugelassene Protokoll befinden. Dieser Portbereich ist unter lync Server 2013 und Vermittlungs Pools definiert. Klicken Sie mit der rechten Maustaste auf den Vermittlungsserver Interessen Pool, und wählen Sie <STRONG>Eigenschaften bearbeiten</STRONG>aus. Geben Sie den Portbereich im Feld <STRONG>Überwachungsports</STRONG> ein.

    
    </div>

10. Klicken Sie auf **Fertig stellen**.

<div>


> [!IMPORTANT]  
> Bevor Sie diesen Schritt abschließen, müssen Sie sicherstellen, dass der definierte Peer ausgeführt wird und den angegebenen FQDN bzw. die angegebene IP-Adresse verwendet.



</div>

Um den Peer zur Topologie hinzuzufügen, befolgen Sie die Verfahren unter [Veröffentlichen der Topologie in lync Server 2013](lync-server-2013-publish-the-topology.md) in der Bereitstellungsdokumentation. Sie müssen Ihre Topologie jedes Mal veröffentlichen, wenn Sie den Topologie-Generator verwenden, um die Topologie zu erstellen oder zu ändern, damit die Daten für die Installation der Dateien für Server mit lync Server verwendet werden können.

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

