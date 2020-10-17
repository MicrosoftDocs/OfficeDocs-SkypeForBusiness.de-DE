---
title: Migrieren von Exchange Unified Messaging-Kontaktobjekten
description: Verschiebt Exchange Unified Messaging-Kontaktobjekte.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Move Exchange Unified Messaging Contact objects
ms:assetid: 35c7e987-41b5-4798-b617-3303f20e52e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688022(v=OCS.15)
ms:contentKeyID: 49733612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e3353427f407523a8778585d27201355714a3085
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549721"
---
# <a name="move-exchange-unified-messaging-contact-objects"></a><span data-ttu-id="951f3-103">Migrieren von Exchange Unified Messaging-Kontaktobjekten</span><span class="sxs-lookup"><span data-stu-id="951f3-103">Move Exchange Unified Messaging Contact objects</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="951f3-104">_**Letztes Änderungsstand des Themas:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="951f3-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="951f3-105">Zum Migrieren von Kontaktobjekten der automatischen Telefonzentrale (AA) und des Teilnehmerzugriffs (SA) zur neuen lync Server 2013-Bereitstellung verschieben Sie zunächst die Objekte aus der vorversions Office Communications Server 2007 R2-Bereitstellung in die neue lync Server 2013-Bereitstellung mithilfe der Cmdlets **Get-CsExUmContact** und **verschieben-CsExUmContact** .</span><span class="sxs-lookup"><span data-stu-id="951f3-105">To migrate Auto Attendant (AA) and Subscriber Access (SA) contact objects to the new Lync Server 2013 deployment, you first move the objects from the legacy Office Communications Server 2007 R2 deployment to the new the Lync Server 2013 deployment using the **Get-CsExUmContact** and **Move-CsExUmContact** cmdlets.</span></span> <span data-ttu-id="951f3-106">Im Exchange Server führen Sie dann das **Skript "ExchUCUtil** -Windows PowerShell Skript aus, um die folgenden Schritte für den neu bereitgestellten lync-Pool auszuführen:</span><span class="sxs-lookup"><span data-stu-id="951f3-106">On the Exchange Server, you then run the **ExchUCUtil** Windows PowerShell script to do the following for the newly deployed Lync pool:</span></span>

  - <span data-ttu-id="951f3-107">Hinzufügen der Kontaktobjekte zu den Unified Messaging-IP-Gateways</span><span class="sxs-lookup"><span data-stu-id="951f3-107">Add it to the Unified Messaging IP gateways.</span></span>

  - <span data-ttu-id="951f3-108">Hinzufügen der Kontaktobjekte zu den Unified Messaging-Sammelanschlüssen</span><span class="sxs-lookup"><span data-stu-id="951f3-108">Add it to the Unified Messaging hunt groups.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="951f3-109">Um die Cmdlets <STRONG>Get-CsExUmContact</STRONG> und <STRONG>CsExUmContact</STRONG> verwenden zu können, müssen Sie Mitglied der RTCUniversalUserAdmins-Gruppe sein und über die Berechtigung Organisationseinheit (Organizational Unit, OU) für die OU verfügen, in der die Contacts-Objekte gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="951f3-109">In order to use the <STRONG>Get-CsExUmContact</STRONG> and <STRONG>Move-CsExUmContact</STRONG> cmdlets, you must be a member of the RTCUniversalUserAdmins group and have organizational unit (OU) permission to the OU where the contacts objects are stored.</span></span> <span data-ttu-id="951f3-110">Die Berechtigung ou kann mit dem Cmdlet <STRONG>Grant-OUPermission</STRONG> erteilt werden.</span><span class="sxs-lookup"><span data-stu-id="951f3-110">OU permission can be granted using the <STRONG>Grant-OUPermission</STRONG> cmdlet.</span></span>



</div>

<div>

## <a name="to-move-contact-objects-by-using-the-lync-server-management-shell"></a><span data-ttu-id="951f3-111">So verschieben Sie Kontaktobjekte mithilfe der Lync Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="951f3-111">To move contact objects by using the Lync Server Management Shell</span></span>

1.  <span data-ttu-id="951f3-112">Öffnen Sie die Lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="951f3-112">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="951f3-113">Geben Sie für jeden Pool, der mit Exchange um registriert ist (wobei pool1.contoso.net ein Pool aus der Office Communications Server 2007 R2-Bereitstellung ist und pool2.contoso.net der Pool aus der lync Server 2013-Bereitstellung ist) an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="951f3-113">For each pool registered with Exchange UM (where pool1.contoso.net is a pool from the Office Communications Server 2007 R2 deployment and pool2.contoso.net is the pool from the Lync Server 2013 deployment) at the command line, type the following:</span></span>
    
        Get-CsExUmContact -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsExUmContact -Target pool02.contoso.net
    
    <span data-ttu-id="951f3-114">Stellen Sie sicher, dass die Kontaktobjekte verschoben wurden, indem Sie das **Get-CsExumContact**-Cmdlet ausführen und sich vergewissern, dass **RegistrarPool** jetzt auf den neuen Pool zeigt.</span><span class="sxs-lookup"><span data-stu-id="951f3-114">To verify that the contact objects are moved, run the **Get-CsExumContact** cmdlet and confirm that **RegistrarPool** is now pointing to the new pool.</span></span>

</div>

<div>

## <a name="to-run-the-exchucutil-windows-powershell-script"></a><span data-ttu-id="951f3-115">So führen Sie das Windows PowerShell-Skript "ExchUCUtil" aus</span><span class="sxs-lookup"><span data-stu-id="951f3-115">To run the ExchUCUtil Windows PowerShell script</span></span>

1.  <span data-ttu-id="951f3-116">Melden Sie sich als Benutzer mit der Berechtigung Exchange-Organisationsadministrator am Exchange UM-Server an.</span><span class="sxs-lookup"><span data-stu-id="951f3-116">Log on to the Exchange UM Server as a user with Exchange Organization Administrator privileges.</span></span>

2.  <span data-ttu-id="951f3-117">Navigieren Sie zum Skript Skript "ExchUCUtil Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="951f3-117">Navigate to the ExchUCUtil Windows PowerShell script.</span></span>
    
    <span data-ttu-id="951f3-118">In Exchange 2007 befindet sich ExchUCUtil.ps1 unter: **% Program Files% \\ Microsoft \\ Exchange Server \\ Scripts \\ExchUCUtil.ps1**</span><span class="sxs-lookup"><span data-stu-id="951f3-118">In Exchange 2007, ExchUCUtil.ps1 is located at: **%Program Files%\\Microsoft\\Exchange Server\\Scripts\\ExchUCUtil.ps1**</span></span>
    
    <span data-ttu-id="951f3-119">In Exchange 2010 befindet sich ExchUCUtil.ps1 unter: **% Program Files% \\ Microsoft \\ Exchange Server V14- \\ \\ Skripts \\ExchUCUtil.ps1**</span><span class="sxs-lookup"><span data-stu-id="951f3-119">In Exchange 2010, ExchUCUtil.ps1 is located at: **%Program Files%\\Microsoft\\Exchange Server\\V14\\Scripts\\ExchUCUtil.ps1**</span></span>

3.  <span data-ttu-id="951f3-120">Wenn Exchange in einer einzigen Gesamtstruktur bereitgestellt wird, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="951f3-120">If Exchange is deployed in a single forest, type:</span></span>
    
        exchucutil.ps1
    
    <span data-ttu-id="951f3-121">Oder geben Sie Folgendes ein, falls Exchange in mehreren Gesamtstrukturen bereitgestellt wird:</span><span class="sxs-lookup"><span data-stu-id="951f3-121">Or, if Exchange is deployed in multiple forests, type:</span></span>
    
        exchucutil.ps1 -Forest:" <forest FQDN>"
    
    <span data-ttu-id="951f3-122">Dabei gibt Gesamtstruktur-FQDN die Gesamtstruktur an, in der lync Server 2013 bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="951f3-122">where forest FQDN specifies the forest in which Lync Server 2013 is deployed.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="951f3-123">Starten Sie den Dienst <STRONG>Lync Server Front-End</STRONG> (rtcsrv.exe) neu, <EM>nachdem</EM> Sie "exchucutil.ps1" ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="951f3-123">Be sure to restart the <STRONG>Lync Server Front-End</STRONG> service (rtcsrv.exe) <EM>after</EM> you run exchucutil.ps1.</span></span> <span data-ttu-id="951f3-124">Andernfalls werden von lync Server 2013 Unified Messaging in der Topologie nicht erkannt.</span><span class="sxs-lookup"><span data-stu-id="951f3-124">Otherwise, Lync Server 2013 will not detect Unified Messaging in the topology.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

