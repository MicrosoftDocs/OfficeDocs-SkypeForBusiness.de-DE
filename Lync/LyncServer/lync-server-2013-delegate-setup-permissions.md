---
title: 'Lync Server 2013: Delegieren von Setup Berechtigungen'
description: 'Lync Server 2013: Delegate Setup Permissions.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delegate setup permissions
ms:assetid: 9dca1683-4c69-4534-8ebe-6bd635cbae49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412735(v=OCS.15)
ms:contentKeyID: 48184997
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a7038cf729bad459dbcd2a84a308b14aa56b68dd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545341"
---
# <a name="delegate-setup-permissions-in-lync-server-2013"></a><span data-ttu-id="8ab0c-103">Delegieren von Setup Berechtigungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8ab0c-103">Delegate setup permissions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8ab0c-104">_**Letztes Änderungsstand des Themas:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="8ab0c-104">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="8ab0c-105">Wenn Sie Benutzern oder Gruppen, die lync Server 2013 bereitstellen, keine Mitgliedschaft in der Gruppe "Domänen-Admins" gewähren möchten, können Sie Mitgliedern der Gruppe "RTCUniversalServerAdmins" das Cmdlet **enable-CsTopology**   Windows PowerShell auf Servern mit lync Server 2013 ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="8ab0c-105">If you do not want to grant membership in the Domain Admins group to users or groups who are deploying Lync Server 2013, you can enable members of the RTCUniversalServerAdmins group to run the **Enable-CsTopology** Windows PowerShell cmdlet on servers running Lync Server 2013.</span></span> <span data-ttu-id="8ab0c-106">Standardmäßig verfügen Mitglieder der Gruppe "RTCUniversalServerAdmins" nicht über die Berechtigung zum Ausführen dieses Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="8ab0c-106">By default, members of the RTCUniversalServerAdmins group do not have the ability to run this cmdlet.</span></span> <span data-ttu-id="8ab0c-107">Sie gewähren Administratorrechte und Berechtigungen zum Ausführen von **enable-CsTopology** auf Servern mit lync Server mithilfe des Cmdlets **Grant-CsSetupPermission** und der Angabe einer Organisationseinheit (Organizational Unit, OU), in der sich Computerobjekte für den Server befinden, auf dem lync Server 2013 ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="8ab0c-107">You grant administrator rights and permissions to run **Enable-CsTopology** on servers running Lync Server by using the **Grant-CsSetupPermission** cmdlet and specifying an organizational unit (OU) where computer objects for the server running Lync Server 2013 are located.</span></span>

<span data-ttu-id="8ab0c-108">Bei der Domänenvorbereitung, die bei der Installation von lync Server erfolgt, werden nicht automatisch die Berechtigungen hinzugefügt, mit denen Mitglieder der RTCUniversalServerAdmins-Gruppe das Enable-CsTopology-Cmdlet ausführen können.</span><span class="sxs-lookup"><span data-stu-id="8ab0c-108">The domain preparation that takes place when you install Lync Server does not automatically add the permissions that enable members of the RTCUniversalServerAdmins group to run the Enable-CsTopology cmdlet.</span></span> <span data-ttu-id="8ab0c-109">Dies bedeutet, dass Sie standardmäßig ein Domänenadministrator sein müssen, um eine Topologie zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="8ab0c-109">That means that, by default, you must be a domain administrator in order to enable a topology.</span></span> <span data-ttu-id="8ab0c-110">Um Mitgliedern der Gruppe "RTCUniversalServerAdmins" das Recht zum Aktivieren einer Topologie zu erteilen, müssen Sie das Cmdlet Grant-CsSetupPermissions ausführen.</span><span class="sxs-lookup"><span data-stu-id="8ab0c-110">To give members of the RTCUniversalServerAdmins group the right to enable a topology you must run the Grant-CsSetupPermissions cmdlet.</span></span> <span data-ttu-id="8ab0c-111">Darüber hinaus müssen Sie dieses Cmdlet für jeden Active Directory Container ausführen, in dem sich Computer befinden, auf denen lync Server ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8ab0c-111">In addition, you will need to run this cmdlet against each Active Directory container that houses computers running Lync Server.</span></span>

<span data-ttu-id="8ab0c-112">Beachten Sie, dass dieses Cmdlet nur der Gruppe "RTCUniversalServerAdmins" Berechtigungen erteilt; das Cmdlet kann keiner anderen Sicherheitsgruppe oder einzelnen Benutzern Berechtigungen gewähren.</span><span class="sxs-lookup"><span data-stu-id="8ab0c-112">Keep in mind that this cmdlet only grants permissions to the RTCUniversalServerAdmins group; the cmdlet cannot be used to grant permissions to other security groups or to individual users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8ab0c-113"><STRONG>Enable-CsTopology</STRONG> ist das Schlüssel-Cmdlet, das es den Mitgliedern der RTCUniversalServerAdmins-Gruppe ermöglicht, lync Server 2013 einzurichten und bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="8ab0c-113"><STRONG>Enable-CsTopology</STRONG> is the key cmdlet to allow the RTCUniversalServerAdmins group members to set up and deploy Lync Server 2013.</span></span>



</div>

<div>

## <a name="to-add-the-ability-to-run-enable-cstopology-to-the-rtcuniversalserveradmins-group"></a><span data-ttu-id="8ab0c-114">So erteilen Sie der Gruppe "RTCUniversalServerAdmins" die Möglichkeit zum Ausführen von "Enable-CsTopology"</span><span class="sxs-lookup"><span data-stu-id="8ab0c-114">To add the ability to run Enable-CsTopology to the RTCUniversalServerAdmins group</span></span>

1.  <span data-ttu-id="8ab0c-115">Melden Sie sich bei einem Server als Mitglied der Gruppe "Domänen-Admins" für die Domäne an, in der der delegierte Benutzer **Enable-CsTopology** ausführen soll.</span><span class="sxs-lookup"><span data-stu-id="8ab0c-115">Log on to a server as a member of the Domain Admins group for the domain on which the delegated user will run **Enable-CsTopology**.</span></span>

2.  <span data-ttu-id="8ab0c-116">Öffnen Sie die lync Server 2013 Management-Shell.</span><span class="sxs-lookup"><span data-stu-id="8ab0c-116">Open the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="8ab0c-117">Die lync Server 2013-Verwaltungsshell wird automatisch auf jedem Front-End-Server oder auf einem Computer installiert, auf dem die lync Server 2013-Verwaltungstools installiert wurden.</span><span class="sxs-lookup"><span data-stu-id="8ab0c-117">The Lync Server 2013 Management Shell is automatically installed on each Front End Server or any computer where the Lync Server 2013 administrative tools have been installed.</span></span> <span data-ttu-id="8ab0c-118">Ausführliche Informationen zur lync Server 2013-Verwaltungsshell finden Sie unter [lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="8ab0c-118">For details about the Lync Server 2013 Management Shell, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) in the Operations documentation.</span></span>

3.  <span data-ttu-id="8ab0c-119">Führen Sie das folgende Cmdlet aus der Verwaltungsshell für die lync Server 2013 Verwaltung aus:</span><span class="sxs-lookup"><span data-stu-id="8ab0c-119">Run the following cmdlet from the Lync Server 2013 Management Shell:</span></span>
    
        Grant-CsSetupPermission -ComputerOU <DN of the OU> -Domain <Domain FQDN>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8ab0c-120">Wenn die Organisationseinheit nicht die oberste Ebene ist, müssen Sie den vollständigen Domänennamen angeben.</span><span class="sxs-lookup"><span data-stu-id="8ab0c-120">If the OU is not top level, you must provide the full domain name.</span></span>

    
    </div>
    
    <span data-ttu-id="8ab0c-121">Im folgenden Beispiel wird als Organisationseinheit "Lync Servers" in der Domäne "contoso.com" festgelegt.</span><span class="sxs-lookup"><span data-stu-id="8ab0c-121">In the following example, the OU is “Lync Servers,” which is in the contoso.com domain.</span></span>
    
        Grant-CsSetupPermission -ComputerOU "OU=Lync Servers" -Domain contoso.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

