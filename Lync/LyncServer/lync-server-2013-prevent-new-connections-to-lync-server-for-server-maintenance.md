---
title: Verhindern neuer Verbindungen mit lync Server für die Serverwartung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Prevent new connections to Lync Server for server maintenance
ms:assetid: 22b27adf-a590-43bd-9306-a5789ae108d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520964(v=OCS.15)
ms:contentKeyID: 48183625
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: db3838af59a6a91699fa6d38b8aa2912e2b30012
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823763"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prevent-new-connections-to-lync-server-2013-for-server-maintenance"></a><span data-ttu-id="034ed-102">Verhindern neuer Verbindungen mit lync Server 2013 für die Server Wartung</span><span class="sxs-lookup"><span data-stu-id="034ed-102">Prevent new connections to Lync Server 2013 for server maintenance</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="034ed-103">_**Letztes Änderungsdatum des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="034ed-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="034ed-104">Mit lync Server können Sie einen Server offline schalten (beispielsweise um Software-oder Hardwareupgrades anzuwenden), ohne dass der Dienst für die Benutzer verloren geht.</span><span class="sxs-lookup"><span data-stu-id="034ed-104">Lync Server enables you to take a server offline (for example, to apply software or hardware upgrades) without any loss of service to users.</span></span>

<span data-ttu-id="034ed-105">Wenn Sie die Option zum verhindern neuer Verbindungen oder Aufrufe an einen Server in einem Pool angeben, werden alle neuen Verbindungen und Anrufe nicht mehr Unternehmen, sobald Sie diese Option implementieren.</span><span class="sxs-lookup"><span data-stu-id="034ed-105">When you specify the option to prevent new connections or calls to a server in a pool, it stops taking any new connections and calls as soon as you implement this option.</span></span> <span data-ttu-id="034ed-106">Diese neuen Verbindungen und Anrufe werden über andere Server im Pool weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="034ed-106">These new connections and calls are routed through other servers in the pool.</span></span> <span data-ttu-id="034ed-107">Ein Server, der neue Verbindungen verhindert, ermöglicht, dass seine Sitzungen an vorhandenen Verbindungen fortgesetzt werden, bis Sie natürlich enden.</span><span class="sxs-lookup"><span data-stu-id="034ed-107">A server that is preventing new connections allows its sessions on existing connections to continue until they naturally end.</span></span> <span data-ttu-id="034ed-108">Wenn alle vorhandenen Sitzungen beendet sind, kann der Server offline geschaltet werden.</span><span class="sxs-lookup"><span data-stu-id="034ed-108">When all existing sessions have ended, the server is ready to be taken offline.</span></span>

<span data-ttu-id="034ed-109">Wenn Sie neue Verbindungen mit einem Front-End-Server verhindern, Vertrauen einige lync Server-Features und-Dienste auf den DNS-Lastenausgleich, um sicherzustellen, dass Sie ordnungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="034ed-109">When you prevent new connections to a Front End Server, some Lync Server features and services rely on DNS load balancing to ensure that it functions properly.</span></span> <span data-ttu-id="034ed-110">Wenn Sie keinen DNS-Lastenausgleich für den Pool verwenden, werden Verbindungen über diese Dienste möglicherweise während des Zeitraums, in dem der Server neue Verbindungen verhindert, nicht an andere Server umgeleitet, und wenn der Server offline geschaltet wird, werden einige Sitzungen und Anrufe möglicherweise unterbrochen.</span><span class="sxs-lookup"><span data-stu-id="034ed-110">If you are not using DNS load balancing on the pool, connections through these services may not be re-routed to other servers during the period that the server is preventing new connections, and thus when the server is taken offline some sessions and calls may be interrupted.</span></span> <span data-ttu-id="034ed-111">Die Features, die vom DNS-Lastenausgleich abhängig sind, um sicherzustellen, dass diese Option ordnungsgemäß funktioniert, sind wie folgt:</span><span class="sxs-lookup"><span data-stu-id="034ed-111">The features that rely on DNS load balancing to ensure that this option operates properly are as follows:</span></span>

  - <span data-ttu-id="034ed-112">Vermittlung</span><span class="sxs-lookup"><span data-stu-id="034ed-112">Attendant</span></span>

  - <span data-ttu-id="034ed-113">Konferenzankündigungsanwendung</span><span class="sxs-lookup"><span data-stu-id="034ed-113">Conferencing Announcement application</span></span>

  - <span data-ttu-id="034ed-114">Reaktionsgruppenanwendung</span><span class="sxs-lookup"><span data-stu-id="034ed-114">Response Group application</span></span>

  - <span data-ttu-id="034ed-115">Ansageanwendung</span><span class="sxs-lookup"><span data-stu-id="034ed-115">Announcement application</span></span>

  - <span data-ttu-id="034ed-116">Anwendung zum Parken von Anrufen</span><span class="sxs-lookup"><span data-stu-id="034ed-116">Call Park application</span></span>

<span data-ttu-id="034ed-117">Details zum DNS-Lastenausgleich finden Sie unter [DNS-Lastenausgleich in lync Server 2013](lync-server-2013-dns-load-balancing.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="034ed-117">For details about DNS load balancing, see [DNS load balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md) in the Planning documentation.</span></span>

<span data-ttu-id="034ed-118">Zusätzlich zum verhindern neuer Verbindungen für alle Dienste auf einem Server, auf dem lync Server ausgeführt wird, können Sie auch neue Verbindungen für einzelne lync Server-Dienste verhindern.</span><span class="sxs-lookup"><span data-stu-id="034ed-118">In addition to preventing new connections for all services on a server running Lync Server, you can also prevent new connections for individual Lync Server services.</span></span> <span data-ttu-id="034ed-119">Diese Methode ist beispielsweise hilfreich in einer Situation, in der Sie ein lync Server-Update anwenden müssen, das nicht erfordert, dass der gesamte Server beendet wird.</span><span class="sxs-lookup"><span data-stu-id="034ed-119">For example, this method is useful in a situation where you need to apply a Lync Server update that does not require the whole server to be shut down.</span></span> <span data-ttu-id="034ed-120">Beachten Sie, dass Sie einen Dienst auswählen müssen, wenn Sie Verbindungen für einen Dienst verhindern, indem Sie ihn gruppieren und in der Windows-Liste der Dienste angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="034ed-120">Note that when you prevent connections for one service, you must select a service as it is grouped and displayed in the Windows list of services.</span></span> <span data-ttu-id="034ed-121">Beispielsweise sind der lync Server-Front-End-Dienst und der Daten Sammlungs-Agent für die Überwachung separate lync Server-Dienste, in der Liste der Windows-Dienste werden Sie jedoch konsolidiert und als der lync Server-Front-End-Dienst angezeigt.</span><span class="sxs-lookup"><span data-stu-id="034ed-121">For example, the Lync Server Front-End service and the data collection agent for Monitoring are separate Lync Server services, but in the Windows services list they are consolidated and shown as the Lync Server Front End service.</span></span> <span data-ttu-id="034ed-122">Sie können neue Verbindungen für den lync Server-Front-End-Dienst verhindern, jedoch können Sie keine neuen Verbindungen für diese beiden einzelnen zugrunde liegenden lync Server-Dienste separat verhindern.</span><span class="sxs-lookup"><span data-stu-id="034ed-122">You can prevent new connections for the Lync Server Front End service, but you cannot prevent new connections for these two individual underlying Lync Server services separately.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="034ed-123">Wenn Sie einen Server so einrichten, dass neue Verbindungen verhindert werden, und den Server dann neu starten, wird der Server standardmäßig unmittelbar nach dem Start neue Verbindungen akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="034ed-123">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts.</span></span> <span data-ttu-id="034ed-124">Um dies zu verhindern, müssen Sie den Server so einrichten, dass er vor dem Neustart des Servers nur manuell angehalten und fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="034ed-124">To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>



</div>

<div>

## <a name="to-prevent-new-connections-to-lync-server"></a><span data-ttu-id="034ed-125">So verhindern Sie neue Verbindungen mit lync Server:</span><span class="sxs-lookup"><span data-stu-id="034ed-125">To prevent new connections to Lync Server:</span></span>

1.  <span data-ttu-id="034ed-126">Melden Sie sich auf dem lokalen Computer als Mitglied der Gruppe "Administratoren" an.</span><span class="sxs-lookup"><span data-stu-id="034ed-126">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="034ed-127">Öffnen Sie die Snap-In-Konsole Dienste: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme**, zeigen Sie auf **Verwaltung**, und klicken Sie dann auf **Dienste**.</span><span class="sxs-lookup"><span data-stu-id="034ed-127">Open the Services snap-in console: Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Services**.</span></span>

3.  <span data-ttu-id="034ed-128">Doppelklicken Sie in der Liste auf den lync Server-Windows-Dienst, auf den Sie neue Verbindungen verhindern möchten.</span><span class="sxs-lookup"><span data-stu-id="034ed-128">In the list, double-click the Lync Server Windows service to which you want to prevent new connections.</span></span>

4.  <span data-ttu-id="034ed-129">Klicken Sie im DialogfeldEigenschaften unter **Dienststatus: gestartet**auf **Anhalten**.</span><span class="sxs-lookup"><span data-stu-id="034ed-129">In the Properties dialog box, under **Service status: Started**, click **Pause**.</span></span>

5.  <span data-ttu-id="034ed-130">Optional, aber empfohlen, klicken Sie \*\*\*\* neben Starttyp auf **manuell**.</span><span class="sxs-lookup"><span data-stu-id="034ed-130">Optionally, but recommended, next to **Startup type**, click **Manual**.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="034ed-131">Wenn Sie einen Server so einrichten, dass neue Verbindungen verhindert werden, und den Server dann neu starten, wird der Server standardmäßig unmittelbar nach dem Start neue Verbindungen akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="034ed-131">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts.</span></span> <span data-ttu-id="034ed-132">Um dies zu verhindern, müssen Sie den Server so einrichten, dass er vor dem Neustart des Servers nur manuell angehalten und fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="034ed-132">To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>

    
    </div>

6.  <span data-ttu-id="034ed-133">Nachdem Sie die Eingabe beendet haben, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="034ed-133">When you are finished, click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

