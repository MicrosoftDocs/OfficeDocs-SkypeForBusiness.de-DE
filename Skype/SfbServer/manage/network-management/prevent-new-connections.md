---
title: Verhindern neuer Verbindungen
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: bc9b4a1e7d6e17f09643ff14ac0e69261c326922
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199020"
---
# <a name="preventing-new-connections-to-skype-for-business-server-for-server-maintenance"></a><span data-ttu-id="cdfab-102">Verhindern neuer Verbindungen mit Skype für Business Server zur Serverwartung</span><span class="sxs-lookup"><span data-stu-id="cdfab-102">Preventing new connections to Skype for Business Server for server maintenance</span></span>


<span data-ttu-id="cdfab-103">Skype für Business Server können Sie einen Server offline schalten (z. B. Software- oder Hardwareupgrades anzuwenden) ohne Verlust des Diensts für Benutzer zu übernehmen.</span><span class="sxs-lookup"><span data-stu-id="cdfab-103">Skype for Business Server enables you to take a server offline (for example, to apply software or hardware upgrades) without any loss of service to users.</span></span>

<span data-ttu-id="cdfab-104">Wenn Sie die Option, um zu verhindern, dass neue Verbindungen oder Anrufe auf einem Server in einem Pool angeben, wird jede neue Verbindungen und Anrufe annimmt, sobald Sie diese Option implementieren beendet.</span><span class="sxs-lookup"><span data-stu-id="cdfab-104">When you specify the option to prevent new connections or calls to a server in a pool, it stops taking any new connections and calls as soon as you implement this option.</span></span> <span data-ttu-id="cdfab-105">Diese neue Verbindungen und Anrufe werden über den anderen Servern im Pool weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="cdfab-105">These new connections and calls are routed through other servers in the pool.</span></span> <span data-ttu-id="cdfab-106">Ein Server, der neue Verbindungen verhindern kann die Sitzungen auf vorhandene Verbindungen, um den Vorgang fortzusetzen, bis sie natürlich enden.</span><span class="sxs-lookup"><span data-stu-id="cdfab-106">A server that is preventing new connections allows its sessions on existing connections to continue until they naturally end.</span></span> <span data-ttu-id="cdfab-107">Wenn Sie alle vorhandene Sitzungen beendet haben, ist der Server offline geschaltet werden bereit.</span><span class="sxs-lookup"><span data-stu-id="cdfab-107">When all existing sessions have ended, the server is ready to be taken offline.</span></span>

<span data-ttu-id="cdfab-108">Wenn Sie neue Verbindungen mit einem Front-End-Server verhindern, einige Skype für Business Server-Features und Dienste hängen von DNS-Lastenausgleich, um sicherzustellen, dass es ordnungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="cdfab-108">When you prevent new connections to a Front End Server, some Skype for Business Server features and services rely on DNS load balancing to ensure that it functions properly.</span></span> <span data-ttu-id="cdfab-109">Wenn Sie DNS-Lastenausgleich im Pool nicht verwenden, Verbindungen über diese Dienste möglicherweise nicht mit anderen Servern weitergeleitet während des Berichtszeitraums, dass der Server neue Verbindungen verhindern ist und daher bei der Server ist offline geschaltet einige Sitzungen und Anrufe möglicherweise unterbrochen.</span><span class="sxs-lookup"><span data-stu-id="cdfab-109">If you are not using DNS load balancing on the pool, connections through these services may not be re-routed to other servers during the period that the server is preventing new connections, and thus when the server is taken offline some sessions and calls may be interrupted.</span></span> <span data-ttu-id="cdfab-110">Die Features, die DNS-Lastenausgleich, um sicherzustellen, dass diese Option reibungsloses abhängig sind wie folgt:</span><span class="sxs-lookup"><span data-stu-id="cdfab-110">The features that rely on DNS load balancing to ensure that this option operates properly are as follows:</span></span>

  - <span data-ttu-id="cdfab-111">Vermittlung</span><span class="sxs-lookup"><span data-stu-id="cdfab-111">Attendant</span></span>

  - <span data-ttu-id="cdfab-112">Konferenzankündigungsanwendung</span><span class="sxs-lookup"><span data-stu-id="cdfab-112">Conferencing Announcement application</span></span>

  - <span data-ttu-id="cdfab-113">Reaktionsgruppenanwendung</span><span class="sxs-lookup"><span data-stu-id="cdfab-113">Response Group application</span></span>

  - <span data-ttu-id="cdfab-114">Ansageanwendung</span><span class="sxs-lookup"><span data-stu-id="cdfab-114">Announcement application</span></span>

  - <span data-ttu-id="cdfab-115">Anwendung zum Parken von Anrufen</span><span class="sxs-lookup"><span data-stu-id="cdfab-115">Call Park application</span></span>

<span data-ttu-id="cdfab-116">Ausführliche Informationen zu DNS-Lastenausgleich finden Sie unter [Lastenausgleich Anforderungen an den](../../plan-your-deployment/network-requirements/load-balancing.md).</span><span class="sxs-lookup"><span data-stu-id="cdfab-116">For details about DNS load balancing, see [Load balancing requirements](../../plan-your-deployment/network-requirements/load-balancing.md).</span></span>

<span data-ttu-id="cdfab-117">Zusätzlich zu verhindern neuer Verbindungen für alle Dienste auf einem Server mit Skype für Business Server, können Sie auch neue Verbindungen für einzelne Skype für Business Server-Dienste verhindern.</span><span class="sxs-lookup"><span data-stu-id="cdfab-117">In addition to preventing new connections for all services on a server running Skype for Business Server, you can also prevent new connections for individual Skype for Business Server services.</span></span> <span data-ttu-id="cdfab-118">Diese Methode eignet sich beispielsweise in einer Situation, in denen Sie müssen einen Skype für Business Serverupdate angewendet wird, die nicht den gesamten Server heruntergefahren werden, erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="cdfab-118">For example, this method is useful in a situation where you need to apply a Skype for Business Server update that does not require the whole server to be shut down.</span></span> <span data-ttu-id="cdfab-119">Beachten Sie, dass wenn Sie Verbindungen für einen Dienst verhindern, wählen Sie einen Dienst aus müssen sie gruppiert und in der Windows-Liste der Dienste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cdfab-119">Note that when you prevent connections for one service, you must select a service as it is grouped and displayed in the Windows list of services.</span></span> <span data-ttu-id="cdfab-120">Angenommen, der Skype für Business Server Front-End-Dienst und den Daten Auflistung-Agent für Überwachung sind separate Skype für Business Server-Dienste, aber in der Liste der Windows-Dienste konsolidierte und dargestellt als die Skype für Business Server-Front-End Dienst.</span><span class="sxs-lookup"><span data-stu-id="cdfab-120">For example, the Skype for Business Server Front-End service and the data collection agent for Monitoring are separate Skype for Business Server services, but in the Windows services list they are consolidated and shown as the Skype for Business Server Front End service.</span></span> <span data-ttu-id="cdfab-121">Sie können verhindern, dass neue Verbindungen für die Skype für Business Server-Front-End-Dienst, aber Sie können nicht verhindern, dass neue Verbindungen für diese zwei einzelne zugrunde liegenden Skype für Business Server-Dienste separat.</span><span class="sxs-lookup"><span data-stu-id="cdfab-121">You can prevent new connections for the Skype for Business Server Front End service, but you cannot prevent new connections for these two individual underlying Skype for Business Server services separately.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cdfab-122">Beim Festlegen eines Servers zum verhindern neuer Verbindungen, und klicken Sie dann den Server neu starten, wird standardmäßig der Server sofort neue Verbindungen akzeptieren, nachdem er beginnt.</span><span class="sxs-lookup"><span data-stu-id="cdfab-122">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts.</span></span> <span data-ttu-id="cdfab-123">Um dies zu verhindern, legen Sie den Server für nur anhalten und Fortsetzen von manuell, bevor Sie den Server neu starten.</span><span class="sxs-lookup"><span data-stu-id="cdfab-123">To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>

## <a name="to-prevent-new-connections-to-skype-for-business-server"></a><span data-ttu-id="cdfab-124">So verhindern Sie neue Verbindungen zu Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="cdfab-124">To prevent new connections to Skype for Business Server</span></span>

1.  <span data-ttu-id="cdfab-125">Melden Sie sich auf dem lokalen Computer als Mitglied der Gruppe "Administratoren" an.</span><span class="sxs-lookup"><span data-stu-id="cdfab-125">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="cdfab-126">Öffnen Sie die Konsole Dienste-Snap-in: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme**, zeigen Sie auf **Verwaltung**, und klicken Sie dann auf **Dienste**.</span><span class="sxs-lookup"><span data-stu-id="cdfab-126">Open the Services snap-in console: Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Services**.</span></span>

3.  <span data-ttu-id="cdfab-127">Doppelklicken Sie in der Liste auf die Skype für Business-Windows-Dienst, dem Sie neue Verbindungen verhindern möchten.</span><span class="sxs-lookup"><span data-stu-id="cdfab-127">In the list, double-click the Skype for Business Server Windows service to which you want to prevent new connections.</span></span>

4.  <span data-ttu-id="cdfab-128">Klicken Sie im Dialogfeld Eigenschaften unter **Dienststatus: gestartet**, klicken Sie auf **Anhalten**.</span><span class="sxs-lookup"><span data-stu-id="cdfab-128">In the Properties dialog box, under **Service status: Started**, click **Pause**.</span></span>

5.  <span data-ttu-id="cdfab-129">Optional, aber empfohlen, klicken Sie neben **Starttyp**auf **manuell**.</span><span class="sxs-lookup"><span data-stu-id="cdfab-129">Optionally, but recommended, next to **Startup type**, click **Manual**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="cdfab-130">Beim Festlegen eines Servers zum verhindern neuer Verbindungen, und klicken Sie dann den Server neu starten, wird standardmäßig der Server sofort neue Verbindungen akzeptieren, nachdem er beginnt.</span><span class="sxs-lookup"><span data-stu-id="cdfab-130">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts.</span></span> <span data-ttu-id="cdfab-131">Um dies zu verhindern, legen Sie den Server für nur anhalten und Fortsetzen von manuell, bevor Sie den Server neu starten.</span><span class="sxs-lookup"><span data-stu-id="cdfab-131">To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>
