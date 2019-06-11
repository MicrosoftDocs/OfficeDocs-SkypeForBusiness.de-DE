---
title: 'Lync Server 2013: Erstellen und Überprüfen von DNS-SRV-Einträgen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create and verify DNS SRV records
ms:assetid: 86888c7e-1401-458f-9a7b-08ac726deeec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398680(v=OCS.15)
ms:contentKeyID: 48184714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a539b58abbad323aaf7c7343b40eabb49d04d91
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832855"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-and-verify-dns-srv-records-in-lync-server-2013"></a>Erstellen und Überprüfen von DNS-SRV-Einträgen in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

Um dieses Verfahren erfolgreich durchführen zu können, sollten Sie am Server oder in der Domäne minimal als Mitglied der Gruppe der Domänenadministratoren oder als Mitglied der DnsAdmins-Gruppe angemeldet sein.

In diesem Thema wird beschrieben, wie Sie die DNS-Einträge (Domain Name System) konfigurieren, die Sie in lync Server 2013-Bereitstellungen erstellen müssen, und die für die automatische Clientanmeldung erforderlich sind. Wenn Sie einen Front-End-Pool erstellen, erstellt Setup Active Directory-Objekte und-Einstellungen für den Pool, einschließlich des vollqualifizierten Domänennamens (Fully Qualified Domain Name, FQDN) des Pools. Ähnliche Objekte und Einstellungen werden für einen Standard Edition-Server erstellt. Damit Clients eine Verbindung mit dem Pool oder dem Standard Edition-Server herstellen können, muss der FQDN des Pools oder Standard Edition-Servers in DNS registriert sein. Sie müssen DNS-SRV-Einträge in Ihrem internen DNS für jede SIP-Domäne erstellen. Bei diesem Verfahren wird davon ausgegangen, dass Ihr interner DNS Zonen für Ihre SIP-Benutzerdomänen aufweist.

<div>

## <a name="to-configure-a-dns-srv-record"></a>So konfigurieren Sie einen DNS-SRV-Eintrag

1.  Klicken Sie auf dem DNS-Server auf **Start**, klicken Sie auf **Verwaltung**, und klicken Sie dann auf **DNS**.

2.  Erweitern Sie in der Konsolenstruktur ihrer SIP-Domäne **Forward-Lookupzonen**, und klicken Sie dann mit der rechten Maustaste auf die SIP-Domäne, in der lync Server 2013 installiert wird.

3.  Klicken Sie auf **andere neue Datensätze**.

4.  Klicken Sie unter **Wählen Sie einen Ressourceneintragstyp** auf **Dienstidentifizierung (SRV)** und dann auf **Eintrag erstellen**.

5.  Klicken Sie auf **Dienst**, und ** \_** geben Sie sipinternaltls ein.

6.  Klicken Sie auf **Protokoll**, und ** \_** geben Sie dann TCP ein.

7.  Klicken Sie auf **Portnummer** und geben Sie **5061** ein.

8.  Klicken Sie auf **Host, der diesen Dienst anbietet** und geben Sie den FQDN des Pools bzw. des Standard Edition-Servers ein.

9.  Klicken Sie auf **OK** und dann auf **Fertig**.

</div>

<div>

## <a name="to-verify-the-creation-of-a-dns-srv-record"></a>So überprüfen Sie die Erstellung eines DNS-SRV-Eintrags

1.  Melden Sie sich mit einem Konto, das Mitglied der Gruppe der authentifizierten Benutzer ist oder über gleichwertige Berechtigungen verfügt, an einem Clientcomputer in der Domäne an.

2.  Klicken Sie auf  **Start ** und dann auf  **Ausführen**.

3.  Geben Sie im Feld **Öffnen** den **Befehl cmd**ein, und klicken Sie dann auf **OK**.

4.  Geben Sie an der Eingabeaufforderung **nslookup**ein, und drücken Sie dann die EINGABETASTE.

5.  Geben Sie Type **= SRV**ein, und drücken Sie dann die EINGABETASTE.

6.  Geben ** \_Sie sipinternaltls\_ ein. TCP.contoso.com**, und drücken Sie dann die EINGABETASTE. Die für den TLS-Eintrag (Transport Layer Security) angezeigte Ausgabe lautet wie folgt:
    
    Server: \<DNS-\>Server. contoso.com
    
    Adresse: \<IP-Adresse des DNS-Servers\>
    
    Nicht autorisierende Antwort:
    
    \_sipinternaltls. \_TCP.contoso.com SRV-Dienststandort:
    
    Priorität = 0
    
    Gewichtung = 0
    
    Port = 5061
    
    SVR Hostname = Poolname.contoso.com (oder Standard Edition Server A Record)
    
    Poolname.contoso.com Internet Address = \<virtuelle IP-Adresse des Load Balancer\> oder \<IP-Adresse eines einzelnen Enterprise Edition-Servers für Pools mit nur einem\> Enter \<Prise Edition-Server oder einer IP-Adresse des Standards Edition-Server\>

7.  Wenn Sie die Eingabeaufforderung beendet haben, geben Sie **Exit**ein, und drücken Sie dann die EINGABETASTE.

</div>

<div>

## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a>So überprüfen Sie, ob der FQDN des Front-End-Pools oder des Standard Edition-Servers aufgelöst werden kann

1.  Melden Sie sich bei einem Clientcomputer in der Domäne an.

2.  Klicken Sie auf  **Start ** und dann auf  **Ausführen**.

3.  Geben Sie im Feld **Öffnen** den **Befehl cmd**ein, und klicken Sie dann auf **OK**.

4.  Geben Sie an der Eingabeaufforderung **nslookup** \<-FQDN des Front-End\> - \<Pools oder den FQDN des Standard\>Edition-Servers ein, und drücken Sie dann die EINGABETASTE.

5.  Überprüfen Sie, ob Sie eine Antwort erhalten, die in die entsprechende IP-Adresse für den FQDN aufgelöst wird.

</div>

</div>

<span> </span>

</div>

</div>

</div>

