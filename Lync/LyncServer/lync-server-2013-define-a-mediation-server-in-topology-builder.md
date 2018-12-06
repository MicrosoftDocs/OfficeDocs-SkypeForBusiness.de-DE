---
title: 'Lync Server 2013: Definieren eines Vermittlungsservers im Topologie-Generator'
TOCTitle: Definieren eines Vermittlungsservers im Topologie-Generator
ms:assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398391(v=OCS.15)
ms:contentKeyID: 49294096
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Definieren eines Vermittlungsservers im Topologie-Generator in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-03-25_

Führen Sie die Schritte in diesem Thema aus, um den Topologie-Generator zum Definieren eines eigenständigen Vermittlungsservers oder eines mit einem Front-End-Pool verbundenen Pools an einem Standort zu verwenden, an dem Enterprise-VoIP zuvor nicht bereitgestellt wurde.

Sie können eine Topologie auch über ein Konto definieren, das Mitglied der Administratorgruppe ist.

## Definieren eines mit einem Front-End-Pool verbundenen Vermittlungsservers

Führen Sie die Schritte in diesem Thema aus, um mit dem Topologie-Generator eine mit einem Front-End-Pool verbundenen Vermittlungsserver an einem Standort zu definieren, an dem Enterprise-VoIP zuvor noch nicht bereitgestellt wurde.

## So fügen Sie einem Front-End-Pool einen Vermittlungsserver hinzu

1.  Starten des Topologie-Generators: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Topologie-Generator**.

2.  Erweitern Sie im Topologie-Generator in der Konsolenstruktur den Namen des Standorts, für den ein Front-End-Pool definiert werden soll.

3.  Klicken Sie in der Konsolenstruktur mit der rechten Maustaste auf den gewünschten Typ des Front-End-Pool, und klicken Sie auf **Neuer Front-End-Pool**.

4.  Navigieren Sie durch den Assistenten **Neuen Front-End-Pool definieren** , bis Sie die Seite **Verbundene Serverrollen auswählen** erreichen.

5.  Aktivieren Sie unter **Verbundene Serverrollen auswählen** die Option **VermittlungsserverVerbinden** .
    

    > [!NOTE]
    > <UL>
    > <LI>
    > <P>Wenn der Typ des Front-End-Pools, den Sie ausgewählt haben, der Enterprise Edition entspricht, wird die Vermittlungsserver-Komponente auf allen Front-End-Server des Front-End-Pools installiert.</P>
    > <LI>
    > <P>Der <STRONG>Nächste Hoppool</STRONG> , der vom Vermittlungsserver verwendet wird, ist der Front-End-Pool, mit dem der Vermittlungsserver verbunden ist.</P>
    > <LI>
    > <P>Der <STRONG>Edge-Pool</STRONG> , der vom Vermittlungsserver verwendet wird, entspricht dem Edgepool, der dem Front-End-Pool zugeordnet wurde, mit dem der Vermittlungsserver verbunden ist.</P></LI></UL>



6.  Klicken Sie auf **Als Standard** , um Anrufe von Microsoft Office Communications Server 2007 R2 mit diesem Front-End-Pool an das Telefonfestnetz weiterzuleiten.

7.  Klicken Sie auf **Fertig stellen** , wenn Sie die Zuordnung eines oder mehrerer Peers zum Front-End-Pool abgeschlossen haben.
    

    > [!NOTE]
    > Bevor Sie mit dem nächsten Schritt im Enterprise-VoIP-Bereitstellungsprozess fortfahren, sollten Sie sich vergewissern, dass der Vermittlungsserver-Pool (d.&nbsp;h. der Front-End-Pool mit der verbundenen Vermittlungsserver) die von Ihnen angegebenen FQDNs verwendet.



8.  Im Anschluss führen Sie die in der Bereitstellungsdokumentation unter [Veröffentlichen der Topologie in Lync Server 2013](lync-server-2013-publish-the-topology.md) beschriebenen Verfahren aus, um den Vermittlungsserver Ihrer Topologie hinzuzufügen, bevor Sie mit dem nächsten Schritt fortfahren und ggf. die Überwachungsports des Vermittlungsserver ändern. Nach jeder Definition oder Änderung Ihrer Topologie mit Topologie-Generator müssen Sie diese veröffentlichen.

## Definieren eines eigenständigen Vermittlungsservers

Führen Sie die Schritte in diesem Thema aus, um mit Topologie-Generator einen eigenständigen Vermittlungsserver oder einen eigenständigen Pool an einem Standort zu definieren, an dem Enterprise-VoIP zuvor noch nicht bereitgestellt wurde.

Wenn Sie bereits Vermittlungsserver bereitgestellt haben, die mit Front-End-Pools an diesem Standort verbunden sind, können Sie diesen Abschnitt überspringen und mit dem [Installieren der Dateien für den Vermittlungsserver in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) fortfahren, bevor Sie das [Konfigurieren von Trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md) durchführen.


> [!NOTE]
> In diesem Abschnitt wird davon ausgegangen, dass Sie bereits mindestens einen Front-End-Pool wie in der Bereitstellungsdokumentation unter <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Definieren und Konfigurieren eines Front-End-Pools oder Standard Edition-Servers in Lync Server 2013</A> und unter <A href="lync-server-2013-publish-the-topology.md">Veröffentlichen der Topologie in Lync Server 2013</A> beschrieben eingerichtet haben.



## So fügen Sie einen Vermittlungsserver hinzu

1.  Starten des Topologie-Generators: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Topologie-Generator**.

2.  Erweitern Sie im Topologie-Generator in der Konsolenstruktur den Namen des Standorts, für den ein Vermittlungsserver definiert werden soll.

3.  Klicken Sie in der Konsolenstruktur mit der rechten Maustaste auf den Knoten **Vermittlungspools** , und klicken Sie auf **Vermittlungsserverpool**.

4.  Geben Sie im Dialogfeld **Neuen Vermittlungspool definieren** den FQDN des Vermittlungsserver-Pools ein.

5.  Führen Sie anschließend eine der folgenden Aktionen aus:
    
      - Wenn Sie für hohe Verfügbarkeit mehrere Vermittlungsserver innerhalb des Pools bereitstellen möchten, wählen Sie **Pool mit mehreren Computern** aus.
        

        > [!NOTE]
        > Sie müssen den DNS-Lastenausgleich implementieren, um Vermittlungsserver-Pools mit mehreren Vermittlungsserver zu unterstützen. Ausführliche Informationen finden Sie im Abschnitt "Verwenden von DNS-Lastenausgleich für Vermittlungsserver-Pools" unter <A href="lync-server-2013-dns-load-balancing.md">DNS-Lastenausgleich in Lync Server 2013</A> in der Planungsdokumentation.

    
      - Wenn keine hohe Verfügbarkeit erforderlich ist und Sie lediglich einen Vermittlungsserver innerhalb des Pools bereitstellen möchten, wählen Sie **Pool mit einem Computer** . Überspringen Sie den folgenden Schritt.

6.  Wenn Sie im vorherigen Schritt **Pool mit mehreren Computern** ausgewählt haben, klicken Sie in **Computer in diesem Pool definieren** auf **Computer-FQDN** , geben Sie die FQDNs der einzelnen Server innerhalb des Pools ein, und klicken Sie anschließend auf **Hinzufügen** . Wiederholen Sie diesen Schritt für alle anderen Vermittlungsserver, die zum Pool hinzugefügt werden sollen. Nachdem Sie alle Computer im Pool definiert haben, klicken Sie auf **Weiter** .

7.  Klicken Sie auf der Seite **Nächsten Hop auswählen** auf **Nächster Hoppool** , klicken Sie auf den FQDN des Front-End-Pools, der diesen Vermittlungsserver-Pool verwenden wird, und klicken Sie anschließend auf **Weiter** .

8.  Führen Sie auf der Seite **Edgeserver auswählen** einen der folgenden Schritte aus:
    
      - Zur Bereitstellung von PSTN-Konnektivität für externe Benutzer, die für Enterprise-VoIP aktiviert sind, klicken Sie unter **Edgepool auswählen, der von diesem Vermittlungsserver verwendet wird** auf den FQDN des Edgeserverpools, der diesen Vermittlungsserver-Pool verwenden wird, und klicken Sie anschließend auf **Weiter** .
    
      - Wenn Sie externe Benutzer nicht für Enterprise-VoIP aktivieren oder keine PSTN-Konnektivität für Benutzer außerhalb des internen Netzwerks bereitstellen möchten, klicken Sie auf **Weiter** .

9.  Führen Sie anschließend die unter [Veröffentlichen der Topologie in Lync Server 2013](lync-server-2013-publish-the-topology.md) in der Bereitstellungsdokumentation beschriebenen Schritte aus, um den Vermittlungsserver zur Topologie hinzuzufügen. Sie müssen Ihre Topologie nach jeder Verwendung des Topologie-Generators zum Erstellen oder Ändern Ihrer Topologie veröffentlichen, sodass die Daten zur Installation der Dateien für Server mit Lync Server verwendet werden können. Fahren Sie dann mit den nächsten Schritten zum Ändern der Überwachungsports auf dem Vermittlungsserver fort (sofern erforderlich).

## Definieren der Vermittlungsserver-Überwachungsports

Führen Sie die Schritte in diesem Thema aus, um mit Topologie-Generator die Überwachungsports eines Vermittlungsserver oder Pools zu definieren, der eingehende Verbindungen von einem Gatewaypeer akzeptiert.

## So ändern Sie die Vermittlungsserver-Überwachungsports

1.  Starten des Topologie-Generators: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Topologie-Generator**.

2.  Erweitern Sie in Topologie-Generator in der Konsolenstruktur den Knoten **Vermittlungspools** , und klicken Sie mit der rechten Maustaste auf den zuvor erstellten Vermittlungsserver.

3.  In der Standardeinstellung lauten die SIP-Überwachungsports auf dem Vermittlungsserver 5070 für TLS-Datenverkehr von Lync Server, und 5067 für TLS-Datenverkehr von Peers (Gateways, Nebenstellenanlagen oder SBCs). Der TCP-Port ist standardmäßig deaktiviert. Wenn Sie über Gateways verfügen, die TLS nicht unterstützen, müssen Sie den TCP-Port aktivieren.

4.  Geben Sie den gewünschten TLS- oder TCP-Überwachungsportbereich an, der vom Vermittlungsserver für eingehende Verbindungen von PSTN-Gateways akzeptiert wird.
    

    > [!NOTE]
    > Wenn die Option <STRONG>TCP-Port aktivieren</STRONG> nicht ausgewählt wird, ist die Eingabe des TCP-Portbereichs nicht erforderlich. Diese Einstellung ist optional.



Der nächste Schritt besteht im [Definieren eines Gateways im Topologie-Generator in Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md) sowie dem Installieren der Dateien auf den einzelnen Vermittlungsserver im Pool. Führen Sie dazu die in [Installieren der Dateien für den Vermittlungsserver in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) beschriebenen Verfahren durch.

