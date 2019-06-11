---
title: 'Lync Server 2013: Definieren eines PSTN-Gateways für eine Zweigstelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define a PSTN gateway for a branch site
ms:assetid: 87be2fe2-1d56-4062-b430-439d4536414c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398689(v=OCS.15)
ms:contentKeyID: 48184724
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c253f82001fef4dd52e19dccb11e7ac77bb12417
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832717"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-pstn-gateway-for-a-branch-site-in-lync-server-2013"></a>Definieren eines PSTN-Gateways für eine Zweigstelle in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

Führen Sie dieses Verfahren an der zentralen Website aus, die mindestens einen Front-End-Pool oder Standard Edition-Server enthält.

<div>


> [!IMPORTANT]  
> Bevor Sie das Verfahren ausführen, müssen die folgenden Bedingungen erfüllt sein: 
> <UL>
> <LI>
> <P>Die lync Server&nbsp;2013-Kommunikationssoftware muss am zentralen Standort eingerichtet werden.</P>
> <LI>
> <P>Der Vermittlungs Server muss am zentralen Standort bereitgestellt werden.</P></LI></UL>



</div>

<div>

## <a name="to-define-a-pstn-gateway"></a>So definieren Sie ein PSTN-Gateway

1.  Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server**, und klicken Sie dann auf **lync Server Topology Builder**.

2.  Erweitern Sie in der Konsolenstruktur den zentralen Standort, erweitern Sie **Zweigstellenstandorte**, erweitern Sie Name der Verzweigungs Website, für die Sie ein PSTN-Gateway (Public Switched Telephone Network) definieren möchten, und erweitern Sie dann **freigegebene Komponenten**.

3.  Klicken Sie mit der rechten Maustaste auf **PSTN-Gateways**, und klicken Sie dann auf **neues IP/PSTN-Gateway**.

4.  Klicken Sie im Dialogfeld **neues IP/PSTN-Gateway definieren** auf **Gateway-FQDN oder IP-Adresse**, und geben Sie dann den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) oder die IP-Adresse des Gateways ein, das Sie auf der Zweigstelle bereitstellen.

5.  Klicken Sie auf **Überwachungs Port für IP/PSTN-Gateway**, und übernehmen Sie dann die Standardwerte.

6.  Klicken Sie in der Liste **SIP-Transportprotokoll** auf das Transportprotokoll, das vom Gateway verwendet wird, und klicken Sie dann auf **OK**.
    
    <div>
    

    > [!NOTE]  
    > Aus Sicherheitsgründen empfehlen wir dringend, ein PSTN-Gateway zu verwenden, das TLS (Transport Layer Security) unterstützt.

    
    </div>

<div>


> [!TIP]  
> Verwenden Sie das Cmdlet <STRONG>Satz-CsPstnGateway</STRONG> , um die Eigenschaften eines PSTN-Gateways zu ändern. Ausführliche Informationen finden Sie unter " <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsPstnGateway">Satz-CsPstnGateway</A>" in der Hilfe zur lync Server-Verwaltungsshell.



</div>

**Nächster Schritt** für die Ausfallsicherheit von Zweigstellen: [Konfigurieren von Benutzern für die Stabilität des Zweigstellen Standorts in lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Bereitstellungsoptionen für PSTN-Gateways in Lync Server 2013](lync-server-2013-pstn-gateway-deployment-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

