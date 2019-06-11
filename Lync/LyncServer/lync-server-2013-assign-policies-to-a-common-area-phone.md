---
title: 'Lync Server 2013: Zuweisen von Richtlinien zu einem öffentlichen Bereich-Telefon'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign policies to a common area phone
ms:assetid: f0554fd1-b237-49b3-9eb4-26f4b91f5604
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994082(v=OCS.15)
ms:contentKeyID: 51803993
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b792d6ae14ee13fd1d95761d2a0d6b0af7bbdfae
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847854"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-policies-in-lync-server-2013-to-a-common-area-phone"></a><span data-ttu-id="3a970-102">Zuweisen von Richtlinien in lync Server 2013 zu einem Telefon im öffentlichen Bereich</span><span class="sxs-lookup"><span data-stu-id="3a970-102">Assign policies in Lync Server 2013 to a common area phone</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3a970-103">_**Letztes Änderungsdatum des Themas:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="3a970-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="3a970-104">Nachdem Sie Ihre Richtlinie für Telefone im öffentlichen Bereich erstellt haben (Details finden Sie unter [Erstellen einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)), können Sie die Richtlinie einem öffentlichen Bereich-Telefon mithilfe von Windows PowerShell und dem entsprechenden \*\*Grant-CS zuweisen. \*\*-Cmdlet aus.</span><span class="sxs-lookup"><span data-stu-id="3a970-104">After you create your policy for common area phones (for details, see [Create a voice policy and configure PSTN usage records in Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)), you can assign the policy to a common area phone by using Windows PowerShell and the appropriate **Grant-Cs** cmdlet.</span></span> <span data-ttu-id="3a970-105">Diese Cmdlets können entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="3a970-105">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="3a970-106">Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="3a970-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="assigning-a-policy-to-a-single-common-area-phone"></a><span data-ttu-id="3a970-107">Zuweisen einer Richtlinie zu einem einzelnen Telefon im öffentlichen Bereich</span><span class="sxs-lookup"><span data-stu-id="3a970-107">Assigning a Policy to a Single Common Area Phone</span></span>

  - <span data-ttu-id="3a970-108">Mit dem folgenden Befehl wird die Richtlinie für die benutzerspezifische VoIP-RedmondVoice dem öffentlichen Bereichs Telefon zugewiesen, in dem sich das Identity Building 14-Foyer befindet.</span><span class="sxs-lookup"><span data-stu-id="3a970-108">The following command assigns the per-user voice policy RedmondVoice to the common area phone that has the Identity Building 14 Lobby.</span></span>
    
        Grant-CsVoicePolicy -Identity "Building 14 Lobby" -PolicyName "RedmondVoicePolicy"

</div>

<div>

## <a name="assigning-a-policy-to-multiple-common-area-phones"></a><span data-ttu-id="3a970-109">Zuweisen einer Richtlinie zu mehreren Telefonen im öffentlichen Bereich</span><span class="sxs-lookup"><span data-stu-id="3a970-109">Assigning a Policy to Multiple Common Area Phones</span></span>

  - <span data-ttu-id="3a970-110">In diesem Beispiel wird die benutzerspezifische VoIP-Richtlinien RedmondVoice allen für die Verwendung in der Organisation konfigurierten Telefonen für den öffentlichen Bereich zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="3a970-110">In this example, the per-user voice policy RedmondVoice is assigned to all the common area phones configured for use in the organization.</span></span>
    
        Get-CsCommonAreaPhone | Grant-CsVoicePolicy  -PolicyName "RedmondVoicePolicy"

</div>

<span data-ttu-id="3a970-111">Ausführliche Informationen finden Sie in den Hilfethemen zu [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsVoicePolicy).</span><span class="sxs-lookup"><span data-stu-id="3a970-111">For details, see the Help topics for the [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsVoicePolicy).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3a970-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3a970-112">See Also</span></span>


[<span data-ttu-id="3a970-113">Get-CsCommonAreaPhone</span><span class="sxs-lookup"><span data-stu-id="3a970-113">Get-CsCommonAreaPhone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

