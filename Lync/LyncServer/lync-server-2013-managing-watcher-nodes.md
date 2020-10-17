---
title: 'Lync Server 2013: Verwalten von Watcher-Knoten'
description: 'Lync Server 2013: Verwalten von Watcher-Knoten.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing watcher nodes
ms:assetid: 66deaf49-a71f-4a6e-ada0-ea8b688ee921
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688078(v=OCS.15)
ms:contentKeyID: 49733674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1795b09bbca73d8157cf796ceeaaeafb9cc2ebc5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556611"
---
# <a name="managing-watcher-nodes-in-lync-server-2013"></a><span data-ttu-id="2c70c-103">Verwalten von Watcher-Knoten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2c70c-103">Managing watcher nodes in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2c70c-104">_**Letztes Änderungsstand des Themas:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="2c70c-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="2c70c-105">Mit dem **Set-CsWatcherNodeConfiguration**-Cmdlet können Administratoren nicht nur die auf einem Watcher-Knoten ausgeführten synthetischen Transaktionen ändern, sondern auch noch zwei andere wichtige Aufgaben durchführen: das Aktivieren und Deaktivieren des Watcher-Knotens sowie das Konfigurieren des Watcher-Knotens zur Verwendung interner oder externer URLs beim Durchführen seiner Tests.</span><span class="sxs-lookup"><span data-stu-id="2c70c-105">In addition to modifying the synthetic transactions that are executed on a watcher node, administrators can also use the **Set-CsWatcherNodeConfiguration** cmdlet to carry out two other important tasks: enabling and disabling the watcher node, and configuring the watcher node to use either internal URLs or external URLs when running its tests.</span></span>

<span data-ttu-id="2c70c-106">In der Standardeinstellung führen Watcher-Knoten in regelmäßigen Abständen alle für sie aktivierten synthetischen Transaktionen aus.</span><span class="sxs-lookup"><span data-stu-id="2c70c-106">By default, watcher nodes are designed to periodically run all their enabled synthetic transactions.</span></span> <span data-ttu-id="2c70c-107">Manchmal müssen solche Transaktionen jedoch angehalten werden.</span><span class="sxs-lookup"><span data-stu-id="2c70c-107">Sometimes, however, you may need to suspend those transactions.</span></span> <span data-ttu-id="2c70c-108">Wenn der Watcher-Knoten zum Beispiel vorübergehend vom Netzwerk getrennt ist, liegt kein Grund vor, dass die synthetischen Transaktionen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2c70c-108">For example, if the watcher node is temporarily disconnected from the network, then there is no reason to run the synthetic transactions.</span></span> <span data-ttu-id="2c70c-109">Ohne Verbindung mit dem Netzwerk würden solche Transaktionen nur fehlerhaft sein.</span><span class="sxs-lookup"><span data-stu-id="2c70c-109">Without network connectivity, those transactions are guaranteed to fail.</span></span> <span data-ttu-id="2c70c-110">Wenn Sie einen Watcher-Knoten vorübergehend deaktivieren möchten, führen Sie einen Befehl wie den folgenden aus dem lync Server-Verwaltungsshell aus:</span><span class="sxs-lookup"><span data-stu-id="2c70c-110">If you want to temporarily disable a watcher node, run a command similar to this from the Lync Server Management Shell:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False

<span data-ttu-id="2c70c-p102">Dieser Befehl deaktiviert die Ausführung synthetischer Transaktionen auf dem Watcher-Knoten "atl-watcher- 001.litwareinc.com". Wenn die synthetischen Transaktionen wieder aufgenommen werden sollen, setzen Sie die Eigenschaft "Enabled" wieder zurück auf "True" ($True):</span><span class="sxs-lookup"><span data-stu-id="2c70c-p102">This command will disable the execution of synthetic transactions on the watcher node atl-watcher- 001.litwareinc.com. To resume execution of the synthetic transactions, set the Enabled property back to True ($True):</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True

<div>


> [!NOTE]  
> <span data-ttu-id="2c70c-113">Mithilfe der Eigenschaft "Enabled" können Watcher-Knoten ein- und ausgeschaltet werden.</span><span class="sxs-lookup"><span data-stu-id="2c70c-113">The Enabled property can be used to turn watcher nodes on or off.</span></span> <span data-ttu-id="2c70c-114">Wenn Sie einen Watcher-Knoten dauerhaft löschen möchten, verwenden Sie das <STRONG>Remove-CsWatcherNodeConfiguration</STRONG>-Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="2c70c-114">If you want to permanently delete a watcher node, use the <STRONG>Remove-CsWatcherNodeConfiguration</STRONG> cmdlet:</span></span><BR><span data-ttu-id="2c70c-115">Remove-CsWatcherNodeConfiguration –Identity "atl-watcher-001.litwareinc.com"</span><span class="sxs-lookup"><span data-stu-id="2c70c-115">Remove-CsWatcherNodeConfiguration –Identity "atl-watcher-001.litwareinc.com"</span></span><BR><span data-ttu-id="2c70c-116">Dieser Befehl entfernt auf dem angegebenen Computer alle Konfigurationseinstellungen für Watcher-Knoten, sodass auf diesem Computer keine synthetischen Transaktionen mehr automatisch ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2c70c-116">That command removes all the watcher node configuration settings from the specified computer, which prevents the computer from automatically running synthetic transactions.</span></span> <span data-ttu-id="2c70c-117">Mit dem Befehl werden die System Center-Agent-Dateien oder die lync Server 2013 Systemdateien jedoch nicht deinstalliert.</span><span class="sxs-lookup"><span data-stu-id="2c70c-117">However, the command does not uninstall the System Center agent files or the Lync Server 2013 system files.</span></span>



</div>

<span data-ttu-id="2c70c-p105">In der Standardeinstellung verwenden Watcher-Knoten bei der Durchführung ihrer Tests externe URLs des Unternehmens. Es ist jedoch auch möglich, die Verwendung interner URLs zu konfigurieren. Dies ermöglicht es Administratoren, den URL-Zugriff für innerhalb des Umkreisnetzwerks befindliche Benutzer zu überprüfen. Wenn Sie einen Watcher-Knoten so konfigurieren möchten, dass er interne anstatt externe URLs verwendet, legen Sie die Eigenschaft "UseInternalWebUrls" auf "True" ($True) fest:</span><span class="sxs-lookup"><span data-stu-id="2c70c-p105">By default, watcher nodes use an organization's external URLs when conducting their tests. However, watcher nodes can also be configured to use the organization's internal URLs. This enables administrators to verify URL access for users located inside the perimeter network. To configure a watcher node to use internal URLs instead of external URLs, set the UseInternalWebUrls property to True ($True):</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True

<span data-ttu-id="2c70c-122">Wenn Sie diese Eigenschaft auf ihren Standardwert ($False) zurücksetzen, wird der Watcher-Knoten wieder externe URLs verwenden:</span><span class="sxs-lookup"><span data-stu-id="2c70c-122">If you reset this property to the default value of False ($False), the watcher will then use the external URLs:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False

</div>

<span> </span>

</div>

</div>

</div>

