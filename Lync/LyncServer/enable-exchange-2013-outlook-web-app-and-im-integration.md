---
title: Aktivieren der Integration von Exchange 2013 Outlook Web App und Chatnachrichten
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Exchange 2013 Outlook Web App and IM integration
ms:assetid: 44d08cf0-b17d-46e1-a4f0-fcc2fe96a958
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204857(v=OCS.15)
ms:contentKeyID: 48184027
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b2f06999b3f7dad3a6dfd92e5e2246b95105fbd
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180339"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-exchange-2013-outlook-web-app-and-im-integration"></a>Aktivieren der Integration von Exchange 2013 Outlook Web App und Chatnachrichten

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-19_

Um die Integration von Exchange 2013 Outlook Web Access (OWA) und Instant Messaging (Chat) mit lync Server 2013 zu ermöglichen, müssen Sie den Exchange 2013 Client Zugriffsserver (CAS) der lync Server 2013 Topologie als vertrauenswürdigen Anwendungsserver hinzufügen.

<div>

## <a name="to-create-a-trusted-application-pool"></a>So erstellen Sie einen vertrauenswürdigen Anwendungspool

1.  Starten Sie die lync Server 2013 Management-Shell.

2.  Führen Sie das folgende Cmdlet aus:
    
        Get-CsSite
    
    Damit wird die "siteIP" für den "siteName" zurückgegeben, unter dem Sie den Pool erstellen. Ausführliche Informationen finden Sie unter [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite) in der Dokumentation zur lync Server 2013 Management Shell.

3.  Führen Sie das folgende Cmdlet aus:
    
        New-CsTrustedApplicationPool -Identity <E14 CAS FQDN> -ThrottleAsServer $true -TreatAsAuthenticated $true -ComputerFQDN <E14 CAS FQDN> -Site <Site> -Registrar <Pool FQDN in the site> -RequiresReplication $false
    
    Ausführliche Informationen finden Sie unter [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplicationPool) in der Dokumentation zur lync Server 2013 Management Shell.
    
    Der Exchange Server-FQDN sollte als Antragstellername oder alternativer Antragstellername des Exchange OWA-Zertifikats konfiguriert werden.
    
    Überprüfen Sie in Exchange OWA, ob der FQDN des Pools ebenfalls vertrauenswürdig ist.
    
    <div>
    

    > [!IMPORTANT]  
    > Wenn sich der CAS-Server <EM>nicht</EM> auf demselben Server befindet, auf dem Exchange 2013 Unified Messaging (um) ausgeführt wird, überspringen Sie die verbleibenden Schritte in diesem Verfahren, und führen Sie das Verfahren "Erstellen einer vertrauenswürdigen Anwendung für den Exchange 2013-CAS-Server" weiter unten in diesem Thema aus. Wenn sich der CAS-Server auf demselben Server befindet, auf dem Exchange 2013 Unified Messaging (um) ausgeführt wird, führen Sie die Schritte in diesem Verfahren aus, und führen Sie das Verfahren "Erstellen einer vertrauenswürdigen Anwendung für den Exchange 2013-CAS-Server" weiter unten in diesem Thema aus.

    
    </div>

4.  Führen Sie **Enable-CsTopology** aus.

5.  Öffnen Sie den Topologie-Generator, und laden Sie die bestehende Topologie herunter.

6.  Erweitern Sie im linken Bereich die Struktur bis hinunter zu **Vertrauenswürdige Anwendungsserver**.

7.  Erweitern Sie den Knoten **Vertrauenswürdige Anwendungsserver**.

8.  Der Exchange 2013 CAS-Server sollte jetzt als vertrauenswürdiger Anwendungsserver aufgeführt sein.

</div>

<div>

## <a name="to-create-a-trusted-application-for-the-exchange-2013-cas-server"></a>So erstellen Sie eine vertrauenswürdige Anwendung für den Exchange 2013 CAS-Server

1.  Starten Sie die lync Server 2013 Management-Shell.

2.  Wenn sich der CAS-Server *nicht* auf demselben Server befindet, auf dem Exchange 2013 Unified Messaging (um) ausgeführt wird, führen Sie das folgende Cmdlet aus:
    
        New-CsTrustedApplication -ApplicationId <AppID String> -TrustedApplicationPoolFqdn <E14 CAS FQDN> -Port <available port number>
    
    Ausführliche Informationen finden Sie im Thema [New-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplication) in der Dokumentation zur lync Server 2013 Management Shell.

3.  Führen Sie **Enable-CsTopology** aus.

4.  Erweitern Sie im linken Bereich des Topologie-Generators die Struktur bis hinunter zu **Vertrauenswürdige Anwendungsserver**.

5.  Erweitern Sie den Knoten **Vertrauenswürdige Anwendungsserver**.

6.  Der Exchange 2013 CAS-Server sollte jetzt als vertrauenswürdiger Anwendungsserver aufgeführt sein.

</div>

</div>

<span> </span>

</div>

</div>

</div>

