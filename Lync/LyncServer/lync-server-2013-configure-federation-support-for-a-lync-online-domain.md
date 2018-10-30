---
title: Konfigurieren der Unterstützung des Partnerverbunds für eine Lync Online-Domäne
TOCTitle: Konfigurieren der Unterstützung des Partnerverbunds für eine Lync Online-Domäne
ms:assetid: 19d5d5be-cd7f-47b8-b6c5-651a3191def7
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Hh202166(v=OCS.15)
ms:contentKeyID: 49293326
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren der Unterstützung des Partnerverbunds für eine Lync Online-Domäne

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Zum Einrichten eines Partnerverbunds mit einem Microsoft Lync Online 2010-Kunden müssen Sie die folgenden Schritte ausführen:

  - Konfigurieren Sie die Unterstützung für die Domäne des Lync Online 2010-Kunden (z. B. "contoso.onmicrosoft.com"). Wie im Abschnitt [Voraussetzungen für den Partnerverbund mit einem Lync Online-Kunden](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md) dieser Dokumentation beschrieben, sollten Sie den Partnerverbund für Ihre Organisation bereits aktiviert haben. Zum Aktivieren des Partnerverbunds muss die Methode zur Steuerung des Zugriffs durch Partnerdomänen angegeben werden. Wenn in Ihrer Organisation die Ermittlung verwendet wird, kann die Domäne optional der Liste der zugelassenen Domänen Ihrer Organisation hinzugefügt werden. Wenn Sie die Domänenermittlung nicht aktiviert haben, müssen Sie den Domänennamen des Lync Online-Kunden Ihrer Liste der zulässigen Domänen hinzufügen. Sie können einen Domänennamen entweder mit der Lync Server-Systemsteuerung oder mit dem Cmdlet **New-CSAllowedDomain** hinzufügen. Ausführliche Informationen zur Verwendung der Lync Server-Systemsteuerung, auch zum Aktivieren der Ermittlung von Domänen, finden Sie unter [Verwalten von SIP-Partnerverbundanbietern für eine Organisation in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) in der Betriebsdokumentation. Ausführliche Informationen zum Hinzufügen einer Domäne mit dem Cmdlet **New-CSAllowedDomain** finden Sie unter [New-CsAllowedDomain](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsAllowedDomain) in der Betriebsdokumentation.
    

    > [!NOTE]
    > Ein Lync Online-Kunde kann über mehrere Domänen verfügen. Wenn Sie einen Partnerverbund mit mehreren Domänen einrichten möchten, müssen Sie die Unterstützung für jede der betreffenden Domänen konfigurieren. Zudem muss der Administrator des Lync Online-Kunden den Partnerverbund für jede dieser Domänen aktivieren.



  - Konfigurieren Sie die Unterstützung für den Hostinganbieter der Lync Online 2010-Kundendomäne, mit der Sie einen Partnerverbund einrichten möchten. Verwenden Sie das Verfahren in diesem Abschnitt, um die Unterstützung für Hostinganbieter zu konfigurieren.
    

    > [!NOTE]
    > Dieser Schritt ist nur für den Partnerverbund mit einer Domäne eines Lync Online-Kunden erforderlich, nicht für den Partnerverbund mit einer Domäne, die lokal am Standort eines Verbundpartners bereitgestellt wurde.



## So konfigurieren Sie die Unterstützung für einen Hostinganbieter

1.  Von einem Front-End-Server, Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Führen Sie das Cmdlet **New-CsHostingProvider** aus, um den Hostinganbieter zu erstellen und zu konfigurieren. Führen Sie beispielsweise Folgendes aus:
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    Im oben stehenden Beispiel werden folgende Parameter festgelegt:
    
      - **Identity** gibt einen eindeutigen Zeichenfolgenwert für den Hostinganbieter an, den Sie erstellen. Beachten Sie, dass der Befehl nicht erfolgreich ist, wenn bereits ein Anbieter mit dieser Identität konfiguriert wurde.
    
      - **ProxyFQDN** gibt den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des vom Hostinganbieter verwendeten Proxyservers an. Dieser Wert kann nicht geändert werden. Wenn der Hostinganbieter seinen Proxyserver ändert, muss der Eintrag für diesen Anbieter gelöscht und neu erstellt werden.
    
      - **VerificationLevel** gibt an, wie (oder ob) von einem Hostinganbieter gesendete Nachrichten überprüft werden, um sicherzustellen, dass sie tatsächlich von diesem Anbieter stammen.
    
      - **Enabled** gibt an, ob die Netzwerkverbindung zwischen Ihrer Domäne und dem Hostinganbieter aktiviert ist. Der Nachrichtenaustausch zwischen zwei Organisationen ist erst möglich, wenn dieser Wert auf **True** festgelegt ist.
    
      - **EnabledSharedAddressSpace** gibt an, ob der Hostinganbieter in einem Szenario mit freigegebenem SIP-Adressraum (getrennte Domäne) verwendet wird.
    
      - **HostsOCSUsers** gibt an, ob der Hostinganbieter zum Hosten von Lync Server-Konten verwendet wird. Der Wert **False** gibt an, dass der Anbieter andere Kontotypen (z. B. Microsoft Exchange-Konten) hostet.
    
      - **IsLocal** gibt an, ob sich der vom Hostinganbieter verwendete Proxyserver in Ihrer Lync Server-Topologie befindet.
    
    Ausführliche Informationen zur Verwendung dieses Cmdlets finden Sie unter [New-CsHostingProvider](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsHostingProvider) in der Betriebsdokumentation.

