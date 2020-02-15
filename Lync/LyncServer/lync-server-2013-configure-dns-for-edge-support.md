---
title: 'Lync Server 2013: Konfigurieren von DNS für die Edge-Unterstützung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS for edge support
ms:assetid: 955493e6-aa29-424d-bb81-1ef87b3b15e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398756(v=OCS.15)
ms:contentKeyID: 48184894
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e22228ec089f5632f30d4eabc2e8c32d87b5e2d5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028606"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-for-edge-support-in-lync-server-2013"></a>Konfigurieren von DNS für die Edge-Unterstützung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-15_

Sie müssen DNS-Einträge (Domain Name System) für interne und externe Edgeschnittstellen konfigurieren, sowohl für Edgeserver- als auch für Reverseproxyschnittstellen. Edgeserver sind standardmäßig nicht Mitglied einer Domäne und haben keinen vollqualifizierten Domänennamen. Der Edgeserver wird nur durch den kurzen Computernamen bezeichnet und nicht durch einen vollqualifizierten Domänennamen. Der Topologie-Generator verwendet jedoch FQDNs und keine Kurznamen. Der Name der Edgeserver muss mit dem FQDN übereinstimmen, der vom Topologie-Generator verwendet wird. Hierzu definieren Sie ein DNS-Suffix, das, wenn es mit dem Computernamen kombiniert wird, den erwarteten FQDN ergibt. Nutzen Sie das unter "So fügen Sie das DNS-Suffix zum Computernamen eines Edgeservers hinzu, der nicht Mitglied einer Domäne ist" beschriebene Verfahren, um das DNS-Suffix zum Computernamen hinzuzufügen.

<div>


> [!NOTE]  
> Standardmäßig verwendet DNS einen Round Robin-Algorithmus, um die Reihenfolge der Ressourcendatensatz Daten zu drehen, die in Abfrage Antworten zurückgegeben werden, wenn mehrere Ressourceneinträge desselben Typs für einen abgefragten DNS-Domänennamen vorhanden sind. Lync Server 2013 DNS-Lastenausgleich hängt vom DNS-Roundrobin als Teil des DNS-Lastenausgleichsmechanismus ab. Stellen Sie sicher, dass die Roundrobin-Einstellung nicht deaktiviert wurde. Wenn Sie einen DNS-Server verwenden, auf dem kein Windows-Betriebssystem installiert ist, stellen Sie sicher, dass die Reihenfolge der Round Robin-Ressourceneinträge aktiviert ist.



</div>

Erstellen und überprüfen Sie einen DNS-SRV-Eintrag entsprechend dem Verfahren **So erstellen Sie einen DNS-SRV-Eintrag**. Definieren Sie die für den Zugriff externer Benutzer erforderlichen DNS-A-Einträge nach dem unter **So erstellen Sie einen DNS-A-Eintrag** beschriebenen Verfahren. Unter **So überprüfen Sie einen DNS-Eintrag** erfahren Sie in diesem Thema, wie Sie prüfen können, ob die Einträge richtig konfiguriert sind und funktionieren. Ausführliche Informationen zu jedem Datensatz, der für die Unterstützung des Zugriffs durch externe Benutzer erforderlich ist, finden Sie unter [bestimmen der DNS-Anforderungen für lync Server 2013](lync-server-2013-determine-dns-requirements.md).

<div>

## <a name="to-add-the-dns-suffix-to-the-computer-name-on-an-edge-server-that-is-not-joined-to-a-domain"></a>So fügen Sie das DNS-Suffix zum Computernamen auf einem Edgeserver hinzu, der nicht Mitglied einer Domäne ist

1.  Klicken Sie auf dem Computer auf **Start**, klicken Sie mit der rechten Maustaste auf **Arbeitsplatz**, und klicken Sie dann auf **Eigenschaften**.

2.  Klicken Sie unter **Einstellungen für Computernamen, Domäne und Arbeitsgruppe** auf **Einstellungen ändern**.

3.  Klicken Sie auf der Registerkarte **Computername** auf **Ändern**.

4.  Klicken Sie in **Ändern des Computernamens bzw. der Domäne** auf **Mehr**.

5.  Geben Sie in **DNS-Suffix und NetBIOS-Computername** unter **Primäres DNS-Suffix des Computers** den Namen Ihrer internen Domäne (z. B. corp.contoso.com) ein, und klicken Sie dann dreimal auf **OK**.

6.  Starten Sie den Computer neu.

</div>

<div>

## <a name="to-create-a-dns-srv-record"></a>So erstellen Sie einen DNS-SRV-Eintrag

1.  Klicken Sie auf dem geeigneten DNS-Server nacheinander auf **Start**, **Systemsteuerung**, **Verwaltung** und dann auf **DNS**.
    
    <div>
    

    > [!IMPORTANT]  
    > Sie müssen DNS so konfigurieren, dass es: 1) externe DNS-Einträge für externe DNS-Lookups von Remotebenutzern und Partnerverbund Partnern gibt; 2) Einträge für DNS-Lookups zur Verwendung durch die Edgeserver innerhalb des Umkreisnetzwerks (auch bekannt als DMZ, demilitarisierte Zone und überwachtes Subnetz), einschließlich einer Datensätze für die internen Server mit lync Server 2013; und 3) interne DNS-Einträge für Nachschlagevorgänge von den internen Clients und Servern mit lync Server 2013.

    
    </div>

2.  Erweitern Sie in der Konsolenstruktur für Ihre SIP-Domäne den Knoten **Forward-Lookupzonen**, und klicken Sie dann mit der rechten Maustaste auf die Domäne, in der lync Server 2013 installiert ist.

3.  Klicken Sie auf **Neue Datensätze**.

4.  Klicken Sie unter **Wählen Sie einen Ressourceneintragstyp** auf **Dienstidentifizierung (SRV)** und dann auf **Eintrag erstellen**.

5.  Stellen Sie alle erforderlichen Informationen für den DNS-SRV-Eintrag bereit.

</div>

<div>

## <a name="to-create-a-dns-a-record"></a>So erstellen Sie einen DNS-A-Eintrag

1.  Klicken Sie auf dem DNS-Server nacheinander auf **Start**, **Systemsteuerung**, **Verwaltung** und dann auf **DNS**.

2.  Erweitern Sie in der Konsolenstruktur für Ihre SIP-Domäne den Knoten **Forward-Lookupzonen**, und klicken Sie dann mit der rechten Maustaste auf die Domäne, in der lync Server 2013 installiert ist.

3.  Klicken Sie auf **Neuer Host (A)**.

4.  Stellen Sie alle erforderlichen Informationen für den DNS-SRV-Eintrag bereit.

</div>

<div>

## <a name="to-verify-a-dns-record"></a>So überprüfen Sie einen DNS-Eintrag

1.  Melden Sie sich bei einem Clientcomputer in der Domäne an.

2.  Klicken Sie auf **Start** und dann auf **Ausführen**.

3.  Führen Sie an der Eingabeaufforderung den folgenden Befehl aus:
    
        nslookup <FQDN edge interface>

4.  Stellen Sie sicher, dass eine Antwort zurückgegeben wird, in welcher der FQDN in die zugehörige IP-Adresse aufgelöst wurde.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Erstellen eines DNS-SRV-Eintrags für die Integration in gehostete Exchange um](lync-server-2013-create-a-dns-srv-record-for-integration-with-hosted-exchange-um.md)  


[Bestimmen der DNS-Anforderungen für lync Server 2013](lync-server-2013-determine-dns-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

