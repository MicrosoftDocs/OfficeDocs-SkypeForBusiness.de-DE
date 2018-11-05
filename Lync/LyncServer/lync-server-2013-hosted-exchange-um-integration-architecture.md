---
title: 'Lync Server 2013: Architektur für die Integration gehosteter Exchange UM-Dienste'
TOCTitle: Architektur für die Integration gehosteter Exchange UM-Dienste
ms:assetid: 0094d5dc-1836-441c-b6e2-f88e35203a8d
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398067(v=OCS.15)
ms:contentKeyID: 49292975
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Architektur für die Integration gehosteter Exchange UM-Dienste in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-25_

Die Lync Server 2013 ExUM-Routinganwendung bietet Unterstützung für die Integration in eine lokale Exchange Unified Messaging (UM)-Bereitstellung, in eine durch einen Dienstanbieter gehostete Exchange UM-Umgebung oder eine Kombination dieser beiden. Im nachfolgenden Diagramm werden alle drei Möglichkeiten dargestellt.

**Integration in eine Umgebung mit lokaler Exchange UM-Bereitstellung und zwei Anbietern für gehostete Exchange-Dienste**

![Lokale Lync Server-Exchange UM-Bereitstellung](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "Lokale Lync Server-Exchange UM-Bereitstellung")

Die folgenden Modi werden unterstützt:

  - **Lokale Bereitstellung:** Sowohl Lync Server 2013 als auch Exchange UM werden auf lokalen Servern innerhalb Ihres Unternehmens bereitgestellt.

  - **Standortübergreifende Bereitstellung :** Lync Server 2013 wird auf lokalen Servern innerhalb Ihres Unternehmens bereitgestellt, und Exchange UM wird in der Umgebung eines Onlinedienstanbieters gehostet, beispielsweise in einem Microsoft Exchange Online-Rechenzentrum.

  - **Gemischte Bereitstellung :** Ihre Lync Server 2013-Bereitstellung umfasst einige Benutzerpostfächer auf lokalen Exchange-Servern sowie Postfächer, die in einem gehosteten Exchange-Rechenzentrum verwaltet werden.
    

    > [!NOTE]
    > Die gemischte Bereitstellung kann als Übergangslösung bei der Evaluierung und bei einer in Phasen durchgeführten Migration von Benutzern zu gehosteten Exchange UM-Diensten oder als dauerhafte Lösung eingesetzt werden, wenn Sie einige Exchange UM-Dienste nach der Migration weiterhin lokal verwalten möchten.



## Freigegebener SIP-Adressraum

Zur Integration von Lync Server 2013 in eine lokale Exchange UM-Bereitstellung gewähren Sie Lync Server 2013 die Berechtigung zum Lesen von Exchange UM-Objekten in den Active Directory-Domänendiensten (AD DS). Dieser Ansatz kann nicht für die Integration in eine gehostete Exchange UM-Umgebung verwendet werden, da Lync Server 2013 und Exchange UM in separaten Gesamtstrukturen ohne Vertrauensbeziehung installiert werden.

Zur Integration von Lync Server 2013 in gehostete Exchange UM-Dienste müssen Sie einen *freigegebenen SIP-Adressraum* konfigurieren. In dieser Konfiguration steht derselbe SIP-Domänenadressraum sowohl für Lync Server 2013 als auch für den Dienstanbieter für gehostete Exchange UM-Dienste zur Verfügung.


> [!NOTE]
> Die Verwendung des freigegebenen SIP-Adressraums ähnelt dem Ansatz in einer standortübergreifenden Lync Server 2013-Umgebung, bei dem einige Benutzer in der lokalen Bereitstellung und andere in einer gehosteten Umgebung verwaltet werden (z.&nbsp;B. Lync Online). Die SIP-Domäne wird zwischen den Umgebungen aufgeteilt. Wenn Sie Lync Server 2013 in eine Umgebung mit gehosteten Exchange UM-Diensten integrieren, stellen Sie sicher, dass Sie den Exchange UM-Dienstanbieter in den freigegebenen Adressraum aufnehmen.



Zum Konfigurieren des freigegebenen SIP-Adressraums für die Integration in eine Umgebung mit einem Exchange UM-Dienstanbieter müssen Sie Ihren Edgeserver folgendermaßen konfigurieren:

1.  Konfigurieren Sie den Edgeserver für den Partnerverbund, indem Sie mit dem Cmdlet **Set-CsAccessEdgeConfiguration** die folgenden Parameter festlegen:
    
      - **UseDnsSrvRouting** gibt an, dass Edgeserver beim Senden und Empfangen von Partnerverbundanforderungen auf DNS-SRV-Einträge zurückgreifen.
    
      - **AllowFederatedUsers** gibt an, ob interne Benutzer mit Benutzern aus Partnerdomänen kommunizieren dürfen. Diese Eigenschaft legt außerdem fest, ob interne Benutzer mit Benutzern in einem Szenario mit getrennten Domänen kommunizieren können.
    
      - **EnablePartnerDiscovery** gibt an, ob Lync Server 2013 DNS-Einträge zur Suche nach Partnerdomänen verwendet, die nicht in der Liste der zulässigen Active Directory-Domänen aufgeführt sind. Bei Festlegung auf "False" erkennt Lync Server 2013 nur Domänen als Partnerdomänen an, die in der Liste der zulässigen Domänen aufgeführt sind. Dieser Parameter ist für die Verwendung von DNS-Dienstrouting erforderlich. In den meisten Bereitstellungen ist der Wert auf "False" gesetzt, um einen Partnerverbund mit allen Partnern zu vermeiden.

2.  Replizieren Sie den zentralen Verwaltungsspeicher auf den Edgeserver und überprüfen Sie die Replikation. Weitere Informationen hierzu finden Sie unter [Exportieren der Lync Server 2013-Topologie und Kopieren auf externe Medien zur Edgeinstallation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) in der Bereitstellungsdokumentation.

3.  Konfigurieren Sie einen *Hostinganbieter* auf dem Edgeserver, indem Sie mit dem Cmdlet **New-CsHostingProvider** die folgenden Parameter festlegen:
    
      - **Identity** gibt einen eindeutigen Zeichenfolgenwert für den Hostinganbieter an, den Sie erstellen, beispielsweise **Hosted Exchange UM**.
    
      - **Enabled** gibt an, ob die Netzwerkverbindung zwischen Ihrer Domäne und dem Hostinganbieter aktiviert ist. Dieser Parameter muss auf **True** festgelegt werden.
    
      - **EnabledSharedAddressSpace** gibt an, ob der Hostinganbieter in einem Szenario mit freigegebenem SIP-Adressraum verwendet wird. Dieser Parameter muss auf **True** festgelegt werden.
    
      - **HostsOCSUsers** gibt an, ob der Hostinganbieter zum Hosten von Lync Server 2013-Konten verwendet wird. Dieser Parameter muss auf **False** festgelegt werden.
    
      - **ProxyFQDN** gibt den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des vom Hostinganbieter verwendeten Proxyservers an, z. B. **proxyserver.fabrikam.com** . Sie erhalten diese Information von Ihrem Hostinganbieter. Dieser Wert kann nicht geändert werden. Wenn der Hostinganbieter seinen Proxyserver ändert, muss der Eintrag für diesen Anbieter gelöscht und neu erstellt werden.
    
      - **IsLocal** gibt an, ob sich der vom Hostinganbieter verwendete Proxyserver in Ihrer Lync Server 2013-Topologie befindet. Dieser Parameter muss auf **False** festgelegt werden.

