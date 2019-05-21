---
title: Bereitstellen von Anrufen über die Arbeit in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4802d733-14ef-4509-92b9-07173614e45f
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie einen Anruf über die Arbeit in Skype for Business Server für einige oder alle Benutzer bereitstellen.'
ms.openlocfilehash: a2d4783f39ca19fd751295f4725f686d843f8d5b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286390"
---
# <a name="deploy-call-via-work-in-skype-for-business-server"></a><span data-ttu-id="ae864-103">Bereitstellen von Anrufen über die Arbeit in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ae864-103">Deploy Call Via Work in Skype for Business Server</span></span>
 
<span data-ttu-id="ae864-104">**Zusammenfassung:** Hier erfahren Sie, wie Sie einen Anruf über die Arbeit in Skype for Business Server für einige oder alle Benutzer bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="ae864-104">**Summary:** Learn how to deploy Call Via Work in Skype for Business Server for some or all of your users.</span></span>
  
<span data-ttu-id="ae864-105">Führen Sie die folgenden Schritte aus, um Anrufe über Arbeit für Ihre Benutzer bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="ae864-105">Use these steps to deploy Call Via Work for your users.</span></span> <span data-ttu-id="ae864-106">Planungsüberlegungen werden in [Plan für Anruf über die Arbeit in Skype for Business Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)erörtert.</span><span class="sxs-lookup"><span data-stu-id="ae864-106">Planning considerations are discussed in [Plan for Call Via Work in Skype for Business Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md).</span></span> <span data-ttu-id="ae864-107">In früheren Versionen von lync Server war die Remoteanrufsteuerung ein Feature, mit dem Benutzer Ihre PBX-Telefone mit lync Server steuern konnten.</span><span class="sxs-lookup"><span data-stu-id="ae864-107">In previous versions of Lync Server remote call control was a feature which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="ae864-108">In Skype for Business Server wurde diese Funktion durch Anruf über Arbeit ersetzt.</span><span class="sxs-lookup"><span data-stu-id="ae864-108">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span> 
  
## <a name="prerequisites-for-call-via-work"></a><span data-ttu-id="ae864-109">Voraussetzungen für Anrufe über die Arbeit</span><span class="sxs-lookup"><span data-stu-id="ae864-109">Prerequisites for Call Via Work</span></span>

<span data-ttu-id="ae864-110">Bei Anrufen über die Arbeit wird die Unified Communications Web API (UCWA) verwendet, die automatisch auf allen Skype for Business Server-Front-End-Servern installiert wird.</span><span class="sxs-lookup"><span data-stu-id="ae864-110">Call Via Work uses Unified Communications Web API (UCWA), which is automatically installed on all Skype for Business Server Front End Servers.</span></span> <span data-ttu-id="ae864-111">Damit Benutzer den Anruf über die Arbeit tätigen können, müssen Sie auch die folgenden Voraussetzungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="ae864-111">To enable users for Call Via Work, you must also have the following prerequisites in place:</span></span> 
  
- <span data-ttu-id="ae864-112">Sie müssen über einen Vermittlungsserver verfügen, der entweder als Teil eines Front-End-Servers oder als eigenständige Rolle bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="ae864-112">You must have a Mediation Server deployed, either as part of a Front End Server or as a standalone role.</span></span> <span data-ttu-id="ae864-113">Weiterhin müssen Sie ein IP-PBX-Gateway bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="ae864-113">You must also deploy an IP-PBX gateway.</span></span>
    
- <span data-ttu-id="ae864-114">Alle Benutzer, die über Arbeit für den Anruf aktiviert werden, müssen über eine direkte nach innen Wahl (DID) auf dem PBX-Telefonsystem verfügen.</span><span class="sxs-lookup"><span data-stu-id="ae864-114">All users who will be enabled for Call Via Work must have a Direct Inward Dialing (DID) on the PBX phone system.</span></span> 
    
- <span data-ttu-id="ae864-115">Sie müssen alle Anrufe über geschäftliche Benutzer für Enterprise-VoIP aktivieren.</span><span class="sxs-lookup"><span data-stu-id="ae864-115">You must enable all Call Via Work users for Enterprise Voice.</span></span> <span data-ttu-id="ae864-116">Wenn Sie dies tun, müssen Sie die Skype for Business-Nummer für jeden Benutzer auf die entsprechende DID-Nummer für das entsprechende PBX-Telefonsystem konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ae864-116">When you do this, you must configure the Skype for Business DID number for each user to the corresponding DID number for the corresponding PBX phone system.</span></span> 
    
- <span data-ttu-id="ae864-117">Alle Benutzer, die über Arbeit anrufen, müssen in Ihrem Skype for Business-Client über die Option " **Erweiterte Verbindungen** " eine **Automatische Konfiguration** ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="ae864-117">All users who will be using Call Via Work must have **Automatic Configuration** selected in their **Advanced Connections** option in their Skype for Business client.</span></span> <span data-ttu-id="ae864-118">Auf diese Weise kann der Client die UCWA-URLs ermitteln.</span><span class="sxs-lookup"><span data-stu-id="ae864-118">This enables the client to discover the UCWA URLs.</span></span> <span data-ttu-id="ae864-119">**Automatische Konfiguration** ist die Standardauswahl.</span><span class="sxs-lookup"><span data-stu-id="ae864-119">**Automatic Configuration** is the default selection.</span></span>
    
- <span data-ttu-id="ae864-120">Aktivieren Sie für jeden Anruf über den Arbeits Benutzer die Anrufweiterleitung und gleichzeitiges Klingeln.</span><span class="sxs-lookup"><span data-stu-id="ae864-120">For each Call Via Work user, enable call forwarding and simultaneous ringing.</span></span> 
    
- <span data-ttu-id="ae864-121">Stellen Sie für jeden Anruf über den Arbeits Benutzer sicher, dass Einwahlkonferenzen und Konferenz Auswahl aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="ae864-121">For each Call Via Work user, ensure that dial-in conferencing and conferencing dial-out are enabled.</span></span> <span data-ttu-id="ae864-122">Auf diese Weise können diese Benutzer in Skype for Business-Konferenzen einstweilen.</span><span class="sxs-lookup"><span data-stu-id="ae864-122">This enables these users to get into and out of Skype for Business conferences.</span></span>
    
- <span data-ttu-id="ae864-123">Stellen Sie sicher, dass Delegierung, Team Anruf und Reaktionsgruppe für jeden Anruf über den Arbeits Benutzer deaktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="ae864-123">Ensure that delegation, team call, and response group are disabled for every Call Via Work user.</span></span>
    
## <a name="deploy-call-via-work"></a><span data-ttu-id="ae864-124">Bereitstellen der Funktion „Anruf über Arbeit“</span><span class="sxs-lookup"><span data-stu-id="ae864-124">Deploy Call Via Work</span></span>

<span data-ttu-id="ae864-125">Wenn alle Voraussetzungen erfüllt sind, gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="ae864-125">After the prerequisites are in place, do the following:</span></span>
  
- <span data-ttu-id="ae864-126">Erstellen Sie eine globale Telefonnummer für Ihre Bereitstellung, die Skype for Business auf der Rufnummernanzeige von Benutzern anzeigt, die Anrufe über geschäftliche Anrufe tätigen.</span><span class="sxs-lookup"><span data-stu-id="ae864-126">Create a global phone number for your deployment which Skype for Business displays on the PBX caller ID of users who are making Call Via Work calls.</span></span> 
    
- <span data-ttu-id="ae864-127">Erstellen eines oder mehrerer Anrufe über Arbeitsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="ae864-127">Create one or more Call Via Work policies</span></span>
    
- <span data-ttu-id="ae864-128">Zuweisen eines Anrufs über die Arbeitsrichtlinie für jeden Benutzer, der über die Arbeit für den Anruf aktiviert wird</span><span class="sxs-lookup"><span data-stu-id="ae864-128">Assign a Call Via Work policy to each user who will be enabled for Call Via Work</span></span>
    
### <a name="create-the-call-via-work-global-phone-number"></a><span data-ttu-id="ae864-129">Erstellen der globalen „Anruf über Arbeit“-Telefonnummer</span><span class="sxs-lookup"><span data-stu-id="ae864-129">Create the Call Via Work global phone number</span></span>

- <span data-ttu-id="ae864-130">Geben Sie das folgende Cmdlet ein</span><span class="sxs-lookup"><span data-stu-id="ae864-130">Type the following cmdlet</span></span>
    
  ```
  Set-CsRoutingConfiguration -CallViaWorkCallerId +<PhoneNumber>
  ```

    <span data-ttu-id="ae864-131">Mit dem folgenden Cmdlet wird die globale Telefonnummer beispielsweise auf 1-555-123-4567 festgelegt.</span><span class="sxs-lookup"><span data-stu-id="ae864-131">For example, the following cmdlet sets the global phone number to 1-555-123-4567.</span></span>
    
  ```
  Set-CsRoutingConfiguration -CallViaWorkCallerId +15551234567
  ```

### <a name="create-a-call-via-work-policy"></a><span data-ttu-id="ae864-132">Erstellen einer Richtlinie für „Anruf über Arbeit“</span><span class="sxs-lookup"><span data-stu-id="ae864-132">Create a Call Via Work policy</span></span>

- <span data-ttu-id="ae864-133">Geben Sie das folgende Cmdlet ein</span><span class="sxs-lookup"><span data-stu-id="ae864-133">Type the following cmdlet</span></span>
    
  ```
  New-CsCallViaWorkPolicy [-Identity] <XdsIdentity> [-Tenant <guid>] [-Enabled <bool>] [-UseAdminCallbackNumber  <bool>] [-AdminCallbackNumber <string>] [-InMemory] [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]
  ```

    <span data-ttu-id="ae864-134">Das folgende Cmdlet erstellt beispielsweise einen Anruf über die Arbeitsrichtlinie mit dem Namen ContosoUser1CvWP, erfordert, dass der Benutzer eine Administrator Rückrufnummer verwendet, und legt diese Rückrufnummer auf 1-555-789-1234 fest.</span><span class="sxs-lookup"><span data-stu-id="ae864-134">For example, the following cmdlet creates a Call Via Work policy called ContosoUser1CvWP, requires the user to use an admin callback number, and sets that callback number to 1-555-789-1234.</span></span>
    
  ```
  New-CsCallViaWorkPolicy -Identity Tag:ContosoUser1CvWP -Enabled $true -UseAdminCallbackNumber $true -AdminCallbackNumber +15557891234
  ```

### <a name="assign-a-call-via-work-policy-to-a-user"></a><span data-ttu-id="ae864-135">Zuweisen eines Anrufs über die Arbeitsrichtlinie an einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="ae864-135">Assign a Call Via Work policy to a user</span></span>

- <span data-ttu-id="ae864-136">Geben Sie das folgende Cmdlet ein</span><span class="sxs-lookup"><span data-stu-id="ae864-136">Type the following cmdlet</span></span>
    
  ```
  Grant-CsCallViaWorkPolicy -Identity <UserName> -PolicyName Tag:<PolicyName>
  ```

    <span data-ttu-id="ae864-137">Das folgende Cmdlet weist beispielsweise dem Benutzer mit dem Namen **ContosoUser1**den Anruf über die Arbeitsrichtlinie "ContosoUser1CvWP" zu.</span><span class="sxs-lookup"><span data-stu-id="ae864-137">For example, the following cmdlet assigns the Call Via Work policy "ContosoUser1CvWP" to the user named **ContosoUser1**.</span></span>
    
  ```
  Grant-CsCallViaWorkPolicy -Identity ContosoUser1 -PolicyName Tag:ContosoUser1CvWP
  ```

## <a name="see-also"></a><span data-ttu-id="ae864-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ae864-138">See also</span></span>

[<span data-ttu-id="ae864-139">Planen eines Anrufs über die Arbeit in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ae864-139">Plan for Call Via Work in Skype for Business Server</span></span>](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)

