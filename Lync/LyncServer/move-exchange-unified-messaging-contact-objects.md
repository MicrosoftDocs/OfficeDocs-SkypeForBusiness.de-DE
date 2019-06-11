---
title: Verschieben von Exchange Unified Messaging-Kontaktobjekten
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Move Exchange Unified Messaging Contact objects
ms:assetid: 35c7e987-41b5-4798-b617-3303f20e52e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688022(v=OCS.15)
ms:contentKeyID: 49733612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 946bf7221ab9f4c5a7111839bca25dabaad31d82
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847085"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-exchange-unified-messaging-contact-objects"></a><span data-ttu-id="52aee-102">Verschieben von Exchange Unified Messaging-Kontaktobjekten</span><span class="sxs-lookup"><span data-stu-id="52aee-102">Move Exchange Unified Messaging Contact objects</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52aee-103">_**Letztes Änderungsdatum des Themas:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="52aee-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="52aee-104">Zum Migrieren von Kontaktobjekten der automatischen Telefonzentrale (AA) und des Abonnenten Zugriffs (SA) zur neuen lync Server 2013-Bereitstellung verschieben Sie zunächst die Objekte aus der Legacy-Bereitstellung von Office Communications Server 2007 R2 auf die neue lync Server 2013-Bereitstellung unter Verwendung der \*\* Cmdlets für Get-CsExUmContact\*\* und **Move-CsExUmContact** .</span><span class="sxs-lookup"><span data-stu-id="52aee-104">To migrate Auto Attendant (AA) and Subscriber Access (SA) contact objects to the new Lync Server 2013 deployment, you first move the objects from the legacy Office Communications Server 2007 R2 deployment to the new the Lync Server 2013 deployment using the **Get-CsExUmContact** and **Move-CsExUmContact** cmdlets.</span></span> <span data-ttu-id="52aee-105">Auf dem Exchange-Server führen Sie dann das Windows PowerShell- **exchucutil** -Skript aus, um die folgenden Schritte für den neu bereitgestellten lync-Pool durchzuführen:</span><span class="sxs-lookup"><span data-stu-id="52aee-105">On the Exchange Server, you then run the **ExchUCUtil** Windows PowerShell script to do the following for the newly deployed Lync pool:</span></span>

  - <span data-ttu-id="52aee-106">Fügen Sie Sie den Unified Messaging-IP-Gateways hinzu.</span><span class="sxs-lookup"><span data-stu-id="52aee-106">Add it to the Unified Messaging IP gateways.</span></span>

  - <span data-ttu-id="52aee-107">Fügen Sie es den Unified Messaging-Sammelanschlüssen hinzu.</span><span class="sxs-lookup"><span data-stu-id="52aee-107">Add it to the Unified Messaging hunt groups.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="52aee-108">Um die Cmdlets " <STRONG>Get-CsExUmContact</STRONG> " und " <STRONG>Move-CsExUmContact</STRONG> " verwenden zu können, müssen Sie ein Mitglied der RTCUniversalUserAdmins-Gruppe sein und über die Organisations Einheits Berechtigung für die OU verfügen, in der die Kontaktobjekte gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="52aee-108">In order to use the <STRONG>Get-CsExUmContact</STRONG> and <STRONG>Move-CsExUmContact</STRONG> cmdlets, you must be a member of the RTCUniversalUserAdmins group and have organizational unit (OU) permission to the OU where the contacts objects are stored.</span></span> <span data-ttu-id="52aee-109">Die OU-Berechtigung kann mit dem <STRONG>Grant-OUPermission-</STRONG> Cmdlet gewährt werden.</span><span class="sxs-lookup"><span data-stu-id="52aee-109">OU permission can be granted using the <STRONG>Grant-OUPermission</STRONG> cmdlet.</span></span>



</div>

<div>

## <a name="to-move-contact-objects-by-using-the-lync-server-management-shell"></a><span data-ttu-id="52aee-110">So verschieben Sie Kontaktobjekte mithilfe der lync Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="52aee-110">To move contact objects by using the Lync Server Management Shell</span></span>

1.  <span data-ttu-id="52aee-111">Öffnen Sie die lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="52aee-111">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="52aee-112">Geben Sie für jeden Pool, der bei Exchange um registriert ist (wobei pool1.contoso.net ein Pool aus der Bereitstellung von Office Communications Server 2007 R2 ist und pool2.contoso.net der Pool aus der lync Server 2013-Bereitstellung ist) in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="52aee-112">For each pool registered with Exchange UM (where pool1.contoso.net is a pool from the Office Communications Server 2007 R2 deployment and pool2.contoso.net is the pool from the Lync Server 2013 deployment) at the command line, type the following:</span></span>
    
        Get-CsExUmContact -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsExUmContact -Target pool02.contoso.net
    
    <span data-ttu-id="52aee-113">Führen Sie das Cmdlet " **Get-CsExumContact** " aus, um zu überprüfen, ob die Kontaktobjekte verschoben wurden, und bestätigen Sie, dass **RegistrarPool** nun auf den neuen Pool zeigt.</span><span class="sxs-lookup"><span data-stu-id="52aee-113">To verify that the contact objects are moved, run the **Get-CsExumContact** cmdlet and confirm that **RegistrarPool** is now pointing to the new pool.</span></span>

</div>

<div>

## <a name="to-run-the-exchucutil-windows-powershell-script"></a><span data-ttu-id="52aee-114">So führen Sie das exchucutil-Windows PowerShell-Skript aus</span><span class="sxs-lookup"><span data-stu-id="52aee-114">To run the ExchUCUtil Windows PowerShell script</span></span>

1.  <span data-ttu-id="52aee-115">Melden Sie sich beim Exchange um-Server als Benutzer mit Administrator Rechten für Exchange-Organisation an.</span><span class="sxs-lookup"><span data-stu-id="52aee-115">Log on to the Exchange UM Server as a user with Exchange Organization Administrator privileges.</span></span>

2.  <span data-ttu-id="52aee-116">Navigieren Sie zum Windows PowerShell-Skript exchucutil.</span><span class="sxs-lookup"><span data-stu-id="52aee-116">Navigate to the ExchUCUtil Windows PowerShell script.</span></span>
    
    <span data-ttu-id="52aee-117">In Exchange 2007 befindet sich exchucutil. ps1 unter: **% Program Files%\\Microsoft\\Exchange Server\\-Skripts\\exchucutil. ps1.**</span><span class="sxs-lookup"><span data-stu-id="52aee-117">In Exchange 2007, ExchUCUtil.ps1 is located at: **%Program Files%\\Microsoft\\Exchange Server\\Scripts\\ExchUCUtil.ps1**</span></span>
    
    <span data-ttu-id="52aee-118">In Exchange 2010 befindet sich exchucutil. ps1 unter: **\\% Program Files% Microsoft\\Exchange Server\\V14\\Scripts\\exchucutil. ps1**</span><span class="sxs-lookup"><span data-stu-id="52aee-118">In Exchange 2010, ExchUCUtil.ps1 is located at: **%Program Files%\\Microsoft\\Exchange Server\\V14\\Scripts\\ExchUCUtil.ps1**</span></span>

3.  <span data-ttu-id="52aee-119">Wenn Exchange in einer einzelnen Gesamtstruktur bereitgestellt wird, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="52aee-119">If Exchange is deployed in a single forest, type:</span></span>
    
        exchucutil.ps1
    
    <span data-ttu-id="52aee-120">Wenn Exchange in mehreren Gesamtstrukturen bereitgestellt wird, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="52aee-120">Or, if Exchange is deployed in multiple forests, type:</span></span>
    
        exchucutil.ps1 -Forest:" <forest FQDN>"
    
    <span data-ttu-id="52aee-121">Dabei gibt Gesamtstruktur-FQDN die Gesamtstruktur an, in der lync Server 2013 bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="52aee-121">where forest FQDN specifies the forest in which Lync Server 2013 is deployed.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="52aee-122">Stellen Sie sicher, dass der <STRONG>lync Server-Front-End-</STRONG> Dienst (RtcSrv. exe) <EM>nach</EM> der Ausführung von exchucutil. ps1 neu gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="52aee-122">Be sure to restart the <STRONG>Lync Server Front-End</STRONG> service (rtcsrv.exe) <EM>after</EM> you run exchucutil.ps1.</span></span> <span data-ttu-id="52aee-123">Andernfalls wird in lync Server 2013 Unified Messaging in der Topologie nicht erkannt.</span><span class="sxs-lookup"><span data-stu-id="52aee-123">Otherwise, Lync Server 2013 will not detect Unified Messaging in the topology.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

