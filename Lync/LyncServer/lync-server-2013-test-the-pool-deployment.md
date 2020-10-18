---
title: 'Lync Server 2013: Testen der Pool Bereitstellung'
description: 'Lync Server 2013: Testen der Pool Bereitstellung.'
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
ms.openlocfilehash: 28101a252eda5048ded9f1eaf76c092c5cb7f986
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576041"
---
# <a name="test-the-pool-deployment-in-lync-server-2013"></a><span data-ttu-id="0ad3c-103">Testen der Pool Bereitstellung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ad3c-103">Test the pool deployment in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0ad3c-104">_**Letztes Änderungsstand des Themas:** 2013-09-25_</span><span class="sxs-lookup"><span data-stu-id="0ad3c-104">_**Topic Last Modified:** 2013-09-25_</span></span>

<span data-ttu-id="0ad3c-105">Im folgenden Verfahren wird beschrieben, wie Sie die Bereitstellung des Front-End-Pool testen.</span><span class="sxs-lookup"><span data-stu-id="0ad3c-105">The following procedure describes how to test the deployment of the Front End pool.</span></span>

<div>

## <a name="to-test-the-pool-deployment"></a><span data-ttu-id="0ad3c-106">So testen Sie die Pool Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="0ad3c-106">To test the pool deployment</span></span>

1.  <span data-ttu-id="0ad3c-107">Verwenden Sie Active Directory Computer und Benutzer, um das Active Directory Benutzerobjekt der Administratorrolle für die lync Server 2013-Bereitstellung (in der lync Server 2013 Systemsteuerung installiert ist) zur Gruppe **CSAdministrator** hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="0ad3c-107">Use Active Directory Computers and Users to add the Active Directory user object of the administrator role for the Lync Server 2013 deployment (on which Lync Server 2013 Control Panel is installed) to the **CSAdministrator** group.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="0ad3c-108">Wenn Sie die entsprechenden Benutzer und Gruppen nicht zur Gruppe CsAdministors hinzufügen, wird beim Öffnen von lync Server-Systemsteuerung eine Fehlermeldung angezeigt, die besagt, dass "nicht autorisiert: der Zugriff aufgrund eines RBAC-Autorisierungs Fehlers (Role-Based Access Control) verweigert wird."</span><span class="sxs-lookup"><span data-stu-id="0ad3c-108">If you do not add the appropriate users and groups to the CsAdministors group, you will receive an error when opening Lync Server Control Panel, which states that “Unauthorized: Access is denied due to a role-based access control (RBAC) authorization failure.”</span></span>

    
    </div>

2.  <span data-ttu-id="0ad3c-109">Wenn das Benutzerobjekt derzeit angemeldet ist, melden Sie es ab und wieder an, um die neue Gruppenzuweisung zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="0ad3c-109">If the user object is currently logged on, log off and then log on again to register the new group assignment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0ad3c-110">Das Benutzerkonto kann nicht der lokale Administrator eines beliebigen Servers mit lync Server 2013 sein.</span><span class="sxs-lookup"><span data-stu-id="0ad3c-110">The user account cannot be the local administrator of any server running Lync Server 2013.</span></span>

    
    </div>

3.  <span data-ttu-id="0ad3c-111">Melden Sie sich mit dem Administratorkonto bei dem Computer an, auf dem lync Server-Systemsteuerung installiert ist.</span><span class="sxs-lookup"><span data-stu-id="0ad3c-111">Use the administrative account to log on to the computer where Lync Server Control Panel is installed.</span></span>

4.  <span data-ttu-id="0ad3c-112">Starten Sie lync Server-Systemsteuerung, und geben Sie dann bei Aufforderung Anmeldeinformationen ein.</span><span class="sxs-lookup"><span data-stu-id="0ad3c-112">Start Lync Server Control Panel, and then provide credentials, if prompted.</span></span> <span data-ttu-id="0ad3c-113">Lync Server-Systemsteuerung zeigt Bereitstellungsinformationen an.</span><span class="sxs-lookup"><span data-stu-id="0ad3c-113">Lync Server Control Panel displays deployment information.</span></span>

5.  <span data-ttu-id="0ad3c-114">Klicken Sie in der linken Navigationsleiste auf **Topologie**, und vergewissern Sie sich dann, dass der Dienststatus einen Computer mit einem grünen Pfeil anzeigt und dass neben jeder lync Server Server Rolle, die bereitgestellt und online geschaltet wurde, ein grünes Häkchen für den Replikationsstatus ist.</span><span class="sxs-lookup"><span data-stu-id="0ad3c-114">In the left navigation bar, click **Topology**, and then confirm that the service status shows a computer with a green arrow and that a green check mark for replication status is next to each Lync Server server role that has been deployed and brought online.</span></span>

6.  <span data-ttu-id="0ad3c-115">Klicken Sie in der linken Navigationsleiste auf **Benutzer**, und klicken Sie dann auf **Benutzer aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="0ad3c-115">In the left navigation bar, click **Users**, and then click **Enable users**.</span></span>

7.  <span data-ttu-id="0ad3c-116">Klicken Sie auf der Seite **neuer lync Server Benutzer** auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="0ad3c-116">On the **New Lync Server User** page, click **Add**.</span></span>

8.  <span data-ttu-id="0ad3c-117">Zum Definieren von Suchparametern für die Objekte, die Sie suchen möchten, können Sie auf der Seite **Active Directory auswählen** die Option **Suche**auswählen und dann optional auf **Filter hinzufügen**klicken.</span><span class="sxs-lookup"><span data-stu-id="0ad3c-117">To define search parameters for the objects you want to find, on the **Select from Active Directory** page, you can select **Search**, and then optionally click **Add Filter**.</span></span> <span data-ttu-id="0ad3c-118">Sie können auch **LDAP-Suche** auswählen und einen LDAP-Ausdruck eingeben, um die zurückzugebenden Objekte zu filtern oder einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="0ad3c-118">You can also select **LDAP search** and enter an LDAP expression to filter or limit the objects that will be returned.</span></span> <span data-ttu-id="0ad3c-119">Nachdem Sie sich für Ihre Suchoptionen entschieden haben, **finden**Sie Klirren.</span><span class="sxs-lookup"><span data-stu-id="0ad3c-119">After you have decided on your Search options, clink **Find**.</span></span>

9.  <span data-ttu-id="0ad3c-120">Wählen Sie im Bereich Suchergebnisse alle Objekte für diese Suchsitzung aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="0ad3c-120">In the Search results pane, select all the objects for this search session, and then click **OK**.</span></span>

10. <span data-ttu-id="0ad3c-121">Auf der Seite **neuer lync Server Benutzer** befinden sich die ausgewählten Objekte in der **Benutzer** Anzeige.</span><span class="sxs-lookup"><span data-stu-id="0ad3c-121">On the **New Lync Server User** page, the object or objects you selected are in the **Users** display.</span></span> <span data-ttu-id="0ad3c-122">Wählen Sie in der Liste **Benutzer einem Pool zuweisen** den Server aus, auf dem die Objekte verwaltet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0ad3c-122">In the **Assign users to a pool** list, select the server where the objects should be homed.</span></span>
    
    <span data-ttu-id="0ad3c-123">Im folgenden finden Sie eine Reihe von Optionen zum Konfigurieren der Objekte.</span><span class="sxs-lookup"><span data-stu-id="0ad3c-123">Following are a number of options for configuring the objects.</span></span>
    
      - <span data-ttu-id="0ad3c-124">**SIP-URI des Benutzers generieren**</span><span class="sxs-lookup"><span data-stu-id="0ad3c-124">**Generate user’s SIP URI**</span></span>
    
      - <span data-ttu-id="0ad3c-125">**Telefonie**</span><span class="sxs-lookup"><span data-stu-id="0ad3c-125">**Telephony**</span></span>
    
      - <span data-ttu-id="0ad3c-126">**Anschluss-URI**</span><span class="sxs-lookup"><span data-stu-id="0ad3c-126">**Line URI**</span></span>
    
      - <span data-ttu-id="0ad3c-127">**Konferenzrichtlinie**</span><span class="sxs-lookup"><span data-stu-id="0ad3c-127">**Conferencing policy**</span></span>
    
      - <span data-ttu-id="0ad3c-128">**Client Versionsrichtlinie**</span><span class="sxs-lookup"><span data-stu-id="0ad3c-128">**Client version policy**</span></span>
    
      - <span data-ttu-id="0ad3c-129">**PIN-Richtlinie**</span><span class="sxs-lookup"><span data-stu-id="0ad3c-129">**PIN policy**</span></span>
    
      - <span data-ttu-id="0ad3c-130">**Richtlinie für den externen Zugriff**</span><span class="sxs-lookup"><span data-stu-id="0ad3c-130">**External access policy**</span></span>
    
      - <span data-ttu-id="0ad3c-131">**Archivierungsrichtlinie**</span><span class="sxs-lookup"><span data-stu-id="0ad3c-131">**Archiving policy**</span></span>
    
      - <span data-ttu-id="0ad3c-132">**Standortrichtlinie**</span><span class="sxs-lookup"><span data-stu-id="0ad3c-132">**Location policy**</span></span>
    
      - <span data-ttu-id="0ad3c-133">**Client Richtlinie**</span><span class="sxs-lookup"><span data-stu-id="0ad3c-133">**Client policy**</span></span>
    
    <span data-ttu-id="0ad3c-134">Zum Testen der grundlegenden Funktionalität wählen Sie die gewünschte Option für die **SIP-URI-Einstellung des Benutzers generieren** (die anderen Optionen in der Konfiguration verwenden Standardeinstellungen), und klicken Sie dann auf **aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="0ad3c-134">For the purposes of testing the basic functionality, select the option you prefer for the **Generate user’s SIP URI** setting (the other options in the configuration will use default settings), and then click **Enable**.</span></span>

11. <span data-ttu-id="0ad3c-135">Eine Zusammenfassungsseite wird angezeigt, die ein Häkchen in der Spalte **aktiviert** zeigt, um anzugeben, dass die Objekte nun zur Verwendung bereit sind.</span><span class="sxs-lookup"><span data-stu-id="0ad3c-135">A summary page is displayed that shows a check mark in the **Enabled** column to indicate that the objects are now ready for use.</span></span> <span data-ttu-id="0ad3c-136">In der Spalte **SIP-Adresse** wird die Adresse angezeigt, die Sie für die Benutzeranmelde Konfiguration benötigen.</span><span class="sxs-lookup"><span data-stu-id="0ad3c-136">The **SIP address** column displays the address you need for the user sign-in configuration.</span></span>

12. <span data-ttu-id="0ad3c-137">Melden Sie einen Benutzer bei einem Computer an, der der Domäne beigetreten ist, und ein anderer Benutzer auf einem anderen Computer in der Domäne.</span><span class="sxs-lookup"><span data-stu-id="0ad3c-137">Log one user on to a computer that is joined to the domain, and another user on to another computer in the domain.</span></span>

13. <span data-ttu-id="0ad3c-138">Installieren Sie lync 2013 auf den beiden Clientcomputern, und stellen Sie dann sicher, dass sich beide Benutzer bei lync Server 2013 anmelden und Sofortnachrichten miteinander senden können.</span><span class="sxs-lookup"><span data-stu-id="0ad3c-138">Install Lync 2013 on each of the two client computers, and then verify that both users can sign in to Lync Server 2013 and can send instant messages to each other.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0ad3c-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0ad3c-139">See Also</span></span>


[<span data-ttu-id="0ad3c-140">Bereitstellen von Clients und Geräten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ad3c-140">Deploying clients and devices in Lync Server 2013</span></span>](lync-server-2013-deploying-clients-and-devices.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

