---
title: 'Lync Server 2013: Konfigurieren von DNS für die Edgeunterstützung'
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
ms.openlocfilehash: c905c8fff7a67b26a7df8d2c741ce0a16fddce6c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757899"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-for-edge-support-in-lync-server-2013"></a>Konfigurieren von DNS für die Edgeunterstützung in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-15_

Sie müssen DNS-Einträge (Domain Name System) für interne und externe Edge-Schnittstellen konfigurieren, einschließlich der Edge-Server-und Reverse-Proxy-Schnittstellen. Edgeserver sind standardmäßig nicht mit einer Domäne verbunden und verfügen nicht über einen vollqualifizierten Domänennamen (vollständig qualifizierter Domänenname). Der Edgeserver wird nur mit dem kurzen Namen (Computer) und nicht mit einem vollqualifizierten Domänennamen bezeichnet. Der Topologie-Generator verwendet jedoch FQDNs und keine kurzen Namen. Der Name des Edgeserver muss dem vom Topologie-Generator verwendeten FQDN entsprechen. Zu diesem Zweck definieren Sie ein DNS-Suffix, das in Kombination mit dem Computernamen zum erwarteten FQDN führt. Gehen Sie wie folgt vor, um das DNS-Suffix zu dem Computernamen auf und dem Edgeserver hinzuzufügen, die nicht zu einer Domäne hinzugefügt wurden.

<div>


> [!NOTE]  
> Standardmäßig verwendet DNS einen Round-Robin-Algorithmus, um die Reihenfolge der in Abfrage Antworten zurückgegebenen Ressourceneintragsdaten zu drehen, wenn mehrere Ressourceneinträge desselben Typs für einen abgefragten DNS-Domänennamen vorhanden sind. Der lync Server 2013-DNS-Lastenausgleich hängt vom DNS-Roundrobin als Teil des DNS-Lastenausgleichsmechanismus ab. Überprüfen Sie, ob die Roundrobin-Einstellung deaktiviert wurde. Wenn Sie einen DNS-Server verwenden, auf dem kein Windows-Betriebssystem ausgeführt wird, stellen Sie sicher, dass die Round-Robin-Ressourceneintrags Reihenfolge aktiviert ist.



</div>

Führen Sie die folgenden Verfahren in "**So erstellen Sie einen DNS-SRV-Eintrag**" aus, um jeden DNS-SRV-Eintrag zu erstellen und zu überprüfen. Verwenden Sie das Verfahren unter "**So erstellen Sie einen DNS-Eintrag**", um die DNS-a-Einträge zu definieren, die für den Zugriff durch externe Benutzer erforderlich sind. Wenn Sie sicherstellen möchten, dass die Datensätze konfiguriert sind und ordnungsgemäß funktionieren, lesen Sie "**So überprüfen Sie einen DNS-Eintrag**" in diesem Thema. Details zu den einzelnen Datensätzen, die für die Unterstützung des Zugriffs externer Benutzer erforderlich sind, finden Sie unter [Ermitteln der DNS-Anforderungen für lync Server 2013](lync-server-2013-determine-dns-requirements.md).

<div>

## <a name="to-add-the-dns-suffix-to-the-computer-name-on-an-edge-server-that-is-not-joined-to-a-domain"></a>So fügen Sie dem Computernamen auf einem Edgeserver, der nicht zu einer Domäne gehört, das DNS-Suffix hinzu

1.  Klicken Sie auf dem Computer auf **Start**, klicken Sie mit der rechten Maustaste auf **Computer**, und klicken Sie dann auf **Eigenschaften**.

2.  Klicken Sie unter **Computer Name, Domäne und Arbeitsgruppeneinstellungen**auf **Einstellungen ändern**.

3.  Klicken Sie auf der Registerkarte **Computer Name** auf **ändern**.

4.  Klicken Sie unter **Computer Name/domänenänderungen**auf **mehr**.

5.  Geben Sie unter **DNS-Suffix und NetBIOS-Computername**in **Primäres DNS-Suffix dieses Computers**den Namen Ihrer internen Domäne (beispielsweise Corp.contoso.com) ein, und klicken Sie dann dreimal auf **OK** .

6.  Starten Sie den Computer neu.

</div>

<div>

## <a name="to-create-a-dns-srv-record"></a>So erstellen Sie einen DNS-SRV-Eintrag

1.  Klicken Sie auf dem entsprechenden DNS-Server auf **Start**, klicken Sie auf **System**Steuerung, klicken Sie auf **Verwaltung**, und klicken Sie dann auf **DNS**.
    
    <div>
    

    > [!IMPORTANT]  
    > Sie müssen DNS so konfigurieren, dass: 1) externe DNS-Einträge für externe DNS-Lookups von Remotebenutzern und Verbundpartnern vorhanden sind. 2) Einträge für DNS-Lookups zur Verwendung durch die Edgeserver im Umkreisnetzwerk (auch bekannt als DMZ, demilitarisierte Zone und geschirmtes Subnetz), einschließlich Datensätzen für die internen Server mit lync Server 2013; und 3) interne DNS-Einträge für Lookups von den internen Clients und Servern, auf denen lync Server 2013 ausgeführt wird.

    
    </div>

2.  Erweitern Sie in der Konsolenstruktur für Ihre SIP-Domäne **Forward-Lookupzonen**, und klicken Sie dann mit der rechten Maustaste auf die Domäne, in der lync Server 2013 installiert ist.

3.  Klicken Sie auf **andere neue Datensätze**.

4.  Geben Sie unter **Ressourceneintragstyp auswählen den**Namen **Dienststandort (SRV)** ein, und klicken Sie dann auf **Datensatz erstellen**.

5.  Geben Sie alle erforderlichen Informationen für den DNS-SRV-Eintrag an.

</div>

<div>

## <a name="to-create-a-dns-a-record"></a>So erstellen Sie einen DNS-a-Eintrag

1.  Klicken Sie auf dem DNS-Server auf **Start**, klicken Sie auf **System**Steuerung, klicken Sie auf **Verwaltung**, und klicken Sie dann auf **DNS**.

2.  Erweitern Sie in der Konsolenstruktur ihrer SIP-Domäne **Forward-Lookupzonen**, und klicken Sie dann mit der rechten Maustaste auf die Domäne, in der lync Server 2013 installiert ist.

3.  Klicken Sie auf **neuer Host (a)**.

4.  Geben Sie alle erforderlichen Informationen für den DNS-SRV-Eintrag an.

</div>

<div>

## <a name="to-verify-a-dns-record"></a>So überprüfen Sie einen DNS-Eintrag

1.  Melden Sie sich bei einem Clientcomputer in der Domäne an.

2.  Klicken Sie auf  **Start ** und dann auf  **Ausführen**.

3.  Führen Sie an der Eingabeaufforderung den folgenden Befehl aus:
    
        nslookup <FQDN edge interface>

4.  Überprüfen Sie, ob Sie eine Antwort erhalten, die in die entsprechende IP-Adresse für den FQDN aufgelöst wird.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Erstellen eines DNS-SRV-Eintrags für die Integration in gehostete Exchange UM-Dienste](lync-server-2013-create-a-dns-srv-record-for-integration-with-hosted-exchange-um.md)  


[Ermitteln von DNS-Anforderungen für Lync Server 2013](lync-server-2013-determine-dns-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

