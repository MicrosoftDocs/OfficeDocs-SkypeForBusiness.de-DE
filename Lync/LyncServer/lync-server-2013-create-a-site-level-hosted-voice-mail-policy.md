---
title: 'Lync Server 2013: Erstellen einer Hosted Voice Mail-Richtlinie auf Standortebene'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a site-level hosted voice mail policy
ms:assetid: 145892c8-a6ca-45fb-9e83-786f709dd775
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398216(v=OCS.15)
ms:contentKeyID: 48183481
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b103369591846cc49b2c676a90103675fe09baec
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034867"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-site-level-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="08cfa-102">Erstellen einer Hosted Voice Mail-Richtlinie auf Standortebene in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="08cfa-102">Create a site-level hosted voice mail policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="08cfa-103">_**Letztes Änderungsstand des Themas:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="08cfa-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="08cfa-p101">Eine *Standortrichtlinie* kann sich auf alle Benutzer auswirken, die an dem Standort verwaltet werden, für den die Richtlinie definiert wurde. Wenn ein Benutzer für den Zugriff auf gehostete Exchange UM-Dienste konfiguriert ist, ihm jedoch keine Benutzerrichtlinie zugewiesen wurde, findet die Standortrichtlinie Anwendung. Wenn Sie keine Standortrichtlinie bereitgestellt haben, wird die globale Richtlinie angewendet.</span><span class="sxs-lookup"><span data-stu-id="08cfa-p101">A *site* policy can impact all users that are homed on the site for which the policy is defined. If a user is configured for hosted Exchange UM access and has not been assigned a Per-user policy, the site policy applies. If you have not deployed a site policy, the global policy applies.</span></span>

<span data-ttu-id="08cfa-107">Ausführliche Informationen zum Konfigurieren von Website Richtlinien finden Sie in der lync Server-Verwaltungsshell Dokumentation für die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="08cfa-107">For details about configuring site policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="08cfa-108">New-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="08cfa-108">New-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="08cfa-109">Gruppe-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="08cfa-109">Set-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="08cfa-110">Get-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="08cfa-110">Get-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-site-hosted-voice-mail-policy"></a><span data-ttu-id="08cfa-111">So erstellen Sie eine Standortrichtlinie für gehostete Voicemail</span><span class="sxs-lookup"><span data-stu-id="08cfa-111">To create a site hosted voice mail policy</span></span>

1.  <span data-ttu-id="08cfa-112">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="08cfa-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="08cfa-p102">Führen Sie das Cmdlet "New-CsHostedVoicemailPolicy" aus, um die Richtlinie zu erstellen.  Führen Sie beispielsweise den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="08cfa-p102">Run the New-CsHostedVoicemailPolicy cmdlet to create the policy. For example, run:</span></span>
    
        New-CsHostedVoicemailPolicy -Identity site:Redmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for the Redmond site." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    <span data-ttu-id="08cfa-115">In diesem Beispiel wird eine Richtlinie für gehostete Voicemail auf Standortebene erstellt. Hierbei werden die folgenden Parameter festgelegt:</span><span class="sxs-lookup"><span data-stu-id="08cfa-115">This example creates a hosted voice mail policy with site scope, and sets the following parameters:</span></span>
    
      - <span data-ttu-id="08cfa-116">**Identity** gibt eine eindeutige ID für die Richtlinie an, die den Bereich einschließt.</span><span class="sxs-lookup"><span data-stu-id="08cfa-116">**Identity** specifies a unique identifier for the policy, which includes the scope.</span></span> <span data-ttu-id="08cfa-117">Für eine Richtlinie mit Website Bereich muss der Wert des Identity-Parameters im `site:` \* \<Format\>Namen\*angegeben werden, `site:Redmond`beispielsweise.</span><span class="sxs-lookup"><span data-stu-id="08cfa-117">For a policy with site scope, the Identity parameter value must be specified in the format `site:`*\<name\>*, for example, `site:Redmond`.</span></span>
    
      - <span data-ttu-id="08cfa-p104">**Destination** gibt den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des gehosteten Exchange UM-Diensts an. Dieser Parameter ist optional. Wenn Sie jedoch versuchen, einen Benutzer für gehostete Voicemail zu aktivieren, und die zugewiesene Richtlinie des Benutzers nicht auf "Destination" festgelegt ist, tritt bei der Aktivierung ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="08cfa-p104">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Exchange UM service. This parameter is optional, but if you attempt to enable a user for hosted voice mail and the user’s assigned policy does not have a Destination value, the enable will fail.</span></span>
    
      - <span data-ttu-id="08cfa-120">**Description** stellt eine optionale Beschreibung zur Richtlinie bereit.</span><span class="sxs-lookup"><span data-stu-id="08cfa-120">**Description** provides optional descriptive information about the policy.</span></span>
    
      - <span data-ttu-id="08cfa-121">**Organization** gibt eine durch trennzeichengetrennte Liste der Exchange-Mandanten an, die lync Server 2013 Benutzer zu Hause sind.</span><span class="sxs-lookup"><span data-stu-id="08cfa-121">**Organization** specifies a comma-separated list of the Exchange tenants that home Lync Server 2013 users.</span></span> <span data-ttu-id="08cfa-122">Für jeden Mandanten muss der vollqualifizierte Domänenname des Mandanten im gehosteten Exchange-Dienst angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="08cfa-122">Each tenant must be specified as the FQDN of that tenant on the hosted Exchange UM service.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

