---
title: 'Lync Server 2013: Verwalten von Watcher-Knoten'
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
ms.openlocfilehash: f01d1375890d632052ee9b6110cf64111a6bdd20
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217721"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-watcher-nodes-in-lync-server-2013"></a><span data-ttu-id="bfc8b-102">Verwalten von Watcher-Knoten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bfc8b-102">Managing watcher nodes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bfc8b-103">_**Letztes Änderungsstand des Themas:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="bfc8b-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="bfc8b-104">Mit dem **Set-CsWatcherNodeConfiguration**-Cmdlet können Administratoren nicht nur die auf einem Watcher-Knoten ausgeführten synthetischen Transaktionen ändern, sondern auch noch zwei andere wichtige Aufgaben durchführen: das Aktivieren und Deaktivieren des Watcher-Knotens sowie das Konfigurieren des Watcher-Knotens zur Verwendung interner oder externer URLs beim Durchführen seiner Tests.</span><span class="sxs-lookup"><span data-stu-id="bfc8b-104">In addition to modifying the synthetic transactions that are executed on a watcher node, administrators can also use the **Set-CsWatcherNodeConfiguration** cmdlet to carry out two other important tasks: enabling and disabling the watcher node, and configuring the watcher node to use either internal URLs or external URLs when running its tests.</span></span>

<span data-ttu-id="bfc8b-105">In der Standardeinstellung führen Watcher-Knoten in regelmäßigen Abständen alle für sie aktivierten synthetischen Transaktionen aus.</span><span class="sxs-lookup"><span data-stu-id="bfc8b-105">By default, watcher nodes are designed to periodically run all their enabled synthetic transactions.</span></span> <span data-ttu-id="bfc8b-106">Manchmal müssen solche Transaktionen jedoch angehalten werden.</span><span class="sxs-lookup"><span data-stu-id="bfc8b-106">Sometimes, however, you may need to suspend those transactions.</span></span> <span data-ttu-id="bfc8b-107">Wenn der Watcher-Knoten zum Beispiel vorübergehend vom Netzwerk getrennt ist, liegt kein Grund vor, dass die synthetischen Transaktionen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="bfc8b-107">For example, if the watcher node is temporarily disconnected from the network, then there is no reason to run the synthetic transactions.</span></span> <span data-ttu-id="bfc8b-108">Ohne Verbindung mit dem Netzwerk würden solche Transaktionen nur fehlerhaft sein.</span><span class="sxs-lookup"><span data-stu-id="bfc8b-108">Without network connectivity, those transactions are guaranteed to fail.</span></span> <span data-ttu-id="bfc8b-109">Wenn Sie einen Watcher-Knoten vorübergehend deaktivieren möchten, führen Sie einen Befehl wie den folgenden aus dem lync Server-Verwaltungsshell aus:</span><span class="sxs-lookup"><span data-stu-id="bfc8b-109">If you want to temporarily disable a watcher node, run a command similar to this from the Lync Server Management Shell:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False

<span data-ttu-id="bfc8b-p102">Dieser Befehl deaktiviert die Ausführung synthetischer Transaktionen auf dem Watcher-Knoten "atl-watcher- 001.litwareinc.com". Wenn die synthetischen Transaktionen wieder aufgenommen werden sollen, setzen Sie die Eigenschaft "Enabled" wieder zurück auf "True" ($True):</span><span class="sxs-lookup"><span data-stu-id="bfc8b-p102">This command will disable the execution of synthetic transactions on the watcher node atl-watcher- 001.litwareinc.com. To resume execution of the synthetic transactions, set the Enabled property back to True ($True):</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True

<div>


> [!NOTE]  
> <span data-ttu-id="bfc8b-112">Mithilfe der Eigenschaft "Enabled" können Watcher-Knoten ein- und ausgeschaltet werden.</span><span class="sxs-lookup"><span data-stu-id="bfc8b-112">The Enabled property can be used to turn watcher nodes on or off.</span></span> <span data-ttu-id="bfc8b-113">Wenn Sie einen Watcher-Knoten dauerhaft löschen möchten, verwenden Sie das <STRONG>Remove-CsWatcherNodeConfiguration</STRONG>-Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="bfc8b-113">If you want to permanently delete a watcher node, use the <STRONG>Remove-CsWatcherNodeConfiguration</STRONG> cmdlet:</span></span><BR><span data-ttu-id="bfc8b-114">Remove-CsWatcherNodeConfiguration –Identity "atl-watcher-001.litwareinc.com"</span><span class="sxs-lookup"><span data-stu-id="bfc8b-114">Remove-CsWatcherNodeConfiguration –Identity "atl-watcher-001.litwareinc.com"</span></span><BR><span data-ttu-id="bfc8b-115">Dieser Befehl entfernt auf dem angegebenen Computer alle Konfigurationseinstellungen für Watcher-Knoten, sodass auf diesem Computer keine synthetischen Transaktionen mehr automatisch ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="bfc8b-115">That command removes all the watcher node configuration settings from the specified computer, which prevents the computer from automatically running synthetic transactions.</span></span> <span data-ttu-id="bfc8b-116">Mit dem Befehl werden die System Center-Agent-Dateien oder die lync Server 2013 Systemdateien jedoch nicht deinstalliert.</span><span class="sxs-lookup"><span data-stu-id="bfc8b-116">However, the command does not uninstall the System Center agent files or the Lync Server 2013 system files.</span></span>



</div>

<span data-ttu-id="bfc8b-p105">In der Standardeinstellung verwenden Watcher-Knoten bei der Durchführung ihrer Tests externe URLs des Unternehmens. Es ist jedoch auch möglich, die Verwendung interner URLs zu konfigurieren. Dies ermöglicht es Administratoren, den URL-Zugriff für innerhalb des Umkreisnetzwerks befindliche Benutzer zu überprüfen. Wenn Sie einen Watcher-Knoten so konfigurieren möchten, dass er interne anstatt externe URLs verwendet, legen Sie die Eigenschaft "UseInternalWebUrls" auf "True" ($True) fest:</span><span class="sxs-lookup"><span data-stu-id="bfc8b-p105">By default, watcher nodes use an organization's external URLs when conducting their tests. However, watcher nodes can also be configured to use the organization's internal URLs. This enables administrators to verify URL access for users located inside the perimeter network. To configure a watcher node to use internal URLs instead of external URLs, set the UseInternalWebUrls property to True ($True):</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True

<span data-ttu-id="bfc8b-121">Wenn Sie diese Eigenschaft auf ihren Standardwert ($False) zurücksetzen, wird der Watcher-Knoten wieder externe URLs verwenden:</span><span class="sxs-lookup"><span data-stu-id="bfc8b-121">If you reset this property to the default value of False ($False), the watcher will then use the external URLs:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False

</div>

<span> </span>

</div>

</div>

</div>

