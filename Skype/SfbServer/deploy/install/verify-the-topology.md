---
title: Überprüfen der Topologie in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a4f4bad1-fc59-47ce-a3ea-b1b893769db6
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie überprüfen können, ob die Skype for Business Server-Topologie und die Active Directory-Server wie erwartet funktionieren. Laden Sie eine ﻿kostenlose Testversion von Skype for Business Server aus dem Microsoft Evaluation https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverCenter unter: herunter.'
ms.openlocfilehash: 6c7d7a67cab2cbd383ee26eb64f478985bcc4b27
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245236"
---
# <a name="verify-the-topology-in-skype-for-business-server"></a><span data-ttu-id="37fd3-104">Überprüfen der Topologie in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="37fd3-104">Verify the topology in Skype for Business Server</span></span>
 
<span data-ttu-id="37fd3-105">**Zusammenfassung:** Erfahren Sie, wie Sie überprüfen können, ob die Skype for Business Server-Topologie und die Active Directory-Server wie erwartet funktionieren.</span><span class="sxs-lookup"><span data-stu-id="37fd3-105">**Summary:** Learn how to verify the Skype for Business Server topology and Active Directory servers are working as expected.</span></span> <span data-ttu-id="37fd3-106">Laden Sie eine ﻿kostenlose Testversion von Skype for Business Server vom [Microsoft Evaluation Center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)herunter.</span><span class="sxs-lookup"><span data-stu-id="37fd3-106">Download a free trial of Skype for Business Server from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="37fd3-107">Nachdem Sie die Topologie veröffentlicht haben und die Systemkomponenten von Skype for Business Server auf jedem der Server in der Topologie installiert sind, können Sie überprüfen, ob die Topologie wie erwartet funktioniert.</span><span class="sxs-lookup"><span data-stu-id="37fd3-107">After you have the topology published and the Skype for Business Server system components installed on each of the servers in the topology, you are ready to verify that the topology is working as expected.</span></span> <span data-ttu-id="37fd3-108">Dies umfasst die Überprüfung, ob die Konfiguration an alle Active Directory-Server weitergegeben wurde, damit die gesamte Domäne weiß, dass Skype for Business in der Domäne verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="37fd3-108">This includes verifying that the configuration has propagated out to all of the Active Directory servers so that the entire domain knows Skype for Business is available in the domain.</span></span> <span data-ttu-id="37fd3-109">Sie können die Schritte 1 bis 5 in einer beliebigen Reihenfolge ausführen.</span><span class="sxs-lookup"><span data-stu-id="37fd3-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="37fd3-110">Die Schritte 6, 7 und 8 müssen jedoch wie in der Abbildung dargestellt nacheinander und nach den Schritten 1 bis 5 ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="37fd3-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="37fd3-111">Die Überprüfung der Topologie ist Schritt 8 von 8.</span><span class="sxs-lookup"><span data-stu-id="37fd3-111">Verifying the topology is step 8 of 8.</span></span>
  
![Übersichtsdiagramm.](../../media/c8698b53-1282-4978-a9a6-ca3f7a778f60.png)
  
## <a name="test-the-front-end-pool-deployment"></a><span data-ttu-id="37fd3-113">Testen der Front-End-Poolbereitstellung</span><span class="sxs-lookup"><span data-stu-id="37fd3-113">Test the Front End pool deployment</span></span>

<span data-ttu-id="37fd3-114">Der letzte Schritt besteht darin, den Front-End-Pool zu testen und zu bestätigen, dass Skype for Business-Clients miteinander kommunizieren können.</span><span class="sxs-lookup"><span data-stu-id="37fd3-114">The final step is to test the Front End pool and confirm that Skype for Business clients can communicate with each other.</span></span> 
  
### <a name="add-users-and-verify-client-connectivity"></a><span data-ttu-id="37fd3-115">Hinzufügen von Benutzern und Überprüfen der Clientkonnektivität</span><span class="sxs-lookup"><span data-stu-id="37fd3-115">Add users and verify client connectivity</span></span>

1. <span data-ttu-id="37fd3-116">Verwenden Sie Active Directory-Computer und-Benutzer zum Hinzufügen des Active Directory-Benutzerobjekts der Administratorrolle für die Skype for Business Server-Bereitstellung (auf der Skype for Business Server-Systemsteuerung installiert ist) zur **CSAdministrator** -Gruppe.</span><span class="sxs-lookup"><span data-stu-id="37fd3-116">Use Active Directory Computers and Users to add the Active Directory user object of the administrator role for the Skype for Business Server deployment (on which Skype for Business Server Control Panel is installed) to the **CSAdministrator** group.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="37fd3-117">Wenn Sie die entsprechenden Benutzer und Gruppen nicht zur CsAdministors-Gruppe hinzufügen, erhalten Sie eine Fehlermeldung, wenn Sie die Skype for Business Server-Systemsteuerung öffnen, die lautet: "nicht autorisiert: Zugriff verweigert aufgrund eines Autorisierungs Fehlers bei der rollenbasierten Zugriffssteuerung (RBAC) ."</span><span class="sxs-lookup"><span data-stu-id="37fd3-117">If you do not add the appropriate users and groups to the CsAdministors group, you will receive an error when you open Skype for Business Server Control Panel which reads, "Unauthorized: Access is denied due to a role-based access control (RBAC) authorization failure."</span></span> 
  
2. <span data-ttu-id="37fd3-118">Wenn das Benutzerobjekt derzeit angemeldet ist, melden Sie es ab und wieder an, um die neue Gruppenzuweisung zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="37fd3-118">If the user object is currently logged on, log off and then log on again to register the new group assignment.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="37fd3-119">Das Benutzerkonto kann nicht der lokale Administrator eines Servers sein, auf dem Skype for Business Server ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="37fd3-119">The user account cannot be the local administrator of any server running Skype for Business Server.</span></span> 
  
3. <span data-ttu-id="37fd3-120">Verwenden Sie das Administratorkonto, um sich bei dem Computer anzumelden, auf dem die Skype for Business Server-Systemsteuerung installiert ist.</span><span class="sxs-lookup"><span data-stu-id="37fd3-120">Use the administrative account to log on to the computer where Skype for Business Server Control Panel is installed.</span></span>
    
4. <span data-ttu-id="37fd3-121">Starten Sie die Skype for Business Server-Systemsteuerung, und geben Sie dann die Anmeldeinformationen ein, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="37fd3-121">Start Skype for Business Server Control Panel, and then provide credentials, if prompted.</span></span> <span data-ttu-id="37fd3-122">In der Skype for Business Server-Systemsteuerung werden Bereitstellungsinformationen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="37fd3-122">Skype for Business Server Control Panel displays deployment information.</span></span>
    
5. <span data-ttu-id="37fd3-123">Klicken Sie in der linken Navigationsleiste auf **Topologie**, und stellen Sie dann sicher, dass der Dienststatus einen Computer mit einem grünen Pfeil anzeigt und ein grünes Häkchen für den Replikationsstatus neben jeder Skype for Business-Server Rolle steht, die bereitgestellt und online geschaltet wurde.</span><span class="sxs-lookup"><span data-stu-id="37fd3-123">In the left navigation bar, click **Topology**, and then confirm that the service status shows a computer with a green arrow and that a green check mark for replication status is next to each Skype for Business Server role that has been deployed and brought online.</span></span> 
    
6. <span data-ttu-id="37fd3-124">Klicken Sie in der linken Navigationsleiste auf **Benutzer** und dann auf **Benutzer aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="37fd3-124">In the left navigation bar, click **Users**, and then click **Enable users**.</span></span> 
    
7. <span data-ttu-id="37fd3-125">Klicken Sie auf der **neuen Skype for Business Server-Benutzer** Seite auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="37fd3-125">On the **New Skype for Business Server User** page, click **Add**.</span></span>
    
8. <span data-ttu-id="37fd3-p105">Wenn Sie Suchparameter für die zu ermittelnden Objekte definieren möchten, aktivieren Sie auf der Seite **Aus Active Directory auswählen** die Option **Suchen** und klicken Sie optional auf **Filter hinzufügen**. Alternativ können Sie auch die Option **LDAP-Suche** aktivieren und einen LDAP-Ausdruck eingeben, um die zurückgegebenen Objekte zu filtern oder einzuschränken. Klicken Sie auf **Suchen**, nachdem Sie die gewünschten Suchoptionen festgelegt haben.</span><span class="sxs-lookup"><span data-stu-id="37fd3-p105">To define search parameters for the objects you want to find, on the **Select from Active Directory** page, you can select **Search**, and then optionally click **Add Filter**. You can also select **LDAP search** and enter an LDAP expression to filter or limit the objects that will be returned. After you have decided on your Search options, click **Find**.</span></span>
    
9. <span data-ttu-id="37fd3-129">Wählen Sie im Bereich mit den Suchergebnissen alle hinzuzufügenden Benutzer aus und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="37fd3-129">In the Search results pane, select the users you want to add, and then click **OK**.</span></span>
    
10. <span data-ttu-id="37fd3-130">Auf der **neuen Benutzerseite für Skype for Business Server** befinden sich die von Ihnen ausgewählten Benutzer in der Ansicht **Benutzer** .</span><span class="sxs-lookup"><span data-stu-id="37fd3-130">On the **New Skype for Business Server User** page, the users you selected are in the **Users** display.</span></span> <span data-ttu-id="37fd3-131">In the **Assign users to a pool** list, select the server where the users should reside.</span><span class="sxs-lookup"><span data-stu-id="37fd3-131">In the **Assign users to a pool** list, select the server where the users should reside.</span></span>
    
    <span data-ttu-id="37fd3-132">Im Folgenden finden Sie eine Liste der Optionen, die Sie zum Konfigurieren der Objekte verwenden können.</span><span class="sxs-lookup"><span data-stu-id="37fd3-132">The following is a list of options you can use to configure the objects.</span></span>
    
    - <span data-ttu-id="37fd3-133">**SIP-URI des Benutzers generieren**</span><span class="sxs-lookup"><span data-stu-id="37fd3-133">**Generate user's SIP URI**</span></span>
    
    - <span data-ttu-id="37fd3-134">**Telefonie**</span><span class="sxs-lookup"><span data-stu-id="37fd3-134">**Telephony**</span></span>
    
    - <span data-ttu-id="37fd3-135">**Anschluss-URI**</span><span class="sxs-lookup"><span data-stu-id="37fd3-135">**Line URI**</span></span>
    
    - <span data-ttu-id="37fd3-136">**Konferenzrichtlinie**</span><span class="sxs-lookup"><span data-stu-id="37fd3-136">**Conferencing policy**</span></span>
    
    - <span data-ttu-id="37fd3-137">**Clientversionsrichtlinie**</span><span class="sxs-lookup"><span data-stu-id="37fd3-137">**Client version policy**</span></span>
    
    - <span data-ttu-id="37fd3-138">**PIN-Richtlinie**</span><span class="sxs-lookup"><span data-stu-id="37fd3-138">**PIN policy**</span></span>
    
    - <span data-ttu-id="37fd3-139">**Externe Zugriffsrichtlinie**</span><span class="sxs-lookup"><span data-stu-id="37fd3-139">**External access policy**</span></span>
    
    - <span data-ttu-id="37fd3-140">**Archivierungsrichtlinie**</span><span class="sxs-lookup"><span data-stu-id="37fd3-140">**Archiving policy**</span></span>
    
    - <span data-ttu-id="37fd3-141">**Standortrichtlinie**</span><span class="sxs-lookup"><span data-stu-id="37fd3-141">**Location policy**</span></span>
    
    - <span data-ttu-id="37fd3-142">**Clientrichtlinie**</span><span class="sxs-lookup"><span data-stu-id="37fd3-142">**Client policy**</span></span>
    
    <span data-ttu-id="37fd3-143">Wenn Sie die grundlegenden Funktionen testen möchten, wählen Sie die gewünschte Option für die **SIP-URI-Einstellung des Benutzers generieren** aus (die anderen Optionen in der Konfiguration verwenden Standardeinstellungen), und klicken Sie dann auf **aktivieren**, wie in der Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="37fd3-143">To test the basic functionality, select the option you prefer for the **Generate user's SIP URI** setting (the other options in the configuration use default settings), and then click **Enable**, as shown in the figure.</span></span>
    
     ![Aktivieren von Benutzern in der Systemsteuerung](../../media/7ee8717d-9a1f-4864-8f45-71071c88878f.png)
  
11. <span data-ttu-id="37fd3-p107">Es wird eine Zusammenfassungsseite angezeigt, auf der ein Häkchen in der Spalte **Aktiviert** darauf hinweist, dass die Benutzer eingerichtet sind. In der Spalte **SIP-Adresse** wird die Adresse angezeigt, die Sie zur Konfiguration der Benutzeranmeldung benötigen.</span><span class="sxs-lookup"><span data-stu-id="37fd3-p107">A summary page is displayed that shows a check mark in the **Enabled** column to indicate that the users are setup. The **SIP address** column displays the address you need for the user sign-in configuration.</span></span>
    
     ![Benutzer, die der Skype for Business Server-Systemsteuerung hinzugefügt wurden](../../media/8960548a-8d6d-44c5-bc01-6f9fb11b7588.png)
  
12. <span data-ttu-id="37fd3-148">Melden Sie einen Benutzer bei einem Computer an, der mit der Domäne verknüpft ist, und einen weiteren Benutzer bei einem anderen Computer in der Domäne.</span><span class="sxs-lookup"><span data-stu-id="37fd3-148">Log one user on to a computer that is joined to the domain and another user on to another computer in the domain.</span></span>
    
13. <span data-ttu-id="37fd3-149">Installieren Sie den Skype for Business-Client auf jedem der beiden Clientcomputer, und stellen Sie dann sicher, dass sich beide Benutzer bei Skype for Business Server anmelden können und Sofortnachrichten senden können.</span><span class="sxs-lookup"><span data-stu-id="37fd3-149">Install Skype for Business client on each of the two client computers, and then verify that both users can sign in to Skype for Business Server and can send instant messages to each other.</span></span>
    

