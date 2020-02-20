---
title: 'Lync Server 2013: Konfigurieren der Umgebung für das Administrator-Webportal von lync Room System'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring your environment for the Lync Room System Administrative Web Portal
ms:assetid: 1bf3cc55-cfa8-46ee-a8bc-6dab3bff76b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436325(v=OCS.15)
ms:contentKeyID: 56737623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 739e440765feb07d70b7f5a8d1490a85a938701d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154067"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-your-lync-server-2013-environment-for-the-lync-room-system-administrative-web-portal"></a>Konfigurieren der lync Server 2013 Umgebung für das Administrator-Webportal von lync Room System

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-05-22_

Für die Verwendung des administrativen Webportal für lync-Raumsysteme müssen Sie die folgenden Voraussetzungen installieren oder konfigurieren.

<div>


> [!IMPORTANT]  
> Wenn der Server mit der Kerberos-und der NTLM-Authentifizierung konfiguriert ist und LRS auf einem Computer ausgeführt wird, der nicht der Domäne angehört, schlägt die Kerberos-Authentifizierung fehl, und der Benutzer kann den Status von LRS im Verwaltungsportal nicht sehen. Um dieses Problem zu beheben, konfigurieren Sie den Server mit NTLM-Authentifizierung oder mit NTLM-und TLS-DSK-Authentifizierung (ohne Kerberos), oder schließen Sie den LRS-Computer der Domäne an.



</div>

1.  Installieren Sie lync Server 2013 kumulative Updates: Juli 2013 in der lync Server-Topologie.
    
    Informationen zum Abrufen des Updates oder zum Anzeigen der darin enthaltenen Informationen finden Sie unter [Updates für lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=323959).

2.  Erstellen Sie einen SIP-aktivierten Active Directory-Benutzer.
    
    Das LRS-Verwaltungsportal verwendet diese Anmeldeinformationen zum Abfragen von Informationen aus lync Server. Der empfohlene Benutzername lautet LRSApp.

3.  Erstellen Sie eine Active Directory Sicherheitsgruppe mit dem Namen LRSSupportAdminGroup.
    
    Erstellen Sie die Gruppe mit dem Gruppenbereich als globaler und Gruppentyp als Sicherheit. SIP-aktivierte Benutzer, die dieser Gruppe hinzugefügt werden, sind berechtigt, die Liste der Räume anzuzeigen und bestimmte Befehle auszuführen, beispielsweise das Sammeln von Protokollen.

4.  Erstellen Sie eine Active Directory Sicherheitsgruppe mit dem Namen LRSFullAccessAdminGroup.
    
    Erstellen Sie die Gruppe mit dem Gruppenbereich als globaler und Gruppentyp als Security. SIP-aktivierte Benutzer, die dieser Gruppe hinzugefügt werden, sind berechtigt, alle Funktionen des Verwaltungsportals zu verwenden.
    
     
    
    ![Liste der Administratorgruppen mit der Rolle "Sicherheitsgruppe"](images/Dn436325.5d432819-a2e2-452c-bc2a-5d4ee79d8c33(OCS.15).png "Liste der Administratorgruppen mit der Rolle "Sicherheitsgruppe"")  
    
     

5.  Fügen Sie LRSFullAccessAdminGroup als Mitglied von LRSSupportAdminGroup hinzu.
    
    ![LRSSupportAdminGroup-Eigenschaften-Mitgliederseite](images/Dn436325.91a4a28a-cacf-4ef6-aac1-915ec41c9648(OCS.15).png "LRSSupportAdminGroup-Eigenschaften-Mitgliederseite")  
    
     

6.  Erstellen Sie einen SIP-aktivierten Active Directory Benutzer mit dem Namen LRSSupport. Fügen Sie diesen Benutzer zu LRSSupportAdminGroup hinzu.
    
    ![LRSSupportAdminGroup-Eigenschaften-Mitgliederseite](images/Dn436325.7638055d-22ac-4909-914d-1966f5623909(OCS.15).png "LRSSupportAdminGroup-Eigenschaften-Mitgliederseite")  
    
     

7.  Installieren Sie ASP.NET MVC 4 für Visual Studio 2010 SP1 und Visual-Webentwickler 2010 SP1, die im Microsoft Download Center [https://go.microsoft.com/fwlink/p/?LinkId=323967](https://go.microsoft.com/fwlink/p/?linkid=323967)unter verfügbar sind.

</div>

<span> </span>

</div>

</div>

</div>

