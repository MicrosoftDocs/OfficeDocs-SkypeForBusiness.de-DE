---
title: 'Lync Server 2013: Verwenden von Cmdlets zum Rückgängigmachen der Gesamtstrukturvorbereitung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using cmdlets to reverse forest preparation
ms:assetid: f48c7eb3-ccb0-48e6-ac79-ab7c7062b9d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413024(v=OCS.15)
ms:contentKeyID: 48185822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd186fc3b2c6171b49cf3fd4c9e78b8e66b4cc71
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847347"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-cmdlets-to-reverse-forest-preparation-for-lync-server-2013"></a><span data-ttu-id="682ae-102">Verwenden von Cmdlets zum Rückgängigmachen der Gesamtstrukturvorbereitung für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="682ae-102">Using cmdlets to reverse forest preparation for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="682ae-103">_**Letztes Änderungsdatum des Themas:** 2013-06-19_</span><span class="sxs-lookup"><span data-stu-id="682ae-103">_**Topic Last Modified:** 2013-06-19_</span></span>

<span data-ttu-id="682ae-104">Verwenden Sie das Cmdlet **Disable-CsAdForest** , um den Vorbereitungsschritt für die Gesamtstruktur umzukehren.</span><span class="sxs-lookup"><span data-stu-id="682ae-104">Use the **Disable-CsAdForest** cmdlet to reverse the forest preparation step.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="682ae-105">Wenn Sie das Cmdlet <STRONG>Disable-CsAdForest</STRONG> in einer Umgebung ausführen, in der auch eine frühere Version von lync Server bereitgestellt ist, werden die globalen Einstellungen für die vorherige Version ebenfalls gelöscht.</span><span class="sxs-lookup"><span data-stu-id="682ae-105">If you run the <STRONG>Disable-CsAdForest</STRONG> cmdlet in an environment where you also have a previous version of Lync Server deployed, the global settings for the previous version will also be deleted.</span></span>



</div>

<div>

## <a name="to-use-cmdlets-to-reverse-forest-preparation"></a><span data-ttu-id="682ae-106">So verwenden Sie Cmdlets zum Umkehren der Gesamtstrukturvorbereitung</span><span class="sxs-lookup"><span data-stu-id="682ae-106">To use cmdlets to reverse forest preparation</span></span>

1.  <span data-ttu-id="682ae-107">Melden Sie sich bei einem Computer an, der einer Domäne als Mitglied der Gruppe der Domänenadministratoren in der Stammdomäne der Gesamtstruktur beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="682ae-107">Log on to a computer that is joined to a domain as a member of the Domain Admins group in the forest root domain.</span></span>

2.  <span data-ttu-id="682ae-108">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="682ae-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="682ae-109">Führen Sie folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="682ae-109">Run:</span></span>
    
        Disable-CsAdForest [-Force] [-GroupDomain <FQDN of the domain in which universal groups were created>]
    
    <span data-ttu-id="682ae-110">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="682ae-110">For example:</span></span>
    
        Disable-CsAdForest -Force -GroupDomain contoso.net
    
    <span data-ttu-id="682ae-111">Der Parameter Force gibt an, ob die Ausführung der Aufgabe erzwungen werden soll.</span><span class="sxs-lookup"><span data-stu-id="682ae-111">The Force parameter specifies whether to force running the task.</span></span> <span data-ttu-id="682ae-112">Wenn dieser Parameter nicht vorhanden ist, wird der Befehl nicht ausgeführt, wenn noch eine Domäne in der Gesamtstruktur für lync Server 2013 vorbereitet ist.</span><span class="sxs-lookup"><span data-stu-id="682ae-112">If this parameter is not present, the command will not run if even one domain in the forest is still prepared for Lync Server 2013.</span></span> <span data-ttu-id="682ae-113">Wenn der Parameter Force angegeben wird, wird die Aktion ungeachtet des Zustands anderer Domänen in der Gesamtstruktur fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="682ae-113">If the Force parameter is specified, the action will continue regardless of the state of other domains in the forest.</span></span>
    
    <span data-ttu-id="682ae-114">Wenn Sie den GroupDomain-Parameter nicht angeben, ist der Standardwert die lokale Domäne.</span><span class="sxs-lookup"><span data-stu-id="682ae-114">If you do not specify the GroupDomain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="682ae-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="682ae-115">See Also</span></span>


[<span data-ttu-id="682ae-116">Ausführen der Gesamtstrukturvorbereitung für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="682ae-116">Running forest preparation for Lync Server 2013</span></span>](lync-server-2013-running-forest-preparation.md)  


[<span data-ttu-id="682ae-117">Vorbereiten der Gesamtstruktur für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="682ae-117">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

