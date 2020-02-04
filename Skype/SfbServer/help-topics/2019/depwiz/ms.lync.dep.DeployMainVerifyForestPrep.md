---
title: Überprüfen der Replikation der Gesamtstrukturvorbereitung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployMainVerifyForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 94e87632-7c28-43df-9238-f5a47c1c43c0
ROBOTS: NOINDEX, NOFOLLOW
description: 'Gehen Sie wie folgt vor, um zu bestätigen, dass die Replikation des globalen Katalogs und das Erstellen von Objekten während der Gesamtstrukturvorbereitung erfolgreich war:'
ms.openlocfilehash: a89e5b1d8dff3f37def101b1cf2cccfad9d1bd5c
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41691750"
---
# <a name="verify-replication-of-forest-preparation"></a><span data-ttu-id="981d6-103">Überprüfen der Replikation der Gesamtstrukturvorbereitung</span><span class="sxs-lookup"><span data-stu-id="981d6-103">Verify Replication of Forest Preparation</span></span>
 
<span data-ttu-id="981d6-104">Gehen Sie wie folgt vor, um zu bestätigen, dass die Replikation des globalen Katalogs und das Erstellen von Objekten während der Gesamtstrukturvorbereitung erfolgreich war:</span><span class="sxs-lookup"><span data-stu-id="981d6-104">To confirm that the replication of the Global Catalog and the creation of objects during Forest Preparation have been successful, do the following:</span></span>
  
1. <span data-ttu-id="981d6-105">Öffnen Sie **Active Directory-Benutzer und -Computer** auf einem Domänencontroller (vorzugsweise an einem Remotestandort gegenüber den anderen Domänencontrollern) in der Gesamtstruktur, in der die Gesamtstrukturvorbereitung durchgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="981d6-105">On a domain controller (preferably in a remote site from the other domain controllers), in the forest where the Forest Preparation was run, open **Active Directory Users and Computers**.</span></span>
    
2. <span data-ttu-id="981d6-106">Erweitern Sie in **Active Directory-Benutzer und -Computer** den Domänennamen Ihrer Gesamtstruktur oder einer untergeordneten Domäne.</span><span class="sxs-lookup"><span data-stu-id="981d6-106">In **Active Directory Users and Computers**, expand the domain name of your forest or a child domain.</span></span>
    
3. <span data-ttu-id="981d6-107">Klicken Sie im linken Bereich auf den Container **Benutzer** , und suchen Sie im rechten Bereich nach der universellen Gruppe CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="981d6-107">Click the **Users** container on the left side pane and look for the Universal group CsAdministrator in the right side pane.</span></span> <span data-ttu-id="981d6-108">Wenn CsAdministrator (unter acht anderen neuen universellen Gruppen, die mit CS beginnen) vorhanden ist, wurde die Replikation der Gesamtstrukturvorbereitung erfolgreich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="981d6-108">If CsAdministrator (among eight other new Universal groups that begin with Cs) is present, replication of the Forest Preparation has been successful.</span></span>
    
4. <span data-ttu-id="981d6-109">Wenn die Gruppe (n) noch nicht vorhanden ist, können Sie die Replikation erzwingen oder 15 Minuten warten und den rechten Seitenbereich aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="981d6-109">If the group(s) is not yet present, you can force the replication or wait 15 minutes and refresh the right side pane.</span></span> <span data-ttu-id="981d6-110">Die Replikation ist abgeschlossen, wenn die Gruppen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="981d6-110">When the groups are present, replication is complete.</span></span>
    
> [!TIP]
> <span data-ttu-id="981d6-111">Wenn Sie die Protokolldateien überprüfen möchten, die vom Bereitstellungs-Assistenten für Skype for Business Server erstellt wurden, können Sie diese auf dem Computer finden, auf dem der Bereitstellungs-Assistent ausgeführt wurde, und zwar im Verzeichnis Benutzer des Active Directory-Domänendienste-Benutzers, der den Schritt ausgeführt hat.</span><span class="sxs-lookup"><span data-stu-id="981d6-111">If you want to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="981d6-112">Wenn sich der Benutzer beispielsweise als Domänenadministrator im Domänen contoso.net angemeldet hat, befinden sich die Protokolldateien in: C:\users\administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="981d6-112">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span> 
  

