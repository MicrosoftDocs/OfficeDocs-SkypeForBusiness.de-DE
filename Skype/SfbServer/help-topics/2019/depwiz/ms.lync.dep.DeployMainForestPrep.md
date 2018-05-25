---
title: Vorbereiten der aktuellen Gesamtstruktur
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11f5e359-97eb-45f7-a730-9ddbbaa40b83
description: Zum Vorbereiten der Active Directory-Domänendienste-Gesamtstruktur müssen Sie erfolgreich das Schema erweitern (Siehe im Thema Running Schema Preparation), und stellen Sie sicher, dass das Schema repliziert wurde.
ms.openlocfilehash: 80218036b6eaee5abb0156ca6a13678f9b9f2238
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2018
---
# <a name="prepare-current-forest"></a><span data-ttu-id="fb205-103">Vorbereiten der aktuellen Gesamtstruktur</span><span class="sxs-lookup"><span data-stu-id="fb205-103">Prepare Current Forest</span></span>
 
<span data-ttu-id="fb205-104">Zum Vorbereiten der Active Directory-Domänendienste-Gesamtstruktur müssen Sie erfolgreich das Schema erweitern (Siehe im Thema [Running Schema Preparation](http://technet.microsoft.com/library/067726ae-fd3f-4133-a32f-26d2603ac674.aspx)), und stellen Sie sicher, dass das Schema repliziert wurde.</span><span class="sxs-lookup"><span data-stu-id="fb205-104">To prepare the Active Directory Domain Services forest, you must successfully extend the schema, as described in the topic [Running Schema Preparation](http://technet.microsoft.com/library/067726ae-fd3f-4133-a32f-26d2603ac674.aspx), and make sure that the schema has replicated.</span></span>
  
<span data-ttu-id="fb205-p101">Sobald diese Voraussetzungen erfüllt sind, können Sie mit **Schritt 3: Aktuelle Gesamtstruktur vorbereiten** beginnen. Melden Sie sich zum Vorbereiten der Gesamtstruktur bei einem Computer in der Stammdomäne der Gesamtstruktur als Mitglied der Gruppe „Domänen-Admins“ in der Stammdomäne der Gesamtstruktur oder der Gruppe „Organisations-Admins“ für die Gesamtstruktur an, die Sie vorbereiten.</span><span class="sxs-lookup"><span data-stu-id="fb205-p101">After completing these prerequisites, you can begin **Step 3: Prepare Current Forest**. To prepare the forest, log on to a computer in the forest root as a member of Domain Admins in the forest root, or as a member of the Enterprise Admins for the forest that you are preparing.</span></span>
  
1. <span data-ttu-id="fb205-107">Klicken Sie im Bereitstellungs-Assistenten unter **Schritt 3: Vorbereiten der aktuellen Gesamtstruktur** auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="fb205-107">From the Deployment Wizard at **Step 3: Prepare Current Forest**, click **Run**.</span></span>
    
2. <span data-ttu-id="fb205-108">Klicken Sie auf der Seite **Vorbereiten der aktuellen Gesamtstruktur** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="fb205-108">From the **Prepare Forest** page, click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fb205-109">Vorbereitung der Gesamtstruktur können Sie wählen, wo die universellen Gruppen für Skype für Business Server 2015 platziert.</span><span class="sxs-lookup"><span data-stu-id="fb205-109">Forest Preparation enables you to choose where to place the Universal Groups for Skype for Business Server 2015.</span></span> <span data-ttu-id="fb205-110">Wählen Sie einen Speicherort entsprechend den Anforderungen Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="fb205-110">Choose a location that is consistent with the requirements of your organization.</span></span> 
  
3. <span data-ttu-id="fb205-p103">Suchen Sie auf der Seite **Befehle ausführen** nach **Aufgabenstatus: Abgeschlossen** und klicken Sie dann auf **Protokoll anzeigen**. Vergewissern Sie sich, dass keine Fehler vorliegen. Überprüfen Sie die Warnungen dahingehend, ob sie erwartet werden und für Ihre Infrastruktur typisch sind.</span><span class="sxs-lookup"><span data-stu-id="fb205-p103">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**. Make sure that there are no errors. Review the warnings to determine if they are expected and typical for your infrastructure.</span></span>
    
4. <span data-ttu-id="fb205-114">Erweitern Sie unter der Spalte **Aktion** im Protokoll **Der Vorbereitung der Gesamtstruktur**, suchen Sie nach einer ** \<Erfolg\> ** Ausführungsergebnis am Ende jeder Aufgabe zu prüfen, Vorbereitung der Gesamtstruktur erfolgreich abgeschlossen wurde, schließen Sie das Protokoll und klicken Sie dann auf Fertig stellen ** **.</span><span class="sxs-lookup"><span data-stu-id="fb205-114">Under the **Action** column in the log, expand **Forest Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that forest preparation completed successfully, close the log, and then click **Finish**.</span></span>
    
5. <span data-ttu-id="fb205-115">Warten Sie Active Directory-Domänendienste-Replikation abgeschlossen ist, oder erzwingen Sie die Replikation auf allen Domänencontrollern in der **Active Directory-Standorte und -Dienste** -Snap-in für den Domänencontroller des Gesamtstrukturstamms, vor dem Ausführen der domänenvorbereitung aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="fb205-115">Wait for Active Directory Domain Services replication to complete, or force replication to all domain controllers listed in the **Active Directory Sites and Services** snap-in for the forest root domain controller, before running domain preparation.</span></span> <span data-ttu-id="fb205-116">Erzwingen Sie die Replikation zwischen den Domänencontrollern an allen Active Directory-Standorte, die dazu führen, dass die Replikation an den Standorten innerhalb von Minuten durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="fb205-116">Force replication between the domain controllers in all Active Directory sites to cause replication within the sites to occur within minutes.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="fb205-117">Wenn Sie die Protokolldateien überprüfen, die durch die Skype für Business Server-Bereitstellungs-Assistenten erstellt werden müssen, können sie auf dem Computer finden Sie dem Bereitstellungs-Assistenten ausgeführt wurde, in das Verzeichnis Benutzer des Benutzers Active Directory Domain Services, die im Schritt ausgeführt hat.</span><span class="sxs-lookup"><span data-stu-id="fb205-117">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="fb205-118">Angenommen, wenn der Benutzer als Domänenadministrator in der Domäne Contoso.net angemeldet, die Protokolldateien befinden sich im: C:\Users\Administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="fb205-118">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span> 
  

