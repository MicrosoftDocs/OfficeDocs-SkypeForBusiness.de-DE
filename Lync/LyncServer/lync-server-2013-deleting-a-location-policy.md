---
title: 'Lync Server 2013: Löschen einer Standortrichtlinie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deleting a location policy
ms:assetid: 8ca9ba10-f45f-435a-b39c-519d251e9085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688125(v=OCS.15)
ms:contentKeyID: 49733724
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4766d2b05cef89ab29b9c303c5ba1ec456843669
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832590"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-a-location-policy-in-lync-server-2013"></a><span data-ttu-id="d25fc-102">Löschen einer Standortrichtlinie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d25fc-102">Deleting a location policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d25fc-103">_**Letztes Änderungsdatum des Themas:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="d25fc-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="d25fc-104">In lync Server 2013 können Sie mithilfe der ortungsrichtlinie Einstellungen anwenden, die sich auf die erweiterte 9-1-1 (E9-1-1)-Funktionalität und auf die Standorteinstellungen für Benutzer oder Kontakte beziehen.</span><span class="sxs-lookup"><span data-stu-id="d25fc-104">In Lync Server 2013, you can use the location policy to apply settings that relate to Enhanced 9-1-1 (E9-1-1) functionality and to location settings for users or contacts.</span></span> <span data-ttu-id="d25fc-105">Die ortungsrichtlinie bestimmt, ob ein Benutzer für E9-1-1 aktiviert ist, und wenn ja, was das Verhalten eines Notrufs ist.</span><span class="sxs-lookup"><span data-stu-id="d25fc-105">The location policy determines whether a user is enabled for E9-1-1, and if so what the behavior is of an emergency call.</span></span> <span data-ttu-id="d25fc-106">So können Sie beispielsweise mithilfe der ortungsrichtlinie definieren, welche Nummer ein Notruf ist (beispielsweise 911 in den USA), ob die Unternehmenssicherheit automatisch benachrichtigt werden soll und wie der Anruf weitergeleitet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d25fc-106">For example, you can use the location policy to define what number constitutes an emergency call (for example, 911 in the United States), whether corporate security should be automatically notified, and how the call should be routed.</span></span>

<span data-ttu-id="d25fc-107">Sie können Standortrichtlinien über die Gruppe **Netzwerkkonfiguration** in der lync Server 2013-Systemsteuerung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="d25fc-107">You can configure location policies from the **Network Configuration** group in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="d25fc-108">In der lync Server-Systemsteuerung können Sie Positions Richtlinien anzeigen, erstellen, ändern oder löschen.</span><span class="sxs-lookup"><span data-stu-id="d25fc-108">From Lync Server Control Panel you can view, create, modify, or delete location policies.</span></span> <span data-ttu-id="d25fc-109">Gehen Sie wie folgt vor, um eine Standortrichtlinie zu löschen.</span><span class="sxs-lookup"><span data-stu-id="d25fc-109">Use the following procedures delete a location policy.</span></span> <span data-ttu-id="d25fc-110">Details zum Erstellen oder Ändern von Standortrichtlinien finden Sie unter [erstellen oder Ändern einer Standortrichtlinie in lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).</span><span class="sxs-lookup"><span data-stu-id="d25fc-110">For details on creating or modifying location policies, see [Creating or modifying a location policy in Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).</span></span>

<div>

## <a name="to-delete-a-location-policy"></a><span data-ttu-id="d25fc-111">So löschen Sie eine Standortrichtlinie</span><span class="sxs-lookup"><span data-stu-id="d25fc-111">To delete a location policy</span></span>

1.  <span data-ttu-id="d25fc-112">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="d25fc-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d25fc-113">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="d25fc-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d25fc-114">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d25fc-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d25fc-115">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** , und klicken Sie dann auf **ortungsrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="d25fc-115">In the left navigation bar, click **Network Configuration** and then click **Location Policy**.</span></span>

4.  <span data-ttu-id="d25fc-116">Wählen Sie auf der Seite **Standortrichtlinie** die zu löschende Standortrichtlinie aus.</span><span class="sxs-lookup"><span data-stu-id="d25fc-116">On the **Location Policy** page, select the location policy that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d25fc-117">Sie können mehr als eine Standortrichtlinie gleichzeitig löschen.</span><span class="sxs-lookup"><span data-stu-id="d25fc-117">You can delete more than one location policy at a time.</span></span> <span data-ttu-id="d25fc-118">Drücken Sie dazu STRG, und wählen Sie mehrere Richtlinien aus, während Sie die STRG-Taste gedrückt halten.</span><span class="sxs-lookup"><span data-stu-id="d25fc-118">To do this, press CTRL and select multiple policies while holding down the CTRL key.</span></span> <span data-ttu-id="d25fc-119">Wenn Sie alle Richtlinien auswählen möchten, klicken Sie im Menü <STRONG>Bearbeiten</STRONG> auf <STRONG>Alle auswählen</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="d25fc-119">Or, to select all policies, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="d25fc-120">Klicken Sie im Menü **Bearbeiten** auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="d25fc-120">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="d25fc-121">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="d25fc-121">Click **OK**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d25fc-122">Sie können die globale Standortrichtlinie nicht löschen.</span><span class="sxs-lookup"><span data-stu-id="d25fc-122">You cannot delete the Global location policy.</span></span> <span data-ttu-id="d25fc-123">Wenn Sie versuchen, die globale Richtlinie zu löschen, wird eine Warnmeldung angezeigt, und die Richtlinie wird auf die Standardwerte zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="d25fc-123">If you attempt to delete the Global policy you will receive a warning message and that policy will be reset to its default values.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d25fc-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d25fc-124">See Also</span></span>


[<span data-ttu-id="d25fc-125">Erstellen oder Ändern einer Standortrichtlinie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d25fc-125">Creating or modifying a location policy in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-a-location-policy.md)  
[<span data-ttu-id="d25fc-126">Anzeigen von Standortrichtlinien Informationen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d25fc-126">Viewing location policy information in Lync Server 2013</span></span>](lync-server-2013-viewing-location-policy-information.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

