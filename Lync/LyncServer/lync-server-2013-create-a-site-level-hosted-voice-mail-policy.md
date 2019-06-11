---
title: 'Lync Server 2013: Erstellen einer Hosted Voicemail-Richtlinie auf Websiteebene'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a site-level hosted voice mail policy
ms:assetid: 145892c8-a6ca-45fb-9e83-786f709dd775
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398216(v=OCS.15)
ms:contentKeyID: 48183481
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9df91e28eeba8bc9769e4fcbeff6ebba2b3746d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839076"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-site-level-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="a3fa6-102">Erstellen einer gehosteten Voicemail-Richtlinie auf Websiteebene in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a3fa6-102">Create a site-level hosted voice mail policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a3fa6-103">_**Letztes Änderungsdatum des Themas:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="a3fa6-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="a3fa6-104">Eine *Website* Richtlinie kann sich auf alle Benutzer auswirken, die sich auf der Website befinden, für die die Richtlinie definiert ist.</span><span class="sxs-lookup"><span data-stu-id="a3fa6-104">A *site* policy can impact all users that are homed on the site for which the policy is defined.</span></span> <span data-ttu-id="a3fa6-105">Wenn ein Benutzer für den gehosteten Exchange um-Zugriff konfiguriert ist und keiner Richtlinie pro Benutzer zugewiesen wurde, gilt die Website Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="a3fa6-105">If a user is configured for hosted Exchange UM access and has not been assigned a Per-user policy, the site policy applies.</span></span> <span data-ttu-id="a3fa6-106">Wenn Sie keine Website Richtlinie bereitgestellt haben, gilt die globale Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="a3fa6-106">If you have not deployed a site policy, the global policy applies.</span></span>

<span data-ttu-id="a3fa6-107">Details zum Konfigurieren von Website Richtlinien finden Sie in der Dokumentation zur lync Server-Verwaltungsshell für die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="a3fa6-107">For details about configuring site policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="a3fa6-108">Neu – CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="a3fa6-108">New-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="a3fa6-109">Satz-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="a3fa6-109">Set-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="a3fa6-110">Get-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="a3fa6-110">Get-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-site-hosted-voice-mail-policy"></a><span data-ttu-id="a3fa6-111">So erstellen Sie eine von der Website gehostete Voicemail-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="a3fa6-111">To create a site hosted voice mail policy</span></span>

1.  <span data-ttu-id="a3fa6-112">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="a3fa6-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="a3fa6-113">Führen Sie das Cmdlet New-CsHostedVoicemailPolicy aus, um die Richtlinie zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a3fa6-113">Run the New-CsHostedVoicemailPolicy cmdlet to create the policy.</span></span> <span data-ttu-id="a3fa6-114">Führen Sie beispielsweise den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="a3fa6-114">For example, run:</span></span>
    
        New-CsHostedVoicemailPolicy -Identity site:Redmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for the Redmond site." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    <span data-ttu-id="a3fa6-115">In diesem Beispiel wird eine gehostete Voicemail-Richtlinie mit Website Bereich erstellt, und die folgenden Parameter werden festgelegt:</span><span class="sxs-lookup"><span data-stu-id="a3fa6-115">This example creates a hosted voice mail policy with site scope, and sets the following parameters:</span></span>
    
      - <span data-ttu-id="a3fa6-116">**Identity** gibt einen eindeutigen Bezeichner für die Richtlinie an, der den Bereich umfasst.</span><span class="sxs-lookup"><span data-stu-id="a3fa6-116">**Identity** specifies a unique identifier for the policy, which includes the scope.</span></span> <span data-ttu-id="a3fa6-117">Bei einer Richtlinie mit Website Bereich muss der Parameterwert Identity im Format `site:` \* \<Namen\>\* angegeben werden, beispielsweise. `site:Redmond`</span><span class="sxs-lookup"><span data-stu-id="a3fa6-117">For a policy with site scope, the Identity parameter value must be specified in the format `site:`*\<name\>*, for example, `site:Redmond`.</span></span>
    
      - <span data-ttu-id="a3fa6-118">**Ziel** gibt den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des gehosteten Exchange um-Diensts an.</span><span class="sxs-lookup"><span data-stu-id="a3fa6-118">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Exchange UM service.</span></span> <span data-ttu-id="a3fa6-119">Dieser Parameter ist optional, aber wenn Sie versuchen, einen Benutzer für gehostete Voicemail zu aktivieren, und die zugewiesene Richtlinie des Benutzers keinen Zielwert hat, schlägt die Aktivierung fehl.</span><span class="sxs-lookup"><span data-stu-id="a3fa6-119">This parameter is optional, but if you attempt to enable a user for hosted voice mail and the user’s assigned policy does not have a Destination value, the enable will fail.</span></span>
    
      - <span data-ttu-id="a3fa6-120">**Beschreibung** enthält optionale beschreibende Informationen zur Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="a3fa6-120">**Description** provides optional descriptive information about the policy.</span></span>
    
      - <span data-ttu-id="a3fa6-121">**Organisation** gibt eine durch trennzeichengetrennte Liste der Exchange-Mandanten an, die lync Server 2013-Benutzer sind.</span><span class="sxs-lookup"><span data-stu-id="a3fa6-121">**Organization** specifies a comma-separated list of the Exchange tenants that home Lync Server 2013 users.</span></span> <span data-ttu-id="a3fa6-122">Jeder Mandant muss als FQDN dieses Mandanten für den gehosteten Exchange um-Dienst angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="a3fa6-122">Each tenant must be specified as the FQDN of that tenant on the hosted Exchange UM service.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

