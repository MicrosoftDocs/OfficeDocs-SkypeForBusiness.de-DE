---
title: Vorbereiten der aktuellen Gesamtstruktur
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11f5e359-97eb-45f7-a730-9ddbbaa40b83
description: Wenn Sie die Active Directory-Domänendienst-Gesamtstruktur vorbereiten möchten, müssen Sie das Schema erfolgreich erweitern, wie im Thema Ausführen der Schemavorbereitung beschrieben, und sicherstellen, dass das Schema repliziert wurde.
ms.openlocfilehash: d13660eb703a793c1fc59ed422bd0b317986a86b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823529"
---
# <a name="prepare-current-forest"></a><span data-ttu-id="ae621-103">Vorbereiten der aktuellen Gesamtstruktur</span><span class="sxs-lookup"><span data-stu-id="ae621-103">Prepare Current Forest</span></span>

<span data-ttu-id="ae621-104">Wenn Sie die Active Directory-Domänendienst-Gesamtstruktur vorbereiten möchten, müssen Sie das Schema erfolgreich erweitern, wie im Thema [Ausführen der Schemavorbereitung](https://technet.microsoft.com/library/067726ae-fd3f-4133-a32f-26d2603ac674.aspx)beschrieben, und sicherstellen, dass das Schema repliziert wurde.</span><span class="sxs-lookup"><span data-stu-id="ae621-104">To prepare the Active Directory Domain Services forest, you must successfully extend the schema, as described in the topic [Running Schema Preparation](https://technet.microsoft.com/library/067726ae-fd3f-4133-a32f-26d2603ac674.aspx), and make sure that the schema has replicated.</span></span>

<span data-ttu-id="ae621-p101">Sobald diese Voraussetzungen erfüllt sind, können Sie mit **Schritt 3: Aktuelle Gesamtstruktur vorbereiten** beginnen. Melden Sie sich zum Vorbereiten der Gesamtstruktur bei einem Computer in der Stammdomäne der Gesamtstruktur als Mitglied der Gruppe „Domänen-Admins“ in der Stammdomäne der Gesamtstruktur oder der Gruppe „Organisations-Admins“ für die Gesamtstruktur an, die Sie vorbereiten.</span><span class="sxs-lookup"><span data-stu-id="ae621-p101">After completing these prerequisites, you can begin **Step 3: Prepare Current Forest**. To prepare the forest, log on to a computer in the forest root as a member of Domain Admins in the forest root, or as a member of the Enterprise Admins for the forest that you are preparing.</span></span>

1. <span data-ttu-id="ae621-107">Klicken Sie im Bereitstellungs-Assistenten unter **Schritt 3: Vorbereiten der aktuellen Gesamtstruktur** auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="ae621-107">From the Deployment Wizard at **Step 3: Prepare Current Forest**, click **Run**.</span></span>

2. <span data-ttu-id="ae621-108">Klicken Sie auf der Seite **Vorbereiten der aktuellen Gesamtstruktur** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ae621-108">From the **Prepare Forest** page, click **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ae621-109">Mit der Gesamtstrukturvorbereitung können Sie auswählen, wo die universellen Gruppen für Skype for Business Server 2015 platziert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ae621-109">Forest Preparation enables you to choose where to place the Universal Groups for Skype for Business Server 2015.</span></span> <span data-ttu-id="ae621-110">Wählen Sie einen Speicherort entsprechend den Anforderungen Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="ae621-110">Choose a location that is consistent with the requirements of your organization.</span></span>

3. <span data-ttu-id="ae621-p103">Suchen Sie auf der Seite **Befehle ausführen** nach **Aufgabenstatus: Abgeschlossen** und klicken Sie dann auf **Protokoll anzeigen**. Vergewissern Sie sich, dass keine Fehler vorliegen. Überprüfen Sie die Warnungen dahingehend, ob sie erwartet werden und für Ihre Infrastruktur typisch sind.</span><span class="sxs-lookup"><span data-stu-id="ae621-p103">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**. Make sure that there are no errors. Review the warnings to determine if they are expected and typical for your infrastructure.</span></span>

4. <span data-ttu-id="ae621-114">Erweitern Sie in der Spalte **Aktion** im Protokoll die Ansicht **Gesamtstruktur**Vorbereitung, suchen Sie am Ende jeder Aufgabe nach einem \*\* \<\> \*\* Ergebnis der erfolgreichen Ausführung, um zu überprüfen, ob die Gesamtstrukturvorbereitung erfolgreich abgeschlossen wurde, schließen Sie das Protokoll, und klicken Sie dann auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="ae621-114">Under the **Action** column in the log, expand **Forest Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that forest preparation completed successfully, close the log, and then click **Finish**.</span></span>

5. <span data-ttu-id="ae621-115">Warten Sie, bis die Active Directory-Domänendienst Replikation abgeschlossen ist, oder erzwingen Sie die Replikation auf alle Domänencontroller, die im Snap-in **Active Directory-Standorte und-Dienste** für den Gesamtstruktur-Stammdomänencontroller aufgelistet sind, bevor Sie die Domänenvorbereitung ausführen.</span><span class="sxs-lookup"><span data-stu-id="ae621-115">Wait for Active Directory Domain Services replication to complete, or force replication to all domain controllers listed in the **Active Directory Sites and Services** snap-in for the forest root domain controller, before running domain preparation.</span></span> <span data-ttu-id="ae621-116">Erzwingen Sie die Replikation zwischen den Domänencontrollern an allen Active Directory-Standorten, damit die Replikation innerhalb der Websites innerhalb weniger Minuten erfolgen kann.</span><span class="sxs-lookup"><span data-stu-id="ae621-116">Force replication between the domain controllers in all Active Directory sites to cause replication within the sites to occur within minutes.</span></span>

    > [!TIP]
    > <span data-ttu-id="ae621-117">Wenn Sie die Protokolldateien überprüfen müssen, die vom Bereitstellungs-Assistenten für Skype for Business Server erstellt wurden, können Sie diese auf dem Computer finden, auf dem der Bereitstellungs-Assistent ausgeführt wurde, und zwar im Verzeichnis Benutzer des Active Directory-Domänendienste-Benutzers, der den Schritt ausgeführt hat.</span><span class="sxs-lookup"><span data-stu-id="ae621-117">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="ae621-118">Wenn sich der Benutzer beispielsweise als Domänenadministrator im Domänen contoso.net angemeldet hat, befinden sich die Protokolldateien in: C:\users\administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="ae621-118">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span>


