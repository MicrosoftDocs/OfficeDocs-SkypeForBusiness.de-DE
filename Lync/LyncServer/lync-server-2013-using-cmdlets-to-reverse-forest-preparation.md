---
title: 'Lync Server 2013: Verwenden von Cmdlets zum Rückgängigmachen der Gesamtstrukturvorbereitung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using cmdlets to reverse forest preparation
ms:assetid: f48c7eb3-ccb0-48e6-ac79-ab7c7062b9d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413024(v=OCS.15)
ms:contentKeyID: 48185822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d39992255bfe6f93d9f41380b4f6b5fb9af1f5b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212851"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-cmdlets-to-reverse-forest-preparation-for-lync-server-2013"></a><span data-ttu-id="1d396-102">Verwenden von Cmdlets zum Rückgängigmachen der Gesamtstrukturvorbereitung für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d396-102">Using cmdlets to reverse forest preparation for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1d396-103">_**Letztes Änderungsstand des Themas:** 2013-06-19_</span><span class="sxs-lookup"><span data-stu-id="1d396-103">_**Topic Last Modified:** 2013-06-19_</span></span>

<span data-ttu-id="1d396-104">Verwenden Sie das Cmdlet **Disable-CsAdForest** , um den Gesamtstrukturvorbereitungsschritt umzukehren.</span><span class="sxs-lookup"><span data-stu-id="1d396-104">Use the **Disable-CsAdForest** cmdlet to reverse the forest preparation step.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="1d396-105">Wenn Sie das Cmdlet <STRONG>Disable-CsAdForest</STRONG> in einer Umgebung ausführen, in der Sie auch eine frühere Version von lync Server bereitgestellt haben, werden die globalen Einstellungen für die vorherige Version ebenfalls gelöscht.</span><span class="sxs-lookup"><span data-stu-id="1d396-105">If you run the <STRONG>Disable-CsAdForest</STRONG> cmdlet in an environment where you also have a previous version of Lync Server deployed, the global settings for the previous version will also be deleted.</span></span>



</div>

<div>

## <a name="to-use-cmdlets-to-reverse-forest-preparation"></a><span data-ttu-id="1d396-106">So verwenden Sie Cmdlets zum Rückgängigmachen der Gesamtstrukturvorbereitung</span><span class="sxs-lookup"><span data-stu-id="1d396-106">To use cmdlets to reverse forest preparation</span></span>

1.  <span data-ttu-id="1d396-107">Melden Sie sich bei einem Domänencomputer als Mitglied der Gruppe "Domänen-Admins" in der Stammdomäne der Gesamtstruktur an.</span><span class="sxs-lookup"><span data-stu-id="1d396-107">Log on to a computer that is joined to a domain as a member of the Domain Admins group in the forest root domain.</span></span>

2.  <span data-ttu-id="1d396-108">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="1d396-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="1d396-109">Ausführen</span><span class="sxs-lookup"><span data-stu-id="1d396-109">Run:</span></span>
    
        Disable-CsAdForest [-Force] [-GroupDomain <FQDN of the domain in which universal groups were created>]
    
    <span data-ttu-id="1d396-110">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1d396-110">For example:</span></span>
    
        Disable-CsAdForest -Force -GroupDomain contoso.net
    
    <span data-ttu-id="1d396-111">Der Parameter Force gibt an, ob die Ausführung der Aufgabe erzwungen werden soll.</span><span class="sxs-lookup"><span data-stu-id="1d396-111">The Force parameter specifies whether to force running the task.</span></span> <span data-ttu-id="1d396-112">Wenn dieser Parameter nicht vorhanden ist, wird der Befehl nicht ausgeführt, wenn auch eine Domäne in der Gesamtstruktur noch für lync Server 2013 vorbereitet ist.</span><span class="sxs-lookup"><span data-stu-id="1d396-112">If this parameter is not present, the command will not run if even one domain in the forest is still prepared for Lync Server 2013.</span></span> <span data-ttu-id="1d396-113">Wenn der Parameter Force angegeben wird, wird die Aktion unabhängig vom Status anderer Domänen in der Gesamtstruktur fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="1d396-113">If the Force parameter is specified, the action will continue regardless of the state of other domains in the forest.</span></span>
    
    <span data-ttu-id="1d396-114">Wenn Sie den Parameter "GroupDomain" nicht angeben, wird standardmäßig die lokale Domäne verwendet.</span><span class="sxs-lookup"><span data-stu-id="1d396-114">If you do not specify the GroupDomain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1d396-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1d396-115">See Also</span></span>


[<span data-ttu-id="1d396-116">Laufende Gesamtstrukturvorbereitung für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d396-116">Running forest preparation for Lync Server 2013</span></span>](lync-server-2013-running-forest-preparation.md)  


[<span data-ttu-id="1d396-117">Vorbereiten der Gesamtstruktur auf lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d396-117">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

