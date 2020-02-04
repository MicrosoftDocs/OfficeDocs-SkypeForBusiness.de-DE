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

# <a name="configuring-your-lync-server-2013-environment-for-the-lync-room-system-administrative-web-portal"></a><span data-ttu-id="a3865-102">Konfigurieren Ihrer Lync Server 2013-Umgebung für das Webportal zur Verwaltung von Lync Room System</span><span class="sxs-lookup"><span data-stu-id="a3865-102">Configuring your Lync Server 2013 environment for the Lync Room System Administrative Web Portal</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a3865-103">_**Letztes Änderungsdatum des Themas:** 2014-05-22_</span><span class="sxs-lookup"><span data-stu-id="a3865-103">_**Topic Last Modified:** 2014-05-22_</span></span>

<span data-ttu-id="a3865-104">Um das lync-Verwaltungs Webportal (lync Room System) zu verwenden, müssen Sie die folgenden Voraussetzungen installieren oder konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="a3865-104">To use the Lync Room System (LRS) Administrative Web Portal, you will need to install or configure the following prerequisites.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a3865-105">Wenn der Server sowohl mit Kerberos-als auch NTLM-Authentifizierung konfiguriert ist und LRS auf einem Computer ausgeführt wird, der nicht mit der Domäne verbunden ist, schlägt die Kerberos-Authentifizierung fehl, und der Benutzer kann den Status von LRS nicht im Verwaltungsportal sehen.</span><span class="sxs-lookup"><span data-stu-id="a3865-105">If the server is configured with both Kerberos and NTLM authentication, and LRS is running on a computer that is not joined to the domain, Kerberos authentication will fail and the user will not see the status of LRS in the administrative portal.</span></span> <span data-ttu-id="a3865-106">Um dieses Problem zu beheben, konfigurieren Sie den Server mit NTLM-Authentifizierung oder NTLM-und TLS-DSK-Authentifizierung (ohne Kerberos), oder nehmen Sie den LRS-Computer an die Domäne an.</span><span class="sxs-lookup"><span data-stu-id="a3865-106">To resolve this issue, configure the server with NTLM authentication or both NTLM and TLS-DSK authentication (without Kerberos), or join the LRS computer to the domain.</span></span>



</div>

1.  <span data-ttu-id="a3865-107">Installieren Sie die kumulativen Updates für lync Server 2013: Juli 2013 in der lync Server-Topologie.</span><span class="sxs-lookup"><span data-stu-id="a3865-107">Install Lync Server 2013 Cumulative Updates: July 2013 in the Lync Server topology.</span></span>
    
    <span data-ttu-id="a3865-108">Wenn Sie das Update erhalten oder sehen möchten, was darin enthalten ist, lesen Sie [Updates für lync Server 2013](http://go.microsoft.com/fwlink/p/?linkid=323959).</span><span class="sxs-lookup"><span data-stu-id="a3865-108">To get the update or see what’s included with it, see [Updates for Lync Server 2013](http://go.microsoft.com/fwlink/p/?linkid=323959).</span></span>

2.  <span data-ttu-id="a3865-109">Erstellen Sie einen SIP-aktivierten Active Directory-Benutzer.</span><span class="sxs-lookup"><span data-stu-id="a3865-109">Create a SIP-enabled Active Directory user.</span></span>
    
    <span data-ttu-id="a3865-110">Das administrative LRS-Webportal verwendet diese Anmeldeinformationen, um Informationen von lync Server abzufragen.</span><span class="sxs-lookup"><span data-stu-id="a3865-110">The LRS Administrative Web Portal uses these credentials to query information from Lync Server.</span></span> <span data-ttu-id="a3865-111">Der empfohlene Benutzername lautet LRSApp.</span><span class="sxs-lookup"><span data-stu-id="a3865-111">The recommended username is LRSApp.</span></span>

3.  <span data-ttu-id="a3865-112">Erstellen Sie eine Active Directory-Sicherheitsgruppe mit dem Namen LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="a3865-112">Create an Active Directory security group with name LRSSupportAdminGroup.</span></span>
    
    <span data-ttu-id="a3865-p103">Erstellen Sie die Gruppe mit dem Gruppenbereich  Global  und dem Gruppentyp  Sicherheit . SIP-aktivierte Benutzer, die dieser Gruppe hinzugefügt werden, sind berechtigt, die Liste der Räume anzuzeigen und bestimmte Befehle auszuführen, wie das Speichern von Protokollen.</span><span class="sxs-lookup"><span data-stu-id="a3865-p103">Create the group with Group Scope as Global and Group Type as Security. SIP enabled users who are added to this group will be authorized to see the list of rooms and execute certain commands, such as collecting logs.</span></span>

4.  <span data-ttu-id="a3865-115">Erstellen Sie eine Active Directory-Sicherheitsgruppe mit dem Namen LRSFullAccessAdminGroup. </span><span class="sxs-lookup"><span data-stu-id="a3865-115">Create an Active Directory security group with name LRSFullAccessAdminGroup.</span></span>
    
    <span data-ttu-id="a3865-116">Erstellen Sie die Gruppe mit dem Gruppenbereich als globaler und Gruppentyp als "Sicherheit". SIP-aktivierte Benutzer, die dieser Gruppe hinzugefügt werden, sind berechtigt, alle Funktionen des Administrator Portals zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="a3865-116">Create the group with Group Scope as Global and Group Type as Security.SIP enabled users who are added to this group are authorized to use all admin portal functionality.</span></span>
    
     
    
    <span data-ttu-id="a3865-117">![Liste der Verwaltungsgruppen mit Sicherheitsgruppenrolle](images/Dn436325.5d432819-a2e2-452c-bc2a-5d4ee79d8c33(OCS.15).png "Liste der Verwaltungsgruppen mit Sicherheitsgruppenrolle")</span><span class="sxs-lookup"><span data-stu-id="a3865-117">![List of Admin Groups with security group role](images/Dn436325.5d432819-a2e2-452c-bc2a-5d4ee79d8c33(OCS.15).png "List of Admin Groups with security group role")</span></span>  
    
     

5.  <span data-ttu-id="a3865-118">Fügen Sie LRSFullAccessAdminGroup als Mitglied von LRSSupportAdminGroup hinzu.</span><span class="sxs-lookup"><span data-stu-id="a3865-118">Add LRSFullAccessAdminGroup as a member of LRSSupportAdminGroup.</span></span>
    
    <span data-ttu-id="a3865-119">![LRSSupportAdminGroup-Eigenschaftenmember (Seite)](images/Dn436325.91a4a28a-cacf-4ef6-aac1-915ec41c9648(OCS.15).png "LRSSupportAdminGroup-Eigenschaftenmember (Seite)")</span><span class="sxs-lookup"><span data-stu-id="a3865-119">![LRSSupportAdminGroup Properties Members page](images/Dn436325.91a4a28a-cacf-4ef6-aac1-915ec41c9648(OCS.15).png "LRSSupportAdminGroup Properties Members page")</span></span>  
    
     

6.  <span data-ttu-id="a3865-120">Erstellen Sie einen SIP-aktivierten Active Directory-Benutzer mit dem Namen LRSSupport.</span><span class="sxs-lookup"><span data-stu-id="a3865-120">Create a SIP enabled Active Directory user with name LRSSupport.</span></span> <span data-ttu-id="a3865-121">Fügen Sie diesen Benutzer zu LRSSupportAdminGroup hinzu.</span><span class="sxs-lookup"><span data-stu-id="a3865-121">Add this user to LRSSupportAdminGroup.</span></span>
    
    <span data-ttu-id="a3865-122">![LRSSupportAdminGroup-Eigenschaftenmember (Seite)](images/Dn436325.7638055d-22ac-4909-914d-1966f5623909(OCS.15).png "LRSSupportAdminGroup-Eigenschaftenmember (Seite)")</span><span class="sxs-lookup"><span data-stu-id="a3865-122">![LRSSupportAdminGroup Properties Members page](images/Dn436325.7638055d-22ac-4909-914d-1966f5623909(OCS.15).png "LRSSupportAdminGroup Properties Members page")</span></span>  
    
     

7.  <span data-ttu-id="a3865-123">Installieren Sie ASP.NET MVC 4 für Visual Studio 2010 SP1 und Visual Web Developer 2010 SP1, das im Microsoft Download Center unter [http://go.microsoft.com/fwlink/p/?LinkId=323967](http://go.microsoft.com/fwlink/p/?linkid=323967)verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="a3865-123">Install ASP.NET MVC 4 for Visual Studio 2010 SP1 and Visual Web Developer 2010 SP1, available in the Microsoft Download Center at [http://go.microsoft.com/fwlink/p/?LinkId=323967](http://go.microsoft.com/fwlink/p/?linkid=323967).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

