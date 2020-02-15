---
title: 'Lync Server 2013: Definieren eines Survivable Branch Appliance oder Servers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a Survivable Branch Appliance or Server
ms:assetid: 1f49cfbe-30b3-4600-af15-47cb2f58d18a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398280(v=OCS.15)
ms:contentKeyID: 48183583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9006aa3a54a2aa38cecb4b49ef56094eb24494fc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043557"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a>Definieren einer Survivable Branch Appliance oder eines Servers in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-07_

Führen Sie das vorliegende Verfahren am zentralen Standort aus, wenn Sie die Survivable Branch Appliance oder den Survivable Branch Server nicht beim Hinzufügen zu Ihrer Topologie definiert haben.

<div>

## <a name="to-define-a-survivable-branch-appliance-or-survivable-branch-server"></a>So definieren Sie eine Survivable Branch Appliance oder Survivable Branch Server

1.  Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topologie-Generator**.

2.  Erweitern Sie in der Konsolenstruktur den zentralen Standort, erweitern Sie **Zweigstellenstandorte**, und erweitern Sie dann den Namen des Zweigstellen Standorts, an dem die Survivable Branch Appliance oder Survivable Branch Server bereitgestellt werden soll.

3.  Klicken Sie mit der rechten Maustaste auf **Survivable Branch Appliances**, und klicken Sie dann auf **neue Survivable Branch Appliance**.
    
    <div>
    

    > [!IMPORTANT]  
    > <STRONG>Survivable Branch Appliances</STRONG> ist der Ort, an dem Sie Survivable Branch-Server und Survivable Branch Appliances definieren.

    
    </div>

4.  Klicken Sie im Dialogfeld **Survivable Branch Appliance definieren** auf **FQDN**, geben Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) der Survivable Branch Appliance oder Survivable Branch Server an, die Sie an dieser Zweigstelle bereitstellen möchten, und klicken Sie dann auf **weiter**.
    
    <div>
    

    > [!IMPORTANT]  
    > Wenn Sie eine Survivable Branch Appliance definieren, muss der Name, den Sie in <STRONG>FQDN</STRONG> eingeben, mit dem Survivable Branch Appliance FQDN identisch sein, den Sie dem <STRONG>servicePrincipalName</STRONG> -Attribut zugewiesen haben. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md">Add a Survivable Branch Appliance to Active Directory in lync Server 2013</A>.

    
    </div>

5.  Klicken Sie auf **Front-End-Pool**, klicken Sie auf den Front-End-Server (User Services Pool) am zentralen Standort, zu dem diese Survivable Branch Appliance oder Survivable Branch Server eine Verbindung herstellen, und klicken Sie dann auf **weiter**.

6.  Klicken Sie auf **Edgeserver**, klicken Sie auf das Edgepool, mit dem diese Survivable Branch Appliance oder Survivable Branch Server eine Verbindung herstellen, um die PSTN-Konnektivität für Remotebenutzer des Zweigstellen Standorts bereitzustellen, und klicken Sie dann auf **weiter**.

7.  Klicken Sie auf **Gateway-FQDN oder IP-Adresse**, und geben Sie dann den FQDN oder die IP-Adresse des Gateway-Peers ein, dem der Survivable Branch Appliance oder der Survivable Branch Server für das Weiterleiten von eingehenden oder ausgehenden PSTN-anrufen zugeordnet ist.
    
    <div>
    

    > [!IMPORTANT]  
    > Beim Definieren einer Survivable Branch Appliance ist dies das Gateway, mit dem sich der Vermittlungsserver in der Survivable Branch Appliance für PSTN-Verbindungen verbindet.

    
    </div>

8.  Klicken Sie auf **Überwachungsport für das IP/PSTN-Gateway**, und akzeptieren Sie den Standardport.

9.  Klicken Sie im **SIP-Transport Protokoll**auf das Transportprotokoll, das von Survivable Branch Appliance oder Survivable Branch Server verwendet wird, und klicken Sie dann auf **Fertig stellen**.
    
    <div>
    

    > [!NOTE]  
    > Aus Sicherheitsgründen wird der Einsatz von TLS (Transport Layer Security) ausdrücklich empfohlen. Konsultieren Sie beim Definieren einer Survivable Branch Appliance die Dokumentation des Herstellers, um sicherzustellen, dass die Survivable Branch Appliance das TLS-Protokoll unterstützt.

    
    </div>

10. Klicken Sie in der Konsolenstruktur mit der rechten Maustaste auf die neue Survivable Branch Appliance oder den Survivable Branch Server, klicken Sie auf **Topologie** und anschließend auf **Veröffentlichen**.

**Nächster Schritt**: [Bereitstelleneiner Survivable Branch Appliance oder eines Servers mit lync Server 2013-Branch-Standort Aufgabe](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

