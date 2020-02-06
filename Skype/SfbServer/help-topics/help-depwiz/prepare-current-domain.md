---
title: Vorbereiten der aktuellen Domäne
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
- ms.lync.dep.DeployMainDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bfcb37ca-34eb-4d0d-9694-6edd2e7fe0f3
description: 'Wenn Sie eine Domäne auf Hostserver vorbereiten möchten, auf denen Skype for Business Server 2015 oder Skype for Business Server-Benutzer ausgeführt werden, müssen Sie Schritt 5: Vorbereiten der aktuellen Domäne ausführen, wie im Thema Verwenden von Setup zum Ausführen der Domänenvorbereitung beschrieben. Zum Abschließen des Schritts müssen Sie als Mitglied der Gruppe „Domänenadmins“ in der Domäne, die Sie vorbereiten, oder der Gruppe „Organisations-Admins“ der Gesamtstruktur, zu der die Domäne gehört, angemeldet sein. So bereiten Sie die Domäne vor:'
ms.openlocfilehash: 2f3563c9a1c857e9d4828ca63cf2cb675f524e56
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823549"
---
# <a name="prepare-current-domain"></a><span data-ttu-id="d8a52-105">Vorbereiten der aktuellen Domäne</span><span class="sxs-lookup"><span data-stu-id="d8a52-105">Prepare Current Domain</span></span>

<span data-ttu-id="d8a52-106">Wenn Sie eine Domäne auf Hostserver vorbereiten möchten, auf denen Skype for Business Server 2015 oder Skype for Business Server-Benutzer ausgeführt werden, müssen Sie **Schritt 5: Vorbereiten der aktuellen Domäne**ausführen, wie im Thema [Verwenden von Setup zum Ausführen der Domänenvorbereitung](https://technet.microsoft.com/library/95dab800-1f2c-4506-b36c-99986643b149.aspx)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d8a52-106">To prepare a domain to host servers running Skype for Business Server 2015 or Skype for Business Server users, you must complete **Step 5: Prepare Current Domain**, as described in the topic [Using Setup to Run Domain Preparation](https://technet.microsoft.com/library/95dab800-1f2c-4506-b36c-99986643b149.aspx).</span></span> <span data-ttu-id="d8a52-107">Zum Abschließen des Schritts müssen Sie als Mitglied der Gruppe „Domänenadmins“ in der Domäne, die Sie vorbereiten, oder der Gruppe „Organisations-Admins“ der Gesamtstruktur, zu der die Domäne gehört, angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="d8a52-107">To complete the step, you must be logged in as a member of the Domain Admins group in the domain that you are preparing, or as a member of the Enterprise Admins group of the forest that the domain belongs to.</span></span> <span data-ttu-id="d8a52-108">So bereiten Sie die Domäne vor:</span><span class="sxs-lookup"><span data-stu-id="d8a52-108">To prepare the domain:</span></span>

1. <span data-ttu-id="d8a52-109">Führen Sie im Skype for Business Server 2015-Installationsordner oder-Medium die Datei "Setup. exe" aus, um den Skype for Business Server-Bereitstellungs-Assistenten zu starten.</span><span class="sxs-lookup"><span data-stu-id="d8a52-109">From the Skype for Business Server 2015 installation folder or media, run Setup.exe to start the Skype for Business Server Deployment Wizard.</span></span>

2. <span data-ttu-id="d8a52-110">Klicken Sie auf **Active Directory vorbereiten** und warten Sie das Bestimmen des Bereitstellungsstatus ab.</span><span class="sxs-lookup"><span data-stu-id="d8a52-110">Click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

3. <span data-ttu-id="d8a52-111">Klicken Sie unter **Schritt 5: Aktuelle Domäne vorbereiten** auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="d8a52-111">At **Step 5: Prepare Current Domain**, click **Run**.</span></span>

4. <span data-ttu-id="d8a52-112">Suchen Sie auf der Seite **Befehle ausführen** nach **Aufgabenstatus: Abgeschlossen** und klicken Sie dann auf **Protokoll anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="d8a52-112">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

5. <span data-ttu-id="d8a52-113">Erweitern Sie in der Spalte " **Aktion** " die **Domäne prep**, suchen Sie nach einem \*\* \<\> \*\* Ergebnis der erfolgreichen Ausführung am Ende jeder Aufgabe, um zu überprüfen, ob die Domänenvorbereitung erfolgreich abgeschlossen wurde, schließen Sie das Protokoll, und klicken Sie dann auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="d8a52-113">Under the **Action** column, expand **Domain Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that domain preparation completed successfully, close the log, and then click **Finish**.</span></span>

> [!TIP]
> <span data-ttu-id="d8a52-114">Wenn Sie die Protokolldateien überprüfen müssen, die vom Bereitstellungs-Assistenten für Skype for Business Server erstellt wurden, können Sie diese auf dem Computer finden, auf dem der Bereitstellungs-Assistent im Verzeichnis Benutzer des Active Directory-Domänendienste-Benutzers ausgeführt wurde, der den Schritt ausgeführt hat.</span><span class="sxs-lookup"><span data-stu-id="d8a52-114">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="d8a52-115">Wenn sich der Benutzer beispielsweise als Domänenadministrator im Domänen contoso.net angemeldet hat, befinden sich die Protokolldateien in: C:\users\administrator.Contoso\AppData\Local\Temp.</span><span class="sxs-lookup"><span data-stu-id="d8a52-115">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp.</span></span>


