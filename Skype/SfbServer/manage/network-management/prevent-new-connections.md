---
title: Verhindern neuer Verbindungen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ''
ms.openlocfilehash: c2df1c491384f8a248f70b67880511a2d496c173
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817454"
---
# <a name="preventing-new-connections-to-skype-for-business-server-for-server-maintenance"></a><span data-ttu-id="d6383-102">Verhindern neuer Verbindungen mit Skype for Business Server für die Serverwartung</span><span class="sxs-lookup"><span data-stu-id="d6383-102">Preventing new connections to Skype for Business Server for server maintenance</span></span>


<span data-ttu-id="d6383-103">Mit Skype for Business Server können Sie einen Server offline schalten (beispielsweise um Software-oder Hardware-Upgrades anzuwenden), ohne dass der Service für die Nutzer verloren geht.</span><span class="sxs-lookup"><span data-stu-id="d6383-103">Skype for Business Server enables you to take a server offline (for example, to apply software or hardware upgrades) without any loss of service to users.</span></span>

<span data-ttu-id="d6383-104">Wenn Sie die Option zum verhindern neuer Verbindungen oder Aufrufe an einen Server in einem Pool angeben, werden alle neuen Verbindungen und Anrufe nicht mehr Unternehmen, sobald Sie diese Option implementieren.</span><span class="sxs-lookup"><span data-stu-id="d6383-104">When you specify the option to prevent new connections or calls to a server in a pool, it stops taking any new connections and calls as soon as you implement this option.</span></span> <span data-ttu-id="d6383-105">Diese neuen Verbindungen und Anrufe werden über andere Server im Pool weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="d6383-105">These new connections and calls are routed through other servers in the pool.</span></span> <span data-ttu-id="d6383-106">Ein Server, der neue Verbindungen verhindert, ermöglicht, dass seine Sitzungen an vorhandenen Verbindungen fortgesetzt werden, bis Sie natürlich enden.</span><span class="sxs-lookup"><span data-stu-id="d6383-106">A server that is preventing new connections allows its sessions on existing connections to continue until they naturally end.</span></span> <span data-ttu-id="d6383-107">Wenn alle vorhandenen Sitzungen beendet sind, kann der Server offline geschaltet werden.</span><span class="sxs-lookup"><span data-stu-id="d6383-107">When all existing sessions have ended, the server is ready to be taken offline.</span></span>

<span data-ttu-id="d6383-108">Wenn Sie neue Verbindungen mit einem Front-End-Server verhindern, Vertrauen einige Funktionen und Dienste von Skype for Business Server auf den DNS-Lastenausgleich, um sicherzustellen, dass Sie ordnungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="d6383-108">When you prevent new connections to a Front End Server, some Skype for Business Server features and services rely on DNS load balancing to ensure that it functions properly.</span></span> <span data-ttu-id="d6383-109">Wenn Sie keinen DNS-Lastenausgleich für den Pool verwenden, werden Verbindungen über diese Dienste möglicherweise während des Zeitraums, in dem der Server neue Verbindungen verhindert, nicht an andere Server umgeleitet, und wenn der Server offline geschaltet wird, werden einige Sitzungen und Anrufe möglicherweise unterbrochen.</span><span class="sxs-lookup"><span data-stu-id="d6383-109">If you are not using DNS load balancing on the pool, connections through these services may not be re-routed to other servers during the period that the server is preventing new connections, and thus when the server is taken offline some sessions and calls may be interrupted.</span></span> <span data-ttu-id="d6383-110">Die Features, die vom DNS-Lastenausgleich abhängig sind, um sicherzustellen, dass diese Option ordnungsgemäß funktioniert, sind wie folgt:</span><span class="sxs-lookup"><span data-stu-id="d6383-110">The features that rely on DNS load balancing to ensure that this option operates properly are as follows:</span></span>

  - <span data-ttu-id="d6383-111">Vermittlung</span><span class="sxs-lookup"><span data-stu-id="d6383-111">Attendant</span></span>

  - <span data-ttu-id="d6383-112">Konferenzankündigungsanwendung</span><span class="sxs-lookup"><span data-stu-id="d6383-112">Conferencing Announcement application</span></span>

  - <span data-ttu-id="d6383-113">Reaktionsgruppenanwendung</span><span class="sxs-lookup"><span data-stu-id="d6383-113">Response Group application</span></span>

  - <span data-ttu-id="d6383-114">Ansageanwendung</span><span class="sxs-lookup"><span data-stu-id="d6383-114">Announcement application</span></span>

  - <span data-ttu-id="d6383-115">Anwendung zum Parken von Anrufen</span><span class="sxs-lookup"><span data-stu-id="d6383-115">Call Park application</span></span>

<span data-ttu-id="d6383-116">Details zum DNS-Lastenausgleich finden Sie unter [Lastenausgleichsanforderungen](../../plan-your-deployment/network-requirements/load-balancing.md).</span><span class="sxs-lookup"><span data-stu-id="d6383-116">For details about DNS load balancing, see [Load balancing requirements](../../plan-your-deployment/network-requirements/load-balancing.md).</span></span>

<span data-ttu-id="d6383-117">Zusätzlich zur Verhinderung neuer Verbindungen für alle Dienste auf einem Server, auf dem Skype for Business Server ausgeführt wird, können Sie auch neue Verbindungen für einzelne Skype for Business Server-Dienste verhindern.</span><span class="sxs-lookup"><span data-stu-id="d6383-117">In addition to preventing new connections for all services on a server running Skype for Business Server, you can also prevent new connections for individual Skype for Business Server services.</span></span> <span data-ttu-id="d6383-118">Diese Methode ist beispielsweise hilfreich in einer Situation, in der Sie ein Skype for Business Server-Update anwenden müssen, das nicht erfordert, dass der gesamte Server beendet wird.</span><span class="sxs-lookup"><span data-stu-id="d6383-118">For example, this method is useful in a situation where you need to apply a Skype for Business Server update that does not require the whole server to be shut down.</span></span> <span data-ttu-id="d6383-119">Beachten Sie, dass Sie einen Dienst auswählen müssen, wenn Sie Verbindungen für einen Dienst verhindern, indem Sie ihn gruppieren und in der Windows-Liste der Dienste angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d6383-119">Note that when you prevent connections for one service, you must select a service as it is grouped and displayed in the Windows list of services.</span></span> <span data-ttu-id="d6383-120">Beispielsweise sind der Skype for Business Server-Front-End-Dienst und der Datenerfassungs-Agent für die Überwachung getrennte Skype for Business Server-Dienste, in der Windows-Diensteliste werden Sie jedoch konsolidiert und als Skype for Business Server-Front-End angezeigt. Dienst.</span><span class="sxs-lookup"><span data-stu-id="d6383-120">For example, the Skype for Business Server Front-End service and the data collection agent for Monitoring are separate Skype for Business Server services, but in the Windows services list they are consolidated and shown as the Skype for Business Server Front End service.</span></span> <span data-ttu-id="d6383-121">Sie können neue Verbindungen für den Skype for Business Server-Front-End-Dienst verhindern, aber Sie können keine neuen Verbindungen für diese beiden einzelnen zugrunde liegenden Skype for Business Server-Dienste separat verhindern.</span><span class="sxs-lookup"><span data-stu-id="d6383-121">You can prevent new connections for the Skype for Business Server Front End service, but you cannot prevent new connections for these two individual underlying Skype for Business Server services separately.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d6383-122">Wenn Sie einen Server so einrichten, dass neue Verbindungen verhindert werden, und den Server dann neu starten, wird der Server standardmäßig unmittelbar nach dem Start neue Verbindungen akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="d6383-122">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts.</span></span> <span data-ttu-id="d6383-123">Um dies zu verhindern, müssen Sie den Server so einrichten, dass er vor dem Neustart des Servers nur manuell angehalten und fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="d6383-123">To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>

## <a name="to-prevent-new-connections-to-skype-for-business-server"></a><span data-ttu-id="d6383-124">So verhindern Sie neue Verbindungen mit Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d6383-124">To prevent new connections to Skype for Business Server</span></span>

1.  <span data-ttu-id="d6383-125">Melden Sie sich auf dem lokalen Computer als Mitglied der Gruppe "Administratoren" an.</span><span class="sxs-lookup"><span data-stu-id="d6383-125">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="d6383-126">Öffnen Sie die Snap-In-Konsole Dienste: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme**, zeigen Sie auf **Verwaltung**, und klicken Sie dann auf **Dienste**.</span><span class="sxs-lookup"><span data-stu-id="d6383-126">Open the Services snap-in console: Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Services**.</span></span>

3.  <span data-ttu-id="d6383-127">Doppelklicken Sie in der Liste auf den Skype for Business Server-Windows-Dienst, auf den Sie neue Verbindungen verhindern möchten.</span><span class="sxs-lookup"><span data-stu-id="d6383-127">In the list, double-click the Skype for Business Server Windows service to which you want to prevent new connections.</span></span>

4.  <span data-ttu-id="d6383-128">Klicken Sie im DialogfeldEigenschaften unter **Dienststatus: gestartet**auf **Anhalten**.</span><span class="sxs-lookup"><span data-stu-id="d6383-128">In the Properties dialog box, under **Service status: Started**, click **Pause**.</span></span>

5.  <span data-ttu-id="d6383-129">Optional, aber empfohlen, klicken Sie neben **Starttyp**auf **manuell**.</span><span class="sxs-lookup"><span data-stu-id="d6383-129">Optionally, but recommended, next to **Startup type**, click **Manual**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="d6383-130">Wenn Sie einen Server so einrichten, dass neue Verbindungen verhindert werden, und den Server dann neu starten, wird der Server standardmäßig unmittelbar nach dem Start neue Verbindungen akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="d6383-130">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts.</span></span> <span data-ttu-id="d6383-131">Um dies zu verhindern, müssen Sie den Server so einrichten, dass er vor dem Neustart des Servers nur manuell angehalten und fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="d6383-131">To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>
