---
title: 'Lync Server 2013: Privatbenutzer auf einem Survivable Branch Appliance oder Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Home users on a Survivable Branch Appliance or Server
ms:assetid: faf1ebb9-6d7d-4a58-8ff7-801b7b31d3ba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413066(v=OCS.15)
ms:contentKeyID: 48185926
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: add711ca547648a6071a22fee6a0bcd0eeb0f6c0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528202"
---
# <a name="home-users-on-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a><span data-ttu-id="51318-102">Privatbenutzer auf einem Survivable Branch Appliance oder Server in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51318-102">Home users on a Survivable Branch Appliance or Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="51318-103">_**Letztes Änderungsstand des Themas:** 2014-12-10_</span><span class="sxs-lookup"><span data-stu-id="51318-103">_**Topic Last Modified:** 2014-12-10_</span></span>

<span data-ttu-id="51318-104">Der Vorgang des Benutzer Verweises auf einem Survivable Branch Appliance oder einem Survivable Branch Server ähnelt dem Verfahren, bei dem Benutzer auf eine Front-End-Pool gereferenzt werden.</span><span class="sxs-lookup"><span data-stu-id="51318-104">The process of homing users on a Survivable Branch Appliance or a Survivable Branch Server is similar to the process of homing users on a Front End pool.</span></span> <span data-ttu-id="51318-105">Führen Sie die Survivable Branch Appliance-oder Survivable Branch Server-Prozedur am zentralen Standort aus.</span><span class="sxs-lookup"><span data-stu-id="51318-105">Perform the Survivable Branch Appliance or Survivable Branch Server procedure at the central site.</span></span>

<div>

## <a name="to-home-users-on-survivable-branch-appliance-or-survivable-branch-server"></a><span data-ttu-id="51318-106">Für Privatbenutzer auf Survivable Branch Appliance oder Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="51318-106">To home users on Survivable Branch Appliance or Survivable Branch Server</span></span>

1.  <span data-ttu-id="51318-107">Bevor Sie Benutzer in die Survivable Branch Server oder Survivable Branch Server verschieben, öffnen Sie die lync Server-Verwaltungsshell, und führen Sie dann die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="51318-107">Before moving users to the Survivable Branch Server or Survivable Branch Server, open the Lync Server Management Shell, and then do all of the following:</span></span>
    
      - <span data-ttu-id="51318-108">Führen Sie das Cmdlet **Test-CsPstnOutboundCall** aus, um sicherzustellen, dass die Survivable Branch Server ausgeführt wird und dass die PSTN-Konnektivität (Public Switched Telephone Network) konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="51318-108">Run the cmdlet **Test-CsPstnOutboundCall** to verify that the Survivable Branch Server is running and that the public switched telephone network (PSTN) connectivity is configured.</span></span> <span data-ttu-id="51318-109">Wenn Sie die Eigenschaften des PSTN-Gateways ändern müssen, verwenden Sie das Cmdlet " **CsPstnGateway**".</span><span class="sxs-lookup"><span data-stu-id="51318-109">If you need to modify PSTN gateway properties, use the cmdlet **Set-CsPstnGateway**.</span></span>
    
      - <span data-ttu-id="51318-110">Führen Sie das Cmdlet **Get-CsVoicePolicy** aus, um sicherzustellen, dass die Benutzer, die im Survivable Branch Server verwaltet werden, über die entsprechende VoIP-Routing Richtlinie verfügen.</span><span class="sxs-lookup"><span data-stu-id="51318-110">Run the cmdlet **Get-CsVoicePolicy** to verify that the users who will be homed on the Survivable Branch Server have the appropriate VoIP routing policy.</span></span> <span data-ttu-id="51318-111">Wenn Sie die VoIP-Richtlinie ändern müssen, verwenden Sie das Cmdlet " **CsVoicePolicy**".</span><span class="sxs-lookup"><span data-stu-id="51318-111">If you need to modify the VoIP policy, use the cmdlet **Set-CsVoicePolicy**.</span></span>
    
      - <span data-ttu-id="51318-112">Führen Sie das Cmdlet **Get-CsVoicemailReroutingConfiguration** aus, um zu überprüfen, ob die Einstellungen für das Umleiten von Voicemail konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="51318-112">Run the cmdlet **Get-CsVoicemailReroutingConfiguration** to verify that the voice mail rerouting settings are configured.</span></span> <span data-ttu-id="51318-113">Wenn Sie die Einstellungen für das Umleiten von Voicemail ändern müssen, verwenden Sie das Cmdlet " **CsVoicemailReroutingConfiguration**".</span><span class="sxs-lookup"><span data-stu-id="51318-113">If you need to modify the voice mail rerouting settings, use the cmdlet **Set-CsVoicemailReroutingConfiguration**.</span></span>

2.  <span data-ttu-id="51318-114">Führen Sie im lync Server-Verwaltungsshell das Cmdlet " **CsUser** " aus, um Benutzer von Privatbenutzern zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="51318-114">In the Lync Server Management Shell, run the cmdlet **Move-CsUser** to move home users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="51318-115">Sie können auch lync Server-Systemsteuerung verwenden, um Voraussetzungen und private Benutzer zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="51318-115">You can also use Lync Server Control Panel to verify prerequisites and home users.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="51318-116">Benutzer, die in einer lync Server Survivable Branch Appliance verwaltet werden, können keine neuen Chatrooms erstellen oder die raumkarte für vorhandene Räume anzeigen.</span><span class="sxs-lookup"><span data-stu-id="51318-116">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new chat rooms or view the room card for existing rooms.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="51318-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="51318-117">See Also</span></span>


[<span data-ttu-id="51318-118">Test-CsPstnOutboundCall</span><span class="sxs-lookup"><span data-stu-id="51318-118">Test-CsPstnOutboundCall</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall)  
[<span data-ttu-id="51318-119">Get-CsVoicePolicy</span><span class="sxs-lookup"><span data-stu-id="51318-119">Get-CsVoicePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[<span data-ttu-id="51318-120">Get-CsVoicemailReroutingConfiguration</span><span class="sxs-lookup"><span data-stu-id="51318-120">Get-CsVoicemailReroutingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicemailReroutingConfiguration)  
[<span data-ttu-id="51318-121">CsUser</span><span class="sxs-lookup"><span data-stu-id="51318-121">Move-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Move-CsUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

