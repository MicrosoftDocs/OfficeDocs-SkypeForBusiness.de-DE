---
title: 'Lync Server 2013: Definieren eines Gateways im Topologie-Generator'
TOCTitle: Definieren eines Gateways im Topologie-Generator
ms:assetid: 456e5a96-d9f6-42a6-862c-a69464391628
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425945(v=OCS.15)
ms:contentKeyID: 49293862
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Definieren eines Gateways im Topologie-Generator in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-04_

Führen Sie diese Schritte aus, um mit dem Topologie-Generator einen *Peer* zu definieren, dem Sie einen Vermittlungsserver zuweisen können, um eine PSTN (Public Switched Telephone Network)-Anbindung für Enterprise-VoIP-aktivierte Benutzer bereitzustellen. Bei diesem Peer für den Vermittlungsserver kann es sich um ein PSTN-Gateway, eine IP-Nebenstellenanlage oder einen SBC (Session Border Controller) eines Anbieters von Internettelefoniediensten (ITSP) handeln, mit dem Sie durch Konfigurieren eines SIP-Trunks eine Verbindung herstellen.


> [!NOTE]
> In diesem Thema wird davon ausgegangen, dass Sie mindestens einen internen Front-End-Pool oder einen internen Standard Edition-Server mit einem verbundenen oder eigenständigen Vermittlungsserver an mindestens einem zentralen Standort eingerichtet haben, wie unter <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Definieren und Konfigurieren eines Front-End-Pools oder Standard Edition-Servers in Lync Server 2013</A> und <A href="lync-server-2013-publish-the-topology.md">Veröffentlichen der Topologie in Lync Server 2013</A> in der Bereitstellungsdokumentation beschrieben. In diesem Thema wird ferner davon ausgegangen, dass Ihre Infrastruktur die unter <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">Erforderliche Software für Enterprise-VoIP in Lync Server 2013</A> und <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">Anforderungen an Sicherheit und Konfiguration für Enterprise-VoIP in Lync Server 2013</A> beschriebenen Voraussetzungen erfüllt.



## So definieren Sie einen Peer für den Vermittlungsserver

1.  Starten des Topologie-Generators: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Topologie-Generator**.

2.  Klicken Sie unter Lync Server 2013, Ihr Sitename, freigegebene Komponenten mit der rechten Maustaste auf den Knoten **PSTN-Gateways** und dann auf **Neues PSTN-Gateway** .
    
    ![Topologie-Generator in Lync Server 2013](images/Gg425945.d898c3c1-8798-4b74-8f02-b994ef3db4c1(OCS.15).png "Topologie-Generator in Lync Server 2013")

3.  Geben Sie unter **Neues IP/PSTN-Gateway definieren** den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) oder die IP-Adresse des Peers ein, und klicken Sie auf **Weiter** .
    
    ![IP/PSTN-Gateway](images/Gg425945.8017ba5e-41bc-48d4-97d9-fd306cd322b8(OCS.15).png "IP/PSTN-Gateway")
    

    > [!NOTE]
    > Wenn Sie TLS (Transport Layer Security) als Transporttyp angeben, müssen Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) anstelle der IP-Adresse des Vermittlungsserverpeers angeben.



4.  Definieren Sie den Überwachungsmodus (IPv4 oder IPv6) für die IP-Adresse Ihres neuen PSTN-Gateway, und klicken Sie auf **Weiter** .
    
    ![IP-Adresse](images/Gg425945.c7fc0d12-adc8-45a7-aca1-b376e1d2fcec(OCS.15).png "IP-Adresse")

5.  Definieren Sie einen *Stammtrunk* für das PSTN-Gateway. Ein Trunk ist eine logische Verbindung zwischen einem Vermittlungsserver und einem Gateway, das anhand des Tupels eindeutig identifiziert wird.
    
    { Vermittlungsserver-FQDN, Vermittlungsserver-Überwachungsport (TLS oder TCP) : Gateway-IP und FQDN, Gatewayüberwachungsport}
    
      - Beim Definieren eines PSTN-Gateways im Topologie-Generator müssen Sie einen Stammtrunk definieren. Andernfalls können Sie den PSTN-Gateway Ihrer Topologie nicht erfolgreich hinzufügen.
    
      - Der Stammtrunk kann erst entfernt werden, nachdem das damit verbundene PSTN-Gateway entfernt wurde.
    
    ![Definieren des Gateways: Stammtrunk](images/Gg425945.3b030757-eb35-4616-bb6b-74ee67507e3d(OCS.15).png "Definieren des Gateways: Stammtrunk")

6.  Geben Sie unter **Überwachungsport für IP/PSTN-Gateway** den Überwachungsport ein, den das Gateway, die Nebenstellenanlage oder der SBC für SIP-Nachrichten vom Vermittlungsserver verwendet, die dem Stammtrunk des PSTN-Gateways zugeordnet wird. (In der Standardeinstellung ist für ein PSTN-Gateway, eine Nebenstellenanlage oder einen SBC Port 5066 für TCP (Transmission Control Protocol) und Port 5067 für TLS (Transport Layer Security) festgelegt. Bei einer Survivable Branch-Anwendung an einem Zweigstellenstandort lauten die Standardports 5081 für TCP und 5082 für TLS.)

7.  Klicken Sie unter **SIP-Transportprotokoll** auf das für den Peer zu verwendende Transportprotokoll, und klicken Sie dann auf **OK** .
    

    > [!NOTE]
    > Aus Sicherheitsgründen wird dringend empfohlen, für den Vermittlungsserver einen Peer bereitzustellen, der TLS verwenden kann.



8.  Wählen Sie unter **Zugeordneter Vermittlungsserver** den Vermittlungsserverpool aus, der dem Stammtrunk dieses PSTN-Gateways zugeordnet werden soll.

9.  Geben Sie unter **Zugeordneter Vermittlungsserver-Port** den Überwachungsport ein, der von der Vermittlungsserver für SIP-Nachrichten vom Gateway verwendet wird.
    

    > [!NOTE]
    > Da Lync Server 2013 mehrere Trunks unterstützt, können Sie im Vermittlungsserver mehrere SIP-Signalports für die Kommunikation mit mehreren PSTN-Gateways definieren. Wenn Sie einen Trunk definieren, muss sich der <STRONG>Verbundene Vermittlungsserver-Port</STRONG> im Bereich der Überwachungsports für das jeweils von der Vermittlungsserver zugelassene Protokoll befinden. Dieser Portbereich wird unter Lync Server 2013 und Vermittlungsserverpools definiert. Klicken Sie mit der rechten Maustaste auf den betreffenden Vermittlungsserverpool, und wählen Sie <STRONG>Eigenschaften bearbeiten</STRONG> aus. Geben Sie den Portbereich im Feld <STRONG>Überwachungsports</STRONG> ein.



10. Klicken Sie auf **Fertig stellen** .


> [!IMPORTANT]
> Bevor Sie diesen Schritt abschließen, müssen Sie sicherstellen, dass der definierte Peer ausgeführt wird und den angegebenen FQDN bzw. die angegebene IP-Adresse verwendet.



Um im nächsten Schritt den Peer zur Topologie hinzuzufügen, führen Sie die Verfahren unter [Veröffentlichen der Topologie in Lync Server 2013](lync-server-2013-publish-the-topology.md) in der Bereitstellungsdokumentation aus. Sie müssen Ihre Topologie nach jeder Verwendung des Topologie-Generators zum Erstellen oder Ändern Ihrer Topologie veröffentlichen, sodass die Daten zur Installation der Dateien für Lync Server-Server verwendet werden können.

## Siehe auch

#### Aufgaben

[Ändern eines Trunks im Topologie-Generator in Lync Server 2013](lync-server-2013-modify-a-trunk-in-topology-builder.md)

