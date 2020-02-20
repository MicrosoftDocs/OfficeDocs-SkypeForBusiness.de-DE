---
title: 'Lync Server 2013: Konfigurieren von Netzwerkadaptern'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure network adapters
ms:assetid: 6519ed80-020f-47a3-851c-03dea5eac5d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429707(v=OCS.15)
ms:contentKeyID: 48184320
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd2609c8b8a900b9c970943a2f24bc0462eafb85
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147668"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-network-adapters-in-lync-server-2013"></a>Konfigurieren von Netzwerkadaptern in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-11-07_

Sie müssen der externen Netzwerkkarte eine oder mehrere IP-Adressen und der internen Netzwerkkarte mindestens eine IP-Adresse zuweisen.

In den folgenden Verfahren verfügt der Server, auf dem Forefront Threat Management Gateway (TMG) 2010 oder Internet Information Server-Anwendungs Anforderungs Routing ausgeführt wird, über zwei Netzwerkadapter:

  - Eine öffentliche (oder externe) Netzwerkkarte für Clients, die versuchen, eine Verbindung zu Ihrer Website herzustellen (normalerweise über das Internet).

  - Eine private oder interne Netzwerkschnittstelle für interne Server, auf denen lync Server gehostet werden, die Webdienste hosten.

<div>


> [!IMPORTANT]  
> Ähnlich wie bei den Edgeserver legen Sie das Standardgateway nur für den externen Netzwerkadapter fest. Das Standardgateway ist die IP-Adresse des Routers oder der Firewall mit externer Ausrichtung, die den Datenverkehr an das Internet weiterleitet. Für Datenverkehr, der vom Reverseproxy zum internen zugewandten Netzwerkadapter bestimmt ist, müssen Sie persistente statische Routen (wie den Befehl Route in Windows Server) für alle Subnetze mit Servern verwenden, auf die von den Webveröffentlichungsregeln verwiesen wird. Das Festlegen einer beständigen Route führt nicht dazu, dass der Computer zu einem Router wird. Wenn die IP-Weiterleitung nicht aktiviert ist, handelt der Computer nur für den direkten spezifischen Datenverkehr, der für ein anderes Netzwerk bestimmt ist, an die entsprechende Schnittstelle. Im Wesentlichen werden zwei Gateways festgesetzt – eine als Standard, der auf die externen Netzwerke verweist, und eine für den Datenverkehr, der an die interne Schnittstelle und an einen Router oder ein anderes Netzwerk gerichtet ist.<BR>Wenn Ihr Router jedoch so konfiguriert ist, dass Routen zusammengefasst werden, brauchen Sie nicht für sämtliche Subnetze beständige Routen zu erstellen. Erstellen Sie eine beständige Route für das Netzwerk, in dem der Router definiert ist, und verwenden Sie den Router dann als Standardgateway. Wenn Sie nicht genau wissen, wie Ihr Netzwerk konfiguriert ist und genauere Anleitungen bezüglich der Erstellung von Routen benötigen, wenden Sie sich an die Netzwerkexperten Ihres Unternehmens.<BR>Der Reverseproxy muss in der Lage sein, die DNS-Hosteinträge (A) für die in den Webveröffentlichungsregeln verwendeten internen Director-oder Front-End-Server-und Next Hop-Pool-FQDN aufzulösen. Wie bei den Edgeserver empfiehlt es sich aus Sicherheitsgründen nicht, einen Reverseproxy für die Verwendung eines DNS-Servers im internen Netzwerk zu konfigurieren. Das bedeutet, dass Sie entweder DNS-Server im Umkreisnetzwerk bereitstellen müssen oder HOST-Dateieinträge auf dem Reverseproxy benötigen, der die einzelnen FQDNs in die internen IP-Adressen der Server auflöst.



</div>

<div>

## <a name="to-configure-the-network-adapter-cards-on-the-reverse-proxy-computer"></a>So konfigurieren Sie die Netzwerkkarten auf dem Reverseproxycomputer

1.  Öffnen Sie auf dem Windows Server 2008-, Windows Server 2008 R2-, Windows Server 2012-oder Windows Server 2012 R2-Server, der als Reverseproxy angezeigt wird, **Adaptereinstellungen ändern** , indem Sie auf **Start**, auf **System**Steuerung, auf **Netzwerk-und Freigabe Center**und dann auf **Adapter Einstellungen ändern**klicken.

2.  Klicken Sie mit der rechten Maustaste auf die externe Netzwerkverbindung, die Sie für die externe Schnittstelle verwenden möchten, und klicken Sie dann auf **Eigenschaften**.

3.  Klicken Sie auf der Seite **Eigenschaften** auf die Registerkarte **Netzwerk**, klicken Sie in der Liste **Diese Verbindung verwendet folgende Elemente** auf **Internetprotokoll Version 4 (TCP/IPv4)**, und klicken Sie dann auf **Eigenschaften**.

4.  Konfigurieren Sie auf der Seite **Internetprotokolleigenschaften (TCP/IP)** die IP-Adressen entsprechend dem Netzwerksubnetz, an das die Netzwerkkarte angeschlossen ist.
    
    <div>
    

    > [!NOTE]  
    > Wenn der Reverseproxy bereits von anderen Anwendungen verwendet wird, die HTTPS/TCP/443 verwenden, beispielsweise zum Veröffentlichen von Outlook Web Access müssen Sie eine andere IP-Adresse hinzufügen, damit Sie die lync Server 2013 Webdienste auf HTTPS/TCP/443 veröffentlichen können, ohne die vorhandenen Regeln und die Weblistener zu stören, oder Sie müssen das vorhandene Zertifikat durch ein anderes ersetzen, das die neuen Namen des externen FQDN dem alternativen Antragstellernamen hinzufügt.

    
    </div>

5.  Klicken Sie auf **OK** und dann nochmals auf **OK**.

6.  Klicken Sie unter **Netzwerkverbindungen** mit der rechten Maustaste auf die interne Netzwerkverbindung, die Sie für die interne Schnittstelle verwenden möchten, und klicken Sie dann auf **Eigenschaften**.

7.  Wiederholen Sie die Schritte 3 bis 5, um die interne Netzwerkverbindung zu konfigurieren.

</div>

</div>

<span> </span>

</div>

</div>

</div>

