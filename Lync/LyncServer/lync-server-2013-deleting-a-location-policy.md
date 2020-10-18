---
title: 'Lync Server 2013: Löschen einer ortungsrichtlinie'
description: 'Lync Server 2013: Löschen einer ortungsrichtlinie.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting a location policy
ms:assetid: 8ca9ba10-f45f-435a-b39c-519d251e9085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688125(v=OCS.15)
ms:contentKeyID: 49733724
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 88935c00a60de377c9812a4d119708fd610338ab
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575841"
---
# <a name="deleting-a-location-policy-in-lync-server-2013"></a><span data-ttu-id="b531c-103">Löschen einer ortungsrichtlinie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b531c-103">Deleting a location policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b531c-104">_**Letztes Änderungsstand des Themas:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="b531c-104">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="b531c-105">In lync Server 2013 können Sie die Standortrichtlinie verwenden, um Einstellungen anzuwenden, die sich auf Erweiterte 9-1-1-Funktionen (E9-1-1) und auf Standorteinstellungen für Benutzer oder Kontakte beziehen.</span><span class="sxs-lookup"><span data-stu-id="b531c-105">In Lync Server 2013, you can use the location policy to apply settings that relate to Enhanced 9-1-1 (E9-1-1) functionality and to location settings for users or contacts.</span></span> <span data-ttu-id="b531c-106">Die ortungsrichtlinie legt fest, ob ein Benutzer für E9-1-1 aktiviert ist und was das Verhalten eines Notrufs ist.</span><span class="sxs-lookup"><span data-stu-id="b531c-106">The location policy determines whether a user is enabled for E9-1-1, and if so what the behavior is of an emergency call.</span></span> <span data-ttu-id="b531c-107">Beispielsweise können Sie die ortungsrichtlinie verwenden, um zu definieren, welche Zahl einen Notruf darstellt (beispielsweise 911 in den USA), ob die Unternehmenssicherheit automatisch benachrichtigt werden soll und wie der Anruf weitergeleitet werden soll.</span><span class="sxs-lookup"><span data-stu-id="b531c-107">For example, you can use the location policy to define what number constitutes an emergency call (for example, 911 in the United States), whether corporate security should be automatically notified, and how the call should be routed.</span></span>

<span data-ttu-id="b531c-108">Sie können Standortrichtlinien in lync Server 2013 Systemsteuerung in der Gruppe " **Netzwerkkonfiguration** " konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b531c-108">You can configure location policies from the **Network Configuration** group in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="b531c-109">In lync Server-Systemsteuerung können Sie Standortrichtlinien anzeigen, erstellen, ändern oder löschen.</span><span class="sxs-lookup"><span data-stu-id="b531c-109">From Lync Server Control Panel you can view, create, modify, or delete location policies.</span></span> <span data-ttu-id="b531c-110">Gehen Sie wie folgt vor, um eine Ortungsrichtlinie zu löschen.</span><span class="sxs-lookup"><span data-stu-id="b531c-110">Use the following procedures delete a location policy.</span></span> <span data-ttu-id="b531c-111">Ausführliche Informationen zum Erstellen oder Ändern von ortungsrichtlinien finden Sie unter [erstellen oder Ändern einer ortungsrichtlinie in lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).</span><span class="sxs-lookup"><span data-stu-id="b531c-111">For details on creating or modifying location policies, see [Creating or modifying a location policy in Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).</span></span>

<div>

## <a name="to-delete-a-location-policy"></a><span data-ttu-id="b531c-112">So löschen Sie eine Ortungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="b531c-112">To delete a location policy</span></span>

1.  <span data-ttu-id="b531c-113">Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="b531c-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b531c-114">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="b531c-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b531c-115">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b531c-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b531c-116">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Ortungsrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="b531c-116">In the left navigation bar, click **Network Configuration** and then click **Location Policy**.</span></span>

4.  <span data-ttu-id="b531c-117">Klicken Sie auf der Seite **Ortungsrichtlinie** auf die Ortungsrichtlinie, die gelöscht werden soll.</span><span class="sxs-lookup"><span data-stu-id="b531c-117">On the **Location Policy** page, select the location policy that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b531c-p104">Sie können mehrere Ortungsrichtlinien in einem Arbeitsschritt löschen. Drücken Sie hierzu die STRG-TASTE, und wählen Sie bei gedrückter STRG-TASTE mehrere Richtlinien aus. Wenn Sie alle Richtlinien auswählen möchten, klicken Sie im Menü <STRONG>Bearbeiten</STRONG> auf <STRONG>Alle auswählen</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="b531c-p104">You can delete more than one location policy at a time. To do this, press CTRL and select multiple policies while holding down the CTRL key. Or, to select all policies, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="b531c-121">Klicken Sie im Menü **Bearbeiten** auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="b531c-121">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="b531c-122">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="b531c-122">Click **OK**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b531c-p105">Die globale Ortungsrichtlinie kann nicht gelöscht werden. Beim Versuch, die globale Richtlinie zu löschen, wird eine Warnmeldung angezeigt, und die Richtlinie wird auf die Standardwerte zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="b531c-p105">You cannot delete the Global location policy. If you attempt to delete the Global policy you will receive a warning message and that policy will be reset to its default values.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b531c-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b531c-125">See Also</span></span>


[<span data-ttu-id="b531c-126">Erstellen oder Ändern einer ortungsrichtlinie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b531c-126">Creating or modifying a location policy in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-a-location-policy.md)  
[<span data-ttu-id="b531c-127">Anzeigen von Informationen zu Standortrichtlinien in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b531c-127">Viewing location policy information in Lync Server 2013</span></span>](lync-server-2013-viewing-location-policy-information.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

