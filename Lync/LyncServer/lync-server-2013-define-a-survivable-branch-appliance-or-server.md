---
title: 'Lync Server 2013: Definieren einer Survivable Branch Appliance oder eines Survivable Branch Servers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define a Survivable Branch Appliance or Server
ms:assetid: 1f49cfbe-30b3-4600-af15-47cb2f58d18a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398280(v=OCS.15)
ms:contentKeyID: 48183583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dadaa26f6a951995906ed29ffd0615da16066928
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832719"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a>Definieren einer Survivable Branch Appliance oder eines Survivable Branch Servers in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-07_

Führen Sie dieses Verfahren am zentralen Standort aus, wenn Sie die Survivable Branch-Appliance oder den Server nicht definiert haben, als Sie Sie zu Ihrer Topologie hinzugefügt haben.

<div>

## <a name="to-define-a-survivable-branch-appliance-or-survivable-branch-server"></a>So definieren Sie eine Survivable Branch-Appliance oder einen Überlebenden Branch-Server

1.  Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topology Builder**.

2.  Erweitern Sie in der Konsolenstruktur die zentrale Website, erweitern Sie **Verzweigungs Standorte**, und erweitern Sie dann den Namen der Zweigstelle, auf der Sie die Survivable Branch-Appliance oder den Survivable Branch-Server bereitstellen möchten.

3.  Klicken Sie mit der rechten Maustaste auf **Survival Branch Appliances**, und klicken Sie dann auf **neue Survivable Branch Appliance**.
    
    <div>
    

    > [!IMPORTANT]  
    > Überlebensfähige <STRONG>Branch</STRONG> -Appliances definieren Sie Survival-Branch-Server und Survivable Branch-Appliances.

    
    </div>

4.  Klicken Sie im Dialogfeld **Survivable Branch-Appliance definieren** auf **FQDN**, geben Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) der Survivable Branch Appliance oder des Survivable Branch-Servers ein, den Sie an dieser Zweigstelle bereitstellen, und klicken Sie dann auf **weiter**.
    
    <div>
    

    > [!IMPORTANT]  
    > Wenn Sie eine Survivable-Branch-Appliance definieren, muss der Name, den Sie in <STRONG>FQDN</STRONG> eingeben, dem Überlebenden Branch Appliance-FQDN entsprechen, den Sie dem <STRONG>servicePrincipalName</STRONG> -Attribut zugewiesen haben. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md">Hinzufügen einer Survivable Branch-Appliance zu Active Directory in lync Server 2013</A>.

    
    </div>

5.  Klicken Sie auf **Front-End-Pool**, klicken Sie auf den Front-End-Server (User Services Pool) an der zentralen Website, mit der die überlebensfähige Branch-Appliance oder der Survivable Branch-Server eine Verbindung herstellen soll, und klicken Sie dann auf **weiter**

6.  Klicken **** Sie auf Edgeserver, klicken Sie auf den Edge-Pool, der von dieser Survivable Branch Appliance oder einem Überlebenden Verzweigungs Server hergestellt wird, um die PSTN-Konnektivität für Remotebenutzer der Zweigstelle bereitzustellen, und klicken Sie dann auf **weiter**.

7.  Klicken Sie auf **Gateway-FQDN oder IP-Adresse**, und geben Sie dann den FQDN oder die IP-Adresse des Gateway-Peers ein, dem die Survivable Branch-Appliance oder der Survivable Branch-Server zugeordnet ist, um eingehende oder ausgehende PSTN-Anrufe weiterzuleiten.
    
    <div>
    

    > [!IMPORTANT]  
    > Wenn Sie eine Survivable Branch-Appliance definieren, ist dies das Gateway, auf das der Vermittlungs Server innerhalb der Survivable Branch-Appliance für PSTN-Konnektivität zugreifen kann.

    
    </div>

8.  Klicken Sie auf **Überwachungs Port für IP/PSTN-Gateway**, und übernehmen Sie den Standardport.

9.  Klicken Sie im **SIP-Transportprotokoll**auf das Transport Protokoll, das von der Survivable Branch-Appliance oder dem Survivable Branch-Server verwendet wird, und klicken Sie dann auf **Fertig stellen**.
    
    <div>
    

    > [!NOTE]  
    > Aus Sicherheitsgründen empfehlen wir dringend, TLS (Transport Layer Security) zu verwenden. Wenn Sie eine Survivable Branch-Appliance definieren, lesen Sie in der Dokumentation Ihres Survivable Branch Appliance-Herstellers nach, ob Ihre Survivable Branch-Appliance das TLS-Protokoll unterstützt.

    
    </div>

10. Klicken Sie in der Konsolenstruktur mit der rechten Maustaste auf die neue Survivable Branch-Appliance oder den neuen Server, klicken Sie auf **Topologie**, und klicken Sie dann auf **veröffentlichen**.

**Nächster Schritt**: [Bereitstelleneiner überlebensfähigen Branch-Appliance oder eines Servers mit lync Server 2013-Branch Site-Aufgabe](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

