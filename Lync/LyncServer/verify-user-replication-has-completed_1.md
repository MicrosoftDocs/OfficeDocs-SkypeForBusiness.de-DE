---
title: Überprüfen, ob die Benutzerreplikation abgeschlossen wurde
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify user replication has completed
ms:assetid: 199dc9de-b555-468f-a42a-9e92ea6c9053
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204712(v=OCS.15)
ms:contentKeyID: 48183524
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31bed57b6e24db0ba6f75e323fe311aa4aaf262c
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755519"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-user-replication-has-completed"></a><span data-ttu-id="7c5f8-102">Überprüfen, ob die Benutzerreplikation abgeschlossen wurde</span><span class="sxs-lookup"><span data-stu-id="7c5f8-102">Verify user replication has completed</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c5f8-103">_**Letztes Änderungsstand des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="7c5f8-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="7c5f8-104">Beim Ausführen des Cmdlets " **CsLegacyUser** " kann ein Fehler auftreten, da Benutzerinformationen zwischen Active Directory-Domänendienste (AD DS) und den lync Server 2013 Datenbanken nicht mehr synchron sind, da die anfängliche Replikation unvollständig ist.</span><span class="sxs-lookup"><span data-stu-id="7c5f8-104">When running the **Move-CsLegacyUser** cmdlet, you may experience a failure due to user information between Active Directory Domain Services (AD DS) and the Lync Server 2013 databases being out of sync because the initial replication is incomplete.</span></span> <span data-ttu-id="7c5f8-105">Die Zeit, die für den erfolgreichen Abschluss der anfänglichen Synchronisierung des lync Server 2013 Benutzerreplikationsdiensts erforderlich ist, hängt von der Anzahl der Domänencontroller ab, die in der Active Directory Gesamtstruktur gehostet werden, die den lync Server 2013 Pool hostet.</span><span class="sxs-lookup"><span data-stu-id="7c5f8-105">The time it takes for the successful completion of the Lync Server 2013 User Replicator service's initial synchronization depends on the number of domain controllers that are hosted in the Active Directory forest that hosts the Lync Server 2013 pool.</span></span> <span data-ttu-id="7c5f8-106">Der anfängliche Synchronisierungsprozess für den lync Server 2013 Benutzerreplikationsdienst tritt auf, wenn die lync Server 2013 Front-End-Server zum ersten Mal gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="7c5f8-106">The Lync Server 2013 User Replicator service initial synchronization process occurs when the Lync Server 2013 Front End Server is started for the first time.</span></span> <span data-ttu-id="7c5f8-107">Danach wird die Synchronisierungshäufigkeit durch das Benutzerreplikationsintervall bestimmt.</span><span class="sxs-lookup"><span data-stu-id="7c5f8-107">After that, the synchronization is then based on the User Replicator interval.</span></span> <span data-ttu-id="7c5f8-108">Führen Sie die folgenden Schritte aus, um zu überprüfen, ob die Benutzerreplikation erfolgreich abgeschlossen wurde, bevor Sie das Cmdlet **Move-CsLegacyUser** ausführen.</span><span class="sxs-lookup"><span data-stu-id="7c5f8-108">Complete the following steps to verify user replication has completed before running the **Move-CsLegacyUser** cmdlet.</span></span>

<div>

## <a name="to-verify-that-user-replication-has-completed"></a><span data-ttu-id="7c5f8-109">So überprüfen Sie, dass die Benutzerreplikation abgeschlossen wurde</span><span class="sxs-lookup"><span data-stu-id="7c5f8-109">To verify that user replication has completed</span></span>

1.  <span data-ttu-id="7c5f8-110">Klicken Sie auf dem lync Server 2013-Front-End-Server auf das **Startmenü** , und klicken Sie dann auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="7c5f8-110">From the Lync Server 2013 Front End server, click the **Start** menu, and then click **Run**.</span></span>

2.  <span data-ttu-id="7c5f8-111">Geben Sie **eventvwr.exe** ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="7c5f8-111">Enter **eventvwr.exe** and then click **OK**.</span></span>

3.  <span data-ttu-id="7c5f8-112">Klicken Sie in der Ereignisanzeige auf **Anwendungs- und Dienstprotokolle**, um die Ansicht zu erweitern, und wählen Sie dann "Lync Server".</span><span class="sxs-lookup"><span data-stu-id="7c5f8-112">In Event Viewer, click **Applications and Services logs** to expand it, and then select Lync Server.</span></span>

4.  <span data-ttu-id="7c5f8-113">Klicken Sie im Bereich **Aktion** auf **Aktuelles Protokoll filtern**.</span><span class="sxs-lookup"><span data-stu-id="7c5f8-113">In the **Actions** pane click **Filter Current Log**.</span></span>

5.  <span data-ttu-id="7c5f8-114">Klicken Sie in der Liste **Ereignisquellen** auf **LS User Replicator**.</span><span class="sxs-lookup"><span data-stu-id="7c5f8-114">From the **Event sources** list, click **LS User Replicator**.</span></span>

6.  <span data-ttu-id="7c5f8-115">**\<All Event IDs\>** Geben Sie in Eingabe **30024** ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="7c5f8-115">In **\<All Event IDs\>** enter **30024** and then click **OK**.</span></span>

7.  <span data-ttu-id="7c5f8-116">Suchen Sie auf der Registerkarte **Allgemein** in der Liste der gefilterten Ereignisse einen Eintrag, der angibt, dass die Benutzerreplikation erfolgreich ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="7c5f8-116">In the filtered events list, on the **General** tab, look for an entry that states user replication has completed successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

