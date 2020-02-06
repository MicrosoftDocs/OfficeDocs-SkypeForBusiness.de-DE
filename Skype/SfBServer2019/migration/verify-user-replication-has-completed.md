---
title: Überprüfen, ob die Benutzerreplikation abgeschlossen wurde
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Bei der Ausführung des Cmdlets Move-CsUser tritt möglicherweise ein Fehler auf, da die Benutzerinformationen zwischen den Active Directory-Domänendiensten (AD DS) und den Skype for Business Server 2019-Datenbanken nicht synchronisiert sind, weil die anfängliche Replikation unvollständig ist. Die Zeitdauer für den erfolgreichen Abschluss der ersten Synchronisierung des Skype for Business Server 2019-Benutzerreplikationsdiensts hängt von der Anzahl der Domänencontroller ab, die in der Active Directory-Gesamtstruktur gehostet werden, die das Skype for Business hostet. Server 2019-Pool. Der erste Synchronisierungsvorgang des Skype for Business Server 2019-Benutzerreplikationsdiensts erfolgt, wenn der Skype for Business Server 2019-Front-End-Server zum ersten Mal gestartet wird. Danach basiert die Synchronisierung auf dem Intervall des Benutzerreplikationsdiensts. Führen Sie die folgenden Schritte aus, um zu überprüfen, ob die Benutzerreplikation abgeschlossen ist, bevor Sie das Cmdlet Move-CsUser ausführen.
ms.openlocfilehash: 31f4f9f1045367e376d4536df54c32be14580312
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812653"
---
# <a name="verify-user-replication-has-completed"></a><span data-ttu-id="4a087-107">Überprüfen, ob die Benutzerreplikation abgeschlossen wurde</span><span class="sxs-lookup"><span data-stu-id="4a087-107">Verify user replication has completed</span></span>

<span data-ttu-id="4a087-108">Bei der Ausführung des Cmdlets **Move-CsUser** tritt möglicherweise ein Fehler auf, wenn die Benutzerinformationen zwischen den Active Directory-Domänendiensten (AD DS) und den Skype for Business Server 2019-Datenbanken nicht synchronisiert sind, weil die anfängliche Replikation unvollständig ist.</span><span class="sxs-lookup"><span data-stu-id="4a087-108">When running the **Move-CsUser** cmdlet, you may experience a failure if user information between Active Directory Domain Services (AD DS) and the Skype for Business Server 2019 databases are out of sync because the initial replication is incomplete.</span></span> <span data-ttu-id="4a087-109">Die Zeitdauer für den erfolgreichen Abschluss der ersten Synchronisierung des Skype for Business Server 2019-Benutzerreplikationsdiensts hängt von der Anzahl der Domänencontroller ab, die in der Active Directory-Gesamtstruktur gehostet werden, die das Skype for Business hostet. Server 2019-Pool.</span><span class="sxs-lookup"><span data-stu-id="4a087-109">The time it takes for the successful completion of the Skype for Business Server 2019 User Replicator service's initial synchronization depends on the number of domain controllers that are hosted in the Active Directory forest that hosts the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="4a087-110">Der erste Synchronisierungsvorgang des Skype for Business Server 2019-Benutzerreplikationsdiensts erfolgt, wenn der Skype for Business Server 2019-Front-End-Server zum ersten Mal gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="4a087-110">The Skype for Business Server 2019 User Replicator service initial synchronization process occurs when the Skype for Business Server 2019 Front End Server is started for the first time.</span></span> <span data-ttu-id="4a087-111">Danach basiert die Synchronisierung auf dem Intervall des Benutzerreplikationsdiensts.</span><span class="sxs-lookup"><span data-stu-id="4a087-111">After that, the synchronization is based on the User Replicator interval.</span></span> <span data-ttu-id="4a087-112">Führen Sie die folgenden Schritte aus, um zu überprüfen, ob die Benutzerreplikation abgeschlossen ist, bevor Sie das Cmdlet **Move-CsUser** ausführen.</span><span class="sxs-lookup"><span data-stu-id="4a087-112">Complete the following steps to verify that user replication has completed before running the **Move-CsUser** cmdlet.</span></span> 
  
### <a name="to-verify-that-user-replication-has-completed"></a><span data-ttu-id="4a087-113">So überprüfen Sie, ob die Benutzerreplikation abgeschlossen ist</span><span class="sxs-lookup"><span data-stu-id="4a087-113">To verify that user replication has completed</span></span>

1. <span data-ttu-id="4a087-114">Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.</span><span class="sxs-lookup"><span data-stu-id="4a087-114">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="4a087-115">Klicken Sie auf das **Startmenü** , und klicken Sie dann auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="4a087-115">Click the **Start** menu, and then click **Run**.</span></span> 
    
3. <span data-ttu-id="4a087-116">Geben Sie **eventvwr. exe**ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="4a087-116">Enter **eventvwr.exe**, and then click **OK**.</span></span>
    
4. <span data-ttu-id="4a087-117">Klicken Sie in der Ereignisanzeige auf **Anwendungen und Dienstprotokolle** , um Sie zu erweitern, und wählen Sie dann Skype for Business Server aus.</span><span class="sxs-lookup"><span data-stu-id="4a087-117">In Event Viewer, click **Applications and Services logs** to expand it, and then select Skype for Business Server.</span></span> 
    
5. <span data-ttu-id="4a087-118">Klicken Sie im Bereich **Aktionen** auf **Aktuelles Protokoll filtern**.</span><span class="sxs-lookup"><span data-stu-id="4a087-118">In the **Actions** pane, click **Filter Current Log**.</span></span>
    
6. <span data-ttu-id="4a087-119">Klicken Sie in der Liste **Ereignisquellen** auf **ls-Benutzer Replikations**Dienst.</span><span class="sxs-lookup"><span data-stu-id="4a087-119">From the **Event sources** list, click **LS User Replicator**.</span></span>
    
7. <span data-ttu-id="4a087-120">Geben Sie in \*\* \<alle\>Ereignis-IDs\*\* **30024**ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="4a087-120">In **\<All Event IDs\>**, enter **30024**, and then click **OK**.</span></span> 
    
8. <span data-ttu-id="4a087-121">Suchen Sie in der Liste Gefilterte Ereignisse auf der Registerkarte **Allgemein** nach einem Eintrag, der besagt, dass die Benutzerreplikation erfolgreich abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="4a087-121">In the filtered events list, on the **General** tab, look for an entry that states that user replication has completed successfully.</span></span> 
    

