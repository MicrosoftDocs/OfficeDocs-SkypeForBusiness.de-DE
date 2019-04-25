---
title: Überprüfen, ob die Benutzerreplikation abgeschlossen wurde
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Wenn Sie das Move-CsUser-Cmdlet ausführen, auftreten einen Fehler, da die Benutzerinformationen zwischen Active Directory-Domänendienste (AD DS) und der Skype für Business Server 2019 Datenbanken sind nicht synchronisiert, da die Erstreplikation unvollständig ist. Der Zeitaufwand für die erfolgreiche der Skype für die anfängliche Synchronisierung des Dienstes Business Server 2019 Benutzerreplikationsdienst hängt von der Anzahl der Domänencontroller, die in der Active Directory-Gesamtstruktur gehostet werden, die die Skype für Unternehmen gehostet wird. Server 2019 Pool. Die Skype für Business Server 2019 Benutzerreplikationsdienst Service erstsynchronisierung Prozess tritt auf, wenn die Skype für Business Server 2019 Front-End-Server zum ersten Mal gestartet wird. Nach Ausführung dieses basiert die Synchronisierung klicken Sie dann auf das Intervall für den Benutzerreplikationsdienst. Führen Sie die folgenden Schritte aus, um sicherzustellen, dass die Benutzerreplikation abgeschlossen ist, bevor Sie das Move-CsUser-Cmdlet ausführen.
ms.openlocfilehash: bab54e91ebda7a10804980e368e05bb58ff911ff
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231336"
---
# <a name="verify-user-replication-has-completed"></a><span data-ttu-id="3bf34-107">Überprüfen, ob die Benutzerreplikation abgeschlossen wurde</span><span class="sxs-lookup"><span data-stu-id="3bf34-107">Verify user replication has completed</span></span>

<span data-ttu-id="3bf34-108">Wenn Sie das **Move-CsUser** -Cmdlet ausführen zu können, kann einen Fehler auftreten, wenn Benutzerinformationen zwischen Active Directory-Domänendienste (AD DS) und der Skype für Business Server 2019 Datenbanken nicht synchronisiert sind, da die Erstreplikation unvollständig ist.</span><span class="sxs-lookup"><span data-stu-id="3bf34-108">When running the **Move-CsUser** cmdlet, you may experience a failure if user information between Active Directory Domain Services (AD DS) and the Skype for Business Server 2019 databases are out of sync because the initial replication is incomplete.</span></span> <span data-ttu-id="3bf34-109">Der Zeitaufwand für die erfolgreiche der Skype für die anfängliche Synchronisierung des Dienstes Business Server 2019 Benutzerreplikationsdienst hängt von der Anzahl der Domänencontroller, die in der Active Directory-Gesamtstruktur gehostet werden, die die Skype für Unternehmen gehostet wird. Server 2019 Pool.</span><span class="sxs-lookup"><span data-stu-id="3bf34-109">The time it takes for the successful completion of the Skype for Business Server 2019 User Replicator service's initial synchronization depends on the number of domain controllers that are hosted in the Active Directory forest that hosts the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="3bf34-110">Die Skype für Business Server 2019 Benutzerreplikationsdienst Service erstsynchronisierung Prozess tritt auf, wenn die Skype für Business Server 2019 Front-End-Server zum ersten Mal gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="3bf34-110">The Skype for Business Server 2019 User Replicator service initial synchronization process occurs when the Skype for Business Server 2019 Front End Server is started for the first time.</span></span> <span data-ttu-id="3bf34-111">Nach Ausführung dieses basiert die Synchronisierung auf das Intervall für den Benutzerreplikationsdienst.</span><span class="sxs-lookup"><span data-stu-id="3bf34-111">After that, the synchronization is based on the User Replicator interval.</span></span> <span data-ttu-id="3bf34-112">Führen Sie die folgenden Schritte aus, um sicherzustellen, dass die Benutzerreplikation abgeschlossen ist, vor dem Ausführen des Cmdlets **Move-CsUser** .</span><span class="sxs-lookup"><span data-stu-id="3bf34-112">Complete the following steps to verify that user replication has completed before running the **Move-CsUser** cmdlet.</span></span> 
  
### <a name="to-verify-that-user-replication-has-completed"></a><span data-ttu-id="3bf34-113">So überprüfen Sie, dass die Benutzerreplikation abgeschlossen hat</span><span class="sxs-lookup"><span data-stu-id="3bf34-113">To verify that user replication has completed</span></span>

1. <span data-ttu-id="3bf34-114">Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.</span><span class="sxs-lookup"><span data-stu-id="3bf34-114">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="3bf34-115">Klicken Sie auf **das Startmenü** , und klicken Sie dann auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="3bf34-115">Click the **Start** menu, and then click **Run**.</span></span> 
    
3. <span data-ttu-id="3bf34-116">Geben Sie **eventvwr.exe**ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3bf34-116">Enter **eventvwr.exe**, and then click **OK**.</span></span>
    
4. <span data-ttu-id="3bf34-117">Klicken Sie in der Ereignisanzeige auf **Anwendungs- und Dienstprotokolle,** um ihn zu erweitern, und wählen Sie dann Skype für Business Server aus.</span><span class="sxs-lookup"><span data-stu-id="3bf34-117">In Event Viewer, click **Applications and Services logs** to expand it, and then select Skype for Business Server.</span></span> 
    
5. <span data-ttu-id="3bf34-118">Klicken Sie im Bereich **Aktionen** auf **Aktuelles Protokoll filtern**.</span><span class="sxs-lookup"><span data-stu-id="3bf34-118">In the **Actions** pane, click **Filter Current Log**.</span></span>
    
6. <span data-ttu-id="3bf34-119">Klicken Sie in der Liste **Ereignisquellen** auf **LS User Replicator**.</span><span class="sxs-lookup"><span data-stu-id="3bf34-119">From the **Event sources** list, click **LS User Replicator**.</span></span>
    
7. <span data-ttu-id="3bf34-120">In \*\* \<alle Ereignis-IDs\>\*\*, geben Sie **den Wert 30024 ein**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3bf34-120">In **\<All Event IDs\>**, enter **30024**, and then click **OK**.</span></span> 
    
8. <span data-ttu-id="3bf34-121">Suchen Sie in der gefilterten Ereignisliste auf der Registerkarte **Allgemein** nach einem Eintrag, der besagt, dass die Benutzerreplikation erfolgreich abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="3bf34-121">In the filtered events list, on the **General** tab, look for an entry that states that user replication has completed successfully.</span></span> 
    

