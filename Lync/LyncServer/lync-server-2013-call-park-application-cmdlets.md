---
title: 'Lync Server 2013: Anwendung zum Parken von Anrufen-Cmdlets'
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
ms.openlocfilehash: 1fb129114962a6f530ad1d52f6b0314d439d9c5d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044457"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-park-application-cmdlets-in-lync-server-2013"></a><span data-ttu-id="d6d26-102">Anwendung zum Parken von Anrufen-Cmdlets in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6d26-102">Call Park application cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d6d26-103">_**Letztes Änderungsstand des Themas:** 2012-03-21_</span><span class="sxs-lookup"><span data-stu-id="d6d26-103">_**Topic Last Modified:** 2012-03-21_</span></span>

<span data-ttu-id="d6d26-104">Anwendung zum Parken von Anrufen ermöglicht es einem Benutzer, einen Anruf in der Warteschleife zu tätigen und diesen Anruf von einem anderen Telefon aus abzurufen.</span><span class="sxs-lookup"><span data-stu-id="d6d26-104">Call Park application allows a user to place a call on hold, then retrieve that call from a different phone.</span></span> <span data-ttu-id="d6d26-105">Verwenden Sie diese Cmdlets, um Einstellungen für Orbits für das Parken von Anrufen und die Anwendung zum Parken von Anrufen zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="d6d26-105">Use these cmdlets to configure settings for call park orbits and the Call Park application.</span></span>

<div>

## <a name="call-park-application-cmdlets"></a><span data-ttu-id="d6d26-106">Cmdlets für die Anwendung zum Parken von Anrufen</span><span class="sxs-lookup"><span data-stu-id="d6d26-106">Call Park Application Cmdlets</span></span>

<span data-ttu-id="d6d26-107">Die folgenden Cmdlets können zum Verwalten von Anwendung zum Parken von Anrufen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d6d26-107">The following cmdlets can be used to manage Call Park application.</span></span>

<span data-ttu-id="d6d26-108">**Anwendung zum Parken von Anrufen**</span><span class="sxs-lookup"><span data-stu-id="d6d26-108">**Call Park Application**</span></span>

  - <span></span>  
    <span data-ttu-id="d6d26-109">[Get-CsCallParkOrbit](https://technet.microsoft.com/library/Gg398554(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d6d26-109">[Get-CsCallParkOrbit](https://technet.microsoft.com/library/Gg398554(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d6d26-110">[New-CsCallParkOrbit](https://technet.microsoft.com/library/Gg398936(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d6d26-110">[New-CsCallParkOrbit](https://technet.microsoft.com/library/Gg398936(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d6d26-111">[Remove-CsCallParkOrbit](https://technet.microsoft.com/library/Gg412901(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d6d26-111">[Remove-CsCallParkOrbit](https://technet.microsoft.com/library/Gg412901(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d6d26-112">[Gruppe-CsCallParkOrbit](https://technet.microsoft.com/library/Gg398796(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d6d26-112">[Set-CsCallParkOrbit](https://technet.microsoft.com/library/Gg398796(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="d6d26-113">[Gruppe-CsCallParkServiceMusicOnHoldFile](https://technet.microsoft.com/library/Gg412836(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d6d26-113">[Set-CsCallParkServiceMusicOnHoldFile](https://technet.microsoft.com/library/Gg412836(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="d6d26-114">[Get-CsCpsConfiguration](https://technet.microsoft.com/library/Gg398948(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d6d26-114">[Get-CsCpsConfiguration](https://technet.microsoft.com/library/Gg398948(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d6d26-115">[New-CsCpsConfiguration](https://technet.microsoft.com/library/Gg412919(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d6d26-115">[New-CsCpsConfiguration](https://technet.microsoft.com/library/Gg412919(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d6d26-116">[Remove-CsCpsConfiguration](https://technet.microsoft.com/library/Gg398358(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d6d26-116">[Remove-CsCpsConfiguration](https://technet.microsoft.com/library/Gg398358(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d6d26-117">[Gruppe-CsCpsConfiguration](https://technet.microsoft.com/library/Gg412721(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d6d26-117">[Set-CsCpsConfiguration](https://technet.microsoft.com/library/Gg412721(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d6d26-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d6d26-118">See Also</span></span>


[<span data-ttu-id="d6d26-119">Lync Server PowerShell-Blog</span><span class="sxs-lookup"><span data-stu-id="d6d26-119">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

