---
title: 'Lync Server 2013: Zuweisen von Richtlinien zu einem Telefon im öffentlichen Bereich'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign policies to a common area phone
ms:assetid: f0554fd1-b237-49b3-9eb4-26f4b91f5604
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994082(v=OCS.15)
ms:contentKeyID: 51803993
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6dfe908f2bb4ca66714d3eef756a0c53c7334fd7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030068"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-policies-in-lync-server-2013-to-a-common-area-phone"></a><span data-ttu-id="224a2-102">Zuweisen von Richtlinien in lync Server 2013 zu einem Telefon im öffentlichen Bereich</span><span class="sxs-lookup"><span data-stu-id="224a2-102">Assign policies in Lync Server 2013 to a common area phone</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="224a2-103">_**Letztes Änderungsstand des Themas:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="224a2-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="224a2-104">Nachdem Sie Ihre Richtlinie für Telefone für gemeinsame Bereiche erstellt haben (Weitere Informationen finden Sie unter [Erstellen einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)), können Sie die Richtlinie mithilfe von Windows PowerShell und dem entsprechenden **Grant-CS-** Cmdlet einem Telefon im öffentlichen Bereich zuweisen.</span><span class="sxs-lookup"><span data-stu-id="224a2-104">After you create your policy for common area phones (for details, see [Create a voice policy and configure PSTN usage records in Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)), you can assign the policy to a common area phone by using Windows PowerShell and the appropriate **Grant-Cs** cmdlet.</span></span> <span data-ttu-id="224a2-105">Diese Cmdlets können entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="224a2-105">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="224a2-106">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="224a2-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="assigning-a-policy-to-a-single-common-area-phone"></a><span data-ttu-id="224a2-107">Zuweisen einer Richtlinie zu einem einzelnen Telefon im öffentlichen Bereich</span><span class="sxs-lookup"><span data-stu-id="224a2-107">Assigning a Policy to a Single Common Area Phone</span></span>

  - <span data-ttu-id="224a2-108">Mit dem folgenden Befehl wird die benutzerspezifische VoIP-Richtlinie RedmondVoice dem Telefon für öffentliche Bereiche zugewiesen, das über die Lobby "Identity Building 14" verfügt.</span><span class="sxs-lookup"><span data-stu-id="224a2-108">The following command assigns the per-user voice policy RedmondVoice to the common area phone that has the Identity Building 14 Lobby.</span></span>
    
        Grant-CsVoicePolicy -Identity "Building 14 Lobby" -PolicyName "RedmondVoicePolicy"

</div>

<div>

## <a name="assigning-a-policy-to-multiple-common-area-phones"></a><span data-ttu-id="224a2-109">Zuweisen einer Richtlinie zu mehreren Telefonen für gemeinsame Bereiche</span><span class="sxs-lookup"><span data-stu-id="224a2-109">Assigning a Policy to Multiple Common Area Phones</span></span>

  - <span data-ttu-id="224a2-110">In diesem Beispiel wird die benutzerspezifische VoIP-Richtlinie RedmondVoice allen für die Verwendung in der Organisation konfigurierten Telefonen für gemeinsame Bereiche zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="224a2-110">In this example, the per-user voice policy RedmondVoice is assigned to all the common area phones configured for use in the organization.</span></span>
    
        Get-CsCommonAreaPhone | Grant-CsVoicePolicy  -PolicyName "RedmondVoicePolicy"

</div>

<span data-ttu-id="224a2-111">Ausführliche Informationen finden Sie in den Hilfethemen für das [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsVoicePolicy).</span><span class="sxs-lookup"><span data-stu-id="224a2-111">For details, see the Help topics for the [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsVoicePolicy).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="224a2-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="224a2-112">See Also</span></span>


[<span data-ttu-id="224a2-113">Get-CsCommonAreaPhone</span><span class="sxs-lookup"><span data-stu-id="224a2-113">Get-CsCommonAreaPhone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

