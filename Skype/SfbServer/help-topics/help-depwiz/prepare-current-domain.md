---
title: Vorbereiten der aktuellen Domäne
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bfcb37ca-34eb-4d0d-9694-6edd2e7fe0f3
description: 'Um eine Domäne und Hostservern, die mit Skype für Business Server 2015 oder Skype für Benutzer von Business Server vorzubereiten, müssen Sie Schritt 5: aktuelle Domäne vorbereiten, wie im Thema Verwenden des Setups zum Ausführen der Domänenvorbereitung beschrieben. Zum Abschließen des Schritts müssen Sie als Mitglied der Gruppe „Domänenadmins“ in der Domäne, die Sie vorbereiten, oder der Gruppe „Organisations-Admins“ der Gesamtstruktur, zu der die Domäne gehört, angemeldet sein. So bereiten Sie die Domäne vor:'
ms.openlocfilehash: 80ee047bd6c5f8ca7b153beb5c45efea953af6ad
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33888828"
---
# <a name="prepare-current-domain"></a><span data-ttu-id="21018-105">Vorbereiten der aktuellen Domäne</span><span class="sxs-lookup"><span data-stu-id="21018-105">Prepare Current Domain</span></span>

<span data-ttu-id="21018-106">Um eine Domäne und Hostservern, die mit Skype für Business Server 2015 oder Skype für Benutzer von Business Server vorzubereiten, müssen Sie **Schritt 5: aktuelle Domäne vorbereiten**, wie im Thema [Verwenden des Setups zum Ausführen der Domänenvorbereitung](https://technet.microsoft.com/library/95dab800-1f2c-4506-b36c-99986643b149.aspx)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="21018-106">To prepare a domain to host servers running Skype for Business Server 2015 or Skype for Business Server users, you must complete **Step 5: Prepare Current Domain**, as described in the topic [Using Setup to Run Domain Preparation](https://technet.microsoft.com/library/95dab800-1f2c-4506-b36c-99986643b149.aspx).</span></span> <span data-ttu-id="21018-107">Zum Abschließen des Schritts müssen Sie als Mitglied der Gruppe „Domänenadmins“ in der Domäne, die Sie vorbereiten, oder der Gruppe „Organisations-Admins“ der Gesamtstruktur, zu der die Domäne gehört, angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="21018-107">To complete the step, you must be logged in as a member of the Domain Admins group in the domain that you are preparing, or as a member of the Enterprise Admins group of the forest that the domain belongs to.</span></span> <span data-ttu-id="21018-108">So bereiten Sie die Domäne vor:</span><span class="sxs-lookup"><span data-stu-id="21018-108">To prepare the domain:</span></span>

1. <span data-ttu-id="21018-109">Führen Sie aus der Skype für Business Server 2015-Installationsordner oder auf dem Installationsmedium Setup.exe, um die Skype für Business Server-Bereitstellungs-Assistenten zu starten.</span><span class="sxs-lookup"><span data-stu-id="21018-109">From the Skype for Business Server 2015 installation folder or media, run Setup.exe to start the Skype for Business Server Deployment Wizard.</span></span>

2. <span data-ttu-id="21018-110">Klicken Sie auf **Active Directory vorbereiten** und warten Sie das Bestimmen des Bereitstellungsstatus ab.</span><span class="sxs-lookup"><span data-stu-id="21018-110">Click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

3. <span data-ttu-id="21018-111">Klicken Sie unter **Schritt 5: Aktuelle Domäne vorbereiten** auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="21018-111">At **Step 5: Prepare Current Domain**, click **Run**.</span></span>

4. <span data-ttu-id="21018-112">Suchen Sie auf der Seite **Befehle ausführen** nach **Aufgabenstatus: Abgeschlossen** und klicken Sie dann auf **Protokoll anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="21018-112">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

5. <span data-ttu-id="21018-113">Erweitern Sie unter der Spalte **Aktion** **Domäne vorbereiten**, suchen Sie nach einer \*\* \<Erfolg\> \*\* Ausführungsergebnis am Ende jeder Aufgabe zu überprüfen, domänenvorbereitung erfolgreich abgeschlossen wurde, schließen Sie das Protokoll, und klicken Sie dann auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="21018-113">Under the **Action** column, expand **Domain Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that domain preparation completed successfully, close the log, and then click **Finish**.</span></span>

> [!TIP]
> <span data-ttu-id="21018-114">Wenn Sie die Protokolldateien überprüfen, die durch die Skype für Business Server-Bereitstellungs-Assistenten erstellt werden müssen, können sie auf dem Computer finden Sie dem Bereitstellungs-Assistenten im Verzeichnis Benutzer des Benutzers Active Directory Domain Services ausgeführt wurde, die im Schritt ausgeführt hat.</span><span class="sxs-lookup"><span data-stu-id="21018-114">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="21018-115">Angenommen, wenn der Benutzer als Domänenadministrator in der Domäne Contoso.net angemeldet, die Protokolldateien befinden sich im: C:\Users\Administrator.Contoso\AppData\Local\Temp.</span><span class="sxs-lookup"><span data-stu-id="21018-115">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp.</span></span>


