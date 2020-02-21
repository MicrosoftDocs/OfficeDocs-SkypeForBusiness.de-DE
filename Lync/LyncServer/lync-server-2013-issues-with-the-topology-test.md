---
title: 'Lync Server 2013: Probleme mit dem Topologie-Test'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Issues with the topology test
ms:assetid: 821e8916-7b5d-4f64-8fb0-e5cc392ec1bb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205045(v=OCS.15)
ms:contentKeyID: 48184670
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa3e9b587a286cdff2b7ef08ec217a420792b121
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186768"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="issues-with-the-topology-test-in-lync-server-2013"></a><span data-ttu-id="83ece-102">Probleme beim Topologie-Test in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83ece-102">Issues with the topology test in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="83ece-103">_**Letztes Änderungsstand des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="83ece-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="83ece-104">Wie das Cmdlet " **Test-CsTopology** " bietet Ihnen Best Practice Analyzer die Möglichkeit, zu überprüfen, ob lync Server 2013 auf globaler Ebene ordnungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="83ece-104">Like the **Test-CsTopology** cmdlet, Best Practice Analyzer provides a way for you to verify that Lync Server 2013 is functioning correctly at a global level.</span></span> <span data-ttu-id="83ece-105">Standardmäßig prüft Best Practice Analyzer wie das Cmdlet die gesamte lync Server 2013 Infrastruktur, überprüft, ob die erforderlichen Dienste aktiv sind und dass die entsprechenden Benutzerrechte und-Berechtigungen für diese Dienste und für die universelle festgelegt wurden. bei der Installation von lync Server 2013 erstellte Sicherheitsgruppen.</span><span class="sxs-lookup"><span data-stu-id="83ece-105">By default, Best Practice Analyzer, like the cmdlet, checks your entire Lync Server 2013 infrastructure, verifying that the required services are running, and that the appropriate user rights and permissions have been set for these services and for the universal security groups created when you install Lync Server 2013.</span></span>

<span data-ttu-id="83ece-106">Zusätzlich zur Überprüfung der Gültigkeit von lync Server als Ganzes überprüft **Test-CsTopology** auch die Gültigkeit eines bestimmten Diensts.</span><span class="sxs-lookup"><span data-stu-id="83ece-106">In addition to verifying the validity of Lync Server as a whole, **Test-CsTopology** also checks the validity of a specific service.</span></span> <span data-ttu-id="83ece-107">Ausführliche Informationen zur Verwendung des Cmdlets zum Testen bestimmter Dienste finden Sie unter [Test-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) in der lync Server-Verwaltungsshell Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="83ece-107">For details about using the cmdlet to test specific services, see [Test-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) in the Lync Server Management Shell documentation.</span></span> <span data-ttu-id="83ece-108">Nutzen Sie die folgenden Informationen, um Probleme mit Ihrer Topologie zu lösen.</span><span class="sxs-lookup"><span data-stu-id="83ece-108">Use the following information to help resolve issues with your topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="83ece-p103">Je nach Konfiguration Ihrer Edgeserver und den entsprechenden Einstellungen im Umkreisnetzwerk, inklusive Firewall- Einstellungen und Berechtigungen, kann Best Practices Analyzer möglicherweise nicht auf Ihre Edgeserver zugreifen, um diese zu scannen. Wenn Sie die Edgeserver scannen lassen und die Berichte anzeigen, dass ein Zugriffsproblem für die Edgeserver vorliegt, deaktivieren Sie das Kontrollkästchen <STRONG>Edgeserver</STRONG>, und führen Sie den Scanvorgang erneut aus, um zu verhindern, dass das Problem in den Berichten aufgelistet wird.</span><span class="sxs-lookup"><span data-stu-id="83ece-p103">Depending on the configuration of your Edge Servers and any related perimeter network settings, including firewall settings and permissions, Best Practices Analyzer might not be able to access and scan your Edge Servers. If you include Edge Servers in your scan and the reports indicate that there is an issue accessing Edge Servers, clear the <STRONG>Edge Servers</STRONG> check box and run the scan again to prevent the issue from showing up in reports.</span></span>



</div>

<div>

## <a name="resolving-issues-with-your-topology"></a><span data-ttu-id="83ece-111">Problembehebung für Ihre Topologie</span><span class="sxs-lookup"><span data-stu-id="83ece-111">Resolving Issues with Your Topology</span></span>

<span data-ttu-id="83ece-112">Wenn beim Topologietest Probleme mit Ihrer Topologie gefunden werden, werden diese Probleme wahrscheinlich durch Fehler verursacht, die beim Veröffentlichen oder Aktivieren Ihrer Topologie aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="83ece-112">If the topology test found issues with your topology, these issues are probably caused by issues that occurred when you published or enabled your topology.</span></span>

<span data-ttu-id="83ece-113">Wenn Sie Änderungen an Ihrer Topologie vornehmen, werden die Änderungen erst dann wirksam, wenn sie sowohl veröffentlicht als auch aktiviert wurden.</span><span class="sxs-lookup"><span data-stu-id="83ece-113">When you make changes to your topology, the changes take effect only when they have been both published and enabled.</span></span> <span data-ttu-id="83ece-114">Sie müssen den Topologie-Generator verwenden, um Topologie-Änderungen vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="83ece-114">You must use Topology Builder to make topology changes.</span></span> <span data-ttu-id="83ece-115">Nachdem Sie Änderungen vorgenommen haben, können Sie diese Änderungen dann mithilfe des Topologie-Generators veröffentlichen und aktivieren.</span><span class="sxs-lookup"><span data-stu-id="83ece-115">After you make changes, you can then publish and enable those changes by using Topology Builder.</span></span>

<span data-ttu-id="83ece-116">Wenn Sie die Änderungen veröffentlichen, werden die neuen Informationen (beispielsweise eine neue Website oder eine neue Serverrolle) in den zentralen Verwaltungsspeicher geschrieben.</span><span class="sxs-lookup"><span data-stu-id="83ece-116">When you publish the changes, the new information (for example, a new site or a new server role) is written to the Central Management store.</span></span> <span data-ttu-id="83ece-117">Diese neuen (oder neu geänderten) Objekte werden jedoch nicht unmittelbar Ihrer Topologie beitreten.</span><span class="sxs-lookup"><span data-stu-id="83ece-117">However, these new (or the newly modified) objects do not immediately join your topology.</span></span> <span data-ttu-id="83ece-118">Objekte werden nur dann an Ihre Topologie anschliessen, wenn Sie die aktualisierte Topologie aktivieren.</span><span class="sxs-lookup"><span data-stu-id="83ece-118">Objects join your topology only when you enable the updated topology.</span></span> <span data-ttu-id="83ece-119">Wenn Sie im Topologie-Generator die Option veröffentlichen auswählen, treten beide Schritte auf: die Änderungen werden veröffentlicht (das heißt, Sie werden in den zentralen Verwaltungsspeicher geschrieben) und dann wird die neue Topologie aktiviert.</span><span class="sxs-lookup"><span data-stu-id="83ece-119">If you select the Publish option in Topology Builder both of these steps occur: the changes are published (that is, they are written to the Central Management store) and then the new topology is enabled.</span></span>

<span data-ttu-id="83ece-120">Standardmäßig sind Mitglieder der Gruppe "RTCUniversalServerAdmins" autorisiert, die Cmdlets **Publish-CsTopology** und **Enable-CsTopology** auszuführen.</span><span class="sxs-lookup"><span data-stu-id="83ece-120">By default, members of the RTCUniversalServerAdmins group are authorized to run the **Publish-CsTopology** cmdlet and the **Enable-CsTopology** cmdlet.</span></span> <span data-ttu-id="83ece-121">Wenn die Setupberechtigungen jedoch nicht delegiert wurden, müssen Sie als Domänenadministrator angemeldet sein, um das Cmdlet **Publish-CsTopology** auszuführen.</span><span class="sxs-lookup"><span data-stu-id="83ece-121">However, if setup permissions have not been delegated, you must be logged on as a domain administrator to run **Publish-CsTopology**.</span></span> <span data-ttu-id="83ece-122">Um RTCUniversalServerAdmins das Recht zu geben, das Cmdlet " **Publish-CsTopology** " tatsächlich zu verwenden, müssen Sie das **Grant-CsSetupPermission-** Cmdlet für jeden Active Directory Container ausführen, der Computer mit lync Server Diensten enthält.</span><span class="sxs-lookup"><span data-stu-id="83ece-122">To give RTCUniversalServerAdmins the right to actually use the **Publish-CsTopology** cmdlet, you must run the **Grant-CsSetupPermission** cmdlet on every Active Directory container that contains computers running Lync Server services.</span></span> <span data-ttu-id="83ece-123">Um RTCUniversalServerAdmins das Recht zu geben, das Cmdlet **enable-CsTopology** zu verwenden, müssen Sie das Cmdlet " **CsSetupPermission** " für jeden Active Directory-Domänendienste Container ausführen, der Computer mit lync Server Diensten enthält.</span><span class="sxs-lookup"><span data-stu-id="83ece-123">To give RTCUniversalServerAdmins the right to use the **Enable-CsTopology** cmdlet, you must run the **Set-CsSetupPermission** cmdlet against every Active Directory Domain Services container that contains computers running Lync Server services.</span></span> <span data-ttu-id="83ece-124">Beachten Sie, dass dies für das Aktivieren und Veröffentlichen einer Topologie mithilfe des Topologie-Generators gilt.</span><span class="sxs-lookup"><span data-stu-id="83ece-124">Note that this applies to enabling and publishing a topology by using Topology Builder.</span></span> <span data-ttu-id="83ece-125">Wenn Sie die Berechtigungen nicht mithilfe von "CsSetupPermission" delegiert haben, kann nur ein Domänenadministrator eine Topologie mithilfe des Topologie **-** Generators aktivieren und veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="83ece-125">If you have not delegated permissions by using **Set-CsSetupPermission**, only a domain administrator can enable and publish a topology through Topology Builder.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

