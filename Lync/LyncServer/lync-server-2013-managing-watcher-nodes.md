---
title: 'Lync Server 2013: Verwalten von Watcher-Knoten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing watcher nodes
ms:assetid: 66deaf49-a71f-4a6e-ada0-ea8b688ee921
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688078(v=OCS.15)
ms:contentKeyID: 49733674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7edddd1a1bb67dc4bf3df5b7809aa76b2397e56
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827641"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-watcher-nodes-in-lync-server-2013"></a>Verwalten von Watcher-Knoten in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-20_

Zusätzlich zum Ändern der synthetischen Transaktionen, die auf einem Watcher-Knoten ausgeführt werden, können Administratoren auch das Cmdlet " **Satz-CsWatcherNodeConfiguration** " verwenden, um zwei weitere wichtige Aufgaben auszuführen: Aktivieren und Deaktivieren des Watcher-Knotens und Konfigurieren des Watcher-Knotens zum Verwenden interner URLs oder externer URLs, wenn die Tests ausgeführt werden.

In der Standardeinstellung führen Watcher-Knoten in regelmäßigen Abständen alle für sie aktivierten synthetischen Transaktionen aus. Manchmal müssen Sie diese Transaktionen aber möglicherweise anhalten. Wenn der Watcher-Knoten zum Beispiel vorübergehend vom Netzwerk getrennt ist, liegt kein Grund vor, dass die synthetischen Transaktionen ausgeführt werden. Ohne Netzwerkkonnektivität sind diese Transaktionen garantiert fehlerhaft. Wenn Sie einen Watcher-Knoten vorübergehend deaktivieren möchten, führen Sie in der lync Server-Verwaltungsshell einen ähnlichen Befehl wie den folgenden aus:

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False

Mit diesem Befehl wird die Ausführung von synthetischen Transaktionen auf dem Watcher-Knoten ATL-Watcher-001.litwareinc.com deaktiviert. Wenn die synthetischen Transaktionen wieder aufgenommen werden sollen, setzen Sie die Eigenschaft „Enabled“ wieder zurück auf „True“ ($True):

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True

<div>


> [!NOTE]  
> Mithilfe der Eigenschaft „Enabled“ können Watcher-Knoten ein- und ausgeschaltet werden. Wenn Sie einen Watcher-Knoten dauerhaft löschen möchten, verwenden Sie das <STRONG>Remove-CsWatcherNodeConfiguration</STRONG>-Cmdlet:<BR>Remove-CsWatcherNodeConfiguration – Identity "ATL-Watcher-001.litwareinc.com"<BR>Dieser Befehl entfernt alle Überwachungsknoten-Konfigurationseinstellungen vom angegebenen Computer, wodurch verhindert wird, dass der Computer synthetische Transaktionen automatisch ausführt. Der Befehl wird jedoch nicht die System Center-Agentendateien oder die lync Server 2013-Systemdateien deinstalliert.



</div>

Standardmäßig verwenden Watcher-Knoten die externen URLs einer Organisation, wenn Sie Ihre Tests durchführen. Watcher-Knoten können jedoch auch so konfiguriert werden, dass Sie die internen URLs der Organisation verwenden. Dies ermöglicht es Administratoren, den URL-Zugriff für innerhalb des Umkreisnetzwerks befindliche Benutzer zu überprüfen. Wenn Sie einen Watcher-Knoten für die Verwendung interner URLs anstelle externer URLs konfigurieren möchten, legen Sie die UseInternalWebUrls-Eigenschaft auf true ($true) fest:

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True

Wenn Sie diese Eigenschaft auf den Standardwert false ($false) zurücksetzen, verwendet der Watcher die externen URLs:

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False

</div>

<span> </span>

</div>

</div>

</div>

