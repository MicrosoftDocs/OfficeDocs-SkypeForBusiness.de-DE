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
ms.openlocfilehash: 7ff6e72d13ddfb80369a0a522abc14a1de459536
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202991"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-dns-for-autodiscover-in-lync-server-2013"></a>Konfigurieren von DNS für die AutoErmittlung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-12-12_

Um die AutoErmittlung für lync-Clients zu unterstützen, müssen Sie die folgenden Domain Name System (DNS)-Einträge erstellen:

  - Ein interner DNS-Eintrag zur Unterstützung von lync-Clients, die im Netzwerk Ihrer Organisation eine Verbindung herstellen

  - Einen externen oder öffentlichen DNS-Eintrag zur Unterstützung von lync-Clients, die eine Verbindung über das Internet herstellen

Für jede SIP-Domäne muss ein interner DNS-Eintrag und ein externer DNS-Eintrag erstellt werden.

Bei den DNS-Einträgen kann es sich entweder um einen (Host-) Eintrag oder um CNAME-Einträge handeln, basierend auf ihrer Fähigkeit, neue Zertifikate mit dem zusätzlichen Antragstellernamen (San) zu erstellen. Wenn Sie kein neues externes (öffentliches) Zertifikat mit dem lyncdiscover anfordern und bereitstellen können. \<Domänenname\> San, verwenden Sie das Verfahren für die Verwendung von http/TCP-Port 80. Die folgenden Vorgehensweisen beschreiben, wie interne und externe DNS-Einträge erstellt werden.

<div>

## <a name="to-create-dns-cname-records"></a>So erstellen Sie DNS-CNAME-Einträge

1.  Melden Sie sich wie folgt an einem DNS-Server an:
    
      - Wenn Sie einen internen DNS-Eintrag erstellen möchten, melden Sie sich an einem DNS-Server in Ihrem Netzwerk als Mitglied der Domänenadministratorgruppe oder der DnsAdmins-Gruppe an.
    
      - Wenn Sie einen externen DNS-Eintrag erstellen möchten, stellen Sie eine Verbindung mit dem öffentlichen DNS-Anbieter her.

2.  Öffnen Sie das DNS-Verwaltungs-Snap-In: Klicken Sie auf **Start**, auf **Verwaltung** und dann auf **DNS**.

3.  Führen Sie einen der folgenden Schritte aus:
    
      - Wenn Sie einen internen DNS-Eintrag erstellen, erweitern Sie in der Konsolenstruktur des DNS-Servers **Forward-Lookupzonen** für die Active Directory-Domäne (z. B. "contoso.local").
        
        <div>
        

        > [!NOTE]  
        > Diese Domäne ist die Active Directory Domäne, in der&nbsp;ihre lync Server 2013 Directorpool und Front-End-Pool installiert sind.

        
        </div>
    
      - Wenn Sie einen externen DNS-Eintrag erstellen, erweitern Sie in der Konsolenstruktur des DNS-Servers **Forward-Lookupzonen** für die SIP-Domäne (z. B. "contoso.com").

4.  Stellen Sie sicher, dass ein Host-a-Eintrag für Ihre Directorpool wie folgt vorhanden ist:
    
      - Für einen internen DNS-Eintrag sollte ein Host-a-Eintrag für den internen Webdienste vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für Ihre Directorpool vorhanden sein (beispielsweise lyncwebdir01. contoso. local).
    
      - Für einen externen DNS-Eintrag sollte ein Host-a-Eintrag für den externen Webdienste-FQDN für Ihre Directorpool vorhanden sein (beispielsweise lyncwebextdir.contoso.com).

5.  Stellen Sie sicher, dass ein Host-a-Eintrag für Ihre Front-End-Pool wie folgt vorhanden ist:
    
      - Für einen internen DNS-Eintrag sollte ein Host-a-Eintrag für den internen Webdienste FQDN für Ihre Front-End-Pool vorhanden sein (beispielsweise lyncwebpool01. contoso. local).
    
      - Für einen externen DNS-Eintrag sollte ein Host-a-Eintrag für den externen Webdienste FQDN für Ihre Front-End-Pool vorhanden sein (beispielsweise lyncwebextpool01.contoso.com).

6.  Wenn Sie einen internen DNS-Eintrag erstellen, erweitern Sie in der Konsolenstruktur des DNS-Servers **Forward-Lookupzonen** für die SIP-Domäne (z. B. "contoso.com").
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie einen externen DNS-Eintrag erstellen, ist <STRONG>Forward-Lookupzonen</STRONG> bereits für die SIP-Domäne aus Schritt 3 erweitert.

    
    </div>

7.  Klicken Sie mit der rechten Maustaste auf den Namen der SIP-Domäne, und klicken Sie dann auf **Neuer Alias (CNAME)**.

8.  Nehmen Sie im Feld **Aliasname** eine der folgenden Eingaben vor:
    
      - Geben Sie für einen internen DNS-Eintrag "lyncdiscoverinternal" als den Hostnamen für die interne AutoErmittlungdienst-URL ein.
    
      - Geben Sie für einen externen DNS-Eintrag "lyncdiscover" als den Hostnamen für die externe AutoErmittlungdienst-URL ein.

9.  Führen Sie in **Vollqualifizierter Domänenname des Zielhosts** einen der folgenden Schritte durch:
    
      - Geben Sie für einen internen DNS-Eintrag den internen Webdienste-FQDN für Ihre Directorpool ein (beispielsweise lyncwebdir01. contoso. local), und klicken Sie dann auf **OK**.
    
      - Geben Sie für einen externen DNS-Eintrag den FQDN des externen Webdienste für die Directorpool ein (beispielsweise lyncwebextdir.contoso.com), und klicken Sie dann auf **OK**.
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie keinen Director verwenden, verwenden Sie den internen und externen Webdienste-FQDN für den Front-End-Pool oder für einen einzelnen Server den FQDN für die Front-End-Server oder Standard Edition-Server.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > Sie müssen einen neuen CNAME-Eintrag für die AutoErmittlung in der Forward-Lookupzone jeder SIP-Domäne erstellen, die Sie in ihrer lync Server 2013 Umgebung unterstützen.

    
    </div>

</div>

<div>

## <a name="to-create-dns-a-records"></a>So erstellen Sie DNS-A-Einträge

1.  Melden Sie sich wie folgt an einem DNS-Server an:
    
      - Wenn Sie einen internen DNS-Eintrag erstellen möchten, melden Sie sich an einem DNS-Server in Ihrem Netzwerk als Mitglied der Domänenadministratorgruppe oder der DnsAdmins-Gruppe an.
    
      - Wenn Sie einen externen DNS-Eintrag erstellen möchten, stellen Sie eine Verbindung mit Ihrem öffentlichen DNS-Anbieter oder externen DNS-Server her.

2.  Öffnen Sie das DNS-Verwaltungs-Snap-In: Klicken Sie auf **Start**, auf **Verwaltung** und dann auf **DNS**.

3.  Führen Sie einen der folgenden Schritte aus:
    
      - Wenn Sie einen internen DNS-Eintrag erstellen, erweitern Sie in der Konsolenstruktur des DNS-Servers **Forward-Lookupzonen** für die Active Directory-Domäne (z. B. "contoso.local").
        
        <div>
        

        > [!NOTE]  
        > Diese Domäne ist die Active Directory Domäne, in der&nbsp;ihre lync Server 2013 Directorpool und Front-End-Pool installiert sind.

        
        </div>
    
      - Wenn Sie einen externen DNS-Eintrag erstellen, erweitern Sie in der Konsolenstruktur des DNS-Servers **Forward-Lookupzonen** für die SIP-Domäne (z. B. "contoso.com").

4.  Stellen Sie sicher, dass ein Host-a-Eintrag (für IPv6, AAAA) für Ihre Directorpool wie folgt vorhanden ist:
    
      - Für einen internen DNS-Eintrag sollte ein Host-a-Eintrag (für IPv6, AAAA) für den internen Webdienste FQDN für Ihre Directorpool vorhanden sein (beispielsweise lyncwebdir01. contoso. local).
    
      - Für einen externen DNS-Eintrag sollte ein Host-a-Eintrag (für IPv6, AAAA) für den externen Webdienste-FQDN für Ihre Directorpool vorhanden sein (beispielsweise lyncwebextdir.contoso.com).

5.  Stellen Sie sicher, dass ein Host-a-Eintrag (für IPv6, AAAA) für Ihre Front-End-Pool wie folgt vorhanden ist:
    
      - Für einen internen DNS-Eintrag sollte ein Host-a-Eintrag (für IPv6, AAAA) für den internen Webdienste FQDN für Ihre Front-End-Pool vorhanden sein (beispielsweise lyncwebpool01. contoso. local).
    
      - Für einen externen DNS-Eintrag sollte ein Host-a-Eintrag (für IPv6, AAAA) für den externen Webdienste-FQDN für Ihre Front-End-Pool vorhanden sein (beispielsweise lyncwebextpool01.contoso.com).

6.  Wenn Sie einen internen DNS-Eintrag erstellen, erweitern Sie in der Konsolenstruktur des DNS-Servers **Forward-Lookupzonen** für die SIP-Domäne (z. B. "contoso.com").
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie einen externen DNS-Eintrag erstellen, ist <STRONG>Forward-Lookupzonen</STRONG> bereits für die SIP-Domäne aus Schritt 3 erweitert.

    
    </div>

7.  Klicken Sie mit der rechten Maustaste auf den Namen der SIP-Domäne, und klicken Sie dann auf **Neuer Host (A oder AAAA)**.

8.  Geben Sie im Feld **Name** den Hostnamen wie folgt ein:
    
      - Geben Sie für einen internen DNS-Eintrag "lyncdiscoverinternal" als den Hostnamen für die interne AutoErmittlungdienst-URL ein.
    
      - Geben Sie für einen externen DNS-Eintrag "lyncdiscover" als den Hostnamen für die externe AutoErmittlungdienst-URL ein.
    
    <div>
    

    > [!NOTE]  
    > Der Domänenname wird von der Zone abgeleitet, in welcher der Eintrag definiert ist, und muss daher nicht als Teil des A-Eintrags eingegeben werden.

    
    </div>

9.  Geben Sie im Feld **IP-Adresse** die IP-Adresse wie folgt ein:
    
      - Geben Sie für einen internen DNS-Eintrag die interne Webdienste-IP-Adresse des Directors ein (oder geben Sie bei Verwendung eines Lastenausgleichs die virtuelle IP (VIP) des Director-Lastenausgleichs) ein.
        
        <div>
        

        > [!NOTE]  
        > Wenn Sie keinen Director verwenden, geben Sie die IP-Adresse des Front-End-Server oder Standard Edition-Server ein, oder geben Sie bei Verwendung eines Lastenausgleichs den VIP des Front-End-Pool Lastenausgleichs ein.

        
        </div>
    
      - Geben Sie für einen externen DNS-Eintrag die externe oder öffentliche IP-Adresse des Reverseproxys ein.

10. Klicken Sie auf **Host hinzufügen** und dann auf **OK**.

11. Wenn Sie einen zusätzlichen A-Eintrag erstellen möchten, wiederholen Sie die Schritte 8 bis 10.
    
    <div>
    

    > [!IMPORTANT]  
    > Sie müssen eine neue lyncdiscover erstellen und "lyncdiscoverinternal" eine Datensätze in der Forward-Lookupzone jeder SIP-Domäne, die Sie in ihrer lync Server 2013 Umgebung unterstützen.

    
    </div>

12. Klicken Sie auf **Fertig**, wenn Sie das Erstellen von A-Einträgen (für IPv6, AAAA) abgeschlossen haben.

</div>

</div>

<span> </span>

</div>

</div>

</div>

