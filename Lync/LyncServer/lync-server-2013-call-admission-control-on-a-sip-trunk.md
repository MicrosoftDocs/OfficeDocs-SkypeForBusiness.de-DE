---
title: 'Lync Server 2013: Anrufsteuerung für einen SIP-Trunk'
TOCTitle: Anrufsteuerung für einen SIP-Trunk
ms:assetid: 7eada098-3d47-4be2-839f-8f87d582efe8
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398632(v=OCS.15)
ms:contentKeyID: 49294547
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anrufsteuerung für einen SIP-Trunk in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-22_

Zur Bereitstellung der Anrufsteuerung für einen SIP-Trunk erstellen Sie einen Netzwerkstandort, der den Anbieter von Internettelefoniediensten repräsentiert. Um Bandbreitenrichtlinienwerte auf den SIP-Trunk anzuwenden, erstellen Sie eine standortübergreifende Richtlinie zwischen dem Netzwerkstandort in Ihrem Unternehmen und dem Netzwerkstandort, der für den Anbieter von Internettelefoniediensten erstellt wird.

Die folgende Abbildung zeigt ein Beispiel für die Bereitstellung der Anrufsteuerung für einen SIP-Trunk.

**Konfiguration der Anrufsteuerung für einen SIP-Trunk**

![Anrufsteuerung – SIP-Trunking (Diagramm)](images/Gg398632.276c0d8f-1dd5-4883-8499-c202399ddbe9(OCS.15).jpg "Anrufsteuerung – SIP-Trunking (Diagramm)")

Zur Konfiguration der Anrufsteuerung für einen SIP-Trunk müssen Sie während der Bereitstellung der Anrufsteuerung die folgenden Aufgaben ausführen:

1.  Erstellen eines Netzwerkstandorts, der den Anbieter von Internettelefoniediensten repräsentiert. Zuordnen des Netzwerkstandorts zu einer geeigneten Netzwerkregion und Zuweisen eines Bandbreitenwerts von Null für Audio und Video für diesen Netzwerkstandort. Ausführliche Informationen finden Sie unter [Konfigurieren von Netzwerkstandorten für die Anrufsteuerung in Lync Server 2013](lync-server-2013-configure-network-sites-for-cac.md) in der Bereitstellungsdokumentation.
    

    > [!NOTE]
    > Für den Anbieter von Internettelefoniediensten ist diese Netzwerkstandortkonfiguration nicht funktionsfähig. Die Bandbreitenrichtlinienwerte werden tatsächlich in Schritt&nbsp;2 angewendet.



2.  Erstellen Sie eine standortübergreifende Verbindung für den SIP-Trunk unter Verwendung der relevanten Parameterwerte für den in Schritt 1 erstellten Standort. Verwenden Sie z. B. den Namen des Netzwerkstandorts in Ihrem Unternehmen als Wert des Parameters "NetworkSiteID1" und den ITSP-Netzwerkstandort als Wert des Parameters "NetworkSiteID2". Ausführliche Informationen finden Sie unter [Erstellen von standortübergreifenden Netzwerkrichtlinien in Lync Server 2013](lync-server-2013-create-network-intersite-policies.md) in der Bereitstellungsdokumentation. Lesen Sie auch die Dokumentation der Lync Server-Verwaltungsshell für das Cmdlet "New-CsNetworkInterSitePolicy".

3.  Lassen Sie sich vom Anbieter der Internettelefoniedienste die IP-Adresse des SBC-Medienendpunkts (Session Border Controller) geben. Fügen Sie diese IP-Adresse mit der Subnetzmaske 32 zu dem Netzwerkstandort hinzu, der den Anbieter von Internettelefoniediensten repräsentiert. Ausführliche Informationen finden Sie unter [Zuordnen eines Subnetzes zu einem Netzwerkstandort in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).

