---
title: 'Lync Server 2013: Definieren eines PSTN-Gateways für einen Zweigstellenstandort'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a PSTN gateway for a branch site
ms:assetid: 87be2fe2-1d56-4062-b430-439d4536414c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398689(v=OCS.15)
ms:contentKeyID: 48184724
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ae74ead7eb481a6551156fc0ce228c743fdf1b6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043667"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-pstn-gateway-for-a-branch-site-in-lync-server-2013"></a>Definieren eines PSTN-Gateways für einen Zweigstellenstandort in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-21_

Führen Sie dieses Verfahren am zentralen Standort aus, der mindestens eine Front-End-Pool oder Standard Edition-Server enthält.

<div>


> [!IMPORTANT]  
> Bevor Sie das Verfahren ausführen, müssen die folgenden Bedingungen erfüllt sein: 
> <UL>
> <LI>
> <P>Lync Server 2013&nbsp;Kommunikationssoftware muss am zentralen Standort eingerichtet werden.</P>
> <LI>
> <P>Vermittlungsserver müssen am zentralen Standort bereitgestellt werden.</P></LI></UL>



</div>

<div>

## <a name="to-define-a-pstn-gateway"></a>So definieren Sie ein PSTN-Gateway

1.  Klicken Sie auf **Start**, **Alle Programme**, **Microsoft Lync Server** und anschließend auf **Lync Server-Topologie-Generator**.

2.  Erweitern Sie in der Konsolenstruktur den zentralen Standort, erweitern Sie **Zweigstellenstandorte**, erweitern Sie den Namen des Zweigstellen Standorts, für den ein PSTN-Gateway (Public Switched Telephone Network) für festgelegt werden soll, und erweitern Sie dann **freigegebene Komponenten**.

3.  Klicken Sie mit der rechten Maustaste auf **PSTN-Gateways**, und klicken Sie auf **Neues IP/PSTN-Gateway**.

4.  Klicken Sie im Dialogfeld **neues IP/PSTN-Gateway definieren** auf **Gateway-FQDN oder IP-Adresse**, und geben Sie dann den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) oder die IP-Adresse des Gateways ein, das Sie an der Zweigstelle bereitstellen.

5.  Klicken Sie auf **Überwachungs Port für IP/PSTN-Gateway**, und übernehmen Sie dann die Standardwerte.

6.  Klicken Sie in der Liste **SIP-Transport Protokoll** auf das vom Gateway verwendete Transport Protokoll, und klicken Sie dann auf **OK**.
    
    <div>
    

    > [!NOTE]  
    > Aus Sicherheitsgründen wird dringend empfohlen, ein PSTN-Gateway zu verwenden, das TLS (Transport Layer Security) unterstützt.

    
    </div>

<div>


> [!TIP]  
> Verwenden Sie das Cmdlet "CsPstnGateway", um die Eigenschaften eines PSTN <STRONG>-</STRONG> Gateways zu ändern. Ausführliche Informationen finden Sie unter <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsPstnGateway">Festlegen von CsPstnGateway</A>in der Hilfe zu lync Server-Verwaltungsshell.



</div>

**Nächster Schritt** für Ausfallsicherheit für Zweigstellenstandorte: [Konfigurieren von Benutzern für Ausfallsicherheit für Zweigstellenstandorte in lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Bereitstellungsoptionen für PSTN-Gateways in lync Server 2013](lync-server-2013-pstn-gateway-deployment-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

