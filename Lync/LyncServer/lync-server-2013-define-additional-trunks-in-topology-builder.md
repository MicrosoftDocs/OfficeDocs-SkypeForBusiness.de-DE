---
title: 'Lync Server 2013: Definieren von zusätzlichen Trunks im Topologie-Generator'
TOCTitle: Definieren von zusätzlichen Trunks im Topologie-Generator
ms:assetid: e68b8377-50a2-452a-bf5c-910929e34236
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ721915(v=OCS.15)
ms:contentKeyID: 49890982
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Definieren von zusätzlichen Trunks im Topologie-Generator in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-04_

Führen Sie die folgenden Schritte aus, um mit dem Topologie-Generator einen zusätzlichen Trunk zu definieren, dem Sie einen *Peer* mit einem Vermittlungsserver zuordnen können. Ein Peer ermöglicht Benutzern, für die Enterprise-VoIP aktiviert ist, die Verbindung mit dem Telefonfestnetz (Public Switched Telephone Network, PSTN). Bei dem Peer kann es sich um ein PSTN-Gateway, eine IP-Nebenstellenanlage oder einen Session Border Controller (SBC) für einen Anbieter von Internettelefoniediensten handeln. Der Trunk definiert die Verbindung zwischen dem Vermittlungsserver und dem Peer. Pro Vermittlungsserver können mehrere Trunks definiert werden. Einem Vermittlungsserver können mehrere Peers zugeordnet werden.

Ein Trunk ist eine durch folgendes Tupel eindeutig identifizierte logische Verbindung zwischen einem Vermittlungsserver und einem Gateway:

{ Vermittlungsserver-FQDN, Vermittlungsserver-Überwachungsport (TLS oder TCP) : Gateway-IP und FQDN, Gatewayüberwachungsport}


> [!NOTE]
> In diesem Thema wird davon ausgegangen, dass Sie ein PSTN-Gateway und einen Stammtrunk mit mindestens einem verbundenen oder eigenständigen Vermittlungsserver oder Pool wie unter <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">Definieren eines Gateways im Topologie-Generator in Lync Server 2013</A> in der Bereitstellungsdokumentation beschrieben eingerichtet haben.




> [!NOTE]
> In diesem Thema wird davon ausgegangen, dass Sie mindestens einen internen Front-End-Pool oder Standard Edition-Server an mindestens einem zentralen Standort wie unter <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Definieren und Konfigurieren eines Front-End-Pools oder Standard Edition-Servers in Lync Server 2013</A> und <A href="lync-server-2013-publish-the-topology.md">Veröffentlichen der Topologie in Lync Server 2013</A> in der Bereitstellungsdokumentation beschrieben eingerichtet haben.



## So definieren Sie einen zusätzlichen Trunk zwischen einem Vermittlungsserver und einem Gatewaypeer

1.  Starten des Topologie-Generators: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Topologie-Generator**.

2.  Klicken Sie unter Lync Server 2013 auf den Namen Ihres Standorts, klicken Sie auf **Freigegebene Komponenten** , klicken Sie mit der rechten Maustaste auf den Knoten **Trunks** , und klicken Sie dann auf **Neuer Trunk** .
    
    ![Dateistruktur des Lync Server-Topologie-Generators (Bildschirm)](images/JJ721915.90d5b349-aa1e-407a-87ed-fa112f478560(OCS.15).png "Dateistruktur des Lync Server-Topologie-Generators (Bildschirm)")

3.  Geben Sie in **Neuen Trunk definieren** einen Anzeigenamen ein, um den Trunk eindeutig zu identifizieren. Zwei Trunks mit demselben Namen sind nicht zulässig.
    

    > [!NOTE]
    > Wenn Sie TLS (Transport Layer Security) als Transporttyp angeben, müssen Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) anstelle der IP-Adresse des Vermittlungsserverpeers angeben.



4.  Wählen Sie unter **Zugeordnetes PSTN-Gateway** den PSTN-Gatewaypeer aus, der diesem Trunk zugeordnet werden soll.
    
    ![Eigenschafteneinstellungen für PSTN-Gatewaypeer für Trunk](images/JJ721915.7c3fe8ee-8f4c-4413-8462-8347228e61bb(OCS.15).png "Eigenschafteneinstellungen für PSTN-Gatewaypeer für Trunk")

5.  Geben Sie unter **Überwachungsport für IP/PSTN-Gateway** den Überwachungsport ein, über den der Peer (PSTN-Gateway, IP-Nebenstellenanlage oder SBC) SIP-Nachrichten vom Vermittlungsserver empfängt, der diesem Trunk zugeordnet ist. Die standardmäßigen Peerports sind 5066 für TCP (Transmission Control Protocol) und 5067 für TLS (Transport Layer Security). Die Standardports für Survivable Branch-Anwendung sind 5081 für TCP und 5082 für TLS.

6.  Klicken Sie unter **SIP-Transportprotokoll** auf den vom Peer verwendeten Transporttyp.
    

    > [!NOTE]
    > Aus Sicherheitsgründen wird dringend empfohlen, für den Vermittlungsserver einen Peer bereitzustellen, der TLS verwenden kann.



7.  Wählen Sie unter **Zugeordneter Vermittlungsserver** den Vermittlungsserverpool aus, der dem Stammtrunk dieses Peers zugeordnet werden soll.

8.  Geben Sie unter **Zugeordneter Port des Vermittlungsservers** den Überwachungsport ein, über den der Vermittlungsserver SIP-Nachrichten vom Peer empfängt.
    

    > [!NOTE]
    > Mit der Unterstützung mehrerer Trunks in Lync Server 2013 können keine zwei Trunks mit unterschiedlichen Trunknamen für denselben <STRONG>Zugeordneten Port des Vermittlungsservers</STRONG> und <STRONG>Überwachungsport für IP/PSTN-Gateway</STRONG> konfiguriert werden.

    

    > [!NOTE]
    > Mit der Unterstützung mehrerer Trunks in Lync Server 2013 können mehrere SIP-Signalports auf dem Vermittlungsserver für die Kommunikation mit mehreren Peers definiert werden. Beim Definieren eines Trunks muss sich der Wert für <STRONG>Zugeordneter Port des Vermittlungsservers</STRONG> innerhalb des vom Vermittlungsserver erlaubten Bereichs für Überwachungsports für das entsprechenden Protokoll befinden. Dieser Portbereich wird unter Lync Server 2013 und Vermittlungsserverpools definiert. Klicken Sie mit der rechten Maustaste auf den entsprechenden Vermittlungsserverpool, und wählen Sie <STRONG>Eigenschaften bearbeiten</STRONG> aus. Geben Sie den Portbereich im Feld <STRONG>Überwachungsports</STRONG> an.



9.  Klicken Sie auf **OK** .

## Siehe auch

#### Aufgaben

[Ändern eines Trunks im Topologie-Generator in Lync Server 2013](lync-server-2013-modify-a-trunk-in-topology-builder.md)

