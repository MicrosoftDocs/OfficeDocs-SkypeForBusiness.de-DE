---
title: 'Lync Server 2013: Anzeigen von Informationen zu Standortrichtlinien'
description: 'Lync Server 2013: Anzeigen von Informationen zur Standortrichtlinie.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing location policy information
ms:assetid: 14e41bcb-ea0a-49c2-99b3-1f61fc34416d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520954(v=OCS.15)
ms:contentKeyID: 48183489
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2fecc5de5fb71014a1641038e9e09afba0e90cdb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565421"
---
# <a name="viewing-location-policy-information-in-lync-server-2013"></a><span data-ttu-id="aee7b-103">Anzeigen von Informationen zu Standortrichtlinien in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aee7b-103">Viewing location policy information in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aee7b-104">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="aee7b-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="aee7b-105">In lync Server 2013 können Sie die Standortrichtlinie verwenden, um Einstellungen anzuwenden, die sich auf Erweiterte 9-1-1-Funktionen (E9-1-1) und auf Standorteinstellungen für Benutzer oder Kontakte beziehen.</span><span class="sxs-lookup"><span data-stu-id="aee7b-105">In Lync Server 2013, you can use the location policy to apply settings that relate to Enhanced 9-1-1 (E9-1-1) functionality and to location settings for users or contacts.</span></span> <span data-ttu-id="aee7b-106">Die ortungsrichtlinie legt fest, ob ein Benutzer für E9-1-1 aktiviert ist und was das Verhalten eines Notrufs ist.</span><span class="sxs-lookup"><span data-stu-id="aee7b-106">The location policy determines whether a user is enabled for E9-1-1, and if so what the behavior is of an emergency call.</span></span> <span data-ttu-id="aee7b-107">Beispielsweise können Sie die ortungsrichtlinie verwenden, um zu definieren, welche Zahl einen Notruf darstellt (beispielsweise 911 in den USA), ob die Unternehmenssicherheit automatisch benachrichtigt werden soll und wie der Anruf weitergeleitet werden soll.</span><span class="sxs-lookup"><span data-stu-id="aee7b-107">For example, you can use the location policy to define what number constitutes an emergency call (for example, 911 in the United States), whether corporate security should be automatically notified, and how the call should be routed.</span></span>

<span data-ttu-id="aee7b-108">Sie können Standortrichtlinien in lync Server 2013 Systemsteuerung in der Gruppe " **Netzwerkkonfiguration** " konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="aee7b-108">You can configure location policies from the **Network Configuration** group in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="aee7b-109">In lync Server-Systemsteuerung können Sie Standortrichtlinien anzeigen, erstellen, ändern oder löschen.</span><span class="sxs-lookup"><span data-stu-id="aee7b-109">From Lync Server Control Panel you can view, create, modify, or delete location policies.</span></span> <span data-ttu-id="aee7b-110">Verwenden Sie das folgende Verfahren, um Informationen zu Ortungsrichtlinien anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="aee7b-110">Use the following procedure to view information about location policies.</span></span> <span data-ttu-id="aee7b-111">Ausführliche Informationen zum Erstellen oder Ändern von ortungsrichtlinien finden Sie unter [erstellen oder Ändern einer ortungsrichtlinie in lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).</span><span class="sxs-lookup"><span data-stu-id="aee7b-111">For details on creating or modifying location policies, see [Creating or modifying a location policy in Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).</span></span>

<div>

## <a name="to-view-information-about-a-location-policy"></a><span data-ttu-id="aee7b-112">So zeigen Sie Informationen zu einer Ortungsrichtlinie an</span><span class="sxs-lookup"><span data-stu-id="aee7b-112">To view information about a location policy</span></span>

1.  <span data-ttu-id="aee7b-113">Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="aee7b-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="aee7b-114">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="aee7b-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="aee7b-115">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="aee7b-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="aee7b-116">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Ortungsrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="aee7b-116">In the left navigation bar, click **Network Configuration** and then click **Location Policy**.</span></span>

4.  <span data-ttu-id="aee7b-117">Klicken Sie auf der Seite **Ortungsrichtlinie** auf die Ortungsrichtlinie, die geändert werden soll.</span><span class="sxs-lookup"><span data-stu-id="aee7b-117">On the **Location Policy** page, select the location policy that you want to modify.</span></span>

5.  <span data-ttu-id="aee7b-118">Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="aee7b-118">On the **Edit** menu, click **Show details**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="aee7b-119">Sie können jeweils nur Informationen zu einer Ortungsrichtlinie anzeigen.</span><span class="sxs-lookup"><span data-stu-id="aee7b-119">You can only view information about one location policy at a time.</span></span>

    
    </div>

<span data-ttu-id="aee7b-p104">Standardmäßig ist eine einzige Richtlinie (Global) vorhanden, die nicht gelöscht oder umbenannt werden kann. Sie können die globale Richtlinie jedoch ändern. Sofern keine Standortrichtlinien oder Richtlinien auf Benutzerbasis erstellt werden, wird diese Richtlinie auf sämtliche Benutzer und Kontakte angewendet. Richtlinien auf Benutzerbasis müssen auf bestimmte Benutzer angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="aee7b-p104">A single policy, called Global, exists by default and cannot be deleted or renamed. However, you can modify the Global policy. This policy will apply to all users and contacts, unless you create site policies or per-user policies. Per-user policies must be applied to specific users.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="aee7b-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aee7b-124">See Also</span></span>


[<span data-ttu-id="aee7b-125">Erstellen oder Ändern einer ortungsrichtlinie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aee7b-125">Creating or modifying a location policy in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-a-location-policy.md)  
[<span data-ttu-id="aee7b-126">Erstellen von ortungsrichtlinien in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aee7b-126">Create location policies in Lync Server 2013</span></span>](lync-server-2013-create-location-policies.md)  
[<span data-ttu-id="aee7b-127">Erstellen oder Ändern eines Netzwerkstandorts in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aee7b-127">Create or modify a network site in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-site.md)  


[<span data-ttu-id="aee7b-128">New-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="aee7b-128">New-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy)  
[<span data-ttu-id="aee7b-129">Gruppe-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="aee7b-129">Set-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy)  
[<span data-ttu-id="aee7b-130">Remove-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="aee7b-130">Remove-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsLocationPolicy)  
[<span data-ttu-id="aee7b-131">Get-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="aee7b-131">Get-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsLocationPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

