---
title: 'Lync Server 2013: Anpassen der Wartemusik für das Parken von Anrufen'
description: 'Lync Server 2013: Anpassen der Wartemusik für das Parken von Anrufen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Customize Call Park music on hold
ms:assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688031(v=OCS.15)
ms:contentKeyID: 49733621
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19219e4a77d4be4a18a43255e142339a4af6f463
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544001"
---
# <a name="customize-call-park-music-on-hold-in-lync-server-2013"></a><span data-ttu-id="d1265-103">Anpassen der Wartemusik für das Parken von Anrufen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1265-103">Customize Call Park music on hold in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d1265-104">_**Letztes Änderungsstand des Themas:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="d1265-104">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="d1265-105">Anstelle der standardmäßigen Musikdatei, die mit lync Server 2013 ausgeliefert wird, können Sie eine eigene Musikdatei angeben, die für die Wartemusik verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d1265-105">You can specify your own music file to use for music on hold, instead of the default music file that ships with Lync Server 2013.</span></span> <span data-ttu-id="d1265-106">Verwenden Sie zum Anpassen der Wartemusik das Cmdlet **Set-CsCallParkServiceMusicOnHoldFile**.</span><span class="sxs-lookup"><span data-stu-id="d1265-106">To customize music on hold, use the **Set-CsCallParkServiceMusicOnHoldFile** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d1265-107">Wenn Sie die Musik in der Warteschleife anpassen und die gleiche Musik für mehrere Websites wünschen, müssen Sie die Musikdatei für jeden Standort konfigurieren, auf dem die Anwendung zum Parken von Anrufen ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d1265-107">If you customize music on hold and want the same music for multiple sites, you must configure the music file for each site that runs the Call Park application.</span></span>



</div>

<div>

## <a name="to-customize-the-music-file"></a><span data-ttu-id="d1265-108">So passen Sie die Musikdatei an</span><span class="sxs-lookup"><span data-stu-id="d1265-108">To customize the music file</span></span>

1.  <span data-ttu-id="d1265-109">Melden Sie sich an dem Computer an, auf dem lync Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe oder mit den erforderlichen Benutzerrechten installiert ist, wie unter [Delegieren von Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d1265-109">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="d1265-110">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="d1265-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="d1265-111">Ausführen</span><span class="sxs-lookup"><span data-stu-id="d1265-111">Run:</span></span>
    
        Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte[]>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="d1265-112">Verwenden Sie das Cmdlet <STRONG>Get-CsService</STRONG>, um den Dienst zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="d1265-112">Use the <STRONG>Get-CsService</STRONG> cmdlet to identify the service.</span></span> <span data-ttu-id="d1265-113">Ausführliche Informationen finden Sie unter <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsService">Get-CsService</A>.</span><span class="sxs-lookup"><span data-stu-id="d1265-113">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsService">Get-CsService</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="d1265-114">Im folgenden Beispiel wird gezeigt, wie die Inhalte der Datei "soothingmusic.wma" als Bytearray abgerufen und einer Variablen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="d1265-114">The following example shows how to obtain the contents of a file, soothingmusic.wma, as a byte array and assign it to a variable.</span></span> <span data-ttu-id="d1265-115">Anschließend wird die Audiodatei als Wartemusikdatei für die Funktion zum Parken von Anrufen zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="d1265-115">Then the audio file is assigned as the music-on-hold file for Call Park.</span></span> <span data-ttu-id="d1265-116">Ausführliche Informationen finden Sie unter [Sets-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkServiceMusicOnHoldFile).</span><span class="sxs-lookup"><span data-stu-id="d1265-116">For details, see [Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkServiceMusicOnHoldFile).</span></span>
    
        $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
        Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d1265-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d1265-117">See Also</span></span>


[<span data-ttu-id="d1265-118">Gruppe-CsCallParkServiceMusicOnHoldFile</span><span class="sxs-lookup"><span data-stu-id="d1265-118">Set-CsCallParkServiceMusicOnHoldFile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkServiceMusicOnHoldFile)  
[<span data-ttu-id="d1265-119">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="d1265-119">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

