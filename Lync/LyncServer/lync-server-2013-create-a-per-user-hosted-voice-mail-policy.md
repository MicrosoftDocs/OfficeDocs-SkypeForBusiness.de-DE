---
title: 'Lync Server 2013: Erstellen einer Richtlinie für gehostete Voicemail-Benutzer pro Benutzer'
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
ms.openlocfilehash: 04dc942c0cd44c6390c8a7d6627c5da4b551b94c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501892"
---
# <a name="create-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="72a97-102">Erstellen Sie eine benutzerbasierte Richtlinie für gehostete Voicemail in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72a97-102">Create a per-user hosted voice mail policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72a97-103">_**Letztes Änderungsstand des Themas:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="72a97-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="72a97-104">Eine Richtlinie auf *Benutzerebene* wirkt sich ausschließlich auf einzelne Benutzer, Gruppen und Kontaktobjekte aus.</span><span class="sxs-lookup"><span data-stu-id="72a97-104">A *per-user* policy can only impact individual users, groups, and contact objects.</span></span> <span data-ttu-id="72a97-105">Zum Bereitstellen einer Richtlinie auf Benutzerebene müssen Sie die Richtlinie explizit auf einen oder mehrere Benutzer, Gruppen oder Kontaktobjekte anwenden.</span><span class="sxs-lookup"><span data-stu-id="72a97-105">To deploy a per-user policy, you must explicitly assign the policy to one or more users, groups, or contact objects.</span></span> <span data-ttu-id="72a97-106">Ausführliche Informationen finden Sie unter [assign a User Hosted Voice Mail Policy in lync Server 2013](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md).</span><span class="sxs-lookup"><span data-stu-id="72a97-106">For details, see [Assign a per-user hosted voice mail policy in Lync Server 2013](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md).</span></span>

<span data-ttu-id="72a97-107">Ausführliche Informationen zum Arbeiten mit benutzerseitigen Richtlinien für gehostete Voicemail finden Sie in der lync Server-Verwaltungsshell-Dokumentation für die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="72a97-107">For details about working with per-user hosted voice mail policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="72a97-108">New-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="72a97-108">New-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="72a97-109">Gruppe-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="72a97-109">Set-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="72a97-110">Get-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="72a97-110">Get-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-per-user-hosted-voice-mail-policy"></a><span data-ttu-id="72a97-111">So erstellen Sie eine Richtlinie für gehostete Voicemail auf Benutzerebene</span><span class="sxs-lookup"><span data-stu-id="72a97-111">To create a per-user hosted voice mail policy</span></span>

1.  <span data-ttu-id="72a97-112">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="72a97-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="72a97-p102">Führen Sie das Cmdlet "New-CsHostedVoicemailPolicy" aus, um die Richtlinie zu erstellen.  Führen Sie beispielsweise den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="72a97-p102">Run the New-CsHostedVoicemailPolicy cmdlet to create the policy. For example, run:</span></span>
    
        New-CsHostedVoicemailPolicy -Identity ExRedmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for Redmond users." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    <span data-ttu-id="72a97-115">In diesem Beispiel wird eine Richtlinie für gehostete Voicemail auf Benutzerebene erstellt. Hierbei werden die folgenden Parameter festgelegt:</span><span class="sxs-lookup"><span data-stu-id="72a97-115">The previous example creates a hosted voice mail policy with per-user scope, and sets the following parameters:</span></span>
    
      - <span data-ttu-id="72a97-p103">**Identity** gibt eine eindeutige ID für die Richtlinie an, die den Bereich einschließt. Für eine Richtlinie auf Benutzerebene wird dieser Parameterwert als einfache Zeichenfolge angegeben, z. B. "ExRedmond".</span><span class="sxs-lookup"><span data-stu-id="72a97-p103">**Identity** specifies a unique identifier for the policy, which includes the scope. For a policy with per-user scope, this parameter value is specified as a simple string, for example, ExRedmond.</span></span>
    
      - <span data-ttu-id="72a97-p104">**Destination** gibt den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des gehosteten Exchange UM-Diensts an. Dieser Parameter ist optional. Wenn Sie jedoch versuchen, einen Benutzer für gehostete Voicemail zu aktivieren, und die zugewiesene Richtlinie des Benutzers nicht auf "Destination" festgelegt ist, tritt bei der Aktivierung ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="72a97-p104">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Exchange UM service. This parameter is optional, but if you attempt to enable a user for hosted voice mail and the user’s assigned policy does not have a Destination value, the enable will fail.</span></span>
    
      - <span data-ttu-id="72a97-120">**Description** stellt eine optionale Beschreibung zur Richtlinie bereit.</span><span class="sxs-lookup"><span data-stu-id="72a97-120">**Description** provides optional descriptive information about the policy.</span></span>
    
      - <span data-ttu-id="72a97-121">**Organization** gibt eine durch trennzeichengetrennte Liste der Exchange-Mandanten an, die lync Server 2013 Benutzer zu Hause sind.</span><span class="sxs-lookup"><span data-stu-id="72a97-121">**Organization** specifies a comma-separated list of the Exchange tenants that home Lync Server 2013 users.</span></span> <span data-ttu-id="72a97-122">Für jeden Mandanten muss der vollqualifizierte Domänenname des Mandanten im gehosteten Exchange-Dienst angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="72a97-122">Each tenant must be specified as the FQDN of that tenant on the hosted Exchange UM service.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="72a97-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="72a97-123">See Also</span></span>


[<span data-ttu-id="72a97-124">Zuweisen einer Richtlinie für gehostete Voicemail pro Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72a97-124">Assign a per-user hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

