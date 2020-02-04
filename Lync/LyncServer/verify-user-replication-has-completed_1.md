---
title: Überprüfen, ob die Benutzerreplikation abgeschlossen wurde
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify user replication has completed
ms:assetid: 199dc9de-b555-468f-a42a-9e92ea6c9053
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204712(v=OCS.15)
ms:contentKeyID: 48183524
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc6d8100a7bd0d348c3414da627584bae8697a1c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730775"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-user-replication-has-completed"></a><span data-ttu-id="4d7cf-102">Überprüfen, ob die Benutzerreplikation abgeschlossen wurde</span><span class="sxs-lookup"><span data-stu-id="4d7cf-102">Verify user replication has completed</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d7cf-103">_**Letztes Änderungsdatum des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="4d7cf-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="4d7cf-104">Bei der Ausführung des Cmdlets **Move-CsLegacyUser** tritt möglicherweise ein Fehler auf, da die Benutzerinformationen zwischen den Active Directory-Domänendiensten (AD DS) und den lync Server 2013-Datenbanken nicht synchronisiert werden, da die anfängliche Replikation unvollständig ist.</span><span class="sxs-lookup"><span data-stu-id="4d7cf-104">When running the **Move-CsLegacyUser** cmdlet, you may experience a failure due to user information between Active Directory Domain Services (AD DS) and the Lync Server 2013 databases being out of sync because the initial replication is incomplete.</span></span> <span data-ttu-id="4d7cf-105">Die Zeit, die für den erfolgreichen Abschluss der ersten Synchronisierung des lync Server 2013-Benutzerreplikationsdiensts benötigt wird, hängt von der Anzahl der Domänencontroller ab, die in der Active Directory-Gesamtstruktur gehostet werden, die den lync Server 2013-Pool hostet.</span><span class="sxs-lookup"><span data-stu-id="4d7cf-105">The time it takes for the successful completion of the Lync Server 2013 User Replicator service's initial synchronization depends on the number of domain controllers that are hosted in the Active Directory forest that hosts the Lync Server 2013 pool.</span></span> <span data-ttu-id="4d7cf-106">Der erst Synchronisierungsvorgang des lync Server 2013-Benutzerreplikationsdiensts erfolgt, wenn der lync Server 2013-Front-End-Server zum ersten Mal gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="4d7cf-106">The Lync Server 2013 User Replicator service initial synchronization process occurs when the Lync Server 2013 Front End Server is started for the first time.</span></span> <span data-ttu-id="4d7cf-107">Danach basiert die Synchronisierung auf dem Intervall des Benutzerreplikationsdiensts.</span><span class="sxs-lookup"><span data-stu-id="4d7cf-107">After that, the synchronization is then based on the User Replicator interval.</span></span> <span data-ttu-id="4d7cf-108">Führen Sie die folgenden Schritte aus, um zu überprüfen, ob die Benutzerreplikation abgeschlossen ist, bevor Sie das Cmdlet **Move-CsLegacyUser** ausführen.</span><span class="sxs-lookup"><span data-stu-id="4d7cf-108">Complete the following steps to verify user replication has completed before running the **Move-CsLegacyUser** cmdlet.</span></span>

<div>

## <a name="to-verify-that-user-replication-has-completed"></a><span data-ttu-id="4d7cf-109">So überprüfen Sie, ob die Benutzerreplikation abgeschlossen ist</span><span class="sxs-lookup"><span data-stu-id="4d7cf-109">To verify that user replication has completed</span></span>

1.  <span data-ttu-id="4d7cf-110">Klicken Sie auf dem lync Server 2013-Front-End-Server auf das **Startmenü** , und klicken Sie dann auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="4d7cf-110">From the Lync Server 2013 Front End server, click the **Start** menu, and then click **Run**.</span></span>

2.  <span data-ttu-id="4d7cf-111">Geben Sie **eventvwr. exe** ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="4d7cf-111">Enter **eventvwr.exe** and then click **OK**.</span></span>

3.  <span data-ttu-id="4d7cf-112">Klicken Sie in der Ereignisanzeige auf **Anwendungen und Dienstprotokolle** , um Sie zu erweitern, und wählen Sie dann lync Server aus.</span><span class="sxs-lookup"><span data-stu-id="4d7cf-112">In Event Viewer, click **Applications and Services logs** to expand it, and then select Lync Server.</span></span>

4.  <span data-ttu-id="4d7cf-113">Klicken Sie im Bereich **Aktionen** auf **Aktuelles Protokoll filtern**.</span><span class="sxs-lookup"><span data-stu-id="4d7cf-113">In the **Actions** pane click **Filter Current Log**.</span></span>

5.  <span data-ttu-id="4d7cf-114">Klicken Sie in der Liste **Ereignisquellen** auf **ls-Benutzer Replikations**Dienst.</span><span class="sxs-lookup"><span data-stu-id="4d7cf-114">From the **Event sources** list, click **LS User Replicator**.</span></span>

6.  <span data-ttu-id="4d7cf-115">Geben Sie in \*\* \<alle\> Ereignis-IDs\*\* **30024** ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="4d7cf-115">In **\<All Event IDs\>** enter **30024** and then click **OK**.</span></span>

7.  <span data-ttu-id="4d7cf-116">Suchen Sie in der Liste Gefilterte Ereignisse auf der Registerkarte **Allgemein** nach einem Eintrag, der besagt, dass die Benutzerreplikation erfolgreich abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="4d7cf-116">In the filtered events list, on the **General** tab, look for an entry that states user replication has completed successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

