---
title: 'Lync Server 2013: Konfigurieren von DNS-Hosteinträgen'
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
ms.openlocfilehash: b74da23cb0139a982a30207b61032f043f795b76
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755979"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-host-records-for-lync-server-2013"></a>Konfigurieren von DNS-Hosteinträgen für Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-01_

Um dieses Verfahren erfolgreich durchführen zu können, sollten Sie mindestens als Mitglied der Gruppe Domänen-Admins oder als Mitglied der DnsAdmins-Gruppe bei dem Server oder der Domäne angemeldet sein.

<div>

## <a name="to-configure-dns-host-a-records"></a>So konfigurieren Sie DNS-Host A-Einträge

1.  Klicken Sie auf dem DNS-Server (Domain Name System) auf **Start**, klicken Sie auf **Verwaltung**, und klicken Sie dann auf **DNS**.

2.  Erweitern Sie in der Konsolenstruktur für Ihre Domäne **Forward-Lookupzonen**, und klicken Sie dann mit der rechten Maustaste auf die Domäne, in der lync Server 2013 installiert wird.

3.  Klicken Sie auf **neuer Host (A oder AAAA)**.

4.  Klicken Sie auf **Name**, geben Sie den Hostnamen für den Pool ein (der Domänen Name wird aus der Zone übernommen, in der der Datensatz definiert ist, und muss nicht als Teil des A-Eintrags eingegeben werden).

5.  Klicken Sie auf **IP-Adresse**, und geben Sie die virtuelle IP (VIP) des Load Balancer für den Front-End-Pool ein.
    
    <div>
    

    > [!IMPORTANT]  
    > In Bereitstellungen, die einen Director-Pool verwenden, sollten die Host (a)-Einträge für die einfachen URLs auf den VIP des Director Load Balancer verweisen.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie nur einen Enterprise Edition-Server oder-Director bereitstellen, der mit der Topologie ohne Load Balancer verbunden ist, oder wenn Sie einen Standard Edition-Server bereitstellen, geben Sie die IP-Adresse des Enterprise Edition-Servers, Standard Edition-Servers oder Directors ein. Ein Lastenausgleichsmodul ist erforderlich, wenn Sie mehr als einen Enterprise Edition-Server oder-Director in einem Pool bereitstellen. Load-Balancer werden nicht mit Standard Edition-Servern verwendet.

    
    </div>

6.  Klicken Sie auf **Host hinzufügen**, und klicken Sie dann auf **OK**.

7.  Wiederholen Sie die Schritte 4 und 5, um einen zusätzlichen A-Eintrag zu erstellen.

8.  Wenn Sie alle benötigten A-Einträge erstellt haben, klicken Sie auf **Fertig**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

