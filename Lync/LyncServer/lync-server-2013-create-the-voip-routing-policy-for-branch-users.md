---
title: 'Lync Server 2013: Erstellen der VoIP-Routing Richtlinie für Zweigstellenbenutzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create the VoIP routing policy for branch users
ms:assetid: 10deca9f-f870-4a42-b25d-e4fc53108658
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398196(v=OCS.15)
ms:contentKeyID: 48183435
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c55f52c104c4a9e49abb8b4989cfa4901dfe02dc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151677"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-the-voip-routing-policy-for-branch-users-in-lync-server-2013"></a><span data-ttu-id="8cb83-102">Erstellen der VoIP-Routing Richtlinie für Zweigstellenbenutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8cb83-102">Create the VoIP routing policy for branch users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8cb83-103">_**Letztes Änderungsstand des Themas:** 2012-09-23_</span><span class="sxs-lookup"><span data-stu-id="8cb83-103">_**Topic Last Modified:** 2012-09-23_</span></span>

<span data-ttu-id="8cb83-104">Es wird empfohlen, eine separate VoIP-Richtlinie (Voice over IP) für Benutzer an Zweigstellen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="8cb83-104">We recommend creating a separate voice over IP (VoIP) policy for users at branch sites.</span></span> <span data-ttu-id="8cb83-105">Diese Richtlinie sollte Routen zum Ausstieg aus dem Survivable Branch Appliance Gateway oder dem Survivable Branch Server externen Gateway sowie Sicherungs Routen zum Ausstieg von einem Gateway am zentralen Standort enthalten.</span><span class="sxs-lookup"><span data-stu-id="8cb83-105">This policy should contain routes to egress from the Survivable Branch Appliance gateway or the Survivable Branch Server external gateway and backup routes to egress from a gateway at the central site.</span></span> <span data-ttu-id="8cb83-106">Unabhängig davon, wo der Benutzer registriert ist, entweder auf der Registrierungsstelle im Survivable Branch Appliance oder Survivable Branch Server oder auf dem Sicherungs Registrierungs Cluster am zentralen Standort ist die VoIP-Richtlinie des Benutzers immer gültig.</span><span class="sxs-lookup"><span data-stu-id="8cb83-106">Regardless of where the user is registered, either on the Registrar on the Survivable Branch Appliance or Survivable Branch Server or on the backup Registrar cluster at the central site, the user’s VoIP policy is always in effect.</span></span>

<div>

## <a name="to-configure-the-voip-routing-policy-for-branch-users"></a><span data-ttu-id="8cb83-107">So konfigurieren Sie die VoIP-Routing Richtlinie für Zweigstellenbenutzer</span><span class="sxs-lookup"><span data-stu-id="8cb83-107">To configure the VoIP routing policy for branch users</span></span>

1.  <span data-ttu-id="8cb83-108">Erstellen Sie einen Wählplan auf Benutzerebene, und weisen Sie ihn Zweigstellenbenutzern zu.</span><span class="sxs-lookup"><span data-stu-id="8cb83-108">Create a user-level dial plan and assign it to branch users.</span></span> <span data-ttu-id="8cb83-109">(Weitere Informationen finden Sie unter [Create a Dial Plan in lync Server 2013](lync-server-2013-create-a-dial-plan.md) in der Betriebsdokumentation.)</span><span class="sxs-lookup"><span data-stu-id="8cb83-109">(See [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) in the Operations documentation.)</span></span>

2.  <span data-ttu-id="8cb83-110">Zuweisen von Normalisierungsregeln entsprechend den Wählgewohnheiten von Benutzern an diesem Standort.</span><span class="sxs-lookup"><span data-stu-id="8cb83-110">Assign normalization rules corresponding to the dialing habits of users at that site.</span></span> <span data-ttu-id="8cb83-111">Wenn der Survivable Branch Appliance-oder Survivable Branch Server-Benutzer einen Failover zum sicherungsregistrierungspool am zentralen Standort vorschlägt, wird derselbe Wählplan wirksam.</span><span class="sxs-lookup"><span data-stu-id="8cb83-111">If the Survivable Branch Appliance or Survivable Branch Server user fails over to the backup Registrar pool at the central site, the same dial plan will be in effect.</span></span> <span data-ttu-id="8cb83-112">(Weitere Informationen finden Sie unter [Create a Dial Plan in lync Server 2013](lync-server-2013-create-a-dial-plan.md) in der Betriebsdokumentation.)</span><span class="sxs-lookup"><span data-stu-id="8cb83-112">(See [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) in the Operations documentation.)</span></span>

3.  <span data-ttu-id="8cb83-113">Konfigurieren Sie eine VoIP-Route, die vom Survivable Branch Appliance Gateway oder dem Survivable Branch Server externen Gateway das.</span><span class="sxs-lookup"><span data-stu-id="8cb83-113">Configure a voice route that egresses from the Survivable Branch Appliance gateway or the Survivable Branch Server external gateway.</span></span> <span data-ttu-id="8cb83-114">(Weitere Informationen finden Sie unter [Create a Voice Route in lync Server 2013](lync-server-2013-create-a-voice-route.md) in der Betriebsdokumentation.)</span><span class="sxs-lookup"><span data-stu-id="8cb83-114">(See [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md) in the Operations documentation.)</span></span>

4.  <span data-ttu-id="8cb83-115">Legen Sie eine Sicherungs Anrufroute auf dem Survivable Branch Appliance oder Survivable Branch Server Gateway so fest, dass Sie auf den sicherungsregistrierungspool (zusammen mit Vermittlungsserver) am zentralen Standort zeigt.</span><span class="sxs-lookup"><span data-stu-id="8cb83-115">Set a backup call route on the Survivable Branch Appliance or Survivable Branch Server gateway to point to the backup Registrar pool (collocated with Mediation Server) at the central site.</span></span> <span data-ttu-id="8cb83-116">(Weitere Informationen finden Sie in ihrer Survivable Branch Appliance-oder Survivable Branch Server Lieferantendokumentation.)</span><span class="sxs-lookup"><span data-stu-id="8cb83-116">(See your Survivable Branch Appliance or Survivable Branch Server vendor documentation.)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8cb83-117">Durch diese Konfiguration für die Sicherung der Anrufweiterleitung wird sichergestellt, dass eingehende Anrufe an den Zweigstellenbenutzer funktionieren, wenn der Survivable Branch Appliance oder Survivable Branch Server nicht verfügbar ist (beispielsweise wenn er für die Wartung nicht zur Verfügung steht).</span><span class="sxs-lookup"><span data-stu-id="8cb83-117">This backup call route setup helps ensure that inbound calls to the branch user will work when the Survivable Branch Appliance or Survivable Branch Server is not available (for example, if it is down for maintenance).</span></span> <span data-ttu-id="8cb83-118">Wenn die Registrierungsstelle und die Vermittlungsserver im Survivable Branch Appliance oder Survivable Branch Server nicht verfügbar sind und der Benutzer beim sicherungsregistrierungspool am zentralen Standort registriert ist, können eingehende Anrufe weiterhin an den Benutzer weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="8cb83-118">If the Registrar and Mediation Server on the Survivable Branch Appliance or Survivable Branch Server are not available, and the user is registered with the backup Registrar pool at the central site, inbound calls can still be routed to the user.</span></span>

    
    </div>

<span data-ttu-id="8cb83-119">**Nächster Schritt**: [Konfigurieren von Einstellungen für die Umleitung von Voicemail in lync Server 2013](lync-server-2013-configure-voice-mail-rerouting-settings.md)</span><span class="sxs-lookup"><span data-stu-id="8cb83-119">**Next step**: [Configure voice mail rerouting settings in Lync Server 2013](lync-server-2013-configure-voice-mail-rerouting-settings.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

