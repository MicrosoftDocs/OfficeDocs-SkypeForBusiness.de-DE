---
title: 'Lync Server 2013: Richtlinien für gehostete Voicemail'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted voice mail policies
ms:assetid: d62a35ed-cbe2-4f06-86b4-e192c18435c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398932(v=OCS.15)
ms:contentKeyID: 48185506
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16570331d0d7e154388c51ecb11be591bf3bbd05
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154907"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hosted-voice-mail-policies-in-lync-server-2013"></a><span data-ttu-id="55434-102">Gehostete Voicemail-Richtlinien in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55434-102">Hosted voice mail policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="55434-103">_**Letztes Änderungsstand des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="55434-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="55434-104">Eine *Richtlinie für gehostete Voicemail* stellt Informationen für die lync Server 2013 ExUM-Routing Anwendung bereit, in der die Anrufe für Benutzer weitergeleitet werden, deren Postfächer sich in einem gehosteten Exchange-Dienst befinden.</span><span class="sxs-lookup"><span data-stu-id="55434-104">A *hosted voice mail policy* provides information to the Lync Server 2013 ExUM Routing application about where to route calls for users whose mailboxes are located on a hosted Exchange service.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="55434-105">Gehostete Voicemail-Richtlinien sind nur für die lync Server 2013 Integration in gehostete Exchange um erforderlich.</span><span class="sxs-lookup"><span data-stu-id="55434-105">Hosted voice mail policies are required only for Lync Server 2013 integration with hosted Exchange UM.</span></span> <span data-ttu-id="55434-106">Für die Integration in lokale Exchange UM-Dienste werden die Richtlinien nicht benötigt.</span><span class="sxs-lookup"><span data-stu-id="55434-106">They are not needed for integration with on-premises Exchange UM.</span></span>



</div>

<div>

## <a name="hosted-voice-mail-policy-scope"></a><span data-ttu-id="55434-107">Bereich einer Richtlinie für gehostete Voicemail</span><span class="sxs-lookup"><span data-stu-id="55434-107">Hosted Voice Mail Policy Scope</span></span>

<span data-ttu-id="55434-p102">Der Bereich einer Richtlinie für gehostete Voicemail bestimmt die Hierarchieebene, auf der die Richtlinie angewendet wird. Sie können Richtlinien für gehostete Voicemail mit folgenden Bereichsebenen konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="55434-p102">Hosted voice mail policy scope determines the hierarchical level at which the policy applies. You can configure hosted voice mail policies with the following scope levels:</span></span>

  - <span data-ttu-id="55434-110">Die *globale* Richtlinie kann sich potenziell auf alle Benutzer in der lync Server 2013-Bereitstellung auswirken.</span><span class="sxs-lookup"><span data-stu-id="55434-110">The *global* policy can potentially affect all users in the Lync Server 2013 deployment.</span></span> <span data-ttu-id="55434-111">Wenn ein Benutzer für den Zugriff auf gehostete Exchange UM-Dienste aktiviert ist, ihm jedoch keine Benutzerrichtlinie und dem Standort des Benutzers keine Standortrichtlinie zugewiesen wurde, wird die globale Richtlinie angewendet.</span><span class="sxs-lookup"><span data-stu-id="55434-111">If a user is enabled for hosted Exchange UM access and has not been assigned a per-user policy, and if a site policy has not been assigned to the user’s site, the global policy applies.</span></span> <span data-ttu-id="55434-112">Die globale Richtlinie wird mit lync Server 2013 installiert.</span><span class="sxs-lookup"><span data-stu-id="55434-112">The global policy is installed with Lync Server 2013.</span></span> <span data-ttu-id="55434-113">Sie können diese Richtlinie Ihren Anforderungen entsprechend ändern, Sie können sie jedoch weder umbenennen noch löschen.</span><span class="sxs-lookup"><span data-stu-id="55434-113">You can modify it to meet your needs, but you cannot rename or delete it.</span></span>

  - <span data-ttu-id="55434-p104">Eine *Standortrichtlinie* kann sich auf alle Benutzer auswirken, die an dem Standort verwaltet werden, für den die Richtlinie definiert wurde. Wenn ein Benutzer für den Zugriff auf gehostete Exchange UM-Dienste konfiguriert ist, ihm jedoch keine Benutzerrichtlinie zugewiesen wurde, findet die Standortrichtlinie Anwendung.</span><span class="sxs-lookup"><span data-stu-id="55434-p104">A *site* policy can affect all users that are homed on the site for which the policy is defined. If a user is configured for hosted Exchange UM access and has not been assigned a per-user policy, the site policy applies.</span></span>

  - <span data-ttu-id="55434-p105">Eine *Benutzerrichtlinie* kann sich nur auf einzelne Benutzer oder Benutzergruppen auswirken. Zum Erzwingen einer Richtlinie auf Benutzerebene müssen Sie die Richtlinie explizit auf einzelne Benutzer, Gruppen oder Kontaktobjekte anwenden.</span><span class="sxs-lookup"><span data-stu-id="55434-p105">A *per-user* policy can affect only individual users or groups. To enforce a per-user policy, you must explicitly assign the policy to individual users, groups, and contact objects.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="55434-p106">In den meisten Fällen ist nur eine Richtlinie für gehostete Voicemail erforderlich. Häufig können Sie die globale Richtlinie ändern, um alle Anforderungen zu erfüllen. Wenn Sie mehrere Richtlinien für gehostete Voicemail bereitstellen, gelten alle diese Richtlinien auf Benutzerebene.</span><span class="sxs-lookup"><span data-stu-id="55434-p106">In most cases, only one hosted voice mail policy is required. You can often modify the global policy to meet all your needs. If you deploy multiple hosted voice mail policies, all such policies have per-user scope.</span></span>



</div>

</div>

<div>

## <a name="hosted-voice-mail-policy-attributes"></a><span data-ttu-id="55434-121">Attribute einer Richtlinie für gehostete Voicemail</span><span class="sxs-lookup"><span data-stu-id="55434-121">Hosted Voice Mail Policy Attributes</span></span>

<span data-ttu-id="55434-122">Eine VoIP-Richtlinie definiert zwei Attribute, die die lync Server 2013 ExUM-Routing Anwendung in den Anforderungs-URI einer INVITE-Nachricht einfügt, die an die gehostete Exchange um-Implementierung gesendet wird:</span><span class="sxs-lookup"><span data-stu-id="55434-122">A voice mail policy defines two attributes that the Lync Server 2013 ExUM Routing application inserts in the request URI of an INVITE message that is sent to the hosted Exchange UM implementation:</span></span>

  - <span data-ttu-id="55434-123">**Ziel:** Der vollqualifizierte Domänenname (FQDN) des gehosteten Exchange um Diensts.</span><span class="sxs-lookup"><span data-stu-id="55434-123">**Destination:** The fully qualified domain name (FQDN) of the hosted Exchange UM service.</span></span> <span data-ttu-id="55434-124">Dieser Wert wird vom lokalen lync Server Edgeserver für Routingzwecke verwendet.</span><span class="sxs-lookup"><span data-stu-id="55434-124">This value is used by the on-premises Lync Server Edge Server for routing purposes.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="55434-125">Der FQDN (Fully Qualified Domain Name, vollqualifizierter Domänenname) für Exchange Online lautet exap.um.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="55434-125">The FQDN for Exchange Online is exap.um.outlook.com.</span></span>

    
    </div>

  - <span data-ttu-id="55434-126">**Organisation:** Der FQDN des Mandanten im gehosteten Exchange um Dienst, der die Postfächer der lync Server 2013-Benutzer beherbergt.</span><span class="sxs-lookup"><span data-stu-id="55434-126">**Organization:** The FQDN of the tenant on the hosted Exchange UM service that homes your Lync Server 2013 users’ mailboxes.</span></span> <span data-ttu-id="55434-127">Eine Voicemailrichtlinie kann mehrere Organisationen umfassen.</span><span class="sxs-lookup"><span data-stu-id="55434-127">A voice mail policy can contain multiple organizations.</span></span> <span data-ttu-id="55434-128">Wenn in der Richtlinie mehr als eine Organisation enthalten ist, muss es sich bei diesem Attribut um eine durch trennzeichengetrennte Liste der Exchange Server Mandanten handeln, die ihre lync Server 2013 Benutzerpostfächer zu Hause sind.</span><span class="sxs-lookup"><span data-stu-id="55434-128">If more than one organization is included in the policy, this attribute must be a comma-separated list of the Exchange Server tenants that home your Lync Server 2013 user mailboxes.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="55434-p109">Der Administrator für Mandanten Ihres gehosteten Exchange UM-Diensts stellt die erforderlichen Werte für die Einstellungen der Attribute "Destination" und "Organization" bereit. Zum Erstellen und Konfigurieren einer neuen Richtlinie müssen Sie das Cmdlet "New-CsHostedVoicemailPolicy" ausführen. Wenn Sie eine vorhandene Richtlinie (z. B. die globale Richtlinie) ändern möchten, verwenden Sie das Cmdlet "Set-CsHostedVoicemailPolicy".</span><span class="sxs-lookup"><span data-stu-id="55434-p109">The tenant administrator of your hosted Exchange UM service will provide the necessary values for your Destination and Organization attribute settings. To configure your policy, you must run the New-CsHostedVoicemailPolicy cmdlet or use the Set-CsHostedVoicemailPolicy cmdlet to modify one that exists (for example, the global policy).</span></span>



</div>

<span data-ttu-id="55434-131">Ausführliche Informationen zum Verwalten von Richtlinien für gehostete Voicemail finden Sie in der lync Server-Verwaltungsshell-Dokumentation für die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="55434-131">For details about managing hosted voice mail policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="55434-132">New-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="55434-132">New-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="55434-133">Gruppe-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="55434-133">Set-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="55434-134">Get-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="55434-134">Get-CsHostedVoicemailPolicy</span></span>

</div>

<div>

## <a name="per-user-voice-mail-policy-assignment"></a><span data-ttu-id="55434-135">Zuweisen von Richtlinien auf Benutzerebene</span><span class="sxs-lookup"><span data-stu-id="55434-135">Per-User Voice Mail Policy Assignment</span></span>

<span data-ttu-id="55434-p110">Wenn Ihre Richtlinien für gehostete Voicemail auf Benutzerebene definiert sind, müssen Sie diese explizit zuweisen. Sie können das Cmdlet "Grant-CsHostedVoicemailPolicy" ausführen, um die Richtlinie einzelnen Benutzern oder Gruppen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="55434-p110">If your hosted voice mail policy is defined with per-user scope, you must explicitly assign it. You can run the Grant-CsHostedVoicemailPolicy cmdlet to assign the policy to individual users or groups.</span></span>

<span data-ttu-id="55434-138">Ausführliche Informationen zum Zuweisen oder Entfernen einer Richtlinie für gehostete Voicemail auf Benutzerbasis finden Sie in der lync Server-Verwaltungsshell-Dokumentation für die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="55434-138">For details about assigning or removing a per-user hosted voice mail policy, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="55434-139">Grant-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="55434-139">Grant-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="55434-140">Remove-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="55434-140">Remove-CsHostedVoicemailPolicy</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

