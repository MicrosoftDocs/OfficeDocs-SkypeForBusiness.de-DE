---
title: 'Lync Server 2013: Testen der Poolbereitstellung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test the pool deployment
ms:assetid: ffd80617-155a-4041-bbeb-74503e7938dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413092(v=OCS.15)
ms:contentKeyID: 48185976
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cfde95e7323d68f05e78f670a6b027a5949f0169
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746065"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-the-pool-deployment-in-lync-server-2013"></a><span data-ttu-id="3bd3f-102">Testen der Poolbereitstellung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3bd3f-102">Test the pool deployment in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3bd3f-103">_**Letztes Änderungsdatum des Themas:** 2013-09-25_</span><span class="sxs-lookup"><span data-stu-id="3bd3f-103">_**Topic Last Modified:** 2013-09-25_</span></span>

<span data-ttu-id="3bd3f-104">Im folgenden Verfahren wird beschrieben, wie die Bereitstellung des Front-End-Pools getestet wird.</span><span class="sxs-lookup"><span data-stu-id="3bd3f-104">The following procedure describes how to test the deployment of the Front End pool.</span></span>

<div>

## <a name="to-test-the-pool-deployment"></a><span data-ttu-id="3bd3f-105">So testen Sie die Pool Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="3bd3f-105">To test the pool deployment</span></span>

1.  <span data-ttu-id="3bd3f-106">Verwenden Sie Active Directory-Computer und-Benutzer, um das Active Directory-Benutzerobjekt der Administratorrolle für die lync Server 2013-Bereitstellung (auf der die lync Server 2013-Systemsteuerung installiert ist) zur **CSAdministrator** -Gruppe hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="3bd3f-106">Use Active Directory Computers and Users to add the Active Directory user object of the administrator role for the Lync Server 2013 deployment (on which Lync Server 2013 Control Panel is installed) to the **CSAdministrator** group.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="3bd3f-107">Wenn Sie die entsprechenden Benutzer und Gruppen nicht zur CsAdministors-Gruppe hinzufügen, wird beim Öffnen der lync Server-Systemsteuerung eine Fehlermeldung angezeigt, die besagt, dass "nicht autorisiert: der Zugriff verweigert wird, weil ein Autorisierungsfehler bei der rollenbasierten Zugriffssteuerung (Role-Based Access Control, RBAC)" vorliegt.</span><span class="sxs-lookup"><span data-stu-id="3bd3f-107">If you do not add the appropriate users and groups to the CsAdministors group, you will receive an error when opening Lync Server Control Panel, which states that “Unauthorized: Access is denied due to a role-based access control (RBAC) authorization failure.”</span></span>

    
    </div>

2.  <span data-ttu-id="3bd3f-108">Wenn das Benutzerobjekt derzeit angemeldet ist, melden Sie es ab und wieder an, um die neue Gruppenzuweisung zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="3bd3f-108">If the user object is currently logged on, log off and then log on again to register the new group assignment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3bd3f-109">Das Benutzerkonto kann nicht der lokale Administrator eines Servers sein, auf dem lync Server 2013 ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="3bd3f-109">The user account cannot be the local administrator of any server running Lync Server 2013.</span></span>

    
    </div>

3.  <span data-ttu-id="3bd3f-110">Verwenden Sie das Administratorkonto, um sich bei dem Computer anzumelden, auf dem die lync Server-Systemsteuerung installiert ist.</span><span class="sxs-lookup"><span data-stu-id="3bd3f-110">Use the administrative account to log on to the computer where Lync Server Control Panel is installed.</span></span>

4.  <span data-ttu-id="3bd3f-111">Starten Sie die lync Server-Systemsteuerung, und geben Sie dann die Anmeldeinformationen ein, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="3bd3f-111">Start Lync Server Control Panel, and then provide credentials, if prompted.</span></span> <span data-ttu-id="3bd3f-112">In der lync Server-Systemsteuerung werden Bereitstellungsinformationen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3bd3f-112">Lync Server Control Panel displays deployment information.</span></span>

5.  <span data-ttu-id="3bd3f-113">Klicken Sie in der linken Navigationsleiste auf **Topologie**, und stellen Sie dann sicher, dass der Dienststatus einen Computer mit einem grünen Pfeil anzeigt und ein grünes Häkchen für den Replikationsstatus neben jeder lync Server-Serverrolle vorhanden ist, die bereitgestellt und online geschaltet wurde.</span><span class="sxs-lookup"><span data-stu-id="3bd3f-113">In the left navigation bar, click **Topology**, and then confirm that the service status shows a computer with a green arrow and that a green check mark for replication status is next to each Lync Server server role that has been deployed and brought online.</span></span>

6.  <span data-ttu-id="3bd3f-114">Klicken Sie in der linken Navigationsleiste auf **Benutzer** und dann auf **Benutzer aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="3bd3f-114">In the left navigation bar, click **Users**, and then click **Enable users**.</span></span>

7.  <span data-ttu-id="3bd3f-115">Klicken Sie auf der Seite **neuer lync Server-Benutzer** auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="3bd3f-115">On the **New Lync Server User** page, click **Add**.</span></span>

8.  <span data-ttu-id="3bd3f-116">Wenn Sie Suchparameter für die zu ermittelnden Objekte definieren möchten, aktivieren Sie auf der Seite **Aus Active Directory auswählen** die Option **Suchen** und klicken Sie optional auf **Filter hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="3bd3f-116">To define search parameters for the objects you want to find, on the **Select from Active Directory** page, you can select **Search**, and then optionally click **Add Filter**.</span></span> <span data-ttu-id="3bd3f-117">Alternativ können Sie auch die Option **LDAP-Suche** aktivieren und einen LDAP-Ausdruck eingeben, um die zurückgegebenen Objekte zu filtern oder einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="3bd3f-117">You can also select **LDAP search** and enter an LDAP expression to filter or limit the objects that will be returned.</span></span> <span data-ttu-id="3bd3f-118">Nachdem Sie sich für Ihre Suchoptionen entschieden haben, **Suchen**Sie nach dem Klirren.</span><span class="sxs-lookup"><span data-stu-id="3bd3f-118">After you have decided on your Search options, clink **Find**.</span></span>

9.  <span data-ttu-id="3bd3f-119">Wählen Sie im Bereich Suchergebnisse alle Objekte für diese Suchsitzung aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3bd3f-119">In the Search results pane, select all the objects for this search session, and then click **OK**.</span></span>

10. <span data-ttu-id="3bd3f-120">Auf der **neuen lync Server-Benutzer** Seite befinden sich die ausgewählten Objekte in der Ansicht **Benutzer** .</span><span class="sxs-lookup"><span data-stu-id="3bd3f-120">On the **New Lync Server User** page, the object or objects you selected are in the **Users** display.</span></span> <span data-ttu-id="3bd3f-121">Wählen Sie in der Liste **Benutzer einem Pool zuweisen** den Server aus, auf dem die Objekte verwaltet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="3bd3f-121">In the **Assign users to a pool** list, select the server where the objects should be homed.</span></span>
    
    <span data-ttu-id="3bd3f-122">Im folgenden finden Sie eine Reihe von Optionen zum Konfigurieren der Objekte.</span><span class="sxs-lookup"><span data-stu-id="3bd3f-122">Following are a number of options for configuring the objects.</span></span>
    
      - <span data-ttu-id="3bd3f-123">**SIP-URI für den Benutzer generieren**</span><span class="sxs-lookup"><span data-stu-id="3bd3f-123">**Generate user’s SIP URI**</span></span>
    
      - <span data-ttu-id="3bd3f-124">**Telefonie**</span><span class="sxs-lookup"><span data-stu-id="3bd3f-124">**Telephony**</span></span>
    
      - <span data-ttu-id="3bd3f-125">**Anschluss-URI**</span><span class="sxs-lookup"><span data-stu-id="3bd3f-125">**Line URI**</span></span>
    
      - <span data-ttu-id="3bd3f-126">**Konferenzrichtlinie**</span><span class="sxs-lookup"><span data-stu-id="3bd3f-126">**Conferencing policy**</span></span>
    
      - <span data-ttu-id="3bd3f-127">**Clientversionsrichtlinie**</span><span class="sxs-lookup"><span data-stu-id="3bd3f-127">**Client version policy**</span></span>
    
      - <span data-ttu-id="3bd3f-128">**PIN-Richtlinie**</span><span class="sxs-lookup"><span data-stu-id="3bd3f-128">**PIN policy**</span></span>
    
      - <span data-ttu-id="3bd3f-129">**Externe Zugriffsrichtlinie**</span><span class="sxs-lookup"><span data-stu-id="3bd3f-129">**External access policy**</span></span>
    
      - <span data-ttu-id="3bd3f-130">**Archivierungsrichtlinie**</span><span class="sxs-lookup"><span data-stu-id="3bd3f-130">**Archiving policy**</span></span>
    
      - <span data-ttu-id="3bd3f-131">**Standortrichtlinie**</span><span class="sxs-lookup"><span data-stu-id="3bd3f-131">**Location policy**</span></span>
    
      - <span data-ttu-id="3bd3f-132">**Clientrichtlinie**</span><span class="sxs-lookup"><span data-stu-id="3bd3f-132">**Client policy**</span></span>
    
    <span data-ttu-id="3bd3f-133">Wenn Sie die grundlegenden Funktionen testen möchten, wählen Sie die gewünschte Option für die **SIP-URI-Einstellung des Benutzers generieren** aus (die anderen Optionen in der Konfiguration verwenden Standardeinstellungen), und klicken Sie dann auf **aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="3bd3f-133">For the purposes of testing the basic functionality, select the option you prefer for the **Generate user’s SIP URI** setting (the other options in the configuration will use default settings), and then click **Enable**.</span></span>

11. <span data-ttu-id="3bd3f-134">Eine Zusammenfassungsseite wird angezeigt, die ein Häkchen in der Spalte " **aktiviert** " zeigt, um anzugeben, dass die Objekte nun einsatzbereit sind.</span><span class="sxs-lookup"><span data-stu-id="3bd3f-134">A summary page is displayed that shows a check mark in the **Enabled** column to indicate that the objects are now ready for use.</span></span> <span data-ttu-id="3bd3f-135">In der Spalte **SIP-Adresse** wird die Adresse angezeigt, die Sie zur Konfiguration der Benutzeranmeldung benötigen.</span><span class="sxs-lookup"><span data-stu-id="3bd3f-135">The **SIP address** column displays the address you need for the user sign-in configuration.</span></span>

12. <span data-ttu-id="3bd3f-136">Melden Sie einen Benutzer auf einem Computer, der mit der Domäne verbunden ist, und einem anderen Benutzer auf einem anderen Computer in der Domäne an.</span><span class="sxs-lookup"><span data-stu-id="3bd3f-136">Log one user on to a computer that is joined to the domain, and another user on to another computer in the domain.</span></span>

13. <span data-ttu-id="3bd3f-137">Installieren Sie lync 2013 auf jedem der beiden Clientcomputer, und überprüfen Sie, ob sich beide Benutzer bei lync Server 2013 anmelden können, und können Sie sich gegenseitig Sofortnachrichten senden.</span><span class="sxs-lookup"><span data-stu-id="3bd3f-137">Install Lync 2013 on each of the two client computers, and then verify that both users can sign in to Lync Server 2013 and can send instant messages to each other.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3bd3f-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3bd3f-138">See Also</span></span>


[<span data-ttu-id="3bd3f-139">Bereitstellen von Clients und Geräten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3bd3f-139">Deploying clients and devices in Lync Server 2013</span></span>](lync-server-2013-deploying-clients-and-devices.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

