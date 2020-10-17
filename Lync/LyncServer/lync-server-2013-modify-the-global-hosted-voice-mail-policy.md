---
title: 'Lync Server 2013: Ändern der Global Hosted Voice Mail-Richtlinie'
description: 'Lync Server 2013: Ändern Sie die Global Hosted Voice Mail-Richtlinie.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify the global hosted voice mail policy
ms:assetid: f059b3ce-a7d8-4ea9-b10b-0052222ec2ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412994(v=OCS.15)
ms:contentKeyID: 48185757
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9cd5e16c78049ce79abd936a79b2025a14e45943
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566861"
---
# <a name="modify-the-global-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="c0661-103">Ändern der Global Hosted Voice Mail-Richtlinie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c0661-103">Modify the global hosted voice mail policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0661-104">_**Letztes Änderungsstand des Themas:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="c0661-104">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="c0661-105">Die *Global* Hosted Voice Mail-Richtlinie wird mit lync Server 2013 installiert.</span><span class="sxs-lookup"><span data-stu-id="c0661-105">The *global* hosted voice mail policy is installed with Lync Server 2013.</span></span> <span data-ttu-id="c0661-106">Sie können diese Richtlinie Ihren Anforderungen entsprechend ändern, Sie können sie jedoch weder umbenennen noch löschen.</span><span class="sxs-lookup"><span data-stu-id="c0661-106">You can modify it to meet your needs, but you cannot rename or delete it.</span></span> <span data-ttu-id="c0661-107">Wenn Sie die globale Richtlinie ändern möchten, verwenden Sie das Cmdlet "Set-CsHostedVoicemailPolicy", um die Parameter auf die für Ihre spezielle Bereitstellung geeigneten Werte zu setzen.</span><span class="sxs-lookup"><span data-stu-id="c0661-107">To modify the global policy, you use the Set-CsHostedVoicemailPolicy cmdlet to set the parameters to appropriate values for your specific deployment.</span></span>

<span data-ttu-id="c0661-108">Ausführliche Informationen zum Cmdlet " [CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy) " finden Sie in der Dokumentation zum lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="c0661-108">For details about the [Set-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy) cmdlet, see the Lync Server Management Shell documentation.</span></span>

<div>

## <a name="to-modify-the-global-hosted-voice-mail-policy"></a><span data-ttu-id="c0661-109">So ändern Sie die globale Richtlinie für gehostete Voicemail</span><span class="sxs-lookup"><span data-stu-id="c0661-109">To modify the global hosted voice mail policy</span></span>

1.  <span data-ttu-id="c0661-110">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="c0661-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="c0661-111">Führen Sie das Cmdlet "Set-CsHostedVoicemailPolicy" aus, um die Parameter der globalen Richtlinie für Ihre Umgebung festzulegen.</span><span class="sxs-lookup"><span data-stu-id="c0661-111">Run the Set-CsHostedVoicemailPolicy cmdlet to set the global policy parameters for your environment.</span></span> <span data-ttu-id="c0661-112">Führen Sie beispielsweise den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="c0661-112">For example, run:</span></span>
    
        Set-CsHostedVoicemailPolicy -Destination ExUM.fabrikam.com -Organization "corp1.litwareinc.com"
    
    <span data-ttu-id="c0661-113">Da dieser Befehl nicht den Identity-Parameter der Richtlinie angibt, legt Windows PowerShell Befehlszeilenschnittstelle die folgenden Werte für die Global Hosted Voicemail-Richtlinie fest:</span><span class="sxs-lookup"><span data-stu-id="c0661-113">Because this command does not specify the policy’s Identity parameter, Windows PowerShell command-line interface sets the following values on the global hosted voice mail policy:</span></span>
    
      - <span data-ttu-id="c0661-p103">**Destination** gibt den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des gehosteten Exchange UM-Diensts an. Dieser Parameter ist optional. Wenn Sie jedoch versuchen, einen Benutzer für gehostete Voicemail zu aktivieren, und die zugewiesene Richtlinie des Benutzers nicht auf "Destination" festgelegt ist, tritt bei der Aktivierung ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="c0661-p103">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Exchange UM service. This parameter is optional, but if you attempt to enable a user for hosted voice mail and the user’s assigned policy does not have a Destination value, the enable will fail.</span></span>
    
      - <span data-ttu-id="c0661-116">**Organization** gibt eine durch trennzeichengetrennte Liste der Exchange-Mandanten an, die lync Server Benutzer zu Hause sind.</span><span class="sxs-lookup"><span data-stu-id="c0661-116">**Organization** specifies a comma-separated list of the Exchange tenants that home Lync Server users.</span></span> <span data-ttu-id="c0661-117">Für jeden Mandanten muss der vollqualifizierte Domänenname des Mandanten im gehosteten Exchange-Dienst angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="c0661-117">Each tenant must be specified as the FQDN of that tenant on the hosted Exchange UM service.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c0661-p105">Im vorherigen Cmdlet-Beispiel ersetzt der Wert "corp1.litwareinc.com" einen beliebigen Wert, der im Parameter "Organization" möglicherweise bereits vorhanden ist. Wenn die Richtlinie beispielsweise bereits eine durch Trennzeichen getrennte Liste mit Organisationen enthält, wird die gesamte Liste ersetzt. Wenn Sie nicht die gesamte Liste ersetzen, sondern der Liste eine Organisation hinzufügen möchten, führen Sie einen Befehl wie den folgenden aus.</span><span class="sxs-lookup"><span data-stu-id="c0661-p105">In the previous example cmdlet, the value “corp1.litwareinc.com” replaces any value that might already be present in the Organization parameter. For example, if the policy already contains a comma-separated list of organizations, the full list would be replaced. If you want to add an organization to the list rather than replace the entire list, run a command similar to the following.</span></span>

    
    </div>
    
        $a = Get-CsHostedVoicemailPolicy
        $a.Organization += ",corp3.litwareinc.com"
        Set-CsHostedVoicemailPolicy -Organization $a.Organization

</div>

</div>

<span> </span>

</div>

</div>

</div>

