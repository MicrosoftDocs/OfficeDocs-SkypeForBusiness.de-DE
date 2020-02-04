---
title: 'Lync Server 2013: Cmdlets für die Anruf Park Anwendung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Park application cmdlets
ms:assetid: 30cc001f-b29e-4d44-bad7-65e1133e67b1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415639(v=OCS.15)
ms:contentKeyID: 48183764
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ebd91f563348575e7498cd3441ffdadb35fec15
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742985"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-park-application-cmdlets-in-lync-server-2013"></a><span data-ttu-id="4bbe2-102">Cmdlets für die Parken-Anwendung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4bbe2-102">Call Park application cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4bbe2-103">_**Letztes Änderungsdatum des Themas:** 2012-03-21_</span><span class="sxs-lookup"><span data-stu-id="4bbe2-103">_**Topic Last Modified:** 2012-03-21_</span></span>

<span data-ttu-id="4bbe2-104">Die Anwendung "Parken" ermöglicht es einem Benutzer, einen Anruf in Wartestellung zu setzen und diesen Anruf dann von einem anderen Telefon aus abzurufen.</span><span class="sxs-lookup"><span data-stu-id="4bbe2-104">Call Park application allows a user to place a call on hold, then retrieve that call from a different phone.</span></span> <span data-ttu-id="4bbe2-105">Verwenden Sie diese Cmdlets, um die Einstellungen für die Orbits des Anruf Parks und die Anwendung Parken zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="4bbe2-105">Use these cmdlets to configure settings for call park orbits and the Call Park application.</span></span>

<div>

## <a name="call-park-application-cmdlets"></a><span data-ttu-id="4bbe2-106">Cmdlets für die Anruf Park Anwendung</span><span class="sxs-lookup"><span data-stu-id="4bbe2-106">Call Park Application Cmdlets</span></span>

<span data-ttu-id="4bbe2-107">Die folgenden Cmdlets können zum Verwalten der Anwendung für den Parken von Anrufen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4bbe2-107">The following cmdlets can be used to manage Call Park application.</span></span>

<span data-ttu-id="4bbe2-108">**Anruf parken-Anwendung**</span><span class="sxs-lookup"><span data-stu-id="4bbe2-108">**Call Park Application**</span></span>

  - <span></span>  
    <span data-ttu-id="4bbe2-109">[Get-CsCallParkOrbit](https://technet.microsoft.com/en-us/library/Gg398554(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4bbe2-109">[Get-CsCallParkOrbit](https://technet.microsoft.com/en-us/library/Gg398554(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4bbe2-110">[Neu – CsCallParkOrbit](https://technet.microsoft.com/en-us/library/Gg398936(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4bbe2-110">[New-CsCallParkOrbit](https://technet.microsoft.com/en-us/library/Gg398936(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4bbe2-111">[Remove-CsCallParkOrbit](https://technet.microsoft.com/en-us/library/Gg412901(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4bbe2-111">[Remove-CsCallParkOrbit](https://technet.microsoft.com/en-us/library/Gg412901(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4bbe2-112">[Satz-CsCallParkOrbit](https://technet.microsoft.com/en-us/library/Gg398796(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4bbe2-112">[Set-CsCallParkOrbit](https://technet.microsoft.com/en-us/library/Gg398796(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="4bbe2-113">[Satz-CsCallParkServiceMusicOnHoldFile](https://technet.microsoft.com/en-us/library/Gg412836(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4bbe2-113">[Set-CsCallParkServiceMusicOnHoldFile](https://technet.microsoft.com/en-us/library/Gg412836(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="4bbe2-114">[Get-CsCpsConfiguration](https://technet.microsoft.com/en-us/library/Gg398948(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4bbe2-114">[Get-CsCpsConfiguration](https://technet.microsoft.com/en-us/library/Gg398948(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4bbe2-115">[Neu – CsCpsConfiguration](https://technet.microsoft.com/en-us/library/Gg412919(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4bbe2-115">[New-CsCpsConfiguration](https://technet.microsoft.com/en-us/library/Gg412919(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4bbe2-116">[Remove-CsCpsConfiguration](https://technet.microsoft.com/en-us/library/Gg398358(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4bbe2-116">[Remove-CsCpsConfiguration](https://technet.microsoft.com/en-us/library/Gg398358(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4bbe2-117">[Satz-CsCpsConfiguration](https://technet.microsoft.com/en-us/library/Gg412721(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4bbe2-117">[Set-CsCpsConfiguration](https://technet.microsoft.com/en-us/library/Gg412721(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4bbe2-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4bbe2-118">See Also</span></span>


[<span data-ttu-id="4bbe2-119">Lync Server PowerShell-Blog</span><span class="sxs-lookup"><span data-stu-id="4bbe2-119">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

