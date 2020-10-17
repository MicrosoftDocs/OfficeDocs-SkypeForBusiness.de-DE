---
title: Überprüfen, ob die Benutzerreplikation abgeschlossen wurde
description: Stellen Sie sicher, dass die Benutzerreplikation abgeschlossen wurde.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify user replication has completed
ms:assetid: 119e9896-45e5-4f8b-af43-7b09360ada0b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204680(v=OCS.15)
ms:contentKeyID: 48183441
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60bca44fcce811c29b1633bd4d3a39f832851885
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555481"
---
# <a name="verify-user-replication-has-completed"></a><span data-ttu-id="e9a55-103">Überprüfen, ob die Benutzerreplikation abgeschlossen wurde</span><span class="sxs-lookup"><span data-stu-id="e9a55-103">Verify user replication has completed</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9a55-104">_**Letztes Änderungsstand des Themas:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="e9a55-104">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="e9a55-105">Beim Ausführen des Cmdlets " **CsUser** " kann ein Fehler auftreten, da die Benutzerinformationen zwischen Active Directory-Domänendienste (AD DS) und den lync Server 2013-Datenbanken nicht mehr synchron sind, da die anfängliche Replikation unvollständig ist.</span><span class="sxs-lookup"><span data-stu-id="e9a55-105">When running the **Move-CsUser** cmdlet, you may experience a failure because user information between Active Directory Domain Services (AD DS) and the Lync Server 2013 databases are out of sync because the initial replication is incomplete.</span></span> <span data-ttu-id="e9a55-106">Die Zeit, die für den erfolgreichen Abschluss der anfänglichen Synchronisierung des lync Server 2013 Benutzerreplikationsdiensts erforderlich ist, hängt von der Anzahl der Domänencontroller ab, die in der Active Directory Gesamtstruktur gehostet werden, die den lync Server 2013 Pool hostet.</span><span class="sxs-lookup"><span data-stu-id="e9a55-106">The time it takes for the successful completion of the Lync Server 2013 User Replicator service's initial synchronization depends on the number of domain controllers that are hosted in the Active Directory forest that hosts the Lync Server 2013 pool.</span></span> <span data-ttu-id="e9a55-107">Der anfängliche Synchronisierungsprozess für den lync Server 2013 Benutzerreplikationsdienst tritt auf, wenn die lync Server 2013 Front-End-Server zum ersten Mal gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="e9a55-107">The Lync Server 2013 User Replicator service initial synchronization process occurs when the Lync Server 2013 Front End Server is started for the first time.</span></span> <span data-ttu-id="e9a55-108">Danach wird die Synchronisierungshäufigkeit durch das Benutzerreplikationsintervall bestimmt.</span><span class="sxs-lookup"><span data-stu-id="e9a55-108">After that, the synchronization is then based on the User Replicator interval.</span></span> <span data-ttu-id="e9a55-109">Führen Sie die folgenden Schritte aus, um zu überprüfen, ob die Benutzerreplikation erfolgreich abgeschlossen wurde, bevor Sie das Cmdlet **Move-CsUser** ausführen.</span><span class="sxs-lookup"><span data-stu-id="e9a55-109">Complete the following steps to verify user replication has completed before running the **Move-CsUser** cmdlet.</span></span>

<div>

## <a name="to-verify-user-replication-has-completed"></a><span data-ttu-id="e9a55-110">So überprüfen Sie, ob die Benutzerreplikation abgeschlossen wurde</span><span class="sxs-lookup"><span data-stu-id="e9a55-110">To verify user replication has completed</span></span>

1.  <span data-ttu-id="e9a55-111">Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.</span><span class="sxs-lookup"><span data-stu-id="e9a55-111">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="e9a55-112">Klicken Sie auf das Menü **Start** und anschließend auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="e9a55-112">Click the **Start** menu, and then click **Run**.</span></span>

3.  <span data-ttu-id="e9a55-113">Geben Sie **eventvwr.exe** ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e9a55-113">Enter **eventvwr.exe** and then click **OK**.</span></span>

4.  <span data-ttu-id="e9a55-114">Klicken Sie in der Ereignisanzeige auf **Anwendungs- und Dienstprotokolle**, um die Ansicht zu erweitern, und wählen Sie dann "Lync Server".</span><span class="sxs-lookup"><span data-stu-id="e9a55-114">In Event Viewer, click **Applications and Services logs** to expand it, and then select Lync Server.</span></span>

5.  <span data-ttu-id="e9a55-115">Klicken Sie im Bereich **Aktion** auf **Aktuelles Protokoll filtern**.</span><span class="sxs-lookup"><span data-stu-id="e9a55-115">In the **Actions** pane click **Filter Current Log**.</span></span>

6.  <span data-ttu-id="e9a55-116">Klicken Sie in der Liste **Ereignisquellen** auf **LS User Replicator**.</span><span class="sxs-lookup"><span data-stu-id="e9a55-116">From the **Event sources** list, click **LS User Replicator**.</span></span>

7.  <span data-ttu-id="e9a55-117">**\<All Event IDs\>** Geben Sie in Eingabe **30024** ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e9a55-117">In **\<All Event IDs\>** enter **30024** and then click **OK**.</span></span>

8.  <span data-ttu-id="e9a55-118">Suchen Sie auf der Registerkarte **Allgemein** in der Liste der gefilterten Ereignisse einen Eintrag, der angibt, dass die Benutzerreplikation erfolgreich ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="e9a55-118">In the filtered events list, on the **General** tab, look for an entry that states user replication has completed successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

