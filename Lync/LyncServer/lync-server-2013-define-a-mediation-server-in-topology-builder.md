---
title: 'Lync Server 2013: Definieren eines Vermittlungsservers im Topologie-Generator'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a Mediation Server in Topology Builder
ms:assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398391(v=OCS.15)
ms:contentKeyID: 48184217
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bdff7da86bd7298511ea0ef384b2736a47882a03
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742555"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-mediation-server-in-topology-builder-in-lync-server-2013"></a>Definieren eines Vermittlungsservers im Topologie-Generator in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-03-25_

Führen Sie die Schritte in diesem Thema aus, um mithilfe des Topologie-Generators einen eigenständigen Vermittlungs Server oder einen Pool mit einem Front-End-Pool an einer Website zu definieren, für die Sie Enterprise-VoIP zuvor nicht bereitgestellt haben.

Sie können eine Topologie mithilfe eines Kontos definieren, das Mitglied der Gruppe Administratoren ist.

<div>

## <a name="define-mediation-server-collocated-to-a-front-end-pool"></a>Definieren des Mediations Servers in einem Front-End-Pool

Führen Sie die Schritte in diesem Thema aus, um mithilfe des Topologie-Generators einen Vermittlungs Server zu definieren, der sich in einem Front-End-Pool an einer Website befindet, auf der Enterprise-VoIP nicht zuvor bereitgestellt wurde

<div>

## <a name="to-add-a-mediation-server-to-a-front-end-pool"></a>So fügen Sie einen Vermittlungs Server zu einem Front-End-Pool hinzu

1.  Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topology Builder**.

2.  Erweitern Sie im Topologie-Generator in der Konsolenstruktur den Namen der Website, für die Sie einen Front-End-Pool definieren möchten.

3.  Klicken Sie in der Konsolenstruktur mit der rechten Maustaste auf den Typ des gewünschten Front-End-Pools, und klicken Sie dann auf **neuer Front-End-Pool.**..

4.  Navigieren Sie durch den Assistenten **Neuen Front-End-Pool definieren**, bis Sie die Seite **Verbundene Serverrollen auswählen** erreichen.

5.  Aktivieren Sie unter **ausgewählte Serverrollen auswählen**die Option **Collocate-Vermittlungsserver**.
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P>Wenn der Typ des ausgewählten Front-End-Pools die Enterprise-Edition ist, wird die Mediation Server-Komponente auf allen Front-End-Servern dieses Front-End-Pools installiert.</P>
    > <LI>
    > <P>Der vom Vermittlungsserver verwendete <STRONG>Next Hop-Pool</STRONG> ist der Front-End-Pool, in dem sich der Vermittlungsserver befindet.</P>
    > <LI>
    > <P>Der vom Vermittlungsserver verwendete <STRONG>Edge-Pool</STRONG> ist derselbe Edge-Pool, der dem Front-End-Pool zugeordnet ist, in dem sich der Vermittlungsserver befindet.</P></LI></UL>

    
    </div>

6.  Klicken Sie auf **Standard festlegen** , um diesen Front-End-Pool zum Weiterleiten von Anrufen von Microsoft Office Communications Server 2007 R2 an das PSTN zu verwenden.

7.  Klicken Sie auf **Fertig stellen** , wenn Sie mit dem Verknüpfen eines oder mehrerer Peers mit dem Front-End-Pool fertig sind.
    
    <div>
    

    > [!NOTE]  
    > Bevor Sie mit dem nächsten Schritt des Enterprise-VoIP-Bereitstellungsprozesses fortfahren, stellen Sie sicher, dass der vermittlungsserverpool (also der Front-End-Pool mit der Mediationsserver Komponente) die von Ihnen angegebenen FQDNs verwendet.

    
    </div>

8.  Führen Sie als nächstes die Verfahren unter [Veröffentlichen der Topologie in lync Server 2013](lync-server-2013-publish-the-topology.md) im Bereitstellungshandbuch aus, um den Vermittlungsserver Ihrer Topologie hinzuzufügen, bevor Sie mit dem nächsten Schritt zum Ändern der Abhör Anschlüsse des Vermittlungsservers bei Bedarf fortfahren. Sie müssen Ihre Topologie jedes Mal veröffentlichen, wenn Sie den Topologie-Generator verwenden, um Ihre Topologie zu definieren oder zu ändern.

</div>

</div>

<div>

## <a name="define-stand-alone-mediation-server"></a>Eigenständigen Vermittlungs Server definieren

Führen Sie die Schritte in diesem Thema aus, um mithilfe des Topologie-Generators einen eigenständigen Vermittlungs Server oder Pool an einer Website zu definieren, auf der Enterprise-VoIP nicht zuvor bereitgestellt wurde.

Wenn Sie bereits Vermittlungsserver an Front-End-Pools auf dieser Website bereitgestellt haben, können Sie diesen Abschnitt überspringen und [die Dateien für den Vermittlungsserver in lync Server 2013 installieren](lync-server-2013-install-the-files-for-mediation-server.md) , bevor Sie mit der [Konfiguration von Trunks in lync Server 2013](lync-server-2013-configuring-trunks.md)fortfahren.

<div>


> [!NOTE]  
> In diesem Abschnitt wird davon ausgegangen, dass Sie bereits mindestens einen Front-End-Pool eingerichtet haben, wie unter <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">definieren und Konfigurieren eines Front-End-Pools oder Standard Edition-Servers in lync Server 2013</A> und <A href="lync-server-2013-publish-the-topology.md">Veröffentlichen der Topologie in lync Server 2013</A> in der Bereitstellungshandbuch-Dokumentation beschrieben wird.



</div>

<div>

## <a name="to-add-a-mediation-server"></a>So fügen Sie einen Vermittlungs Server hinzu

1.  Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topology Builder**.

2.  Erweitern Sie im Topologie-Generator in der Konsolenstruktur den Namen der Website, für die Sie einen Vermittlungs Server definieren möchten.

3.  Klicken Sie in der Konsolenstruktur mit der rechten Maustaste auf den Knoten **Mediations Pools** , und klicken Sie dann auf **Vermittlungs Server Pool**.

4.  Geben Sie unter **neuen Mediations Pool definieren**den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Mediation Server Pools ein.

5.  Führen Sie anschließend eine der folgenden Aktionen aus:
    
      - Wenn Sie mehrere Vermittlungsserver im Pool bereitstellen möchten, um eine höhere Verfügbarkeit zu gewährleisten, wählen Sie den **Pool für mehrere Computer**aus.
        
        <div>
        

        > [!NOTE]  
        > Sie müssen den DNS-Lastenausgleich bereitstellen, um Vermittlungsserver Pools mit mehreren Vermittlungsservern zu unterstützen. Ausführliche Informationen finden Sie im Abschnitt Verwenden des DNS-Lastenausgleichs für Mediationsserver Pools des <A href="lync-server-2013-dns-load-balancing.md">DNS-Lastenausgleichs in lync Server 2013</A> in der Planungsdokumentation.

        
        </div>
    
      - Wenn Sie nur einen Vermittlungs Server im Pool bereitstellen möchten, weil Sie keine höhere Verfügbarkeit benötigen, wählen Sie den **Pool für einzelne Computer**aus. Überspringen Sie den folgenden Schritt.

6.  Wenn Sie im vorherigen Schritt **Pool mit mehreren Computern** ausgewählt haben, klicken Sie in **Computer in diesem Pool definieren** auf **Computer-FQDN**, geben Sie die FQDNs der einzelnen Server innerhalb des Pools ein und klicken Sie anschließend auf **Hinzufügen**. Wiederholen Sie diesen Schritt für alle anderen Vermittlungsserver, die Sie dem Pool hinzufügen möchten. Nachdem Sie alle Computer im Pool definiert haben, klicken Sie auf **Weiter**.

7.  Klicken Sie auf der Seite **Nächster Hop auswählen** auf **Nächster Hop-Pool**, klicken Sie auf den FQDN des Front-End-Pools, in dem dieser Vermittlungs Server Pool verwendet wird, und klicken Sie dann auf **weiter**.

8.  Führen Sie auf der Seite **Edgeserver auswählen** einen der folgenden Schritte aus:
    
      - Wenn Sie die PSTN-Konnektivität für externe Benutzer bereitstellen möchten, die für Enterprise-VoIP aktiviert sind, klicken Sie unter Wählen Sie den **von diesem Vermittlungsserver verwendeten Edge-Pool**aus auf den FQDN des Edgeserver-Pools, der diesen vermittlungsserverpool verwendet, um PSTN-Konnektivität für diese externen Benutzer bereitzustellen, und klicken Sie dann auf **weiter**.
    
      - Wenn Sie nicht beabsichtigen, externe Benutzer für Enterprise-VoIP zu aktivieren, oder wenn Sie keine PSTN-Konnektivität für Benutzer bereitstellen möchten, wenn diese sich außerhalb des internen Netzwerks befinden, klicken Sie auf **weiter**.

9.  Führen Sie als nächstes die Verfahren unter [Veröffentlichen der Topologie in lync Server 2013](lync-server-2013-publish-the-topology.md) in der Bereitstellungsdokumentation aus, um den Vermittlungs Server zur Topologie hinzuzufügen. Sie müssen Ihre Topologie jedes Mal veröffentlichen, wenn Sie den Topologie-Generator verwenden, um Ihre Topologie zu erstellen oder zu ändern, damit die Daten zum Installieren der Dateien für Server verwendet werden können, auf denen lync Server ausgeführt wird. Fahren Sie dann mit den nächsten Schritten fort, um die Abhör Anschlüsse auf dem Vermittlungs Server bei Bedarf zu ändern.

</div>

</div>

<div>

## <a name="define-the-mediation-server-listening-ports"></a>Definieren der Abhör Anschlüsse des Vermittlungsservers

Führen Sie die Schritte in diesem Thema aus, um mithilfe des Topologie-Generators die Abhör Anschlüsse zu definieren, die von einem Vermittlungs Server oder-Pool eingehende Verbindungen von einem Gateway-Peer akzeptiert werden.

<div>

## <a name="to-modify-the-mediation-server-listening-ports"></a>So ändern Sie die Abhör Anschlüsse des Vermittlungsservers

1.  Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topology Builder**.

2.  Erweitern Sie im Topologie-Generator in der Konsolenstruktur den Knoten **Mediations Pools** , und klicken Sie mit der rechten Maustaste auf den zuvor erstellten Mediations Server.

3.  Standardmäßig sind die SIP-Abhör Anschlüsse auf dem Vermittlungsserver 5070 für den TLS-Datenverkehr von lync Server, 5067 für TLS-Datenverkehr von Peers (Gateways, TK oder SBCS). Der TCP-Port ist standardmäßig deaktiviert. Wenn Sie über Gateways verfügen, die TLS nicht unterstützen, müssen Sie den TCP-Port aktivieren.

4.  Geben Sie den gewünschten TLS-oder TCP-Überwachungs Portbereich an der Vermittlungs Server akzeptiert eingehende Verbindungen von PSTN-Gateways.
    
    <div>
    

    > [!NOTE]  
    > Wenn die Option <STRONG>TCP-Port aktivieren</STRONG> nicht ausgewählt wird, ist die Eingabe des TCP-Portbereichs nicht erforderlich. Diese Einstellung ist optional.

    
    </div>

Definieren Sie als nächstes [ein Gateway im Topologie-Generator in lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md) , und installieren Sie die Dateien auf jedem Vermittlungsserver im Pool, indem Sie die Verfahren unter [Installieren der Dateien für Mediation Server in lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md)befolgen.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

