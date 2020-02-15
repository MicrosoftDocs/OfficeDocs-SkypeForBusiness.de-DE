---
title: 'Lync Server 2013: Konfigurieren von DNS-Host Einträgen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS Host records
ms:assetid: 78a1afcf-41c8-4da5-8740-c6570c19078c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398593(v=OCS.15)
ms:contentKeyID: 48184577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54ae1e2502ec1618f007ba76255ae6d01ebb66f5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028586"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-host-records-for-lync-server-2013"></a>Konfigurieren von DNS-Host Einträgen für lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-01_

Zum erfolgreichen Durchführen dieses Verfahrens müssen Sie mindestens als Mitglied der Gruppe "RTCUniversalServerAdmins" angemeldet sein.

<div>

## <a name="to-configure-dns-host-a-records"></a>So konfigurieren Sie DNS-Hosteinträge (A)

1.  Klicken Sie auf dem DNS-Server (Domain Name System) auf **Start**, klicken Sie auf **Verwaltung** und anschließend auf **DNS**.

2.  Erweitern Sie in der Konsolenstruktur für Ihre Domäne den Knoten **Forward-Lookupzonen**, und klicken Sie dann mit der rechten Maustaste auf die Domäne, in der lync Server 2013 installiert werden soll.

3.  Klicken Sie auf **Neuer Host (A oder AAAA)**.

4.  Klicken Sie auf **Name**, und geben Sie den Hostnamen für den Pool ein (der Domänenname wird von der Zone abgeleitet, in welcher der Eintrag definiert ist, und muss nicht als Teil des A-Eintrags eingegeben werden).

5.  Klicken Sie auf **IP-Adresse**, geben Sie die virtuelle IP (VIP) des Lastenausgleichs für die Front-End-Pool ein.
    
    <div>
    

    > [!IMPORTANT]  
    > In Bereitstellungen, die einen Director-Pool verwenden, sollten die Hosteinträge (A) für die einfachen URLs auf die VIP des Director-Lastenausgleichssystems zeigen.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie nur einen Enterprise Edition-Server oder Director bereitstellen, der ohne ein Lastenausgleichssystem mit der Topologie verbunden ist, oder wenn Sie einen Standard Edition-Server bereitstellen, geben Sie die IP-Adresse des Enterprise Edition-Servers, Standard Edition-Servers oder Directors ein. Ein Lastenausgleichssystem ist erforderlich, wenn sich mehrere Enterprise Edition-Server oder Directors in einem Pool befinden. Bei Standard Edition-Servern werden keine Lastenausgleichssysteme verwendet.

    
    </div>

6.  Klicken Sie auf **Host hinzufügen** und dann auf **OK**.

7.  Wenn Sie einen zusätzlichen A-Eintrag erstellen möchten, wiederholen Sie die Schritte 4 und 5.

8.  Wenn Sie alle erforderlichen A-Einträge erstellt haben, klicken Sie auf **Fertig**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

