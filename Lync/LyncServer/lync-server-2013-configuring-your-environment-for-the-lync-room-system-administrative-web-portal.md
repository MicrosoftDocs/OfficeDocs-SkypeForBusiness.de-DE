---
title: 'Lync Server 2013: Konfigurieren Ihrer Umgebung für das Webportal zur Verwaltung von Lync Room System'
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
ms.openlocfilehash: 4f0f415cfeca5b798a1e29ac6ebe09105fbf08b4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740585"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-your-lync-server-2013-environment-for-the-lync-room-system-administrative-web-portal"></a>Konfigurieren Ihrer Lync Server 2013-Umgebung für das Webportal zur Verwaltung von Lync Room System

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-05-22_

Um das lync-Verwaltungs Webportal (lync Room System) zu verwenden, müssen Sie die folgenden Voraussetzungen installieren oder konfigurieren.

<div>


> [!IMPORTANT]  
> Wenn der Server sowohl mit Kerberos-als auch NTLM-Authentifizierung konfiguriert ist und LRS auf einem Computer ausgeführt wird, der nicht mit der Domäne verbunden ist, schlägt die Kerberos-Authentifizierung fehl, und der Benutzer kann den Status von LRS nicht im Verwaltungsportal sehen. Um dieses Problem zu beheben, konfigurieren Sie den Server mit NTLM-Authentifizierung oder NTLM-und TLS-DSK-Authentifizierung (ohne Kerberos), oder nehmen Sie den LRS-Computer an die Domäne an.



</div>

1.  Installieren Sie die kumulativen Updates für lync Server 2013: Juli 2013 in der lync Server-Topologie.
    
    Wenn Sie das Update erhalten oder sehen möchten, was darin enthalten ist, lesen Sie [Updates für lync Server 2013](http://go.microsoft.com/fwlink/p/?linkid=323959).

2.  Erstellen Sie einen SIP-aktivierten Active Directory-Benutzer.
    
    Das administrative LRS-Webportal verwendet diese Anmeldeinformationen, um Informationen von lync Server abzufragen. Der empfohlene Benutzername lautet LRSApp.

3.  Erstellen Sie eine Active Directory-Sicherheitsgruppe mit dem Namen LRSSupportAdminGroup.
    
    Erstellen Sie die Gruppe mit dem Gruppenbereich  Global  und dem Gruppentyp  Sicherheit . SIP-aktivierte Benutzer, die dieser Gruppe hinzugefügt werden, sind berechtigt, die Liste der Räume anzuzeigen und bestimmte Befehle auszuführen, wie das Speichern von Protokollen.

4.  Erstellen Sie eine Active Directory-Sicherheitsgruppe mit dem Namen LRSFullAccessAdminGroup. 
    
    Erstellen Sie die Gruppe mit dem Gruppenbereich als globaler und Gruppentyp als "Sicherheit". SIP-aktivierte Benutzer, die dieser Gruppe hinzugefügt werden, sind berechtigt, alle Funktionen des Administrator Portals zu verwenden.
    
     
    
    ![Liste der Verwaltungsgruppen mit Sicherheitsgruppenrolle](images/Dn436325.5d432819-a2e2-452c-bc2a-5d4ee79d8c33(OCS.15).png "Liste der Verwaltungsgruppen mit Sicherheitsgruppenrolle")  
    
     

5.  Fügen Sie LRSFullAccessAdminGroup als Mitglied von LRSSupportAdminGroup hinzu.
    
    ![LRSSupportAdminGroup-Eigenschaftenmember (Seite)](images/Dn436325.91a4a28a-cacf-4ef6-aac1-915ec41c9648(OCS.15).png "LRSSupportAdminGroup-Eigenschaftenmember (Seite)")  
    
     

6.  Erstellen Sie einen SIP-aktivierten Active Directory-Benutzer mit dem Namen LRSSupport. Fügen Sie diesen Benutzer zu LRSSupportAdminGroup hinzu.
    
    ![LRSSupportAdminGroup-Eigenschaftenmember (Seite)](images/Dn436325.7638055d-22ac-4909-914d-1966f5623909(OCS.15).png "LRSSupportAdminGroup-Eigenschaftenmember (Seite)")  
    
     

7.  Installieren Sie ASP.NET MVC 4 für Visual Studio 2010 SP1 und Visual Web Developer 2010 SP1, das im Microsoft Download Center unter [http://go.microsoft.com/fwlink/p/?LinkId=323967](http://go.microsoft.com/fwlink/p/?linkid=323967)verfügbar ist.

</div>

<span> </span>

</div>

</div>

</div>

