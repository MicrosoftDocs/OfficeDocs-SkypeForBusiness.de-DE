---
title: 'Lync Server 2013: Definieren eines Vermittlungsserver im Topologie-Generator'
description: 'Lync Server 2013: definieren Sie einen Vermittlungsserver im Topologie-Generator.'
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
ms.openlocfilehash: 2159b06c5587a17d24928febc11a883bc1520778
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567791"
---
# <a name="define-a-mediation-server-in-topology-builder-in-lync-server-2013"></a>Definieren eines Vermittlungsserver im Topologie-Generator in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-03-25_

Befolgen Sie die Schritte in diesem Thema, um mithilfe des Topologie-Generators eine eigenständige Vermittlungsserver oder einen Pool mit einer Front-End-Pool an einem Standort zu definieren, für den Sie Enterprise-VoIP zuvor nicht bereitgestellt haben.

Sie können eine Topologie auch über ein Konto definieren, das Mitglied der Administratorgruppe ist.

<div>

## <a name="define-mediation-server-collocated-to-a-front-end-pool"></a>Definieren Vermittlungsserver zusammen mit einem Front-End-Pool

Führen Sie die Schritte in diesem Thema aus, um mithilfe des Topologie-Generators eine Vermittlungsserver zu definieren, die mit einem Front-End-Pool an einem Standort verbunden ist, an dem Enterprise-VoIP noch nicht bereitgestellt wurde.

<div>

## <a name="to-add-a-mediation-server-to-a-front-end-pool"></a>So fügen Sie einem Front-End-Pool ein Vermittlungsserver hinzu

1.  Starten Sie den Topologie-Generator: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topologie-Generator**.

2.  Erweitern Sie im Topologie-Generator in der Konsolenstruktur den Namen der Website, für die Sie eine Front-End-Pool definieren möchten.

3.  Klicken Sie in der Konsolenstruktur mit der rechten Maustaste auf den gewünschten Front-End-Pooltyp, und klicken Sie dann auf **neue Front-End-Pool.**..

4.  Navigieren Sie durch den Assistenten **Neuen Front-End-Pool definieren**, bis Sie die Seite **Verbundene Serverrollen auswählen** erreichen.

5.  Aktivieren Sie unter verbundene **Serverrollen auswählen**die Option **Collocate Vermittlungsserver**.
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P>Wenn es sich bei dem ausgewählten Front-End-Pool um die Enterprise Edition handelt, wird die Vermittlungsserver-Komponente auf allen Front-End-Servern dieses Front-End-Pool installiert.</P>
    > <LI>
    > <P>Der <STRONG>nächste Hop-Pool</STRONG> , der von der Vermittlungsserver verwendet wird, ist der Front-End-Pool, in dem die Vermittlungsserver zusammengefasst ist.</P>
    > <LI>
    > <P>Der <STRONG>Edgepool</STRONG> , der von der Vermittlungsserver verwendet wird, ist derselbe Edgepool, der dem Front-End-Pool zugeordnet ist, in dem die Vermittlungsserver zusammengefasst ist.</P></LI></UL>

    
    </div>

6.  Klicken Sie auf **Standard festlegen** , um diese Front-End-Pool zum Weiterleiten von Anrufen von Microsoft Office Communications Server 2007 R2 an das PSTN zu verwenden.

7.  Klicken Sie auf **Fertig stellen** , wenn Sie dem Front-End-Pool das Zuordnen eines oder mehrerer Peers abgeschlossen haben.
    
    <div>
    

    > [!NOTE]  
    > Bevor Sie mit dem nächsten Schritt im Enterprise-VoIP-Bereitstellungsprozess fortfahren, stellen Sie sicher, dass der Vermittlungsserver-Pool (d. h. Front-End-Pool mit der Vermittlungsserver-Komponente nebeneinander) die von Ihnen angegebenen FQDNs verwendet.

    
    </div>

8.  Befolgen Sie anschließend die Verfahren unter [Veröffentlichen der Topologie in lync Server 2013](lync-server-2013-publish-the-topology.md) im Bereitstellungshandbuch, um die Vermittlungsserver zu Ihrer Topologie hinzuzufügen, bevor Sie mit dem nächsten Schritt der Änderung der Überwachungs Ports des Vermittlungsserver falls erforderlich fortfahren. Sie müssen Ihre Topologie jedes Mal veröffentlichen, wenn Sie den Topologie-Generator verwenden, um die Topologie zu definieren oder zu ändern.

</div>

</div>

<div>

## <a name="define-stand-alone-mediation-server"></a>Eigenständige Vermittlungsserver definieren

Befolgen Sie die Schritte in diesem Thema, um mithilfe des Topologie-Generators einen eigenständigen Vermittlungsserver oder Pool an einem Standort zu definieren, an dem Enterprise-VoIP noch nicht bereitgestellt wurde.

Wenn Sie bereits Vermittlungsserver in einem Front-End-Pool an diesem Standort bereitgestellt haben, können Sie diesen Abschnitt überspringen und [die Dateien für Vermittlungsserver in lync Server 2013 installieren](lync-server-2013-install-the-files-for-mediation-server.md) , bevor Sie mit dem [Konfigurieren von Trunks in lync Server 2013](lync-server-2013-configuring-trunks.md)fortfahren.

<div>


> [!NOTE]  
> In diesem Abschnitt wird davon ausgegangen, dass Sie bereits mindestens eine Front-End-Pool eingerichtet haben, wie unter <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">define and configure a Front-End-Pool or Standard Edition-Server in lync Server 2013</A> und <A href="lync-server-2013-publish-the-topology.md">Veröffentlichen der Topologie in lync Server 2013</A> in der Dokumentation zum Bereitstellungshandbuch beschrieben.



</div>

<div>

## <a name="to-add-a-mediation-server"></a>So fügen Sie einen Vermittlungsserver hinzu

1.  Starten Sie den Topologie-Generator: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topologie-Generator**.

2.  Erweitern Sie im Topologie-Generator in der Konsolenstruktur den Namen der Website, für die Sie eine Vermittlungsserver definieren möchten.

3.  Klicken Sie in der Konsolenstruktur mit der rechten Maustaste auf den Knoten **Vermittlungs Pools** , und klicken Sie dann auf **Vermittlungsserver Pool**.

4.  Geben Sie unter **neuen vermittlungspool definieren**den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Vermittlungsserver Pools ein.

5.  Führen Sie anschließend eine der folgenden Aktionen aus:
    
      - Wenn Sie mehrere Vermittlungsserver im Pool bereitstellen möchten, um eine hohe Verfügbarkeit bereitzustellen, wählen Sie **Pool mit mehreren Computern**aus.
        
        <div>
        

        > [!NOTE]  
        > Sie müssen den DNS-Lastenausgleich bereitstellen, um Vermittlungsserver Pools zu unterstützen, die über mehrere Vermittlungsserver verfügen. Ausführliche Informationen finden Sie im Abschnitt Verwenden des DNS-Lastenausgleichs in Vermittlungsserver Pools des <A href="lync-server-2013-dns-load-balancing.md">DNS-Lastenausgleichs in lync Server 2013</A> in der Planungsdokumentation.

        
        </div>
    
      - Wenn Sie nur eine Vermittlungsserver im Pool bereitstellen möchten, da keine hohe Verfügbarkeit erforderlich ist, wählen Sie **Pool mit einem einzelnen Computer**aus. Überspringen Sie den folgenden Schritt.

6.  Wenn Sie im vorherigen Schritt **Pool mit mehreren Computern** ausgewählt haben, klicken Sie in **Computer in diesem Pool definieren** auf **Computer-FQDN**, geben Sie die FQDNs der einzelnen Server innerhalb des Pools ein, und klicken Sie anschließend auf **Hinzufügen**. Wiederholen Sie diesen Schritt für alle anderen Vermittlungsserver, die Sie dem Pool hinzufügen möchten. Nachdem Sie alle Computer im Pool definiert haben, klicken Sie auf **Weiter**.

7.  Klicken Sie auf der Seite **nächsten Hop auswählen** auf **Pool für nächsten**Hop, klicken Sie auf den FQDN des Front-End-Pool, in dem dieser Vermittlungsserver Pool verwendet wird, und klicken Sie dann auf **weiter**.

8.  Führen Sie auf der Seite **Edgeserver auswählen** einen der folgenden Schritte aus:
    
      - Wenn Sie PSTN-Konnektivität für für Enterprise-VoIP aktivierte externe Benutzer bereitstellen möchten, klicken Sie unter **Edge-Pool auswählen, der von diesem Vermittlungsserver verwendet**wird auf den FQDN des Edgeserver Pools, der diesen Vermittlungsserver Pool verwendet, um PSTN-Konnektivität für diese externen Benutzer bereitzustellen, und klicken Sie dann auf **weiter**.
    
      - Wenn Sie nicht beabsichtigen, externe Benutzer für Enterprise-VoIP zu aktivieren oder wenn Sie keine PSTN-Konnektivität für Benutzer bereitstellen möchten, die sich außerhalb des internen Netzwerks befinden, klicken Sie auf **weiter**.

9.  Befolgen Sie anschließend die Verfahren unter [Veröffentlichen der Topologie in lync Server 2013](lync-server-2013-publish-the-topology.md) in der Bereitstellungsdokumentation, um die Vermittlungsserver der Topologie hinzuzufügen. Sie müssen Ihre Topologie jedes Mal veröffentlichen, wenn Sie den Topologie-Generator verwenden, um die Topologie zu erstellen oder zu ändern, damit die Daten für die Installation der Dateien für Server mit lync Server verwendet werden können. Fahren Sie dann mit den nächsten Schritten zum Ändern der Überwachungsports auf dem Vermittlungsserver fort (sofern erforderlich).

</div>

</div>

<div>

## <a name="define-the-mediation-server-listening-ports"></a>Definieren der Vermittlungsserver Abhör-Ports

Befolgen Sie die Schritte in diesem Thema, um mithilfe des Topologie-Generators die Überwachungs Ports zu definieren, die ein Vermittlungsserver oder Pool eingehende Verbindungen von einem Gateway-Peer akzeptiert.

<div>

## <a name="to-modify-the-mediation-server-listening-ports"></a>So ändern Sie die Vermittlungsserver Abhör-Ports

1.  Starten Sie den Topologie-Generator: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topologie-Generator**.

2.  Erweitern Sie im Topologie-Generator in der Konsolenstruktur den Knoten **Vermittlungs Pools** , und klicken Sie mit der rechten Maustaste auf den zuvor erstellten Vermittlungsserver.

3.  Standardmäßig sind die SIP-Überwachungsanschlüsse am Vermittlungsserver 5070 für den TLS-Datenverkehr von lync Server, 5067 für TLS-Datenverkehr von Peers (Gateways, TK oder SBCS). Der TCP-Port ist standardmäßig deaktiviert. Wenn Sie über Gateways verfügen, die TLS nicht unterstützen, müssen Sie den TCP-Port aktivieren.

4.  Geben Sie den gewünschten TLS-oder TCP-Überwachungs Portbereich an, der vom Vermittlungsserver eingehende Verbindungen von PSTN-Gateways akzeptiert wird.
    
    <div>
    

    > [!NOTE]  
    > Wenn die Option <STRONG>TCP-Port aktivieren</STRONG> nicht ausgewählt wird, ist die Eingabe des TCP-Portbereichs nicht erforderlich. Diese Einstellung ist optional.

    
    </div>

Definieren Sie als nächstes in [lync Server 2013 ein Gateway im Topologie-Generator](lync-server-2013-define-a-gateway-in-topology-builder.md) , und installieren Sie die Dateien auf jeder Vermittlungsserver im Pool, indem Sie die Verfahren unter [install the files for Vermittlungsserver in lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md)ausführen.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

