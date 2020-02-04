---
title: 'Lync Server 2013: Erstellen einer pro Benutzer gehosteten Voicemail-Richtlinie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a per-user hosted voice mail policy
ms:assetid: 39018a7c-e0c3-46a2-be4e-05604ec67a50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425867(v=OCS.15)
ms:contentKeyID: 48183902
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 535515fd11c0cb736b5b6fb4b70d041ea3af8a3c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740375"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="a1846-102">Erstellen einer pro Benutzer gehosteten Voicemail-Richtlinie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1846-102">Create a per-user hosted voice mail policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a1846-103">_**Letztes Änderungsdatum des Themas:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="a1846-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="a1846-104">Eine Richtlinie *pro Benutzer* kann nur Auswirkungen auf einzelne Benutzer, Gruppen und Kontaktobjekte haben.</span><span class="sxs-lookup"><span data-stu-id="a1846-104">A *per-user* policy can only impact individual users, groups, and contact objects.</span></span> <span data-ttu-id="a1846-105">Wenn Sie eine Richtlinie pro Benutzer bereitstellen möchten, müssen Sie die Richtlinie explizit einem oder mehreren Benutzern, Gruppen oder Kontaktobjekten zuweisen.</span><span class="sxs-lookup"><span data-stu-id="a1846-105">To deploy a per-user policy, you must explicitly assign the policy to one or more users, groups, or contact objects.</span></span> <span data-ttu-id="a1846-106">Ausführliche Informationen finden Sie unter [Zuweisen einer pro Benutzer gehosteten Voicemail-Richtlinie in lync Server 2013](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md).</span><span class="sxs-lookup"><span data-stu-id="a1846-106">For details, see [Assign a per-user hosted voice mail policy in Lync Server 2013](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md).</span></span>

<span data-ttu-id="a1846-107">Ausführliche Informationen zum Arbeiten mit Richtlinien für gehostete Voicemail pro Benutzer finden Sie in der Dokumentation zur lync Server-Verwaltungsshell für die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="a1846-107">For details about working with per-user hosted voice mail policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="a1846-108">Neu – CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="a1846-108">New-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="a1846-109">Satz-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="a1846-109">Set-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="a1846-110">Get-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="a1846-110">Get-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-per-user-hosted-voice-mail-policy"></a><span data-ttu-id="a1846-111">So erstellen Sie eine pro Benutzer gehostete Voicemail-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="a1846-111">To create a per-user hosted voice mail policy</span></span>

1.  <span data-ttu-id="a1846-112">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="a1846-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="a1846-113">Führen Sie das Cmdlet New-CsHostedVoicemailPolicy aus, um die Richtlinie zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a1846-113">Run the New-CsHostedVoicemailPolicy cmdlet to create the policy.</span></span> <span data-ttu-id="a1846-114">Führen Sie beispielsweise den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="a1846-114">For example, run:</span></span>
    
        New-CsHostedVoicemailPolicy -Identity ExRedmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for Redmond users." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    <span data-ttu-id="a1846-115">Im vorherigen Beispiel wird eine gehostete Voicemail-Richtlinie mit benutzerspezifischem Bereich erstellt, und die folgenden Parameter werden festgelegt:</span><span class="sxs-lookup"><span data-stu-id="a1846-115">The previous example creates a hosted voice mail policy with per-user scope, and sets the following parameters:</span></span>
    
      - <span data-ttu-id="a1846-116">**Identity** gibt einen eindeutigen Bezeichner für die Richtlinie an, der den Bereich umfasst.</span><span class="sxs-lookup"><span data-stu-id="a1846-116">**Identity** specifies a unique identifier for the policy, which includes the scope.</span></span> <span data-ttu-id="a1846-117">Bei einer Richtlinie mit benutzerspezifischem Gültigkeitsbereich wird dieser Parameterwert als einfache Zeichenfolge angegeben, beispielsweise "" "," "".</span><span class="sxs-lookup"><span data-stu-id="a1846-117">For a policy with per-user scope, this parameter value is specified as a simple string, for example, ExRedmond.</span></span>
    
      - <span data-ttu-id="a1846-118">**Ziel** gibt den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des gehosteten Exchange um-Diensts an.</span><span class="sxs-lookup"><span data-stu-id="a1846-118">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Exchange UM service.</span></span> <span data-ttu-id="a1846-119">Dieser Parameter ist optional, aber wenn Sie versuchen, einen Benutzer für gehostete Voicemail zu aktivieren, und die zugewiesene Richtlinie des Benutzers keinen Zielwert hat, schlägt die Aktivierung fehl.</span><span class="sxs-lookup"><span data-stu-id="a1846-119">This parameter is optional, but if you attempt to enable a user for hosted voice mail and the user’s assigned policy does not have a Destination value, the enable will fail.</span></span>
    
      - <span data-ttu-id="a1846-120">**Beschreibung** enthält optionale beschreibende Informationen zur Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="a1846-120">**Description** provides optional descriptive information about the policy.</span></span>
    
      - <span data-ttu-id="a1846-121">**Organisation** gibt eine durch trennzeichengetrennte Liste der Exchange-Mandanten an, die lync Server 2013-Benutzer sind.</span><span class="sxs-lookup"><span data-stu-id="a1846-121">**Organization** specifies a comma-separated list of the Exchange tenants that home Lync Server 2013 users.</span></span> <span data-ttu-id="a1846-122">Jeder Mandant muss als FQDN dieses Mandanten für den gehosteten Exchange um-Dienst angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="a1846-122">Each tenant must be specified as the FQDN of that tenant on the hosted Exchange UM service.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a1846-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a1846-123">See Also</span></span>


[<span data-ttu-id="a1846-124">Zuweisen einer pro Benutzer gehosteten Voicemail-Richtlinie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1846-124">Assign a per-user hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

