---
title: 'Lync Server 2013: Aktivieren des Anruf Parks für Benutzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable Call Park for users
ms:assetid: 9430763f-3394-467c-9c6d-426bf761604e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398753(v=OCS.15)
ms:contentKeyID: 48184814
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16538ba00571c429493a2bc0ce1ef14b0a331305
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832325"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-call-park-for-users-in-lync-server-2013"></a><span data-ttu-id="d91a9-102">Aktivieren des Anruf Parks für Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d91a9-102">Enable Call Park for users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d91a9-103">_**Letztes Änderungsdatum des Themas:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="d91a9-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="d91a9-104">Benutzer können keine Anrufe parken oder geparkte Anrufe abrufen, bis Sie in der VoIP-Richtlinie für den Anruf Park aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="d91a9-104">Users cannot park calls or retrieve parked calls until they are enabled for Call Park in voice policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d91a9-105">Standardmäßig ist der Parken von Anrufen für alle Benutzer deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="d91a9-105">By default, Call Park is disabled for all users.</span></span>



</div>

<span data-ttu-id="d91a9-106">Sie können das Parken von Anrufen im globalen Bereich oder auf dem Website Bereich oder dem Benutzerbereich aktivieren.</span><span class="sxs-lookup"><span data-stu-id="d91a9-106">You can enable Call Park at the global scope, or at the site scope or user scope.</span></span> <span data-ttu-id="d91a9-107">Der Benutzerbereich hat Vorrang vor dem Website Bereich, und der Website Bereich hat Vorrang vor dem globalen Bereich.</span><span class="sxs-lookup"><span data-stu-id="d91a9-107">User scope takes precedence over site scope, and site scope takes precedence over global scope.</span></span> <span data-ttu-id="d91a9-108">Wenn Sie über mehrere VoIP-Richtlinien verfügen, überprüfen Sie alle Richtlinien, um den Anruf Park zu aktivieren, und nicht nur die globale Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="d91a9-108">If you have multiple voice policies, review all the policies to enable Call Park, not just the global policy.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-enable-call-park-for-users"></a><span data-ttu-id="d91a9-109">So verwenden Sie die lync Server-Systemsteuerung zum Aktivieren des Anruf Parks für Benutzer</span><span class="sxs-lookup"><span data-stu-id="d91a9-109">To Use Lync Server Control Panel to Enable Call Park for Users</span></span>

1.  <span data-ttu-id="d91a9-110">Melden Sie sich als Mitglied der Gruppe **RTCUniversalServerAdmins** oder als Benutzer mit der Administratorrolle **CsVoiceAdministrator**, **CsServerAdministrator** oder **CsAdministrator** beim Computer an.</span><span class="sxs-lookup"><span data-stu-id="d91a9-110">Log on to the computer as a member of the **RTCUniversalServerAdmins** group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>

2.  <span data-ttu-id="d91a9-111">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="d91a9-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d91a9-112">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d91a9-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d91a9-113">Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing**.</span><span class="sxs-lookup"><span data-stu-id="d91a9-113">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="d91a9-114">Klicken Sie auf die Registerkarte **VoIP-Richtlinie**.</span><span class="sxs-lookup"><span data-stu-id="d91a9-114">Click the **Voice Policy** tab.</span></span>

5.  <span data-ttu-id="d91a9-115">Doppelklicken Sie auf eine vorhandene VoIP-Richtlinie, um das Dialogfeld **VoIP-Richtlinie bearbeiten** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="d91a9-115">Double-click an existing voice policy to open the **Edit Voice Policy** dialog box.</span></span>

6.  <span data-ttu-id="d91a9-116">Wählen Sie unter **Anruffunktionen** die Option **Parken von Anrufen aktivieren** aus.</span><span class="sxs-lookup"><span data-stu-id="d91a9-116">Under **Calling features**, select **Enable call park**.</span></span>

7.  <span data-ttu-id="d91a9-117">Klicken Sie auf **OK**, um die VoIP-Richtlinie zu speichern.</span><span class="sxs-lookup"><span data-stu-id="d91a9-117">Click **OK** to save the voice policy</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-enable-call-park-for-users"></a><span data-ttu-id="d91a9-118">So verwenden Sie Cmdlets zum Aktivieren des Anruf Parks für Benutzer</span><span class="sxs-lookup"><span data-stu-id="d91a9-118">To Use Cmdlets to Enable Call Park for Users</span></span>

1.  <span data-ttu-id="d91a9-119">Melden Sie sich auf dem Computer als Mitglied der Gruppe „RTCUniversalServerAdmins“ oder als Benutzer mit der administrativen Rolle „CsVoiceAdministrator“, „CsServerAdministrator“ oder „CsAdministrator“ an.</span><span class="sxs-lookup"><span data-stu-id="d91a9-119">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator administrative role.</span></span>

2.  <span data-ttu-id="d91a9-120">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="d91a9-120">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="d91a9-121">Führen Sie folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="d91a9-121">Run:</span></span>
    
        Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
    
    <span data-ttu-id="d91a9-122">So können Sie beispielsweise den Anruf Park für die standardmäßige globale VoIP-Richtlinie aktivieren:</span><span class="sxs-lookup"><span data-stu-id="d91a9-122">For example, to enable Call Park for the default global voice policy:</span></span>
    
        Set-CsVoicePolicy -EnableCallPark $true

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d91a9-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d91a9-123">See Also</span></span>


[<span data-ttu-id="d91a9-124">Erstellen einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d91a9-124">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

