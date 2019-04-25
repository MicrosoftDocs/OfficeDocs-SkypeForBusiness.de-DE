---
title: Bereitstellen Sie Anruf über den Arbeitsplatz in Skype für Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4802d733-14ef-4509-92b9-07173614e45f
description: 'Zusammenfassung: Informationen Sie zum Bereitstellen von Anrufen über Arbeitsplatz in Skype für Business Server für einige oder alle Benutzer.'
ms.openlocfilehash: d0cee2cbf3a88514983efd77e2b1728b2df1e792
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32227536"
---
# <a name="deploy-call-via-work-in-skype-for-business-server"></a><span data-ttu-id="8bf29-103">Bereitstellen Sie Anruf über den Arbeitsplatz in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="8bf29-103">Deploy Call Via Work in Skype for Business Server</span></span>
 
<span data-ttu-id="8bf29-104">**Zusammenfassung:** Informationen Sie zum Bereitstellen von Anrufen über Arbeitsplatz in Skype für Business Server für einige oder alle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="8bf29-104">**Summary:** Learn how to deploy Call Via Work in Skype for Business Server for some or all of your users.</span></span>
  
<span data-ttu-id="8bf29-105">Verwenden Sie folgende Schritte aus, um über Arbeitsplatz anrufen für Benutzer bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="8bf29-105">Use these steps to deploy Call Via Work for your users.</span></span> <span data-ttu-id="8bf29-106">In [Planen von Anrufen über Arbeitsplatz in Skype für Business Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)werden Planungsaspekte erläutert.</span><span class="sxs-lookup"><span data-stu-id="8bf29-106">Planning considerations are discussed in [Plan for Call Via Work in Skype for Business Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md).</span></span> <span data-ttu-id="8bf29-107">In früheren Versionen von Lync Server Remoteaufruf war Steuerelement ein Feature, das Benutzer ihre Nebenstellentelefone über mit Lync Server steuern aktiviert.</span><span class="sxs-lookup"><span data-stu-id="8bf29-107">In previous versions of Lync Server remote call control was a feature which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="8bf29-108">Dieses Feature wurde in Skype für Business Server mit über Arbeitsplatz anrufen ersetzt.</span><span class="sxs-lookup"><span data-stu-id="8bf29-108">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span> 
  
## <a name="prerequisites-for-call-via-work"></a><span data-ttu-id="8bf29-109">Erforderliche Komponenten für Anruf über den Arbeitsplatz</span><span class="sxs-lookup"><span data-stu-id="8bf29-109">Prerequisites for Call Via Work</span></span>

<span data-ttu-id="8bf29-110">Über Arbeitsplatz anrufen verwendet Unified Communications Web API (UCWA), die automatisch auf alle Skype für Business Server-Front-End-Server installiert ist.</span><span class="sxs-lookup"><span data-stu-id="8bf29-110">Call Via Work uses Unified Communications Web API (UCWA), which is automatically installed on all Skype for Business Server Front End Servers.</span></span> <span data-ttu-id="8bf29-111">Damit Benutzer für über Arbeitsplatz anrufen können, müssen Sie auch die folgenden erforderlichen Komponenten verfügen:</span><span class="sxs-lookup"><span data-stu-id="8bf29-111">To enable users for Call Via Work, you must also have the following prerequisites in place:</span></span> 
  
- <span data-ttu-id="8bf29-112">Sie müssen einen Vermittlungsserver bereitgestellt haben, entweder als Teil eines Front-End-Servers oder als eigenständige Rolle verfügen.</span><span class="sxs-lookup"><span data-stu-id="8bf29-112">You must have a Mediation Server deployed, either as part of a Front End Server or as a standalone role.</span></span> <span data-ttu-id="8bf29-113">Weiterhin müssen Sie ein IP-PBX-Gateway bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="8bf29-113">You must also deploy an IP-PBX gateway.</span></span>
    
- <span data-ttu-id="8bf29-114">Alle Benutzer, die für über Arbeitsplatz anrufen aktiviert, benötigen ein (Direct Inward Dialing DIALING) auf die Telefonanlage.</span><span class="sxs-lookup"><span data-stu-id="8bf29-114">All users who will be enabled for Call Via Work must have a Direct Inward Dialing (DID) on the PBX phone system.</span></span> 
    
- <span data-ttu-id="8bf29-115">Sie müssen alle über Arbeitsplatz anrufen Benutzer für Enterprise-VoIP aktivieren.</span><span class="sxs-lookup"><span data-stu-id="8bf29-115">You must enable all Call Via Work users for Enterprise Voice.</span></span> <span data-ttu-id="8bf29-116">Wenn Sie dies tun, müssen Sie die Skype für Business haben Anzahl für jeden Benutzer auf die entsprechende DID-Nummer für das entsprechende PBX-Telefon-System konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="8bf29-116">When you do this, you must configure the Skype for Business DID number for each user to the corresponding DID number for the corresponding PBX phone system.</span></span> 
    
- <span data-ttu-id="8bf29-117">Alle Benutzer, die über Arbeitsplatz anrufen verwenden sollen müssen **Automatische Konfiguration** in die Option **Erweiterte Verbindungen** in ihren Skype für Business Client ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="8bf29-117">All users who will be using Call Via Work must have **Automatic Configuration** selected in their **Advanced Connections** option in their Skype for Business client.</span></span> <span data-ttu-id="8bf29-118">Dies ermöglicht dem Client die UCWA-URLs zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="8bf29-118">This enables the client to discover the UCWA URLs.</span></span> <span data-ttu-id="8bf29-119">**Automatische Konfiguration** ist die Standardauswahl.</span><span class="sxs-lookup"><span data-stu-id="8bf29-119">**Automatic Configuration** is the default selection.</span></span>
    
- <span data-ttu-id="8bf29-120">Aktivieren Sie für jeden Benutzer über Arbeitsplatz anrufen die anrufweiterleitung und Gleichzeitiges Klingeln.</span><span class="sxs-lookup"><span data-stu-id="8bf29-120">For each Call Via Work user, enable call forwarding and simultaneous ringing.</span></span> 
    
- <span data-ttu-id="8bf29-121">Für jeden Benutzer über Arbeitsplatz anrufen stellen Sie sicher, dass einwahlkonferenzen und Konferenzen Dial-Out-aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="8bf29-121">For each Call Via Work user, ensure that dial-in conferencing and conferencing dial-out are enabled.</span></span> <span data-ttu-id="8bf29-122">Dadurch können diese Benutzer an- und wieder abmelden Skype für Business Konferenzen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="8bf29-122">This enables these users to get into and out of Skype for Business conferences.</span></span>
    
- <span data-ttu-id="8bf29-123">Stellen Sie sicher, dass Delegierung, teamanrufe und reaktionsgruppen für jeden Benutzer über Arbeitsplatz anrufen deaktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="8bf29-123">Ensure that delegation, team call, and response group are disabled for every Call Via Work user.</span></span>
    
## <a name="deploy-call-via-work"></a><span data-ttu-id="8bf29-124">Bereitstellen der Funktion „Anruf über Arbeit“</span><span class="sxs-lookup"><span data-stu-id="8bf29-124">Deploy Call Via Work</span></span>

<span data-ttu-id="8bf29-125">Wenn alle Voraussetzungen erfüllt sind, gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="8bf29-125">After the prerequisites are in place, do the following:</span></span>
  
- <span data-ttu-id="8bf29-126">Erstellen Sie eine globale Rufnummer für Ihre Bereitstellung Skype für Unternehmen auf der Nebenstellenanlage Anrufer-ID der Benutzer anzeigt, die über Arbeitsplatz anrufen erachtet werden.</span><span class="sxs-lookup"><span data-stu-id="8bf29-126">Create a global phone number for your deployment which Skype for Business displays on the PBX caller ID of users who are making Call Via Work calls.</span></span> 
    
- <span data-ttu-id="8bf29-127">Erstellen Sie eine oder mehrere über Arbeitsplatz anrufen Richtlinien</span><span class="sxs-lookup"><span data-stu-id="8bf29-127">Create one or more Call Via Work policies</span></span>
    
- <span data-ttu-id="8bf29-128">Zuweisen einer Richtlinie auf über Arbeitsplatz anrufen an jeden Benutzer, die für über Arbeitsplatz anrufen aktiviert wird</span><span class="sxs-lookup"><span data-stu-id="8bf29-128">Assign a Call Via Work policy to each user who will be enabled for Call Via Work</span></span>
    
### <a name="create-the-call-via-work-global-phone-number"></a><span data-ttu-id="8bf29-129">Erstellen der globalen „Anruf über Arbeit“-Telefonnummer</span><span class="sxs-lookup"><span data-stu-id="8bf29-129">Create the Call Via Work global phone number</span></span>

- <span data-ttu-id="8bf29-130">Geben Sie das folgende Cmdlet ein</span><span class="sxs-lookup"><span data-stu-id="8bf29-130">Type the following cmdlet</span></span>
    
  ```
  Set-CsRoutingConfiguration -CallViaWorkCallerId +<PhoneNumber>
  ```

    <span data-ttu-id="8bf29-131">Mit dem folgenden Cmdlet wird die globale Telefonnummer beispielsweise auf 1-555-123-4567 festgelegt.</span><span class="sxs-lookup"><span data-stu-id="8bf29-131">For example, the following cmdlet sets the global phone number to 1-555-123-4567.</span></span>
    
  ```
  Set-CsRoutingConfiguration -CallViaWorkCallerId +15551234567
  ```

### <a name="create-a-call-via-work-policy"></a><span data-ttu-id="8bf29-132">Erstellen einer Richtlinie für „Anruf über Arbeit“</span><span class="sxs-lookup"><span data-stu-id="8bf29-132">Create a Call Via Work policy</span></span>

- <span data-ttu-id="8bf29-133">Geben Sie das folgende Cmdlet ein</span><span class="sxs-lookup"><span data-stu-id="8bf29-133">Type the following cmdlet</span></span>
    
  ```
  New-CsCallViaWorkPolicy [-Identity] <XdsIdentity> [-Tenant <guid>] [-Enabled <bool>] [-UseAdminCallbackNumber  <bool>] [-AdminCallbackNumber <string>] [-InMemory] [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]
  ```

    <span data-ttu-id="8bf29-134">Das folgende Cmdlet beispielsweise über Arbeitsplatz anrufen-Richtlinie namens ContosoUser1CvWP erstellt, bewirkt, dass den Benutzer eine Rückrufnummer Admin verwenden und diese Rückrufnummer auf 1-555-789-1234 festgelegt.</span><span class="sxs-lookup"><span data-stu-id="8bf29-134">For example, the following cmdlet creates a Call Via Work policy called ContosoUser1CvWP, requires the user to use an admin callback number, and sets that callback number to 1-555-789-1234.</span></span>
    
  ```
  New-CsCallViaWorkPolicy -Identity Tag:ContosoUser1CvWP -Enabled $true -UseAdminCallbackNumber $true -AdminCallbackNumber +15557891234
  ```

### <a name="assign-a-call-via-work-policy-to-a-user"></a><span data-ttu-id="8bf29-135">Zuweisen einer Richtlinie auf über Arbeitsplatz anrufen, die einem Benutzer</span><span class="sxs-lookup"><span data-stu-id="8bf29-135">Assign a Call Via Work policy to a user</span></span>

- <span data-ttu-id="8bf29-136">Geben Sie das folgende Cmdlet ein</span><span class="sxs-lookup"><span data-stu-id="8bf29-136">Type the following cmdlet</span></span>
    
  ```
  Grant-CsCallViaWorkPolicy -Identity <UserName> -PolicyName Tag:<PolicyName>
  ```

    <span data-ttu-id="8bf29-137">Beispielsweise weist das folgende Cmdlet die Richtlinie über Arbeitsplatz anrufen "ContosoUser1CvWP" dem Benutzer mit dem Namen **ContosoUser1**.</span><span class="sxs-lookup"><span data-stu-id="8bf29-137">For example, the following cmdlet assigns the Call Via Work policy "ContosoUser1CvWP" to the user named **ContosoUser1**.</span></span>
    
  ```
  Grant-CsCallViaWorkPolicy -Identity ContosoUser1 -PolicyName Tag:ContosoUser1CvWP
  ```

## <a name="see-also"></a><span data-ttu-id="8bf29-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8bf29-138">See also</span></span>

[<span data-ttu-id="8bf29-139">Planen der Anruf über den Arbeitsplatz in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="8bf29-139">Plan for Call Via Work in Skype for Business Server</span></span>](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)

