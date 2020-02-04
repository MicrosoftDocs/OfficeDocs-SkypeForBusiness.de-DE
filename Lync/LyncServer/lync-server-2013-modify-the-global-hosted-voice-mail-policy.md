---
title: 'Lync Server 2013: Ändern der Global Hosted Voicemail-Richtlinie'
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
ms.openlocfilehash: e930e0b1f9a6e2d246a8011c59e2c92c75ba138d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756879"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-global-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="bd5f7-102">Ändern der Global Hosted Voicemail-Richtlinie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bd5f7-102">Modify the global hosted voice mail policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bd5f7-103">_**Letztes Änderungsdatum des Themas:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="bd5f7-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="bd5f7-104">Die *Global* Hosted Voicemail-Richtlinie wird mit lync Server 2013 installiert.</span><span class="sxs-lookup"><span data-stu-id="bd5f7-104">The *global* hosted voice mail policy is installed with Lync Server 2013.</span></span> <span data-ttu-id="bd5f7-105">Sie können Sie ändern, um Ihre Anforderungen zu erfüllen, aber Sie können Sie nicht umbenennen oder löschen.</span><span class="sxs-lookup"><span data-stu-id="bd5f7-105">You can modify it to meet your needs, but you cannot rename or delete it.</span></span> <span data-ttu-id="bd5f7-106">Zum Ändern der globalen Richtlinie verwenden Sie das Cmdlet "festlegen-CsHostedVoicemailPolicy", um die Parameter auf die entsprechenden Werte für die jeweilige Bereitstellung zu setzen.</span><span class="sxs-lookup"><span data-stu-id="bd5f7-106">To modify the global policy, you use the Set-CsHostedVoicemailPolicy cmdlet to set the parameters to appropriate values for your specific deployment.</span></span>

<span data-ttu-id="bd5f7-107">Details zum Cmdlet " [setCsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy) " finden Sie in der Dokumentation zur lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="bd5f7-107">For details about the [Set-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy) cmdlet, see the Lync Server Management Shell documentation.</span></span>

<div>

## <a name="to-modify-the-global-hosted-voice-mail-policy"></a><span data-ttu-id="bd5f7-108">So ändern Sie die Global Hosted Voicemail-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="bd5f7-108">To modify the global hosted voice mail policy</span></span>

1.  <span data-ttu-id="bd5f7-109">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="bd5f7-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="bd5f7-110">Führen Sie das Cmdlet "Satz-CsHostedVoicemailPolicy" aus, um die globalen Richtlinienparameter für Ihre Umgebung einzurichten.</span><span class="sxs-lookup"><span data-stu-id="bd5f7-110">Run the Set-CsHostedVoicemailPolicy cmdlet to set the global policy parameters for your environment.</span></span> <span data-ttu-id="bd5f7-111">Führen Sie beispielsweise den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="bd5f7-111">For example, run:</span></span>
    
        Set-CsHostedVoicemailPolicy -Destination ExUM.fabrikam.com -Organization "corp1.litwareinc.com"
    
    <span data-ttu-id="bd5f7-112">Da dieser Befehl den Identitätsparameter der Richtlinie nicht angibt, legt die Windows PowerShell-Befehlszeilenschnittstelle die folgenden Werte für die Global Hosted Voicemail-Richtlinie fest:</span><span class="sxs-lookup"><span data-stu-id="bd5f7-112">Because this command does not specify the policy’s Identity parameter, Windows PowerShell command-line interface sets the following values on the global hosted voice mail policy:</span></span>
    
      - <span data-ttu-id="bd5f7-113">**Ziel** gibt den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des gehosteten Exchange um-Diensts an.</span><span class="sxs-lookup"><span data-stu-id="bd5f7-113">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Exchange UM service.</span></span> <span data-ttu-id="bd5f7-114">Dieser Parameter ist optional, aber wenn Sie versuchen, einen Benutzer für gehostete Voicemail zu aktivieren, und die zugewiesene Richtlinie des Benutzers keinen Zielwert hat, schlägt die Aktivierung fehl.</span><span class="sxs-lookup"><span data-stu-id="bd5f7-114">This parameter is optional, but if you attempt to enable a user for hosted voice mail and the user’s assigned policy does not have a Destination value, the enable will fail.</span></span>
    
      - <span data-ttu-id="bd5f7-115">**Organisation** gibt eine durch trennzeichengetrennte Liste der Exchange-Mandanten an, die zu den lync Server-Benutzern werden.</span><span class="sxs-lookup"><span data-stu-id="bd5f7-115">**Organization** specifies a comma-separated list of the Exchange tenants that home Lync Server users.</span></span> <span data-ttu-id="bd5f7-116">Jeder Mandant muss als FQDN dieses Mandanten für den gehosteten Exchange um-Dienst angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="bd5f7-116">Each tenant must be specified as the FQDN of that tenant on the hosted Exchange UM service.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bd5f7-117">Im vorherigen Beispiel-Cmdlet ersetzt der Wert "corp1.litwareinc.com" alle Werte, die möglicherweise bereits im Parameter Organization vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="bd5f7-117">In the previous example cmdlet, the value “corp1.litwareinc.com” replaces any value that might already be present in the Organization parameter.</span></span> <span data-ttu-id="bd5f7-118">Wenn die Richtlinie beispielsweise bereits eine durch trennzeichengetrennte Liste von Organisationen enthält, wird die vollständige Liste ersetzt.</span><span class="sxs-lookup"><span data-stu-id="bd5f7-118">For example, if the policy already contains a comma-separated list of organizations, the full list would be replaced.</span></span> <span data-ttu-id="bd5f7-119">Wenn Sie der Liste eine Organisation hinzufügen möchten, anstatt die gesamte Liste zu ersetzen, führen Sie einen Befehl wie den folgenden aus.</span><span class="sxs-lookup"><span data-stu-id="bd5f7-119">If you want to add an organization to the list rather than replace the entire list, run a command similar to the following.</span></span>

    
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

