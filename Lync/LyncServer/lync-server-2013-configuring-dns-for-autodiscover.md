---
title: 'Lync Server 2013: Konfigurieren von DNS für die AutoErmittlung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring DNS for Autodiscover
ms:assetid: f07a634c-3cf3-4958-8556-84596319ef54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945656(v=OCS.15)
ms:contentKeyID: 51541528
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77cf81cd82655a37ad089d915e9e3799671025bb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736455"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-dns-for-autodiscover-in-lync-server-2013"></a>Konfigurieren von DNS für die AutoErmittlung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-12-12_

Um die AutoDiscovery für lync-Clients zu unterstützen, müssen Sie die folgenden DNS-Einträge (Domain Name System) erstellen:

  - Ein interner DNS-Eintrag zur Unterstützung von lync-Clients, die innerhalb des Netzwerks Ihrer Organisation eine Verbindung herstellen

  - Ein externer oder öffentlicher DNS-Eintrag zur Unterstützung von lync-Clients, die eine Verbindung mit dem Internet herstellen

Sie müssen einen internen DNS-Eintrag und einen externen DNS-Eintrag für jede SIP-Domäne erstellen.

Bei den DNS-Einträgen kann es sich um eine (Host-) oder CNAME-Einträge handeln, basierend auf ihrer Möglichkeit zum Erstellen neuer Zertifikate mit dem zusätzlichen Subject-Namen (Alternate Name, San). Wenn Sie nicht in der Lage sind, ein neues externes (öffentliches) Zertifikat mit dem lyncdiscover anzufordern und bereitzustellen. \<Domänennamen\> -San verwenden Sie das Verfahren für die Verwendung von http/TCP-Port 80. In den folgenden Verfahren wird beschrieben, wie interne und externe DNS-Einträge erstellt werden.

<div>

## <a name="to-create-dns-cname-records"></a>So erstellen Sie DNS-CNAME-Einträge

1.  Melden Sie sich wie folgt bei einem DNS-Server an:
    
      - Wenn Sie einen internen DNS-Eintrag erstellen möchten, melden Sie sich bei einem DNS-Server in Ihrem Netzwerk als Mitglied der Gruppe der Domänenadministratoren oder als Mitglied der DnsAdmins-Gruppe an.
    
      - Wenn Sie einen externen DNS-Eintrag erstellen möchten, stellen Sie eine Verbindung mit Ihrem öffentlichen DNS-Anbieter her.

2.  Öffnen Sie das DNS-Administrator-Snap-in: Klicken Sie auf **Start**, klicken Sie auf **Verwaltung**, und klicken Sie dann auf **DNS**.

3.  Führen Sie einen der folgenden Schritte aus:
    
      - Erweitern Sie für einen internen DNS-Eintrag in der Konsolenstruktur des DNS-Servers **Forward-Lookupzonen** für Ihre Active Directory-Domäne (beispielsweise "contoso. local").
        
        <div>
        

        > [!NOTE]  
        > Diese Domäne ist die Active Directory-Domäne, in der der&nbsp;lync Server 2013 Director-Pool und der Front-End-Pool installiert sind.

        
        </div>
    
      - Erweitern Sie für einen externen DNS-Eintrag in der Konsolenstruktur des DNS-Servers **Forward-Lookupzonen** für Ihre SIP-Domäne (beispielsweise contoso.com).

4.  Stellen Sie sicher, dass für Ihren Director-Pool wie folgt ein Host-a-Eintrag vorhanden ist:
    
      - Bei einem internen DNS-Eintrag sollte ein Host-a-Eintrag für den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) Ihres Director-Pools (beispielsweise lyncwebdir01. contoso. local) vorhanden sein.
    
      - Bei einem externen DNS-Eintrag sollte ein Host-a-Eintrag für den FQDN externer Webdienste für Ihren Director-Pool vorhanden sein (beispielsweise lyncwebextdir.contoso.com).

5.  Stellen Sie sicher, dass für Ihren Front-End-Pool wie folgt ein Host-a-Eintrag vorhanden ist:
    
      - Bei einem internen DNS-Eintrag sollte ein Host-a-Eintrag für den internen Webdienst-FQDN für Ihren Front-End-Pool vorhanden sein (beispielsweise "lyncwebpool01. contoso. local").
    
      - Bei einem externen DNS-Eintrag sollte ein Host-a-Eintrag für den FQDN externer Dienste für den Front-End-Pool vorhanden sein (beispielsweise lyncwebextpool01.contoso.com).

6.  Erweitern Sie für einen internen DNS-Eintrag in der Konsolenstruktur Ihres DNS-Servers **Forward-Lookupzonen** für Ihre SIP-Domäne (beispielsweise contoso.com).
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie einen externen DNS-Eintrag erstellen, werden <STRONG>Forward-Lookupzonen</STRONG> für Ihre SIP-Domäne bereits aus Schritt 3 erweitert.

    
    </div>

7.  Klicken Sie mit der rechten Maustaste auf den SIP-Domänennamen, und klicken Sie dann auf **Neuer Alias (CNAME)**.

8.  Geben Sie unter **Alias Name**eine der folgenden Optionen ein:
    
      - Geben Sie für einen internen DNS-Eintrag lyncdiscoverinternal als Hostname für die interne URL des AutoErmittlungsdiensts ein.
    
      - Geben Sie für einen externen DNS-Eintrag lyncdiscover als Hostnamen für die URL des externen AutoErmittlungsdiensts ein.

9.  Führen Sie im **vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für den Ziel Host**eine der folgenden Aktionen aus:
    
      - Geben Sie für einen internen DNS-Eintrag den internen FQDN des Webdiensts für Ihren Director-Pool ein, oder suchen Sie nach ihm (beispielsweise lyncwebdir01. contoso. local), und klicken Sie dann auf **OK**.
    
      - Geben Sie für einen externen DNS-Eintrag den FQDN externer Webdienste für Ihren Director-Pool ein, oder suchen Sie nach ihm (beispielsweise lyncwebextdir.contoso.com), und klicken Sie dann auf **OK**.
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie keinen Director verwenden, verwenden Sie den FQDN für interne und externe Webdienste für den Front-End-Pool oder für einen einzelnen Server den FQDN für den Front-End-Server oder den Standard Edition-Server.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > Sie müssen einen neuen CNAME-Eintrag für die AutoErmittlung in der Forward-Lookupzone jeder SIP-Domäne erstellen, die Sie in ihrer lync Server 2013-Umgebung unterstützen.

    
    </div>

</div>

<div>

## <a name="to-create-dns-a-records"></a>So erstellen Sie DNS-A-Einträge

1.  Melden Sie sich wie folgt bei einem DNS-Server an:
    
      - Wenn Sie einen internen DNS-Eintrag erstellen möchten, melden Sie sich bei einem DNS-Server in Ihrem Netzwerk als Mitglied der Gruppe der Domänenadministratoren oder als Mitglied der DnsAdmins-Gruppe an.
    
      - Wenn Sie einen externen DNS-Eintrag erstellen möchten, stellen Sie eine Verbindung mit Ihrem öffentlichen DNS-Anbieter oder einem externen DNS-Server her.

2.  Öffnen Sie das DNS-Administrator-Snap-in: Klicken Sie auf **Start**, klicken Sie auf **Verwaltung**, und klicken Sie dann auf **DNS**.

3.  Führen Sie einen der folgenden Schritte aus:
    
      - Erweitern Sie für einen internen DNS-Eintrag in der Konsolenstruktur des DNS-Servers **Forward-Lookupzonen** für Ihre Active Directory-Domäne (beispielsweise "contoso. local").
        
        <div>
        

        > [!NOTE]  
        > Diese Domäne ist die Active Directory-Domäne, in der der&nbsp;lync Server 2013 Director-Pool und der Front-End-Pool installiert sind.

        
        </div>
    
      - Erweitern Sie für einen externen DNS-Eintrag in der Konsolenstruktur des DNS-Servers **Forward-Lookupzonen** für Ihre SIP-Domäne (beispielsweise contoso.com).

4.  Überprüfen Sie, ob ein Host-a-Eintrag (für IPv6, AAAA) für Ihren Director-Pool wie folgt vorhanden ist:
    
      - Für einen internen DNS-Eintrag sollte ein Host-a-Eintrag (für IPv6, AAAA) für den internen Webdienst-FQDN für Ihren Director-Pool vorhanden sein (beispielsweise "lyncwebdir01. contoso. local").
    
      - Bei einem externen DNS-Eintrag sollte ein Host-a-Eintrag (für IPv6, AAAA) für den FQDN externer Webdienste für Ihren Director-Pool vorhanden sein (beispielsweise lyncwebextdir.contoso.com).

5.  Überprüfen Sie, ob ein Host-a-Eintrag (für IPv6, AAAA) für Ihren Front-End-Pool wie folgt vorhanden ist:
    
      - Für einen internen DNS-Eintrag sollte ein Host-a-Eintrag (für IPv6, AAAA) für den internen Webdienst-FQDN für Ihren Front-End-Pool vorhanden sein (beispielsweise "lyncwebpool01. contoso. local").
    
      - Bei einem externen DNS-Eintrag sollte ein Host-a-Eintrag (für IPv6, AAAA) für den FQDN externer Dienste für Ihren Front-End-Pool vorhanden sein (beispielsweise lyncwebextpool01.contoso.com).

6.  Erweitern Sie für einen internen DNS-Eintrag in der Konsolenstruktur Ihres DNS-Servers **Forward-Lookupzonen** für Ihre SIP-Domäne (beispielsweise contoso.com).
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie einen externen DNS-Eintrag erstellen, werden <STRONG>Forward-Lookupzonen</STRONG> für Ihre SIP-Domäne bereits aus Schritt 3 erweitert.

    
    </div>

7.  Klicken Sie mit der rechten Maustaste auf den SIP-Domänennamen, und klicken Sie dann auf **neuer Host (A oder AAAA)**.

8.  Geben Sie unter **Name**den Namen des Hosts wie folgt ein:
    
      - Geben Sie für einen internen DNS-Eintrag lyncdiscoverinternal als Hostname für die interne URL des AutoErmittlungsdiensts ein.
    
      - Geben Sie für einen externen DNS-Eintrag lyncdiscover als Hostnamen für die URL des externen AutoErmittlungsdiensts ein.
    
    <div>
    

    > [!NOTE]  
    > Der Domänenname wird aus der Zone übernommen, in der der Datensatz definiert ist und daher nicht als Teil des A-Eintrags eingegeben werden muss.

    
    </div>

9.  Geben Sie unter **IP-Adresse**die IP-Adresse wie folgt ein:
    
      - Geben Sie für einen internen DNS-Eintrag die interne Webdienste-IP-Adresse des Directors ein (oder, wenn Sie ein Lastenausgleichsmodul verwenden, die virtuelle IP (VIP) des Director Load Balancer).
        
        <div>
        

        > [!NOTE]  
        > Wenn Sie keinen Director verwenden, geben Sie die IP-Adresse des Front-End-Servers oder des Standard Edition-Servers ein, oder geben Sie bei Verwendung eines Load Balancer den VIP des Load Balancer des Front-End-Pools ein.

        
        </div>
    
      - Geben Sie für einen externen DNS-Eintrag die externe oder öffentliche IP-Adresse des Reverse-Proxys ein.

10. Klicken Sie auf **Host hinzufügen**, und klicken Sie dann auf **OK**.

11. Wenn Sie einen zusätzlichen A-Eintrag erstellen möchten, wiederholen Sie die Schritte 8 bis 10.
    
    <div>
    

    > [!IMPORTANT]  
    > Sie müssen ein neues lyncdiscover-und lyncdiscoverinternal-Datensätze in der Forward-Lookupzone jeder SIP-Domäne erstellen, die Sie in ihrer lync Server 2013-Umgebung unterstützen.

    
    </div>

12. Wenn Sie mit dem Erstellen eines (für IPv6-, AAAA)-Datensatzes fertig sind, klicken Sie auf **Fertig**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

