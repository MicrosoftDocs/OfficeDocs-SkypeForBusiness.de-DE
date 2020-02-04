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
ms.openlocfilehash: 30889a6b145e7256a313c4deedafc74d99499719
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758383"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-adapters-in-lync-server-2013"></a>Konfigurieren von Netzwerkadaptern in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-11-07_

Sie müssen dem externen Netzwerkadapter eine oder mehrere IP-Adressen und mindestens eine IP-Adresse für den internen Netzwerkadapter zuweisen.

In den folgenden Verfahren verfügt der Server, auf dem Forefront Threat Management Gateway (TMG) 2010 oder Internet Information Server-Anwendungs Anforderungs Routing ausgeführt wird, über zwei Netzwerkadapter:

  - Ein öffentlicher oder externer Netzwerkadapter für Clients, die versuchen, eine Verbindung mit Ihrer Website herzustellen (in der Regel über das Internet).

  - Eine private oder interne Netzwerkschnittstelle für interne Server, auf denen lync Server ausgeführt wird, die Webdienste hosten.

<div>


> [!IMPORTANT]  
> Ähnlich wie die Edgeserver setzen Sie das Standardgateway nur für den externen Netzwerkadapter. Das Standardgateway ist die IP-Adresse des Routers oder der extern zugewandten Firewall, die den Datenverkehr an das Internet weiterleitet. Für Datenverkehr, der vom Reverse-Proxy an den internen Netzwerkadapter ausgerichtet ist, müssen Sie für alle Subnetze mit Servern, auf die die Webveröffentlichungsregeln verweisen, persistente statische Routen (wie den Befehl Route in Windows Server) verwenden. Das Festlegen einer beständigen Route führt nicht dazu, dass der Computer zu einem Router wird. Wenn die IP-Weiterleitung nicht aktiviert ist, handelt es sich bei dem Computer nur um den direkten bestimmten Datenverkehr, der für ein anderes Netzwerk bestimmt ist, an die entsprechende Schnittstelle. Dies ist im Wesentlichen die Festlegung von zwei Gateways – einer als Standardverweis auf die externen Netzwerke und einer für den Datenverkehr, der an die interne Schnittstelle und an einen Router oder ein anderes Netzwerk weitergeleitet wird.<BR>Das Erstellen beständiger Routen für alle Subnetze ist jedoch möglicherweise nicht erforderlich, wenn die Router Ihres Netzwerks für die Zusammenfassung von Routen konfiguriert sind. Erstellen Sie eine permanente Route zu dem Netzwerk, in dem der Router definiert ist, und verwenden Sie den Router als Standardgateway. Wenn Sie nicht genau wissen, wie Ihr Netzwerk konfiguriert ist und Anleitungen dazu benötigen, welche persistenten Routen erstellt werden müssen, konsultieren Sie die Netzwerktechniker Ihres Unternehmens.<BR>Der Reverseproxy muss in der Lage sein, die DNS-Hosteinträge (A) für den internen Director-oder Front-End-Server und die FQDNs des nächsten Hop zu beheben, die in den Webveröffentlichungsregeln verwendet werden. Wie bei den Edge-Servern sollten Sie aus Sicherheitsgründen keinen Reverse-Proxy für die Verwendung eines DNS-Servers konfigurieren, der sich im internen Netzwerk befindet. Das bedeutet, dass Sie entweder DNS-Server im Umkreis benötigen, oder Sie benötigen Hosts-Dateieinträge auf dem Reverse-Proxy, der jede dieser FQDNs in die interne IP-Adresse der Server auflöst.



</div>

<div>

## <a name="to-configure-the-network-adapter-cards-on-the-reverse-proxy-computer"></a>So konfigurieren Sie die Netzwerkadapterkarten auf dem Reverse Proxy-Computer

1.  Öffnen Sie auf dem Windows Server 2008-, Windows Server 2008 R2-, Windows Server 2012-oder Windows Server 2012 R2-Server, der als Reverseproxy ausgeführt wird, die Option **Adaptereinstellungen ändern** , indem Sie auf **Start**klicken, auf **System**Steuerung zeigen, auf **Netzwerk-und Freigabe Center**klicken und dann auf **Adaptereinstellungen ändern**klicken.

2.  Klicken Sie mit der rechten Maustaste auf die externe Netzwerkverbindung, die Sie für die externe Schnittstelle verwenden möchten, und klicken Sie dann auf **Eigenschaften**.

3.  Klicken Sie auf der Seite **Eigenschaften** auf die Registerkarte **Netzwerk** , klicken Sie in der Liste **diese Verbindung verwendet die folgenden Elemente** auf **Internet Protokoll, Version 4 (TCP/IPv4)** , und klicken Sie dann auf **Eigenschaften**.

4.  Konfigurieren Sie auf der Seite **Eigenschaften von Internet Protokoll (TCP/IP)** die IP-Adressen entsprechend dem Netzwerk-Subnetz, an das der Netzwerkadapter angefügt ist.
    
    <div>
    

    > [!NOTE]  
    > Wenn der Reverse-Proxy bereits von anderen Anwendungen verwendet wird, die HTTPS/TCP/443 verwenden, wie bei der Veröffentlichung von Outlook Web Access müssen Sie entweder eine weitere IP-Adresse hinzufügen, damit Sie die lync Server 2013-Webdienste auf HTTPS/TCP/443 veröffentlichen können, ohne die vorhandenen Regeln und Weblistener zu stören, oder Sie müssen das vorhandene Zertifikat durch ein ersetzen, das dem alternativen Namen des Antragstellers den neuen Namen des externen FQDN hinzufügt.

    
    </div>

5.  Klicken Sie auf **OK**, und klicken Sie dann auf **OK**.

6.  Klicken Sie unter **Netzwerkverbindungen**mit der rechten Maustaste auf die interne Netzwerkverbindung, die Sie für die interne Schnittstelle verwenden möchten, und klicken Sie dann auf **Eigenschaften**.

7.  Wiederholen Sie die Schritte 3 bis 5, um die interne Netzwerkverbindung zu konfigurieren.

</div>

</div>

<span> </span>

</div>

</div>

</div>

