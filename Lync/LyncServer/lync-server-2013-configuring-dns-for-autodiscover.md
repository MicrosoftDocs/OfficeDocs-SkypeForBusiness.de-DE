---
title: Konfigurieren von DNS für die AutoErmittlung
TOCTitle: Konfigurieren von DNS für die AutoErmittlung
ms:assetid: f07a634c-3cf3-4958-8556-84596319ef54
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ945656(v=OCS.15)
ms:contentKeyID: 52056484
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von DNS für die AutoErmittlung

 

_**Letztes Änderungsdatum des Themas:** 2012-12-12_

Um die AutoErmittlung für Lync-Clients zu unterstützen, müssen Sie folgende DNS (Domain Name System)-Einträge erstellen:

  - Einen internen DNS-Eintrag zur Unterstützung von Lync-Clients, die über das Netzwerk Ihrer Organisation eine Verbindung herstellen

  - Einen externen oder öffentlichen DNS-Eintrag zur Unterstützung von Lync-Clients, die eine Verbindung über das Internet herstellen

Für jede SIP-Domäne muss ein interner DNS-Eintrag und ein externer DNS-Eintrag erstellt werden.

Bei den DNS-Einträgen kann es sich entweder um A-Einträge (Host) oder um CNAME-Einträge handeln, je nachdem, ob Sie neue Zertifikate mit dem zusätzlichen alternativen Antragstellernamen (SAN) erstellen können. Wenn Sie nicht in der Lage sind, ein neues externes (öffentliches) Zertifikat mit dem SAN "lyncdiscover.\<domänenname\>" anzufordern und bereitzustellen, verwenden Sie das Verfahren zum Verwenden des HTTP/TCP-Ports 80. Die folgenden Vorgehensweisen beschreiben, wie interne und externe DNS-Einträge erstellt werden.

## So erstellen Sie DNS-CNAME-Einträge

1.  Melden Sie sich wie folgt an einem DNS-Server an:
    
      - Wenn Sie einen internen DNS-Eintrag erstellen möchten, melden Sie sich an einem DNS-Server in Ihrem Netzwerk als Mitglied der Domänenadministratorgruppe oder der DnsAdmins-Gruppe an.
    
      - Wenn Sie einen externen DNS-Eintrag erstellen möchten, stellen Sie eine Verbindung mit dem öffentlichen DNS-Anbieter her.

2.  Öffnen Sie das DNS-Verwaltungs-Snap-In: Klicken Sie auf **Start**, auf **Verwaltung** und dann auf **DNS**.

3.  Führen Sie einen der folgenden Schritte aus:
    
      - Wenn Sie einen internen DNS-Eintrag erstellen, erweitern Sie in der Konsolenstruktur des DNS-Servers **Forward-Lookupzonen** für die Active Directory-Domäne (z. B. "contoso.local").
        

        > [!NOTE]
        > Diese Domäne ist die Active Directory-Domäne, in der der Lync Server 2013Director-Pool und Front-End-Pool installiert sind.

    
      - Wenn Sie einen externen DNS-Eintrag erstellen, erweitern Sie in der Konsolenstruktur des DNS-Servers **Forward-Lookupzonen** für die SIP-Domäne (z. B. "contoso.com").

4.  Stellen Sie wie folgt sicher, dass ein Host-A-Eintrag für den Directorpool vorhanden ist:
    
      - Für einen internen DNS-Eintrag sollte für den internen vollqualifizierten Domänennamen (FQDN) der Webdienste ein Host-A-Eintrag für den Directorpool vorhanden sein (z. B."lyncwebdir01.contoso.local").
    
      - Für einen externen DNS-Eintrag sollte für den FQND der externen Webdienste ein Host-A-Eintrag für den Directorpool vorhanden sein (z. B. "lyncwebextdir.contoso.com").

5.  Stellen Sie wie folgt sicher, dass ein Host-A-Eintrag für den Front-End-Pool vorhanden ist:
    
      - Für einen internen DNS-Eintrag sollte für den internen Webdienste-FQDN ein Host-A-Eintrag für den Front-End-Pool vorhanden sein (z. B."lyncwebpool01.contoso.local").
    
      - Für einen externen DNS-Eintrag sollte für den externen Webdienste-FQND ein Host-A-Eintrag für den Front-End-Pool vorhanden sein (z. B. "lyncwebextpool01.contoso.com").

6.  Wenn Sie einen internen DNS-Eintrag erstellen, erweitern Sie in der Konsolenstruktur des DNS-Servers **Forward-Lookupzonen** für die SIP-Domäne (z. B. "contoso.com").
    

    > [!NOTE]
    > Wenn Sie einen externen DNS-Eintrag erstellen, ist <STRONG>Forward-Lookupzonen</STRONG> bereits für die SIP-Domäne aus Schritt&nbsp;3 erweitert.



7.  Klicken Sie mit der rechten Maustaste auf den Namen der SIP-Domäne, und klicken Sie dann auf **Neuer Alias (CNAME)**.

8.  Nehmen Sie im Feld **Aliasname** eine der folgenden Eingaben vor:
    
      - Geben Sie für einen internen DNS-Eintrag "lyncdiscoverinternal" als den Hostnamen für die interne AutoErmittlungdienst-URL ein.
    
      - Geben Sie für einen externen DNS-Eintrag "lyncdiscover" als den Hostnamen für die externe AutoErmittlungdienst-URL ein.

9.  Führen Sie in **Vollqualifizierter Domänenname des Zielhosts** einen der folgenden Schritte durch:
    
      - Geben Sie für einen internen DNS-Eintrag den internen Webdienste-FQDN für den Directorpool ein (z. B. "lyncwebdir01.contoso.local"), oder navigieren Sie zum FQDN, und klicken Sie dann auf **OK**.
    
      - Geben Sie für einen externen DNS-Eintrag den externen Webdienste-FQDN für den Directorpool ein (z. B. "lyncwebextdir.contoso.com"), und klicken Sie dann auf **OK**.
    

    > [!NOTE]
    > Wenn Sie keinen Director verwenden, verwenden Sie den internen und externen Webdienste-FQDN für den Front-End-Pool oder, für einen einzelnen Server, den FQDN für den Front-End-Server oder den Standard Edition-Server.

    

    > [!IMPORTANT]
    > Sie müssen einen neuen AutoErmittlung-CNAME-Eintrag in der Forward-Lookupzone jeder SIP-Domäne erstellen, die in Ihrer Lync Server 2013-Umgebung unterstützt wird.



## So erstellen Sie DNS-A-Einträge

1.  Melden Sie sich wie folgt an einem DNS-Server an:
    
      - Wenn Sie einen internen DNS-Eintrag erstellen möchten, melden Sie sich an einem DNS-Server in Ihrem Netzwerk als Mitglied der Domänenadministratorgruppe oder der DnsAdmins-Gruppe an.
    
      - Wenn Sie einen externen DNS-Eintrag erstellen möchten, stellen Sie eine Verbindung mit dem öffentlichen DNS-Anbieter oder dem externen DNS-Server her.

2.  Öffnen Sie das DNS-Verwaltungs-Snap-In: Klicken Sie auf **Start**, auf **Verwaltung** und dann auf **DNS**.

3.  Führen Sie einen der folgenden Schritte aus:
    
      - Wenn Sie einen internen DNS-Eintrag erstellen, erweitern Sie in der Konsolenstruktur des DNS-Servers **Forward-Lookupzonen** für die Active Directory-Domäne (z. B. "contoso.local").
        

        > [!NOTE]
        > Diese Domäne ist die Active Directory-Domäne, in der der Lync Server 2013Director-Pool und Front-End-Pool installiert sind.

    
      - Wenn Sie einen externen DNS-Eintrag erstellen, erweitern Sie in der Konsolenstruktur des DNS-Servers **Forward-Lookupzonen** für die SIP-Domäne (z. B. "contoso.com").

4.  Stellen Sie wie folgt sicher, dass ein Host-A-Eintrag (für IPv6, AAAA) für den Directorpool vorhanden ist:
    
      - Für einen internen DNS-Eintrag sollte für den internen Webdienste-FQDN ein Host-A-Eintrag (für IPv6, AAAA) für den Directorpool vorhanden sein (z. B."lyncwebdir01.contoso.local").
    
      - Für einen externen DNS-Eintrag sollte für den FQND der externen Webdienste ein Host-A-Eintrag (für IPv6, AAAA) für den Directorpool vorhanden sein (z. B. "lyncwebextdir.contoso.com").

5.  Stellen Sie wie folgt sicher, dass ein Host-A-Eintrag (für IPv6, AAAA) für den Front-End-Pool vorhanden ist:
    
      - Für einen internen DNS-Eintrag sollte für den internen Webdienste-FQDN ein Host-A-Eintrag (für IPv6, AAAA) für den Front-End-Pool vorhanden sein (z. B."lyncwebpool01.contoso.local").
    
      - Für einen externen DNS-Eintrag sollte für den FQND der externen Webdienste ein Host-A-Eintrag (für IPv6, AAAA) für den Front-End-Pool vorhanden sein (z. B. "lyncwebextpool01.contoso.com").

6.  Wenn Sie einen internen DNS-Eintrag erstellen, erweitern Sie in der Konsolenstruktur des DNS-Servers **Forward-Lookupzonen** für die SIP-Domäne (z. B. "contoso.com").
    

    > [!NOTE]
    > Wenn Sie einen externen DNS-Eintrag erstellen, ist <STRONG>Forward-Lookupzonen</STRONG> bereits für die SIP-Domäne aus Schritt&nbsp;3 erweitert.



7.  Klicken Sie mit der rechten Maustaste auf den Namen der SIP-Domäne, und klicken Sie dann auf **Neuer Host (A oder AAAA)**.

8.  Geben Sie im Feld **Name** den Hostnamen wie folgt ein:
    
      - Geben Sie für einen internen DNS-Eintrag "lyncdiscoverinternal" als den Hostnamen für die interne AutoErmittlungdienst-URL ein.
    
      - Geben Sie für einen externen DNS-Eintrag "lyncdiscover" als den Hostnamen für die externe AutoErmittlungdienst-URL ein.
    

    > [!NOTE]
    > Der Domänenname wird von der Zone abgeleitet, in welcher der Eintrag definiert ist, und muss daher nicht als Teil des A-Eintrags eingegeben werden.



9.  Geben Sie im Feld **IP-Adresse** die IP-Adresse wie folgt ein:
    
      - Geben Sie für einen internen DNS-Eintrag die interne Webdienste-IP-Adresse des Directors ein (oder geben Sie die virtuelle IP (VIP) des Director-Lastenausgleichs ein, wenn Sie einen Lastenausgleich verwenden).
        

        > [!NOTE]
        > Wenn Sie keinen Director verwenden, geben Sie die IP-Adresse des Front-End-Servers oder Standard Edition-Servers ein, oder geben Sie die virtuelle IP (VIP) des Front-End-Pool-Lastenausgleichs ein, wenn Sie einen Lastenausgleich verwenden.

    
      - Geben Sie für einen externen DNS-Eintrag die externe oder öffentliche IP-Adresse des Reverseproxys ein.

10. Klicken Sie auf **Host hinzufügen** und dann auf **OK**.

11. Wenn Sie einen zusätzlichen A-Eintrag erstellen möchten, wiederholen Sie die Schritte 8 bis 10.
    

    > [!IMPORTANT]
    > Sie müssen einen neuen A-Eintrag "lyncdiscover" und A-Eintrag "lyncdiscoverinternal" in der Forward-Lookupzone jeder SIP-Domäne erstellen, die in Ihrer Lync Server 2013-Umgebung unterstützt wird.



12. Klicken Sie auf **Fertig**, wenn Sie das Erstellen von A-Einträgen (für IPv6, AAAA) abgeschlossen haben.

