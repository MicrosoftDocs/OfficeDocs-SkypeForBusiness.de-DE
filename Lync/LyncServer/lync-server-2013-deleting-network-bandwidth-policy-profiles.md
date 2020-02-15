---
title: 'Lync Server 2013: Löschen von Richtlinienprofilen für Netzwerkbandbreiten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting network bandwidth policy profiles
ms:assetid: 4d6beda8-6aa5-4d5e-8a07-363598f0e0c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688050(v=OCS.15)
ms:contentKeyID: 49733643
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a340cae47a73cb2b7926cf3f3b3832d22432ab2b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048436"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-network-bandwidth-policy-profiles-in-lync-server-2013"></a><span data-ttu-id="4b4f9-102">Löschen von Richtlinienprofilen für Netzwerkbandbreite in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4b4f9-102">Deleting network bandwidth policy profiles in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4b4f9-103">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="4b4f9-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="4b4f9-104">Im Rahmen der Anrufsteuerung wird eine Bandbreitenrichtlinie dazu verwendet, Bandbreiteneinschränkungen für bestimmte Modalitäten zu definieren.</span><span class="sxs-lookup"><span data-stu-id="4b4f9-104">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="4b4f9-105">In Microsoft lync Server 2013 können nur Audio-und Video Modalitäten Bandbreiteneinschränkungen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="4b4f9-105">In Microsoft Lync Server 2013, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="4b4f9-106">Sie können allgemeine Bandbreiteneinschränkungen und Sitzungseinschränkungen festlegen.</span><span class="sxs-lookup"><span data-stu-id="4b4f9-106">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="4b4f9-107">Sie können das lync Server-Systemsteuerung verwenden, um ein Container Profil für diese Richtlinien zu erstellen, zu ändern oder zu löschen.</span><span class="sxs-lookup"><span data-stu-id="4b4f9-107">You can use the Lync Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="4b4f9-108">Mit den folgenden Verfahren können Sie Richtlinienprofile für Netzwerkbandbreiten löschen.</span><span class="sxs-lookup"><span data-stu-id="4b4f9-108">Use the following procedures to delete a network bandwidth policy profiles.</span></span> <span data-ttu-id="4b4f9-109">Ausführliche Informationen zum Erstellen oder Ändern eines Richtlinienprofils für die Netzwerkbandbreite finden Sie unter [erstellen oder Ändern von Bandbreitenrichtlinien Profilen in lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="4b4f9-109">For details on creating or modifying a network bandwidth policy profile, see [Creating or modifying bandwidth policy profiles in Lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md).</span></span>

<div>

## <a name="to-delete-a-bandwidth-policy-profile"></a><span data-ttu-id="4b4f9-110">So löschen Sie ein Richtlinienprofil für die Bandbreite</span><span class="sxs-lookup"><span data-stu-id="4b4f9-110">To delete a bandwidth policy profile</span></span>

1.  <span data-ttu-id="4b4f9-111">Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="4b4f9-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4b4f9-112">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="4b4f9-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4b4f9-113">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4b4f9-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4b4f9-114">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Bandbreitenrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="4b4f9-114">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="4b4f9-115">Klicken Sie auf der Seite **Bandbreitenrichtlinie** auf das Richtlinienprofil der Bandbreite, das Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="4b4f9-115">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4b4f9-p103">Sie können auch mehrere Profile auf einmal löschen. Drücken Sie dazu die STRG-TASTE, und halten Sie sie gedrückt, während Sie mit der Maus auf die einzelnen Profile klicken. Wenn Sie alle Profile auswählen möchten, klicken Sie einfach im Menü <STRONG>Bearbeiten</STRONG> auf <STRONG>Alle auswählen</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="4b4f9-p103">You can delete more than one profile at a time. To do this, press CTRL and select multiple profiles while holding down the CTRL key. Or, to select all profiles, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="4b4f9-119">Abschließend klicken Sie im Menü **Bearbeiten** auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="4b4f9-119">On the **Edit** menu, click **Delete**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="4b4f9-120">Richtlinienprofile für Bandbreiten, die mit einem Netzwerkstandort verknüpft sind, können nicht ohne Weiteres gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="4b4f9-120">You cannot delete a bandwidth policy profile that is associated with a network site.</span></span> <span data-ttu-id="4b4f9-121">In diesem Fall müssen Sie zuerst die Verknüpfung mit dem Netzwerkstandort aufheben, bevor Sie das Profil löschen können.</span><span class="sxs-lookup"><span data-stu-id="4b4f9-121">You must first remove the association with the network site before you can delete the profile.</span></span> <span data-ttu-id="4b4f9-122">Ausführliche Informationen zum Ändern des Netzwerkstandorts finden Sie unter <A href="lync-server-2013-creating-or-modifying-network-sites.md">erstellen oder Ändern von Netzwerkstandorten in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="4b4f9-122">For details about how to modify the network site, see <A href="lync-server-2013-creating-or-modifying-network-sites.md">Creating or modifying network sites in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4b4f9-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4b4f9-123">See Also</span></span>


[<span data-ttu-id="4b4f9-124">Erstellen oder Ändern von Bandbreitenrichtlinien Profilen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4b4f9-124">Creating or modifying bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)  
[<span data-ttu-id="4b4f9-125">Anzeigen von Richtlinienprofil Informationen für Netzwerkbandbreite in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4b4f9-125">Viewing network bandwidth policy profile information in Lync Server 2013</span></span>](lync-server-2013-viewing-network-bandwidth-policy-profile-information.md)  


[<span data-ttu-id="4b4f9-126">Konfigurieren der Anrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4b4f9-126">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)  
[<span data-ttu-id="4b4f9-127">Remove-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="4b4f9-127">Remove-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

