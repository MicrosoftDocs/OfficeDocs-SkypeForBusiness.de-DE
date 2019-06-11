---
title: 'Lync Server 2013: Erstellen einer VoIP-Routingrichtlinie für Zweigstellenbenutzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create the VoIP routing policy for branch users
ms:assetid: 10deca9f-f870-4a42-b25d-e4fc53108658
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398196(v=OCS.15)
ms:contentKeyID: 48183435
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f53e69069bc1f39f84c057f1e90882d5ae0d65d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832763"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-the-voip-routing-policy-for-branch-users-in-lync-server-2013"></a><span data-ttu-id="827fd-102">Erstellen einer VoIP-Routingrichtlinie für Zweigstellenbenutzer in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="827fd-102">Create the VoIP routing policy for branch users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="827fd-103">_**Letztes Änderungsdatum des Themas:** 2012-09-23_</span><span class="sxs-lookup"><span data-stu-id="827fd-103">_**Topic Last Modified:** 2012-09-23_</span></span>

<span data-ttu-id="827fd-104">Es wird empfohlen, eine separate VoIP-Richtlinie für Benutzer an Zweigstellen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="827fd-104">We recommend creating a separate voice over IP (VoIP) policy for users at branch sites.</span></span> <span data-ttu-id="827fd-105">Diese Richtlinie sollte Routen zu Ausgängen vom Survivable Branch Appliance-Gateway oder dem überlebensfähigen externen Branch Server-Gateway sowie Backup-Routen zum Ausstieg von einem Gateway am zentralen Standort enthalten.</span><span class="sxs-lookup"><span data-stu-id="827fd-105">This policy should contain routes to egress from the Survivable Branch Appliance gateway or the Survivable Branch Server external gateway and backup routes to egress from a gateway at the central site.</span></span> <span data-ttu-id="827fd-106">Unabhängig davon, wo der Benutzer registriert ist, entweder auf der Registrierungsstelle auf der Survivable Branch-Appliance oder auf dem Überlebenden Branch-Server oder auf dem Backup-Registrar-Cluster am zentralen Standort, ist die VoIP-Richtlinie des Benutzers immer gültig.</span><span class="sxs-lookup"><span data-stu-id="827fd-106">Regardless of where the user is registered, either on the Registrar on the Survivable Branch Appliance or Survivable Branch Server or on the backup Registrar cluster at the central site, the user’s VoIP policy is always in effect.</span></span>

<div>

## <a name="to-configure-the-voip-routing-policy-for-branch-users"></a><span data-ttu-id="827fd-107">So konfigurieren Sie die VoIP-Routing Richtlinie für Verzweigungs Benutzer</span><span class="sxs-lookup"><span data-stu-id="827fd-107">To configure the VoIP routing policy for branch users</span></span>

1.  <span data-ttu-id="827fd-108">Erstellen Sie einen Wählplan auf Benutzerebene, und weisen Sie ihn Verzweigungs Benutzern zu.</span><span class="sxs-lookup"><span data-stu-id="827fd-108">Create a user-level dial plan and assign it to branch users.</span></span> <span data-ttu-id="827fd-109">(Weitere Informationen finden Sie unter [Erstellen eines Wählplans in lync Server 2013](lync-server-2013-create-a-dial-plan.md) in der Betriebsdokumentation.)</span><span class="sxs-lookup"><span data-stu-id="827fd-109">(See [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) in the Operations documentation.)</span></span>

2.  <span data-ttu-id="827fd-110">Weisen Sie Normalisierungsregeln zu, die den Wählgewohnheiten der Benutzer auf dieser Website entsprechen.</span><span class="sxs-lookup"><span data-stu-id="827fd-110">Assign normalization rules corresponding to the dialing habits of users at that site.</span></span> <span data-ttu-id="827fd-111">Wenn der überlebensfähige Branch Appliance-oder Survivable Branch Server-Benutzer an den sicherungsregistrierungspool am zentralen Standort scheitert, ist derselbe Wählplan in Kraft.</span><span class="sxs-lookup"><span data-stu-id="827fd-111">If the Survivable Branch Appliance or Survivable Branch Server user fails over to the backup Registrar pool at the central site, the same dial plan will be in effect.</span></span> <span data-ttu-id="827fd-112">(Weitere Informationen finden Sie unter [Erstellen eines Wählplans in lync Server 2013](lync-server-2013-create-a-dial-plan.md) in der Betriebsdokumentation.)</span><span class="sxs-lookup"><span data-stu-id="827fd-112">(See [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) in the Operations documentation.)</span></span>

3.  <span data-ttu-id="827fd-113">Konfigurieren Sie eine VoIP-Route, die vom Survivable Branch Appliance-Gateway oder dem egresses-externen Gateway überlebensfähig ist.</span><span class="sxs-lookup"><span data-stu-id="827fd-113">Configure a voice route that egresses from the Survivable Branch Appliance gateway or the Survivable Branch Server external gateway.</span></span> <span data-ttu-id="827fd-114">(Weitere Informationen finden Sie unter [Erstellen einer VoIP-Route in lync Server 2013](lync-server-2013-create-a-voice-route.md) in der Betriebsdokumentation.)</span><span class="sxs-lookup"><span data-stu-id="827fd-114">(See [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md) in the Operations documentation.)</span></span>

4.  <span data-ttu-id="827fd-115">Legen Sie eine Backup-Anrufroute auf der Survivable Branch-Appliance oder einem Überlebenden Branch Server-Gateway fest, um auf den sicherungsregistrierungspool (zusammen mit dem Mediation Server) am zentralen Standort zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="827fd-115">Set a backup call route on the Survivable Branch Appliance or Survivable Branch Server gateway to point to the backup Registrar pool (collocated with Mediation Server) at the central site.</span></span> <span data-ttu-id="827fd-116">(Weitere Informationen finden Sie in der Dokumentation zu ihrer Survivable Branch-Appliance oder der Survivable Branch Server-Anbieter.)</span><span class="sxs-lookup"><span data-stu-id="827fd-116">(See your Survivable Branch Appliance or Survivable Branch Server vendor documentation.)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="827fd-117">Mit dieser Konfiguration für eine Backup-Anrufroute können Sie sicherstellen, dass eingehende Anrufe an den Verzweigungs Benutzer funktionieren, wenn die Survivable Branch-Appliance oder der Survivable Branch-Server nicht zur Verfügung steht (beispielsweise, wenn Sie nicht gewartet werden kann).</span><span class="sxs-lookup"><span data-stu-id="827fd-117">This backup call route setup helps ensure that inbound calls to the branch user will work when the Survivable Branch Appliance or Survivable Branch Server is not available (for example, if it is down for maintenance).</span></span> <span data-ttu-id="827fd-118">Wenn die Registrierungsstelle und der Vermittlungsserver auf der Survivable Branch-Appliance oder dem Survivable Branch-Server nicht verfügbar sind und der Benutzer beim sicherungsregistrierungspool am zentralen Standort registriert ist, können eingehende Anrufe weiterhin an den Benutzer weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="827fd-118">If the Registrar and Mediation Server on the Survivable Branch Appliance or Survivable Branch Server are not available, and the user is registered with the backup Registrar pool at the central site, inbound calls can still be routed to the user.</span></span>

    
    </div>

<span data-ttu-id="827fd-119">**Nächster Schritt**: [Konfigurieren der Einstellungen für die Umleitung von Voicemail in lync Server 2013](lync-server-2013-configure-voice-mail-rerouting-settings.md)</span><span class="sxs-lookup"><span data-stu-id="827fd-119">**Next step**: [Configure voice mail rerouting settings in Lync Server 2013](lync-server-2013-configure-voice-mail-rerouting-settings.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

