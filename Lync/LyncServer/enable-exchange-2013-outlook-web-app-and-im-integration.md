---
title: Aktivieren von Exchange 2013 Outlook Web App und der Integration von Chat
TOCTitle: Aktivieren von Exchange 2013 Outlook Web App und der Integration von Chat
ms:assetid: 44d08cf0-b17d-46e1-a4f0-fcc2fe96a958
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204857(v=OCS.15)
ms:contentKeyID: 49293850
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Aktivieren von Exchange 2013 Outlook Web App und der Integration von Chat

 

_**Letztes Änderungsdatum des Themas:** 2012-10-19_

Zur Unterstützung der Integration von Exchange 2013 Outlook Web Access (OWA) und Instant Messaging in Lync Server 2013 müssen Sie der Lync Server 2013-Topologie den Exchange 2013-Clientzugriffsserver (Client Access Server, CAS) als vertrauenswürdigen Anwendungsserver hinzufügen.

## So erstellen Sie einen vertrauenswürdigen Anwendungspool

1.  Starten Sie die Verwaltungsshell für Lync Server 2013.

2.  Führen Sie das folgende Cmdlet aus:
    
        Get-CsSite
    
    Damit wird die "siteIP" für den "siteName" zurückgegeben, unter dem Sie den Pool erstellen. Ausführliche Informationen finden Sie unter [Get-CsSite](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsSite) in der Dokumentation zur Verwaltungsshell für Lync Server 2013.

3.  Führen Sie das folgende Cmdlet aus:
    
        New-CsTrustedApplicationPool -Identity <E14 CAS FQDN> -ThrottleAsServer $true -TreatAsAuthenticated $true -ComputerFQDN <E14 CAS FQDN> -Site <Site> -Registrar <Pool FQDN in the site> -RequiresReplication $false
    
    Ausführliche Informationen finden Sie unter [New-CsTrustedApplicationPool](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsTrustedApplicationPool) in der Verwaltungsshell für Lync Server 2013-Dokumentation.
    
    Der Exchange Server-FQDN sollte als Antragstellername oder alternativer Antragstellername des Exchange OWA-Zertifikats konfiguriert werden.
    
    Überprüfen Sie in Exchange OWA, ob der FQDN des Pools ebenfalls vertrauenswürdig ist.
    

    > [!IMPORTANT]
    > Wenn der Clientzugriffsserver <EM>nicht</EM> mit dem Server verbunden ist, auf dem auch Exchange 2013 Unified Messaging (UM) ausgeführt wird, überspringen Sie die restlichen Schritte dieses Verfahrens, und führen Sie die Schritte unter "So erstellen Sie eine vertrauenswürdige Anwendung für den Exchange 2013-Clientzugriffsserver" weiter unten aus. Ist der Clientzugriffsserver mit dem Server verbunden, auf dem Exchange 2013 Unified Messaging (UM) ausgeführt wird, führen Sie die Schritte in diesem Verfahren hier aus und nicht das Verfahren "So erstellen Sie eine vertrauenswürdige Anwendung für den Exchange 2013-Clientzugriffsserver" weiter unten.



4.  Führen Sie **Enable-CsTopology** aus.

5.  Öffnen Sie den Topologie-Generator, und laden Sie die bestehende Topologie herunter.

6.  Erweitern Sie im linken Bereich die Struktur bis hinunter zu **Vertrauenswürdige Anwendungsserver** .

7.  Erweitern Sie den Knoten **Vertrauenswürdige Anwendungsserver** .

8.  Der Exchange 2013-Clientzugriffsserver sollte jetzt als vertrauenswürdiger Anwendungsserver angezeigt werden.

## So erstellen Sie eine vertrauenswürdige Anwendung für den Exchange 2013-Clientzugriffsserver

1.  Starten Sie die Verwaltungsshell für Lync Server 2013.

2.  Wenn der Clientzugriffsserver *nicht* mit dem Server verbunden ist, auf dem Exchange 2013 Unified Messaging (UM) ausgeführt wird, führen Sie das folgende Cmdlet aus:
    
        New-CsTrustedApplication -ApplicationId <AppID String> -TrustedApplicationPoolFqdn <E14 CAS FQDN> -Port <available port number>
    
    Ausführliche Informationen hierzu finden Sie unter dem Thema [New-CsTrustedApplication](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsTrustedApplication) in der Dokumentation zur Verwaltungsshell für Lync Server 2013.

3.  Führen Sie **Enable-CsTopology** aus.

4.  Erweitern Sie im linken Bereich des Topologie-Generators die Struktur bis hinunter zu **Vertrauenswürdige Anwendungsserver** .

5.  Erweitern Sie den Knoten **Vertrauenswürdige Anwendungsserver** .

6.  Der Exchange 2013-Clientzugriffsserver sollte jetzt als vertrauenswürdiger Anwendungsserver angezeigt werden.

