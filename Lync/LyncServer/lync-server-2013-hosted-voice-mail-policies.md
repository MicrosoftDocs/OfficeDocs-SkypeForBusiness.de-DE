---
title: 'Lync Server 2013: Richtlinien für gehostete Voicemail'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hosted voice mail policies
ms:assetid: d62a35ed-cbe2-4f06-86b4-e192c18435c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398932(v=OCS.15)
ms:contentKeyID: 48185506
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a23f5fa67a34d479bbc5b9d5c9bf55071b187c1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832062"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-voice-mail-policies-in-lync-server-2013"></a><span data-ttu-id="73992-102">Richtlinien für gehostete Voicemail in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="73992-102">Hosted voice mail policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="73992-103">_**Letztes Änderungsdatum des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="73992-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="73992-104">Eine *Richtlinie für gehostete Voicemail* bietet Informationen für die lync Server 2013 ExUM-Routing Anwendung über den Ort, an den Anrufe für Benutzer weitergeleitet werden sollen, deren Postfächer sich in einem gehosteten Exchange-Dienst befinden.</span><span class="sxs-lookup"><span data-stu-id="73992-104">A *hosted voice mail policy* provides information to the Lync Server 2013 ExUM Routing application about where to route calls for users whose mailboxes are located on a hosted Exchange service.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="73992-105">Richtlinien für gehostete Voicemail sind nur für die lync Server 2013-Integration in Hosted Exchange um erforderlich.</span><span class="sxs-lookup"><span data-stu-id="73992-105">Hosted voice mail policies are required only for Lync Server 2013 integration with hosted Exchange UM.</span></span> <span data-ttu-id="73992-106">Sie werden für die Integration in lokale Exchange um nicht benötigt.</span><span class="sxs-lookup"><span data-stu-id="73992-106">They are not needed for integration with on-premises Exchange UM.</span></span>



</div>

<div>

## <a name="hosted-voice-mail-policy-scope"></a><span data-ttu-id="73992-107">Richtlinienbereich für gehostete Voicemails</span><span class="sxs-lookup"><span data-stu-id="73992-107">Hosted Voice Mail Policy Scope</span></span>

<span data-ttu-id="73992-108">Der Richtlinien-Bereich für gehostete Voicemail bestimmt die hierarchische Ebene, auf der die Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="73992-108">Hosted voice mail policy scope determines the hierarchical level at which the policy applies.</span></span> <span data-ttu-id="73992-109">Sie können gehostete Voicemail-Richtlinien mit den folgenden Bereichsebenen konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="73992-109">You can configure hosted voice mail policies with the following scope levels:</span></span>

  - <span data-ttu-id="73992-110">Die *globale* Richtlinie kann sich potenziell auf alle Benutzer in der lync Server 2013-Bereitstellung auswirken.</span><span class="sxs-lookup"><span data-stu-id="73992-110">The *global* policy can potentially affect all users in the Lync Server 2013 deployment.</span></span> <span data-ttu-id="73992-111">Wenn ein Benutzer für den gehosteten Exchange um-Zugriff aktiviert ist und keiner Richtlinie pro Benutzer zugewiesen wurde und eine Website Richtlinie nicht der Website des Benutzers zugewiesen wurde, gilt die globale Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="73992-111">If a user is enabled for hosted Exchange UM access and has not been assigned a per-user policy, and if a site policy has not been assigned to the user’s site, the global policy applies.</span></span> <span data-ttu-id="73992-112">Die globale Richtlinie wird mit lync Server 2013 installiert.</span><span class="sxs-lookup"><span data-stu-id="73992-112">The global policy is installed with Lync Server 2013.</span></span> <span data-ttu-id="73992-113">Sie können Sie ändern, um Ihre Anforderungen zu erfüllen, aber Sie können Sie nicht umbenennen oder löschen.</span><span class="sxs-lookup"><span data-stu-id="73992-113">You can modify it to meet your needs, but you cannot rename or delete it.</span></span>

  - <span data-ttu-id="73992-114">Eine *Website* Richtlinie kann sich auf alle Benutzer auswirken, die sich auf der Website befinden, für die die Richtlinie definiert ist.</span><span class="sxs-lookup"><span data-stu-id="73992-114">A *site* policy can affect all users that are homed on the site for which the policy is defined.</span></span> <span data-ttu-id="73992-115">Wenn ein Benutzer für den gehosteten Exchange um-Zugriff konfiguriert ist und keiner Richtlinie pro Benutzer zugewiesen wurde, gilt die Website Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="73992-115">If a user is configured for hosted Exchange UM access and has not been assigned a per-user policy, the site policy applies.</span></span>

  - <span data-ttu-id="73992-116">Eine Richtlinie *pro Benutzer* kann sich nur auf einzelne Benutzer oder Gruppen auswirken.</span><span class="sxs-lookup"><span data-stu-id="73992-116">A *per-user* policy can affect only individual users or groups.</span></span> <span data-ttu-id="73992-117">Wenn Sie eine Richtlinie pro Benutzer erzwingen möchten, müssen Sie die Richtlinie explizit einzelnen Benutzern, Gruppen und Kontaktobjekten zuweisen.</span><span class="sxs-lookup"><span data-stu-id="73992-117">To enforce a per-user policy, you must explicitly assign the policy to individual users, groups, and contact objects.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="73992-118">In den meisten Fällen ist nur eine Richtlinie für gehostete Voicemail erforderlich.</span><span class="sxs-lookup"><span data-stu-id="73992-118">In most cases, only one hosted voice mail policy is required.</span></span> <span data-ttu-id="73992-119">Sie können die globale Richtlinie oft so ändern, dass Sie allen Ihren Anforderungen entspricht.</span><span class="sxs-lookup"><span data-stu-id="73992-119">You can often modify the global policy to meet all your needs.</span></span> <span data-ttu-id="73992-120">Wenn Sie mehrere gehostete Voicemail-Richtlinien bereitstellen, verfügen alle Richtlinien über einen Benutzerbereich.</span><span class="sxs-lookup"><span data-stu-id="73992-120">If you deploy multiple hosted voice mail policies, all such policies have per-user scope.</span></span>



</div>

</div>

<div>

## <a name="hosted-voice-mail-policy-attributes"></a><span data-ttu-id="73992-121">Attribute für gehostete Voicemail-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="73992-121">Hosted Voice Mail Policy Attributes</span></span>

<span data-ttu-id="73992-122">Eine Voicemail-Richtlinie definiert zwei Attribute, die von der lync Server 2013-ExUM-Routing Anwendung in den Anforderungs-URI einer INVITE-Nachricht eingefügt werden, die an die gehostete Exchange um-Implementierung gesendet wird:</span><span class="sxs-lookup"><span data-stu-id="73992-122">A voice mail policy defines two attributes that the Lync Server 2013 ExUM Routing application inserts in the request URI of an INVITE message that is sent to the hosted Exchange UM implementation:</span></span>

  - <span data-ttu-id="73992-123">**Ziel:** Der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des gehosteten Exchange um-Diensts.</span><span class="sxs-lookup"><span data-stu-id="73992-123">**Destination:** The fully qualified domain name (FQDN) of the hosted Exchange UM service.</span></span> <span data-ttu-id="73992-124">Dieser Wert wird vom lokalen lync Server-Edgeserver für Routingzwecke verwendet.</span><span class="sxs-lookup"><span data-stu-id="73992-124">This value is used by the on-premises Lync Server Edge Server for routing purposes.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="73992-125">Der FQDN für Exchange Online lautet exap.um.Outlook.com.</span><span class="sxs-lookup"><span data-stu-id="73992-125">The FQDN for Exchange Online is exap.um.outlook.com.</span></span>

    
    </div>

  - <span data-ttu-id="73992-126">**Organisation:** Der FQDN des Mandanten des gehosteten Exchange um-Diensts, in dem die Postfächer ihrer lync Server 2013-Benutzer gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="73992-126">**Organization:** The FQDN of the tenant on the hosted Exchange UM service that homes your Lync Server 2013 users’ mailboxes.</span></span> <span data-ttu-id="73992-127">Eine Voicemail-Richtlinie kann mehrere Organisationen enthalten.</span><span class="sxs-lookup"><span data-stu-id="73992-127">A voice mail policy can contain multiple organizations.</span></span> <span data-ttu-id="73992-128">Wenn in der Richtlinie mehr als eine Organisation enthalten ist, muss dieses Attribut eine durch trennzeichengetrennte Liste der Exchange Server-Mandanten sein, die ihre Benutzerpostfächer in lync Server 2013 verwenden.</span><span class="sxs-lookup"><span data-stu-id="73992-128">If more than one organization is included in the policy, this attribute must be a comma-separated list of the Exchange Server tenants that home your Lync Server 2013 user mailboxes.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="73992-129">Der mandantenadministrator des gehosteten Exchange um-Diensts stellt die erforderlichen Werte für die Attributeinstellungen für Ziel und Organisation bereit.</span><span class="sxs-lookup"><span data-stu-id="73992-129">The tenant administrator of your hosted Exchange UM service will provide the necessary values for your Destination and Organization attribute settings.</span></span> <span data-ttu-id="73992-130">Wenn Sie Ihre Richtlinie konfigurieren möchten, müssen Sie das Cmdlet New-CsHostedVoicemailPolicy ausführen oder das Cmdlet "CsHostedVoicemailPolicy" verwenden, um ein vorhandenes zu ändern (beispielsweise die globale Richtlinie).</span><span class="sxs-lookup"><span data-stu-id="73992-130">To configure your policy, you must run the New-CsHostedVoicemailPolicy cmdlet or use the Set-CsHostedVoicemailPolicy cmdlet to modify one that exists (for example, the global policy).</span></span>



</div>

<span data-ttu-id="73992-131">Details zum Verwalten von Richtlinien für gehostete Voicemail finden Sie in der Dokumentation zur lync Server-Verwaltungsshell für die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="73992-131">For details about managing hosted voice mail policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="73992-132">Neu – CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="73992-132">New-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="73992-133">Satz-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="73992-133">Set-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="73992-134">Get-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="73992-134">Get-CsHostedVoicemailPolicy</span></span>

</div>

<div>

## <a name="per-user-voice-mail-policy-assignment"></a><span data-ttu-id="73992-135">Benutzerspezifische Voicemail-Richtlinienzuweisung</span><span class="sxs-lookup"><span data-stu-id="73992-135">Per-User Voice Mail Policy Assignment</span></span>

<span data-ttu-id="73992-136">Wenn Ihre gehostete Voicemail-Richtlinie mit benutzerdefiniertem Bereich definiert ist, müssen Sie Sie explizit zuweisen.</span><span class="sxs-lookup"><span data-stu-id="73992-136">If your hosted voice mail policy is defined with per-user scope, you must explicitly assign it.</span></span> <span data-ttu-id="73992-137">Sie können das Cmdlet Grant-CsHostedVoicemailPolicy ausführen, um die Richtlinie einzelnen Benutzern oder Gruppen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="73992-137">You can run the Grant-CsHostedVoicemailPolicy cmdlet to assign the policy to individual users or groups.</span></span>

<span data-ttu-id="73992-138">Details zum Zuweisen oder Entfernen einer pro Benutzer gehosteten Voicemail-Richtlinie finden Sie in der Dokumentation zur lync Server-Verwaltungsshell für die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="73992-138">For details about assigning or removing a per-user hosted voice mail policy, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="73992-139">Grant-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="73992-139">Grant-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="73992-140">Remove-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="73992-140">Remove-CsHostedVoicemailPolicy</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

