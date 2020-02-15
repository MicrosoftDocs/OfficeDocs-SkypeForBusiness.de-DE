---
title: 'Lync Server 2013: Einrichten von Netzwerkschnittstellen für Edgeserver'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up network interfaces for Edge Servers
ms:assetid: b0aecdf6-4ae2-46f6-b9b6-948bfc3df11e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412847(v=OCS.15)
ms:contentKeyID: 48185152
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 49b363e4803d493ed5859455104945d0d1d2d23c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034235"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-network-interfaces-for-edge-servers-in-lync-server-2013"></a>Einrichten von Netzwerkschnittstellen für Edgeserver in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-08_

Jeder Edgeserver ist ein mehrfach vernetzter Computer mit externen und internen Schnittstellen. Die Einstellungen für den Adapter Domain Name System (DNS) hängen davon ab, ob sich DNS-Server im Umkreisnetzwerk befinden. Wenn sich DNS-Server im Umkreis befinden, müssen Sie über eine Zone mit mindestens einem DNS-a-Eintrag für den nächsten Hop-Server oder-Pool verfügen (also entweder Director oder Designated Front-End-Pool), und für externe Abfragen, die Sie Namenssuche auf andere öffentliche DNS-Server referieren. Wenn im Umkreis keine DNS-Server vorhanden sind, verwenden die Edgeserver (s) externe DNS-Server zum Auflösen von Internet Namen suchen, und jede Edgeserver verwendet einen Host, um die Server Namen des nächsten Hops in IP-Adressen aufzulösen.

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="Sicherheits" alt="security" />Sicherheitshinweis:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Aus Sicherheitsgründen wird empfohlen, dass Ihre Edgeserver nicht auf einen DNS-Server zugreifen können, der sich im internen Netzwerk befindet.</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-configure-interfaces-with-dns-servers-in-the-perimeter-network"></a>So konfigurieren Sie Schnittstellen mit DNS-Servern im Umkreisnetzwerk

1.  Installieren Sie zwei Netzwerkadapter für jeden Edgeserver, einen für die interne Schnittstelle und einen für die extern ausgerichtete Schnittstelle.
    
    <div>
    

    > [!IMPORTANT]  
    > Die internen und externen Subnetze dürfen nicht zueinander geroutet werden.

    
    </div>

2.  Konfigurieren Sie auf der externen Schnittstelle drei statische IP-Adressen im Subnetz des externen Umkreisnetzwerks (auch als DMZ, demilitarisierte Zone und überwachtes Subnetz bezeichnet), und richten Sie das Standardgateway auf die interne Schnittstelle der externen Firewall. Konfigurieren Sie die DNS-Einstellungen des Adapters so, dass Sie auf ein paar von Umkreis-DNS-Servern deuten.
    
    <div>
    

    > [!NOTE]  
    > Für diese Schnittstelle ist es möglich, nur eine IP-Adresse zu verwenden, aber dazu müssen Sie die Portzuweisungen in nicht-Standardwerte ändern. Sie bestimmen dies, wenn Sie die Topologie im Topologie-Generator erstellen.

    
    </div>

3.  Konfigurieren Sie auf der internen Schnittstelleeine statische IP-Adresse im Subnetz des internen Umkreisnetzwerks, und legen Sie kein Standardgateway fest. Konfigurieren Sie die Adapter-DNS-Einstellungen so, dass Sie auf mindestens einen DNS-Server, vorzugsweise ein paar von Umkreis-DNS-Servern, verweist.

4.  Erstellen Sie persistente statische Routen auf der internen Schnittstelle zu allen internen Netzwerken, in denen sich Clients, lync Server 2013 und Exchange Unified Messaging (um) Server befinden.

</div>

<div>

## <a name="to-configure-interfaces-without-dns-servers-in-the-perimeter-network"></a>So konfigurieren Sie Schnittstellen ohne DNS-Server im Umkreisnetzwerk

1.  Installieren Sie zwei Netzwerkadapter für jeden Edgeserver, einen für die interne Schnittstelle und einen für die extern ausgerichtete Schnittstelle.
    
    <div>
    

    > [!IMPORTANT]  
    > Die internen und externen Subnetze dürfen nicht zueinander geroutet werden.

    
    </div>

2.  Konfigurieren Sie auf der externen Schnittstelle drei statische IP-Adressen im Subnetz des externen Umkreisnetzwerks. Außerdem konfigurieren Sie das Standardgateway für die externe Schnittstelle. Definieren Sie beispielsweise den mit dem Internet verbundenen Router oder die externe Firewall als Standardgateway. Konfigurieren Sie DNS-Einstellungen so, dass Sie auf einen DNS-Server, vorzugsweise auf ein paar externer DNS-Server, verweist.
    
    <div>
    

    > [!NOTE]  
    > Es ist möglich, aber nicht empfehlenswert, nur so wenige IP-Adressen für die externe Schnittstelle zu verwenden. Damit dies funktioniert, müssen Sie die Portzuweisungen auf nicht standardmäßige Werte und den standardmäßigen Port 443, der normalerweise "Firewall-freundlich" für die Clientkommunikation ist, ändern. Sie bestimmen die IP-Adresseinstellung und die Porteinstellungen beim Erstellen der Topologie im Topologie-Generator.

    
    </div>

3.  Konfigurieren Sie auf der internen Schnittstelleeine statische IP-Adresse im Subnetz des internen Umkreisnetzwerks, und legen Sie kein Standardgateway fest. Lassen Sie die Adapter-DNS-Einstellungen leer.

4.  Erstellen Sie persistente statische Routen auf der internen Schnittstelle für alle internen Netzwerke, in denen sich lync-Clients oder-Server mit lync Server 2013 befinden.

5.  Bearbeiten Sie die Hostdatei auf jeder Edgeserver, um einen Datensatz für den nächsten Hop-Server oder die virtuelle IP (VIP) aufzunehmen (der Datensatz ist der Director, Standard Edition-Server oder ein Front-End-Pool, der als Edgeserver nächster Hop-Adresse im Topologie-Generator konfiguriert wurde). Wenn Sie DNS-Lastenausgleich verwenden, fügen Sie für jedes Mitglied des Pools für den nächsten Hop eine Codezeile ein.

</div>

</div>

<span> </span>

</div>

</div>

</div>

