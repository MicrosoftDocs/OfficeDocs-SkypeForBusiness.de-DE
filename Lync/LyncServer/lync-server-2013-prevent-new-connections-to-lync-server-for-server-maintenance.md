---
title: Verhindern, dass neue Verbindungen für die Server Wartung lync Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prevent new connections to Lync Server for server maintenance
ms:assetid: 22b27adf-a590-43bd-9306-a5789ae108d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520964(v=OCS.15)
ms:contentKeyID: 48183625
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06516c3d47a9ec5e491a5a16098dfae334ff4f4e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139076"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="prevent-new-connections-to-lync-server-2013-for-server-maintenance"></a><span data-ttu-id="0adb5-102">Verhindern, dass neue Verbindungen für die Server Wartung lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0adb5-102">Prevent new connections to Lync Server 2013 for server maintenance</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0adb5-103">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="0adb5-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="0adb5-104">Mit lync Server können Sie einen Server offline schalten (beispielsweise zum Anwenden von Software-oder Hardwareupgrades), ohne dass der Dienst für die Benutzer verloren geht.</span><span class="sxs-lookup"><span data-stu-id="0adb5-104">Lync Server enables you to take a server offline (for example, to apply software or hardware upgrades) without any loss of service to users.</span></span>

<span data-ttu-id="0adb5-p101">Wenn Sie die Option zum Verhindern neuer Verbindungen oder Anrufe an einen Server innerhalb eines Pools angeben, werden keine neuen Verbindungen hergestellt oder Anrufe angenommen, sobald Sie diese Option aktivieren. Alle neuen Verbindungen und Anrufe werden an andere Server im Pool umgeleitet. Ein Server, der neue Verbindungen verhindert, ermöglicht die Fortsetzung von Sitzungen für bereits hergestellte Verbindungen, bis diese vom Benutzer beendet werden. Sobald alle vorhandenen Sitzungen beendet wurden, kann der Server offline geschaltet werden.</span><span class="sxs-lookup"><span data-stu-id="0adb5-p101">When you specify the option to prevent new connections or calls to a server in a pool, it stops taking any new connections and calls as soon as you implement this option. These new connections and calls are routed through other servers in the pool. A server that is preventing new connections allows its sessions on existing connections to continue until they naturally end. When all existing sessions have ended, the server is ready to be taken offline.</span></span>

<span data-ttu-id="0adb5-109">Wenn Sie neue Verbindungen mit einem Front-End-Server verhindern, beruhen einige lync Server-Features und-Dienste auf dem DNS-Lastenausgleich, um sicherzustellen, dass er ordnungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="0adb5-109">When you prevent new connections to a Front End Server, some Lync Server features and services rely on DNS load balancing to ensure that it functions properly.</span></span> <span data-ttu-id="0adb5-110">Wenn Sie keinen DNS-Lastenausgleich im Pool verwenden, werden Verbindungen über diese Dienste möglicherweise nicht an andere Server umgeleitet, während der Zeitraum, in dem der Server neue Verbindungen verhindert, und daher, wenn der Server offline geschaltet wird, einige Sitzungen und Anrufe möglicherweise unterbrochen.</span><span class="sxs-lookup"><span data-stu-id="0adb5-110">If you are not using DNS load balancing on the pool, connections through these services may not be re-routed to other servers during the period that the server is preventing new connections, and thus when the server is taken offline some sessions and calls may be interrupted.</span></span> <span data-ttu-id="0adb5-111">Die Funktionen, die DNS-Lastenausgleich verwenden, um sicherzustellen, dass diese Option ordnungsgemäß funktioniert, lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="0adb5-111">The features that rely on DNS load balancing to ensure that this option operates properly are as follows:</span></span>

  - <span data-ttu-id="0adb5-112">Telefonzentrale</span><span class="sxs-lookup"><span data-stu-id="0adb5-112">Attendant</span></span>

  - <span data-ttu-id="0adb5-113">Konferenzankündigungsanwendung</span><span class="sxs-lookup"><span data-stu-id="0adb5-113">Conferencing Announcement application</span></span>

  - <span data-ttu-id="0adb5-114">Reaktionsgruppenanwendung</span><span class="sxs-lookup"><span data-stu-id="0adb5-114">Response Group application</span></span>

  - <span data-ttu-id="0adb5-115">Ankündigungsanwendung</span><span class="sxs-lookup"><span data-stu-id="0adb5-115">Announcement application</span></span>

  - <span data-ttu-id="0adb5-116">Anwendung zum Parken von Anrufen</span><span class="sxs-lookup"><span data-stu-id="0adb5-116">Call Park application</span></span>

<span data-ttu-id="0adb5-117">Ausführliche Informationen zum DNS-Lastenausgleich finden Sie unter [DNS-Lastenausgleich in lync Server 2013](lync-server-2013-dns-load-balancing.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="0adb5-117">For details about DNS load balancing, see [DNS load balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md) in the Planning documentation.</span></span>

<span data-ttu-id="0adb5-118">Zusätzlich zur Verhinderung neuer Verbindungen für alle Dienste auf einem Server mit lync Server können Sie auch neue Verbindungen für einzelne lync Server Dienste verhindern.</span><span class="sxs-lookup"><span data-stu-id="0adb5-118">In addition to preventing new connections for all services on a server running Lync Server, you can also prevent new connections for individual Lync Server services.</span></span> <span data-ttu-id="0adb5-119">Diese Methode ist beispielsweise hilfreich in Situationen, in denen Sie ein lync Server-Update anwenden müssen, bei dem der gesamte Server nicht heruntergefahren werden muss.</span><span class="sxs-lookup"><span data-stu-id="0adb5-119">For example, this method is useful in a situation where you need to apply a Lync Server update that does not require the whole server to be shut down.</span></span> <span data-ttu-id="0adb5-120">Hinweis: Wenn Sie Verbindungen für einen Dienst verhindern, müssen Sie den Dienst basierend auf der Gruppierung und Anzeige in der Windows-Liste von Diensten auswählen.</span><span class="sxs-lookup"><span data-stu-id="0adb5-120">Note that when you prevent connections for one service, you must select a service as it is grouped and displayed in the Windows list of services.</span></span> <span data-ttu-id="0adb5-121">Beispielsweise sind der lync Server-Front-End-Dienst und der Datenerfassungs-Agent für die Überwachung separate lync Server Dienste, in der Liste der Windows-Dienste werden Sie jedoch konsolidiert und als lync Server Front-End-Dienst angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0adb5-121">For example, the Lync Server Front-End service and the data collection agent for Monitoring are separate Lync Server services, but in the Windows services list they are consolidated and shown as the Lync Server Front End service.</span></span> <span data-ttu-id="0adb5-122">Sie können neue Verbindungen für den lync Server-Front-End-Dienst verhindern, aber Sie können keine neuen Verbindungen für diese beiden einzelnen zugrunde liegenden lync Server Dienste separat verhindern.</span><span class="sxs-lookup"><span data-stu-id="0adb5-122">You can prevent new connections for the Lync Server Front End service, but you cannot prevent new connections for these two individual underlying Lync Server services separately.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="0adb5-p104">Wenn Sie einen Server so konfigurieren, dass neue Verbindungen verhindert werden, und diesen Server anschließend neu starten, lässt der Server standardmäßig sofort wieder neue Verbindungen zu. Um dies zu verhindern, konfigurieren Sie den Server vor dem Neustart so, dass der Dienst nur manuell angehalten und fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="0adb5-p104">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts. To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>



</div>

<div>

## <a name="to-prevent-new-connections-to-lync-server"></a><span data-ttu-id="0adb5-125">So verhindern Sie, dass neue Verbindungen lync Server:</span><span class="sxs-lookup"><span data-stu-id="0adb5-125">To prevent new connections to Lync Server:</span></span>

1.  <span data-ttu-id="0adb5-126">Melden Sie sich beim lokalen Computer als Mitglied der Gruppe Administratoren an.</span><span class="sxs-lookup"><span data-stu-id="0adb5-126">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="0adb5-127">Öffnen Sie die Konsole Dienste-Snap-in: Klicken Sie auf **Start**, dann auf **Alle Programme**, dann auf **Verwaltung**, und klicken Sie dann auf **Dienste**.</span><span class="sxs-lookup"><span data-stu-id="0adb5-127">Open the Services snap-in console: Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Services**.</span></span>

3.  <span data-ttu-id="0adb5-128">Doppelklicken Sie in der Liste auf den Lync Server-Windows-Dienst, für den Sie neue Verbindungen verhindern möchten.</span><span class="sxs-lookup"><span data-stu-id="0adb5-128">In the list, double-click the Lync Server Windows service to which you want to prevent new connections.</span></span>

4.  <span data-ttu-id="0adb5-129">Klicken Sie im Eigenschaftendialogfeld unter **Dienststatus: Gestartet** auf **Anhalten**.</span><span class="sxs-lookup"><span data-stu-id="0adb5-129">In the Properties dialog box, under **Service status: Started**, click **Pause**.</span></span>

5.  <span data-ttu-id="0adb5-130">Es empfiehlt sich, neben **Starttyp** auf **Manuell** zu klicken. Dies ist jedoch optional.</span><span class="sxs-lookup"><span data-stu-id="0adb5-130">Optionally, but recommended, next to **Startup type**, click **Manual**.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="0adb5-p105">Wenn Sie einen Server so konfigurieren, dass neue Verbindungen verhindert werden, und diesen Server anschließend neu starten, lässt der Server standardmäßig sofort wieder neue Verbindungen zu. Um dies zu verhindern, konfigurieren Sie den Server vor dem Neustart so, dass der Dienst nur manuell angehalten und fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="0adb5-p105">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts. To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>

    
    </div>

6.  <span data-ttu-id="0adb5-133">Nachdem Sie die Eingabe beendet haben, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="0adb5-133">When you are finished, click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

