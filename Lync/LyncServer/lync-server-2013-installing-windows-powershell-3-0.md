---
title: 'Lync Server 2013: Installieren von Windows PowerShell 3,0'
description: 'Lync Server 2013: Installieren von Windows PowerShell 3,0.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing Windows PowerShell 3.0
ms:assetid: d87bf21e-0a43-41cb-8fdc-626cedec8538
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205328(v=OCS.15)
ms:contentKeyID: 48185621
ms.date: 06/28/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4605231f4e73f6aada4fb34de895cdeb883d82b1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550651"
---
# <a name="installing-windows-powershell-30-for-lync-server-2013"></a><span data-ttu-id="777b2-103">Installieren von Windows PowerShell 3,0 für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="777b2-103">Installing Windows PowerShell 3.0 for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="777b2-104">_**Letztes Änderungsstand des Themas:** 2014-06-27_</span><span class="sxs-lookup"><span data-stu-id="777b2-104">_**Topic Last Modified:** 2014-06-27_</span></span>

<span data-ttu-id="777b2-105">Um lync Server 2013 erfolgreich bereitzustellen, benötigen Sie Windows PowerShell 3,0 auf jedem Computer, der Teil ihrer lync Server Topologie ist.</span><span class="sxs-lookup"><span data-stu-id="777b2-105">To deploy Lync Server 2013 successfully, you’ll need Windows PowerShell 3.0 on each computer that’s part of your Lync Server topology.</span></span>

<span data-ttu-id="777b2-106">Für Systeme, die Windows Server 2012 oder Windows Server 2012 R2 ausführen, müssen Sie jetzt nichts mehr tun und können zur nächsten Bereitstellungsphase übergehen, da PowerShell 3,0 in diesen Betriebssystemen enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="777b2-106">Now, for systems running Windows Server 2012 or Windows Server 2012 R2, you don’t need to do anything here, and can go ahead to the next stage of deployment, because PowerShell 3.0 is included with those operating systems.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="777b2-107">Für Systeme, die Windows Server 2008 R2 SP1 ausführen, müssen Sie jedoch PowerShell 3,0 als Voraussetzung installieren, bevor Sie lync Server 2013 installieren, oder es funktioniert nicht.</span><span class="sxs-lookup"><span data-stu-id="777b2-107">But for systems running Windows Server 2008 R2 SP1, you’ll need to install PowerShell 3.0 as a prerequisite before you install Lync Server 2013, or things won’t work.</span></span> <span data-ttu-id="777b2-108">Informationen zum Installieren von PowerShell 3,0 finden Sie unter <A href="https://go.microsoft.com/fwlink/p/?linkid=329800">Windows Management Framework 3,0</A>.</span><span class="sxs-lookup"><span data-stu-id="777b2-108">To install PowerShell 3.0, see <A href="https://go.microsoft.com/fwlink/p/?linkid=329800">Windows Management Framework 3.0</A>.</span></span> <span data-ttu-id="777b2-109">Dies ist ein direkter Link zur PowerShell 3,0-Download Seite sowie Informationen zur erfolgreichen Installation.</span><span class="sxs-lookup"><span data-stu-id="777b2-109">This is a direct link to the PowerShell 3.0 download page, along with information relating to installing it successfully.</span></span>



</div>

<span data-ttu-id="777b2-110">Wenn Sie die Installation abgeschlossen haben oder nur überprüfen möchten, bevor Sie mit der lync Server-Bereitstellung fortfahren, ist es ziemlich einfach, sich zu vergewissern, dass sich PowerShell 3,0 auf einem Server befindet:</span><span class="sxs-lookup"><span data-stu-id="777b2-110">Once you’ve done the install, or if you just want to check and be sure before continuing with the Lync Server deployment, confirming that PowerShell 3.0 is on a server is pretty straightforward if you do this:</span></span>

1.  <span data-ttu-id="777b2-111">Wählen Sie auf dem Server, den Sie überprüfen möchten, **Start**aus, klicken Sie auf **Alle Programme**, klicken Sie auf **Zubehör**, klicken Sie auf **Windows PowerShell**, und klicken Sie dann auf **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="777b2-111">On the server you want to check, choose **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, and then click **Windows PowerShell**.</span></span>

2.  <span data-ttu-id="777b2-112">Geben Sie in der Windows PowerShell Konsole den folgenden Befehl an der Eingabeaufforderung ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="777b2-112">In the Windows PowerShell console, type the following command at the command prompt, and then press ENTER:</span></span>
    
        Get-Host | Select-Object Version

3.  <span data-ttu-id="777b2-113">Wenn Windows PowerShell 3,0 installiert ist, sehen Sie die Ausgabe wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="777b2-113">If Windows PowerShell 3.0 is installed you’ll see output that looks like this:</span></span>
    
        Version
        -------
        3.0

</div>

<span> </span>

</div>

</div>

</div>

