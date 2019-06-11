---
title: 'Lync Server 2013: Adressbuchserver-Cmdlets'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Address Book Server cmdlets
ms:assetid: 33da45da-3c57-4d04-9679-f0e5a0cfd37e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415643(v=OCS.15)
ms:contentKeyID: 48183793
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 634e6ae86a68cece6472d04ba1870159dc9b866f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839920"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="address-book-server-cmdlets-in-lync-server-2013"></a><span data-ttu-id="cffe9-102">Cmdlets des Adressbuchservers in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cffe9-102">Address Book Server cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cffe9-103">_**Letztes Änderungsdatum des Themas:** 2012-06-26_</span><span class="sxs-lookup"><span data-stu-id="cffe9-103">_**Topic Last Modified:** 2012-06-26_</span></span>

<span data-ttu-id="cffe9-104">Adressbuchserver sind Vermittler zwischen Active Directory-Domänendiensten und Microsoft lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cffe9-104">Address Book servers are intermediaries between Active Directory Domain Services and Microsoft Lync Server 2013.</span></span> <span data-ttu-id="cffe9-105">Der Adressbuchserver stellt sicher, dass die in lync Server 2013 gespeicherten Benutzerinformationen mit den in Active Directory gespeicherten Benutzerinformationen synchron sind.</span><span class="sxs-lookup"><span data-stu-id="cffe9-105">The Address Book server ensures that the user information stored in Lync Server 2013 is in synch with the user information stored in Active Directory.</span></span> <span data-ttu-id="cffe9-106">Dies erfolgt durch regelmäßiges Synchronisieren von Adressbuchdateien mit Informationen, die in der Benutzerdatenbank gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="cffe9-106">This is done by periodically synching Address Book files with information stored in the User database.</span></span> <span data-ttu-id="cffe9-107">Lync Server enthält wiederum eine Reihe von Cmdlets für die Verwaltung von Adressbuch Servern.</span><span class="sxs-lookup"><span data-stu-id="cffe9-107">In turn, Lync Server includes a number of cmdlets for managing Address Book servers.</span></span>

<div>

## <a name="address-book-server-cmdlets"></a><span data-ttu-id="cffe9-108">Adressbuch Server-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="cffe9-108">Address Book Server Cmdlets</span></span>

<span data-ttu-id="cffe9-109">In der lync Server-Systemsteuerung können die Adressbuchserver Einstellungen nicht konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="cffe9-109">You cannot configure the Address Book Server settings in Lync Server Control Panel.</span></span> <span data-ttu-id="cffe9-110">Windows PowerShell ist das wichtigste Tool für die Verwaltung dieser Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="cffe9-110">Windows PowerShell is the primary tool for managing these settings.</span></span> <span data-ttu-id="cffe9-111">Die folgende Liste enthält Cmdlets, die sich direkt auf die Verwaltung des Adressbuchservers beziehen:</span><span class="sxs-lookup"><span data-stu-id="cffe9-111">The following is a list of cmdlets that relate directly to managing the Address Book Server:</span></span>

<span data-ttu-id="cffe9-112">**Adressbuchserver**</span><span class="sxs-lookup"><span data-stu-id="cffe9-112">**Address Book Server**</span></span>

  - <span></span>  
    <span data-ttu-id="cffe9-113">[Get-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398132(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cffe9-113">[Get-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398132(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="cffe9-114">[Neu – CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398395(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cffe9-114">[New-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398395(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="cffe9-115">[Remove-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398934(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cffe9-115">[Remove-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398934(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="cffe9-116">[Satz-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg412784(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cffe9-116">[Set-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg412784(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="cffe9-117">[Update-CsAddressBook](https://technet.microsoft.com/en-us/library/Gg398194(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cffe9-117">[Update-CsAddressBook](https://technet.microsoft.com/en-us/library/Gg398194(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="cffe9-118">[Debug-CsAddressBookReplication](https://technet.microsoft.com/en-us/library/JJ205232(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cffe9-118">[Debug-CsAddressBookReplication](https://technet.microsoft.com/en-us/library/JJ205232(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="cffe9-119">[Test-CsAddressBookService](https://technet.microsoft.com/en-us/library/Gg398661(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cffe9-119">[Test-CsAddressBookService](https://technet.microsoft.com/en-us/library/Gg398661(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="cffe9-120">[Test-CsAddressBookWebQuery](https://technet.microsoft.com/en-us/library/Gg398773(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cffe9-120">[Test-CsAddressBookWebQuery](https://technet.microsoft.com/en-us/library/Gg398773(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cffe9-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cffe9-121">See Also</span></span>


[<span data-ttu-id="cffe9-122">Lync Server PowerShell-Blog</span><span class="sxs-lookup"><span data-stu-id="cffe9-122">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

