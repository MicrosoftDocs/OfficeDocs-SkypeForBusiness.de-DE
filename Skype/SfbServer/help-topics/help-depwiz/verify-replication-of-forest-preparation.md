---
title: Überprüfen der Replikation der Gesamtstrukturvorbereitung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifyForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 94e87632-7c28-43df-9238-f5a47c1c43c0
description: 'Um zu bestätigen, dass die Replikation des globalen Katalogs und die Erstellung von Objekten während der Vorbereitung der Gesamtstruktur verfügen erfolgreich war, gehen Sie folgendermaßen vor:'
ms.openlocfilehash: 23e3aa84cd00c68ae126991c714c35b5fdf33536
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33887279"
---
# <a name="verify-replication-of-forest-preparation"></a><span data-ttu-id="ad9f6-103">Überprüfen der Replikation der Gesamtstrukturvorbereitung</span><span class="sxs-lookup"><span data-stu-id="ad9f6-103">Verify Replication of Forest Preparation</span></span>
 
<span data-ttu-id="ad9f6-104">Um zu bestätigen, dass die Replikation des globalen Katalogs und die Erstellung von Objekten während der Vorbereitung der Gesamtstruktur verfügen erfolgreich war, gehen Sie folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="ad9f6-104">To confirm that the replication of the Global Catalog and the creation of objects during Forest Preparation have been successful, do the following:</span></span>
  
1. <span data-ttu-id="ad9f6-105">Öffnen Sie **Active Directory-Benutzer und -Computer** auf einem Domänencontroller (vorzugsweise an einem Remotestandort gegenüber den anderen Domänencontrollern) in der Gesamtstruktur, in der die Gesamtstrukturvorbereitung durchgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="ad9f6-105">On a domain controller (preferably in a remote site from the other domain controllers), in the forest where the Forest Preparation was run, open **Active Directory Users and Computers**.</span></span>
    
2. <span data-ttu-id="ad9f6-106">Erweitern Sie in **Active Directory-Benutzer und -Computer** den Domänennamen Ihrer Gesamtstruktur oder einer untergeordneten Domäne.</span><span class="sxs-lookup"><span data-stu-id="ad9f6-106">In **Active Directory Users and Computers**, expand the domain name of your forest or a child domain.</span></span>
    
3. <span data-ttu-id="ad9f6-107">Klicken Sie auf den Container **Users** , klicken Sie im linken Bereich, und suchen Sie nach der universellen Gruppe CsAdministrator klicken Sie im rechten Bereich.</span><span class="sxs-lookup"><span data-stu-id="ad9f6-107">Click the **Users** container on the left side pane and look for the Universal group CsAdministrator in the right side pane.</span></span> <span data-ttu-id="ad9f6-108">Wenn CsAdministrator (zwischen acht andere neuen universellen Gruppen, die beginnen mit Cs) vorhanden ist, wurde die Replikation der Vorbereitung der Gesamtstruktur erfolgreich hergestellt.</span><span class="sxs-lookup"><span data-stu-id="ad9f6-108">If CsAdministrator (among eight other new Universal groups that begin with Cs) is present, replication of the Forest Preparation has been successful.</span></span>
    
4. <span data-ttu-id="ad9f6-109">Wenn die Gruppe noch nicht vorhanden ist, können Sie erzwingen, dass die Replikation oder warten Sie 15 Minuten und aktualisieren im rechten Bereich.</span><span class="sxs-lookup"><span data-stu-id="ad9f6-109">If the group(s) is not yet present, you can force the replication or wait 15 minutes and refresh the right side pane.</span></span> <span data-ttu-id="ad9f6-110">Die Replikation ist abgeschlossen, wenn die Gruppen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="ad9f6-110">When the groups are present, replication is complete.</span></span>
    
> [!TIP]
> <span data-ttu-id="ad9f6-111">Wenn Sie die Protokolldateien, die durch die Skype für Business Server-Bereitstellungs-Assistenten erstellt werden, prüfen möchten, können Sie diese auf dem Computer finden, in dem Bereitstellungs-Assistenten ausgeführt wurde, in das Verzeichnis Benutzer des Benutzers Active Directory Domain Services, die im Schritt ausgeführt hat.</span><span class="sxs-lookup"><span data-stu-id="ad9f6-111">If you want to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="ad9f6-112">Angenommen, wenn der Benutzer als Domänenadministrator in der Domäne Contoso.net angemeldet, die Protokolldateien befinden sich im: C:\Users\Administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="ad9f6-112">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span> 
  

