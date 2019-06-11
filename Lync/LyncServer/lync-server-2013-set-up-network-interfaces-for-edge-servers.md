---
title: 'Lync Server 2013: Einrichten von Netzwerkschnittstellen für Edgeserver'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Set up network interfaces for Edge Servers
ms:assetid: b0aecdf6-4ae2-46f6-b9b6-948bfc3df11e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412847(v=OCS.15)
ms:contentKeyID: 48185152
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7263c2d7cad3cf1339351f2cb5f90b15a9fa0a2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34821915"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-network-interfaces-for-edge-servers-in-lync-server-2013"></a>Einrichten von Netzwerkschnittstellen für Edgeserver in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-08_

Bei jedem Edgeserver handelt es sich um einen mehr vernetzten Computer mit externen und internen Schnittstellen. Die DNS-Einstellungen (Domain Name System) des Adapters hängen davon ab, ob im Umkreisnetzwerk DNS-Server vorhanden sind. Wenn DNS-Server im Umkreis vorhanden sind, müssen Sie über eine Zone verfügen, die mindestens einen DNS-a-Eintrag für den Server oder Pool des nächsten Hop enthält (also entweder einen Director oder einen benannten Front-End-Pool), und für externe Abfragen, die Sie auf andere öffentliche DNS-Server verweisen. Wenn keine DNS-Server im Umkreis vorhanden sind, verwenden die Edgeserver externe DNS-Server zum Auflösen von Internet Namen suchen, und jeder Edgeserver verwendet einen Host, um die Servernamen für den nächsten Hop in IP-Adressen aufzulösen.

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="Sicherheits" alt="security" />Sicherheitshinweis:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Aus Sicherheitsgründen empfehlen wir, dass Ihre Edgeserver nicht auf einen DNS-Server zugreifen, der sich im internen Netzwerk befindet.</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-configure-interfaces-with-dns-servers-in-the-perimeter-network"></a>So konfigurieren Sie Schnittstellen mit DNS-Servern im Umkreisnetzwerk

1.  Installieren Sie zwei Netzwerkadapter für jeden Edgeserver, einen für die interne Schnittstelle und einen für die extern anliegende Schnittstelle.
    
    <div>
    

    > [!IMPORTANT]  
    > Ein Routing vom internen Subnetz zum externen Subnetz (und umgekehrt) darf nicht möglich sein.

    
    </div>

2.  Konfigurieren Sie auf der externen Schnittstelle drei statische IP-Adressen im Subnetz des externen Umkreisnetzwerks (auch bekannt als DMZ, demilitarisierte Zone und geschirmtes Subnetz), und zeigen Sie das Standardgateway auf die interne Schnittstelle der externen Firewall. Konfigurieren Sie die Adapter-DNS-Einstellungen so, dass Sie auf ein paar von Umkreis-DNS-Servern verweisen.
    
    <div>
    

    > [!NOTE]  
    > Es ist möglich, nur eine IP-Adresse für diese Schnittstelle zu verwenden, aber dazu müssen Sie die Portzuweisungen auf nicht Standardwerte ändern. Sie bestimmen dies, wenn Sie die Topologie im Topologie-Generator erstellen.

    
    </div>

3.  Konfigurieren Sie auf der internen Schnittstelleeine statische IP-Adresse im Subnetz des internen Umkreisnetzwerks, und legen Sie kein Standardgateway an. Konfigurieren Sie die Adapter-DNS-Einstellungen so, dass Sie auf mindestens einen DNS-Server verweisen, vorzugsweise auf ein paar von Umkreis-DNS-Servern.

4.  Erstellen Sie persistente statische Routen auf der internen Schnittstelle für alle internen Netzwerke, auf denen sich Clients, lync Server 2013 und Exchange Unified Messaging-Server befinden.

</div>

<div>

## <a name="to-configure-interfaces-without-dns-servers-in-the-perimeter-network"></a>So konfigurieren Sie Schnittstellen ohne DNS-Server im Umkreisnetzwerk

1.  Installieren Sie zwei Netzwerkadapter für jeden Edgeserver, einen für die interne Schnittstelle und einen für die extern anliegende Schnittstelle.
    
    <div>
    

    > [!IMPORTANT]  
    > Ein Routing vom internen Subnetz zum externen Subnetz (und umgekehrt) darf nicht möglich sein.

    
    </div>

2.  Konfigurieren Sie auf der externen Schnittstelle drei statische IP-Adressen im Subnetz des externen Umkreisnetzwerks. Darüber hinaus konfigurieren Sie das Standardgateway auf der externen Schnittstelle. Definieren Sie beispielsweise den mit dem Internet versehenen Router oder die externe Firewall als Standardgateway. Konfigurieren Sie die DNS-Einstellungen so, dass Sie auf einen DNS-Server verweisen, vorzugsweise auf ein paar externer DNS-Server.
    
    <div>
    

    > [!NOTE]  
    > Es ist möglich, aber nicht empfehlenswert, nur eine IP-Adresse für die externe Schnittstelle zu verwenden. Damit dies funktioniert, müssen Sie die Portzuweisungen auf nicht standardmäßige Werte und außerhalb des standardmäßigen Port 443 ändern, der in der Regel für die Clientkommunikation "Firewall-freundlich" ist. Sie bestimmen die IP-Adresseneinstellung und die Porteinstellungen, wenn Sie die Topologie im Topologie-Generator erstellen.

    
    </div>

3.  Konfigurieren Sie auf der internen Schnittstelleeine statische IP-Adresse im Subnetz des internen Umkreisnetzwerks, und legen Sie kein Standardgateway an. Lassen Sie die Adapter-DNS-Einstellungen leer.

4.  Erstellen Sie persistente statische Routen auf der internen Schnittstelle für alle internen Netzwerke, in denen lync-Clients oder-Server mit lync Server 2013 befinden.

5.  Bearbeiten Sie die Hostdatei auf jedem Edgeserver, um einen Eintrag für den nächsten Hop-Server oder die virtuelle IP (VIP) zu enthalten (der Datensatz ist der Director, Standard Edition-Server oder ein Front-End-Pool, der im Topologie-Generator als Adresse des Edge-Servers für den nächsten Hop konfiguriert wurde). Wenn Sie den DNS-Lastenausgleich verwenden, schließen Sie eine Zeile für jedes Mitglied des nächsten Hop-Pools ein.

</div>

</div>

<span> </span>

</div>

</div>

</div>

