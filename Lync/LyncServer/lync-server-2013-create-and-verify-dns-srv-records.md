---
title: 'Lync Server 2013: Erstellen und Überprüfen von DNS-SRV-Einträgen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create and verify DNS SRV records
ms:assetid: 86888c7e-1401-458f-9a7b-08ac726deeec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398680(v=OCS.15)
ms:contentKeyID: 48184714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6f56b2c406a14a6a1781705017d13d8b823472c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008707"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-and-verify-dns-srv-records-in-lync-server-2013"></a>Erstellen und Überprüfen von DNS-SRV-Einträgen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-21_

Zum erfolgreichen Durchführen dieses Verfahrens müssen Sie mindestens als Mitglied der Gruppe "Domänen-Admins" oder als Mitglied der Gruppe "DNS-Admins" beim Server oder bei der Domäne angemeldet sein.

In diesem Thema wird beschrieben, wie Sie die Domain Name System (DNS) Datensätze konfigurieren, die Sie in lync Server 2013-Bereitstellungen erstellen müssen und die für die automatische Clientanmeldung erforderlich sind. Wenn Sie eine Front-End-Pool erstellen, erstellt Setup Active Directory Objekte und Einstellungen für den Pool, einschließlich des vollqualifizierten Domänennamens (FQDN) des Pools. Für ein Standard Edition-Server werden ähnliche Objekte und Einstellungen erstellt. Damit Clients eine Verbindung mit dem Pool oder Standard Edition-Server herstellen können, muss der FQDN des Pools oder Standard Edition-Server in DNS registriert sein. Sie müssen DNS-SRV-Einträge in Ihrem internen DNS für jede SIP-Domäne erstellen. Für diese Vorgehensweise wird davon ausgegangen, dass das interne DNS Zonen für die SIP-Benutzerdomänen aufweist.

<div>

## <a name="to-configure-a-dns-srv-record"></a>So konfigurieren Sie einen DNS-SRV-Eintrag

1.  Klicken Sie auf dem DNS-Server auf **Start**, klicken Sie auf **Verwaltung** und anschließend auf **DNS**.

2.  Erweitern Sie in der Konsolenstruktur für Ihre SIP-Domäne den Knoten **Forward-Lookupzonen**, und klicken Sie dann mit der rechten Maustaste auf die SIP-Domäne, in der lync Server 2013 installiert wird.

3.  Klicken Sie auf **Neue Datensätze**.

4.  Klicken Sie unter **Ressourceneintragstyp auswählen**auf **Dienststandort (SRV)**, und klicken Sie dann auf **Datensatz erstellen**.

5.  Klicken Sie auf **Dienst**, und ** \_** geben Sie sipinternaltls.

6.  Klicken Sie auf **Protokoll**, und ** \_** geben Sie dann TCP ein.

7.  Klicken Sie auf **Portnummer**, und geben Sie **5061** ein.

8.  Klicken Sie auf Host, der **diesen Dienst anbietet**, und geben Sie dann den FQDN des Pools oder Standard Edition-Server ein.

9.  Klicken Sie auf **OK** und dann auf **Fertig**.

</div>

<div>

## <a name="to-verify-the-creation-of-a-dns-srv-record"></a>So überprüfen Sie die Erstellung eines DNS-SRV-Eintrags

1.  Melden Sie sich bei einem Clientcomputer in der Domäne mit einem Konto an, das Mitglied der Gruppe der authentifizierten Benutzer ist oder über entsprechende Berechtigungen verfügt.

2.  Klicken Sie auf **Start** und dann auf **Ausführen**.

3.  Geben Sie im Feld **Öffnen** die Zeichenfolge **cmd** ein, und klicken Sie dann auf **OK**.

4.  Geben Sie an der Eingabeaufforderung **nslookup**ein, und drücken Sie dann die EINGABETASTE.

5.  Geben Sie Typ **festlegen = SRV**ein, und drücken Sie dann die EINGABETASTE.

6.  Geben ** \_Sie sipinternaltls\_ ein. TCP.contoso.com**, und drücken Sie dann die EINGABETASTE. Die für den TLS-Eintrag (Transport Layer Security) angezeigte Ausgabe lautet wie folgt:
    
    Server: \<DNS-\>Server. contoso.com
    
    Adresse: \<IP-Adresse des DNS-Servers\>
    
    Nicht autorisierende Antwort:
    
    \_sipinternaltls. \_Speicherort des TCP.contoso.com-SRV-Diensts:
    
    Priorität = 0
    
    Gewichtung = 0
    
    Port = 5061
    
    SVR Hostname = Poolname.contoso.com (oder Standard Edition-Server eines Datensatzes)
    
    Poolname.contoso.com Internet Address = \<virtuelle IP-Adresse des Lastenausgleichs\> oder \<die IP-Adresse eines einzelnen Enterprise Edition-Server für Pools mit nur einem\> Enterprise Edition-Server \<oder einer IP-Adresse des Standard Edition-Server\>

7.  Geben Sie nach Abschluss der Eingabeaufforderung **Exit**ein, und drücken Sie dann die EINGABETASTE.

</div>

<div>

## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a>So überprüfen Sie, ob der FQDN des Front-End-Pools oder Standard Edition-Servers aufgelöst werden kann

1.  Melden Sie sich an einem Clientcomputer in der Domäne an.

2.  Klicken Sie auf **Start** und dann auf **Ausführen**.

3.  Geben Sie im Feld **Öffnen** die Zeichenfolge **cmd** ein, und klicken Sie dann auf **OK**.

4.  Geben Sie an der Eingabeaufforderung **nslookup** \<-FQDN des Front-End-Pool\> oder \<FQDN des Standard Edition-Server\>ein, und drücken Sie dann die EINGABETASTE.

5.  Stellen Sie sicher, dass eine Antwort zurückgegeben wird, in welcher der FQDN in die zugehörige IP-Adresse aufgelöst wurde.

</div>

</div>

<span> </span>

</div>

</div>

</div>

