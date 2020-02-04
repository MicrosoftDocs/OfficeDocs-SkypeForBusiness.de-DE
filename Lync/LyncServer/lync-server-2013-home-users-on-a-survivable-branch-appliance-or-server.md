---
title: 'Lync Server 2013: Verwalten von Benutzern in einer Survivable Branch Appliance oder auf einem Survivable Branch Server'
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
ms.openlocfilehash: 0c6cca9528e884807f6180d8c99b143eb0041211
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739135"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="home-users-on-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a><span data-ttu-id="f2387-102">Verwalten von Benutzern in einer Survivable Branch Appliance oder auf einem Survivable Branch Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2387-102">Home users on a Survivable Branch Appliance or Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2387-103">_**Letztes Änderungsdatum des Themas:** 2014-12-10_</span><span class="sxs-lookup"><span data-stu-id="f2387-103">_**Topic Last Modified:** 2014-12-10_</span></span>

<span data-ttu-id="f2387-104">Der Vorgang zum Durchführen von Benutzern auf einer überlebensfähigen Branch-Appliance oder einem Überlebenden Verzweigungs Server ähnelt dem Verfahren zum Durchführen von Benutzern in einem Front-End-Pool.</span><span class="sxs-lookup"><span data-stu-id="f2387-104">The process of homing users on a Survivable Branch Appliance or a Survivable Branch Server is similar to the process of homing users on a Front End pool.</span></span> <span data-ttu-id="f2387-105">Führen Sie das Survivable Branch Appliance-oder Survivable Branch Server-Verfahren am zentralen Standort aus.</span><span class="sxs-lookup"><span data-stu-id="f2387-105">Perform the Survivable Branch Appliance or Survivable Branch Server procedure at the central site.</span></span>

<div>

## <a name="to-home-users-on-survivable-branch-appliance-or-survivable-branch-server"></a><span data-ttu-id="f2387-106">Für private Benutzer auf Survivable Branch Appliance oder Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="f2387-106">To home users on Survivable Branch Appliance or Survivable Branch Server</span></span>

1.  <span data-ttu-id="f2387-107">Öffnen Sie die lync Server-Verwaltungsshell, bevor Sie Benutzer auf den Überlebenden Verzweigungs Server oder Überlebenden Verzweigungs Server verschieben, und führen Sie dann die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="f2387-107">Before moving users to the Survivable Branch Server or Survivable Branch Server, open the Lync Server Management Shell, and then do all of the following:</span></span>
    
      - <span data-ttu-id="f2387-108">Führen Sie das Cmdlet **Test-CsPstnOutboundCall** aus, um zu überprüfen, ob der überlebensfähige Verzweigungs Server ausgeführt wird und ob die PSTN-Konnektivität (Public Switched Telephone Network) konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="f2387-108">Run the cmdlet **Test-CsPstnOutboundCall** to verify that the Survivable Branch Server is running and that the public switched telephone network (PSTN) connectivity is configured.</span></span> <span data-ttu-id="f2387-109">Wenn Sie die Eigenschaften des PSTN-Gateways ändern müssen, verwenden Sie das Cmdlet **Satz-CsPstnGateway**.</span><span class="sxs-lookup"><span data-stu-id="f2387-109">If you need to modify PSTN gateway properties, use the cmdlet **Set-CsPstnGateway**.</span></span>
    
      - <span data-ttu-id="f2387-110">Führen Sie das Cmdlet **Get-CsVoicePolicy** aus, um zu überprüfen, ob die Benutzer, die auf dem Überlebenden Verzweigungs Server verwaltet werden, über die entsprechende VoIP-Routing Richtlinie verfügen.</span><span class="sxs-lookup"><span data-stu-id="f2387-110">Run the cmdlet **Get-CsVoicePolicy** to verify that the users who will be homed on the Survivable Branch Server have the appropriate VoIP routing policy.</span></span> <span data-ttu-id="f2387-111">Wenn Sie die VoIP-Richtlinie ändern müssen, verwenden Sie das Cmdlet **Satz-CsVoicePolicy**.</span><span class="sxs-lookup"><span data-stu-id="f2387-111">If you need to modify the VoIP policy, use the cmdlet **Set-CsVoicePolicy**.</span></span>
    
      - <span data-ttu-id="f2387-112">Führen Sie das Cmdlet **Get-CsVoicemailReroutingConfiguration** aus, um zu überprüfen, ob die Einstellungen für Voicemail-Umleitungen konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="f2387-112">Run the cmdlet **Get-CsVoicemailReroutingConfiguration** to verify that the voice mail rerouting settings are configured.</span></span> <span data-ttu-id="f2387-113">Wenn Sie die Einstellungen für das Ändern der Voicemail-Einstellungen ändern müssen, verwenden Sie das Cmdlet **-Cmdlet-Satz-CsVoicemailReroutingConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="f2387-113">If you need to modify the voice mail rerouting settings, use the cmdlet **Set-CsVoicemailReroutingConfiguration**.</span></span>

2.  <span data-ttu-id="f2387-114">Führen Sie in der lync Server-Verwaltungsshell das Cmdlet **Move-CsUser** aus, um private Benutzer zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="f2387-114">In the Lync Server Management Shell, run the cmdlet **Move-CsUser** to move home users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f2387-115">Sie können auch die lync Server-Systemsteuerung verwenden, um Voraussetzungen und private Benutzer zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="f2387-115">You can also use Lync Server Control Panel to verify prerequisites and home users.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="f2387-116">Benutzer, die sich in einer Überlebenden lync Server-Branch-Appliance befinden, können keine neuen Chatrooms erstellen oder die raumkarte für vorhandene Räume anzeigen.</span><span class="sxs-lookup"><span data-stu-id="f2387-116">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new chat rooms or view the room card for existing rooms.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f2387-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f2387-117">See Also</span></span>


[<span data-ttu-id="f2387-118">Test-CsPstnOutboundCall</span><span class="sxs-lookup"><span data-stu-id="f2387-118">Test-CsPstnOutboundCall</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall)  
[<span data-ttu-id="f2387-119">Get-CsVoicePolicy</span><span class="sxs-lookup"><span data-stu-id="f2387-119">Get-CsVoicePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[<span data-ttu-id="f2387-120">Get-CsVoicemailReroutingConfiguration</span><span class="sxs-lookup"><span data-stu-id="f2387-120">Get-CsVoicemailReroutingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicemailReroutingConfiguration)  
[<span data-ttu-id="f2387-121">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="f2387-121">Move-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Move-CsUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

