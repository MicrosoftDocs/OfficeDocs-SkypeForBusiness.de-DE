---
title: Erstellen eines DNS-SRV-Eintrags für die Integration in gehostete Exchange um
description: Erstellen eines DNS-SRV-Eintrags für die Integration in gehostete Exchange um.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a DNS SRV record for integration with hosted Exchange UM
ms:assetid: 8ea590ae-58ea-4ca5-9853-e0708b3ea760
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh500728(v=OCS.15)
ms:contentKeyID: 48184770
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 694a595977abe33bebbb5fbcf2a508c9bb4e35a4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542141"
---
# <a name="create-a-dns-srv-record-for-integration-with-hosted-exchange-um"></a>Erstellen eines DNS-SRV-Eintrags für die Integration in gehostete Exchange um

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-20_

In diesem Thema wird beschrieben, wie Sie den Domain Name System (DNS) SRV-Eintrag konfigurieren, der erforderlich ist, damit ein lync Server 2013 Edgeserver an einen gehosteten Exchange-Dienst wie Microsoft Exchange Online weitergeleitet wird.

<div>

## <a name="to-create-an-external-dns-srv-record-for-the-hosted-exchange-service"></a>So erstellen Sie einen externen DNS-SRV-Eintrag für den gehosteten Exchange-Dienst

1.  Melden Sie sich am externen DNS-Server als Mitglied der Gruppe "DnsAdmins" an.

2.  Klicken Sie auf **Start**, auf **Verwaltung** und anschließend auf **DNS**.

3.  Erweitern Sie in der Konsolenstruktur für Ihre SIP-Domäne den Knoten **Forward-Lookupzonen**, und wählen Sie die SIP-Domäne aus, in der lync Server 2013 installiert werden soll.
    
    <div>
    

    > [!IMPORTANT]
    > Sie müssen den DNS-SRV-Eintrag in der SIP-Domäne erstellen, in der Lync Server installiert ist oder wird. Wenn Sie den SRV-Eintrag erstellen, muss für das Feld "Host, der diesen Dienst anbietet" der externe FQDN des Edgepools verwendet werden. Wenn beispielsweise der externe FQDN des Edgepools "edge01.contoso.net" ist, geben Sie diesen Wert in das Feld ein. Der FQDN muss sich auch in derselben Domäne wie der DNS-A-Eintrag (Hosts) befinden.

    
    </div>

4.  Klicken Sie mit der rechten Maustaste auf die ausgewählte Domäne, und klicken Sie dann auf **Andere neue Einträge**.

5.  Klicken Sie In **Ressourceneintragstyp** auf **Dienstidentifizierung (SRV)**, und klicken Sie dann auf **Eintrag erstellen**.

6.  Klicken Sie unter **neuer Ressourceneintrag**auf **Dienst**, und geben Sie ** \_ sipfederationtls**.

7.  Klicken Sie auf **Protokoll**, und geben Sie dann ** \_ TCP**ein.

8.  Klicken Sie auf **Portnummer**, und geben Sie **5061** ein.

9.  Klicken Sie auf Host, der **diesen Dienst anbietet**, und geben Sie dann den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des lync Server 2013 Edgepool ein, der Zugriff auf das lync Server 2013 System für vertrauenswürdige externe Clients bereitstellt.
    
    <div>
    

    > [!NOTE]
    > Die Domäne muss auch als autorisierende akzeptierte Domäne in den Exchange Online-Einstellungen eingerichtet werden. Ausführliche Informationen finden Sie unter CREATE accepted domains at <A href="https://go.microsoft.com/fwlink/p/?linkid=229762">https://go.microsoft.com/fwlink/p/?linkId=229762</A> .

    
    </div>

10. Klicken Sie auf **OK** und dann auf **Fertig**.

</div>

<div>

## <a name="to-verify-that-the-dns-srv-record-was-created-successfully"></a>So stellen Sie sicher, dass der DNS-SRV-Eintrag erfolgreich erstellt wurde

1.  Melden Sie sich an einem Clientcomputer in der Domäne an.

2.  Klicken Sie auf **Start** und dann auf **Ausführen**.

3.  Führen Sie an der Eingabeaufforderung den folgenden Befehl aus:
    
        nslookup <FQDN Lync Edge Pool>

4.  Stellen Sie sicher, dass eine Antwort zurückgegeben wird, in welcher der FQDN in die zugehörige IP-Adresse aufgelöst wurde.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Erstellen von DNS-Einträgen für Reverse-Proxy Server in lync Server 2013](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

