---
title: Überprüfen Sie die Topologie in Skype für Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/14/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a4f4bad1-fc59-47ce-a3ea-b1b893769db6
description: 'Zusammenfassung: Informationen zum Überprüfen der Skype für Business Server-Topologie und Active Directory-Server wie erwartet funktionieren. Laden Sie eine kostenlose Testversion von Skype für Business Server aus dem Microsoft Evaluation Center herunter: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: 03dfb45c03aa104cc5a9b265a37c347380590877
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30896421"
---
# <a name="verify-the-topology-in-skype-for-business-server"></a><span data-ttu-id="007fb-104">Überprüfen Sie die Topologie in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="007fb-104">Verify the topology in Skype for Business Server</span></span>
 
<span data-ttu-id="007fb-105">**Zusammenfassung:** Erfahren Sie, wie die Skype für Business Server-Topologie überprüfen und Active Directory-Server wie erwartet funktionieren.</span><span class="sxs-lookup"><span data-stu-id="007fb-105">**Summary:** Learn how to verify the Skype for Business Server topology and Active Directory servers are working as expected.</span></span> <span data-ttu-id="007fb-106">Laden Sie eine kostenlose Testversion von Skype für Business Server aus dem [Microsoft-Evaluierungscenter](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="007fb-106">Download a free trial of Skype for Business Server from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="007fb-107">Nachdem Sie die Topologie veröffentlicht und die Skype für Business Server Systemkomponenten auf jedem Server in der Topologie installiert haben, können Sie überprüfen, ob die Topologie wie erwartet funktioniert.</span><span class="sxs-lookup"><span data-stu-id="007fb-107">After you have the topology published and the Skype for Business Server system components installed on each of the servers in the topology, you are ready to verify that the topology is working as expected.</span></span> <span data-ttu-id="007fb-108">Dazu gehören, die die Konfiguration aller Active Directory-Server weitergegeben wurde, damit die gesamte Domäne bekannt ist, dass Skype für Unternehmen verfügbar ist, in der Domäne überprüfen.</span><span class="sxs-lookup"><span data-stu-id="007fb-108">This includes verifying that the configuration has propagated out to all of the Active Directory servers so that the entire domain knows Skype for Business is available in the domain.</span></span> <span data-ttu-id="007fb-109">Sie können die Schritte 1 bis 5 in einer beliebigen Reihenfolge ausführen.</span><span class="sxs-lookup"><span data-stu-id="007fb-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="007fb-110">Die Schritte 6, 7 und 8 müssen jedoch wie in der Abbildung dargestellt nacheinander und nach den Schritten 1 bis 5 ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="007fb-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="007fb-111">Überprüfen der Topologie wird in Schritt 8 des 8.</span><span class="sxs-lookup"><span data-stu-id="007fb-111">Verifying the topology is step 8 of 8.</span></span>
  
![Übersichtsdiagramm.](../../media/c8698b53-1282-4978-a9a6-ca3f7a778f60.png)
  
## <a name="test-the-front-end-pool-deployment"></a><span data-ttu-id="007fb-113">Testen der Front-End-Poolbereitstellung</span><span class="sxs-lookup"><span data-stu-id="007fb-113">Test the Front End pool deployment</span></span>

<span data-ttu-id="007fb-114">Der letzte Schritt besteht, testen den Front-End-Pool, und stellen Sie sicher, dass Skype für Business Clients miteinander kommunizieren kann.</span><span class="sxs-lookup"><span data-stu-id="007fb-114">The final step is to test the Front End pool and confirm that Skype for Business clients can communicate with each other.</span></span> 
  
### <a name="add-users-and-verify-client-connectivity"></a><span data-ttu-id="007fb-115">Hinzufügen von Benutzern und Überprüfen der Clientkonnektivität</span><span class="sxs-lookup"><span data-stu-id="007fb-115">Add users and verify client connectivity</span></span>

1. <span data-ttu-id="007fb-116">Verwenden Sie Active Directory-Computer und Benutzer hinzufügen, das Active Directory-Benutzerobjekt der Administratorrolle für die Skype für Business Server-Bereitstellung (auf dem Skype Business Server-Systemsteuerung installiert ist) der Gruppe **csadministrator hinzu** .</span><span class="sxs-lookup"><span data-stu-id="007fb-116">Use Active Directory Computers and Users to add the Active Directory user object of the administrator role for the Skype for Business Server deployment (on which Skype for Business Server Control Panel is installed) to the **CSAdministrator** group.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="007fb-117">Wenn Sie nicht die entsprechenden Benutzer und Gruppen zur Gruppe CsAdministors hinzufügen, wird eine Fehlermeldung beim Öffnen von Skype Business Server-Systemsteuerung die liest, "nicht autorisiert: Zugriff verweigert aufgrund einer rollenbasierten Zugriffssteuerung (RBAC) Autorisierungsfehler ."</span><span class="sxs-lookup"><span data-stu-id="007fb-117">If you do not add the appropriate users and groups to the CsAdministors group, you will receive an error when you open Skype for Business Server Control Panel which reads, "Unauthorized: Access is denied due to a role-based access control (RBAC) authorization failure."</span></span> 
  
2. <span data-ttu-id="007fb-118">Wenn das Benutzerobjekt derzeit angemeldet ist, melden Sie es ab und wieder an, um die neue Gruppenzuweisung zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="007fb-118">If the user object is currently logged on, log off and then log on again to register the new group assignment.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="007fb-119">Das Benutzerkonto darf nicht den lokalen Administrator eines Servers mit Skype für Business Server sein.</span><span class="sxs-lookup"><span data-stu-id="007fb-119">The user account cannot be the local administrator of any server running Skype for Business Server.</span></span> 
  
3. <span data-ttu-id="007fb-120">Verwenden Sie das Administratorkonto zur Anmeldung bei dem Computer, auf dem Skype Business Server-Systemsteuerung installiert ist.</span><span class="sxs-lookup"><span data-stu-id="007fb-120">Use the administrative account to log on to the computer where Skype for Business Server Control Panel is installed.</span></span>
    
4. <span data-ttu-id="007fb-121">Starten Sie Skype Business Server-Systemsteuerung, und klicken Sie dann die Anmeldeinformationen Sie, wenn Sie aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="007fb-121">Start Skype for Business Server Control Panel, and then provide credentials, if prompted.</span></span> <span data-ttu-id="007fb-122">Skype für Business Server-Systemsteuerung zeigt Informationen zur Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="007fb-122">Skype for Business Server Control Panel displays deployment information.</span></span>
    
5. <span data-ttu-id="007fb-123">In der linken Navigationsleiste auf **Topologie**, und stellen dann sicher, dass der Dienststatus auf einen Computer mit einem grünen Pfeil zeigt und für Replikationsstatus ein grünes Häkchen neben jedem Skype für Business Server-Rolle ist, die bereitgestellt und online geschaltet wurde.</span><span class="sxs-lookup"><span data-stu-id="007fb-123">In the left navigation bar, click **Topology**, and then confirm that the service status shows a computer with a green arrow and that a green check mark for replication status is next to each Skype for Business Server role that has been deployed and brought online.</span></span> 
    
6. <span data-ttu-id="007fb-124">Klicken Sie in der linken Navigationsleiste auf **Benutzer** und dann auf **Benutzer aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="007fb-124">In the left navigation bar, click **Users**, and then click **Enable users**.</span></span> 
    
7. <span data-ttu-id="007fb-125">Klicken Sie auf der Seite **Neue Skype für Business Server-Benutzer** auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="007fb-125">On the **New Skype for Business Server User** page, click **Add**.</span></span>
    
8. <span data-ttu-id="007fb-p105">Wenn Sie Suchparameter für die zu ermittelnden Objekte definieren möchten, aktivieren Sie auf der Seite **Aus Active Directory auswählen** die Option **Suchen** und klicken Sie optional auf **Filter hinzufügen**. Alternativ können Sie auch die Option **LDAP-Suche** aktivieren und einen LDAP-Ausdruck eingeben, um die zurückgegebenen Objekte zu filtern oder einzuschränken. Klicken Sie auf **Suchen**, nachdem Sie die gewünschten Suchoptionen festgelegt haben.</span><span class="sxs-lookup"><span data-stu-id="007fb-p105">To define search parameters for the objects you want to find, on the **Select from Active Directory** page, you can select **Search**, and then optionally click **Add Filter**. You can also select **LDAP search** and enter an LDAP expression to filter or limit the objects that will be returned. After you have decided on your Search options, click **Find**.</span></span>
    
9. <span data-ttu-id="007fb-129">Wählen Sie im Bereich mit den Suchergebnissen alle hinzuzufügenden Benutzer aus und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="007fb-129">In the Search results pane, select the users you want to add, and then click **OK**.</span></span>
    
10. <span data-ttu-id="007fb-130">Auf der Seite **Neue Skype für Business Server-Benutzer** sind in die Anzeige der **Benutzer** die Benutzer gewählte.</span><span class="sxs-lookup"><span data-stu-id="007fb-130">On the **New Skype for Business Server User** page, the users you selected are in the **Users** display.</span></span> <span data-ttu-id="007fb-131">In the **Assign users to a pool** list, select the server where the users should reside.</span><span class="sxs-lookup"><span data-stu-id="007fb-131">In the **Assign users to a pool** list, select the server where the users should reside.</span></span>
    
    <span data-ttu-id="007fb-132">Im Folgenden finden Sie eine Liste der Optionen, die Sie zum Konfigurieren der Objekte verwenden können.</span><span class="sxs-lookup"><span data-stu-id="007fb-132">The following is a list of options you can use to configure the objects.</span></span>
    
    - <span data-ttu-id="007fb-133">**Generieren von SIP-URI des Benutzers**</span><span class="sxs-lookup"><span data-stu-id="007fb-133">**Generate user's SIP URI**</span></span>
    
    - <span data-ttu-id="007fb-134">**Telefonie**</span><span class="sxs-lookup"><span data-stu-id="007fb-134">**Telephony**</span></span>
    
    - <span data-ttu-id="007fb-135">**Anschluss-URI**</span><span class="sxs-lookup"><span data-stu-id="007fb-135">**Line URI**</span></span>
    
    - <span data-ttu-id="007fb-136">**Konferenzrichtlinie**</span><span class="sxs-lookup"><span data-stu-id="007fb-136">**Conferencing policy**</span></span>
    
    - <span data-ttu-id="007fb-137">**Clientversionsrichtlinie**</span><span class="sxs-lookup"><span data-stu-id="007fb-137">**Client version policy**</span></span>
    
    - <span data-ttu-id="007fb-138">**PIN-Richtlinie**</span><span class="sxs-lookup"><span data-stu-id="007fb-138">**PIN policy**</span></span>
    
    - <span data-ttu-id="007fb-139">**Externe Zugriffsrichtlinie**</span><span class="sxs-lookup"><span data-stu-id="007fb-139">**External access policy**</span></span>
    
    - <span data-ttu-id="007fb-140">**Archivierungsrichtlinie**</span><span class="sxs-lookup"><span data-stu-id="007fb-140">**Archiving policy**</span></span>
    
    - <span data-ttu-id="007fb-141">**Standortrichtlinie**</span><span class="sxs-lookup"><span data-stu-id="007fb-141">**Location policy**</span></span>
    
    - <span data-ttu-id="007fb-142">**Clientrichtlinie**</span><span class="sxs-lookup"><span data-stu-id="007fb-142">**Client policy**</span></span>
    
    <span data-ttu-id="007fb-143">Um die grundlegenden Funktionen testen möchten, wählen Sie die Option, die Sie bevorzugen für die **SIP-URI des Benutzers generieren** -Einstellung (die anderen Optionen in der Standardeinstellungen Konfiguration verwenden), die und klicken Sie dann auf **Aktivieren**, wie in der Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="007fb-143">To test the basic functionality, select the option you prefer for the **Generate user's SIP URI** setting (the other options in the configuration use default settings), and then click **Enable**, as shown in the figure.</span></span>
    
     ![Aktivieren von Benutzern in der Systemsteuerung](../../media/7ee8717d-9a1f-4864-8f45-71071c88878f.png)
  
11. <span data-ttu-id="007fb-p107">Es wird eine Zusammenfassungsseite angezeigt, auf der ein Häkchen in der Spalte **Aktiviert** darauf hinweist, dass die Benutzer eingerichtet sind. In der Spalte **SIP-Adresse** wird die Adresse angezeigt, die Sie zur Konfiguration der Benutzeranmeldung benötigen.</span><span class="sxs-lookup"><span data-stu-id="007fb-p107">A summary page is displayed that shows a check mark in the **Enabled** column to indicate that the users are setup. The **SIP address** column displays the address you need for the user sign-in configuration.</span></span>
    
     ![Benutzer, die der Skype for Business Server-Systemsteuerung hinzugefügt wurden](../../media/8960548a-8d6d-44c5-bc01-6f9fb11b7588.png)
  
12. <span data-ttu-id="007fb-148">Melden Sie einen Benutzer bei einem Computer an, der mit der Domäne verknüpft ist, und einen weiteren Benutzer bei einem anderen Computer in der Domäne.</span><span class="sxs-lookup"><span data-stu-id="007fb-148">Log one user on to a computer that is joined to the domain and another user on to another computer in the domain.</span></span>
    
13. <span data-ttu-id="007fb-149">Installieren von Skype für Business-Client auf jedem den beiden Clientcomputern, und stellen Sie sicher, dass beide Benutzer sich zu Skype für Business Server anmelden können und Sofortnachrichten austauschen senden können.</span><span class="sxs-lookup"><span data-stu-id="007fb-149">Install Skype for Business client on each of the two client computers, and then verify that both users can sign in to Skype for Business Server and can send instant messages to each other.</span></span>
    

