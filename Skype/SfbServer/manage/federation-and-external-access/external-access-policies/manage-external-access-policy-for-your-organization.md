---
title: Verwalten von Richtlinien für den externen Zugriff für Ihre Organisation
ms.reviewer: ''
ms:assetid: 5571811e-34c8-443a-b94c-1ab5d4275581
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520995(v=OCS.15)
ms:contentKeyID: 48184160
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Nach der Bereitstellung eines oder mehrerer Edge-Server müssen Sie die spezifischen Typen des externen Benutzerzugriffs aktivieren, die für Ihre Organisation unterstützt werden sollen.
ms.openlocfilehash: e4405585da71dc48f5fa1790f83938a814270d84
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818276"
---
# <a name="manage-external-access-policy-for-your-organization"></a><span data-ttu-id="f8813-103">Verwalten von Richtlinien für den externen Zugriff für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="f8813-103">Manage external access policy for your organization</span></span>

<span data-ttu-id="f8813-104">Nach der Bereitstellung eines oder mehrerer Edge-Server müssen Sie die spezifischen Typen des externen Benutzerzugriffs aktivieren, die für Ihre Organisation unterstützt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f8813-104">After deploying one or more Edge Servers, you must enable the types of external access that will be supported for your organization.</span></span>

<span data-ttu-id="f8813-p101">In der Standardeinstellung sind keine Richtlinien für den Zugriff durch externe Benutzer (einschließlich Remotebenutzerzugriff und Partnerbenutzerzugriff) konfiguriert. Dies gilt auch, wenn Sie die Unterstützung für externe Benutzer in Ihrer Organisation bereits aktiviert haben. Um den Zugriff durch externe Benutzer zu kontrollieren, müssen Sie eine oder mehrere Richtlinien konfigurieren und die Art des Benutzerzugriffs angeben, der durch die jeweilige Richtlinie ermöglicht wird. Sie können die nachstehend angegebenen Richtlinienbereiche erstellen und konfigurieren. Die "Globale Richtlinie" wird standardmäßig erstellt. Sie kann nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="f8813-p101">By default, there are no policies configured to support external user access, including remote user access, federated user access, even if you have already enabled external user access support for your organization. To control the use of external user access, you must configure one or more policies, specifying the type of external user access supported for each policy. The following policy scopes are available for creation and configuration. By default, the Global policy is created, but cannot be deleted.</span></span>

  - <span data-ttu-id="f8813-109">**Globale Richtlinie**   Die globale Richtlinie wird bei der Bereitstellung der Edgeserver erstellt.</span><span class="sxs-lookup"><span data-stu-id="f8813-109">**Global policy**   The global policy is created when you deploy your Edge Servers.</span></span> <span data-ttu-id="f8813-110">Standardmäßig sind in der globalen Richtlinie keine Optionen für den externen Benutzerzugriff aktiviert.</span><span class="sxs-lookup"><span data-stu-id="f8813-110">By default, no external user access options are enabled in the global policy.</span></span> <span data-ttu-id="f8813-111">Zur Unterstützung des Zugriffs durch externe Benutzer auf globaler Ebene konfigurieren Sie die globale Richtlinie so, dass mindestens ein Typ des externen Benutzerzugriffs unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="f8813-111">To support external user access at the global level, you configure the global policy to support one or more types of external user access options.</span></span> <span data-ttu-id="f8813-112">Die globale Richtlinie gilt für alle Benutzer in Ihrer Organisation, wird jedoch durch Standort- und Benutzerrichtlinien außer Kraft gesetzt.</span><span class="sxs-lookup"><span data-stu-id="f8813-112">The global policy applies to all users in your organization, but site policies and user policies override the global policy.</span></span> <span data-ttu-id="f8813-113">Wenn Sie die globale Richtlinie löschen, wird diese nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="f8813-113">If you delete the global policy, you do not remove it.</span></span> <span data-ttu-id="f8813-114">Stattdessen wird sie auf die Standardeinstellung zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="f8813-114">Instead, you reset it to the default setting.</span></span>

  - <span data-ttu-id="f8813-115">**Standortrichtlinie**   Sie können eine oder mehrere Standortrichtlinien erstellen und konfigurieren, um die Unterstützung für den Zugriff durch externe Benutzer auf bestimmte Standorte einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="f8813-115">**Site policy**   You can create and configure one or more site policies to limit support for external user access to specific sites.</span></span> <span data-ttu-id="f8813-116">Die Konfiguration in der Standortrichtlinie setzt die globale Richtlinie außer Kraft, jedoch nur für den durch die Standortrichtlinie abgedeckten Standort.</span><span class="sxs-lookup"><span data-stu-id="f8813-116">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="f8813-117">Wenn Sie beispielsweise den Remotebenutzerzugriff in der globalen Richtlinie aktivieren, können Sie eine Standortrichtlinie festlegen, die den Remotebenutzerzugriff für einen bestimmten Standort deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="f8813-117">For example, if you enable remote user access in the global policy, you might specify a site policy that disables remote user access for a specific site.</span></span> <span data-ttu-id="f8813-118">Standardmäßig wird eine Standortrichtlinie auf alle Benutzer des jeweiligen Standorts angewendet, Sie können jedoch einem Benutzer eine Benutzerrichtlinie zuweisen, um die Standortrichtlinieneinstellung außer Kraft zu setzen.</span><span class="sxs-lookup"><span data-stu-id="f8813-118">By default, a site policy is applied to all users of that site, but you can assign a user policy to a user to override the site policy setting.</span></span>

  - <span data-ttu-id="f8813-119">**Benutzerrichtlinie**   Die Konfiguration der Benutzerrichtlinie überschreibt die globale Richtlinie und die Standortrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="f8813-119">**User policy**   You can create and configure one or more user policies to limit support for remote user access to specific users.</span></span> <span data-ttu-id="f8813-120">Dies gilt jedoch nur für die von der entsprechenden Richtlinie betroffenen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="f8813-120">The configuration in the user policy overrides the global and site policy, but only for the specific users to whom the user policy is assigned.</span></span> <span data-ttu-id="f8813-121">Wenn Sie beispielsweise den Remotebenutzerzugriff in der globalen Richtlinie und in der Standardrichtlinie aktivieren, können Sie eine Benutzerrichtlinie festlegen, die den Remotebenutzerzugriff deaktiviert, und diese Richtlinie bestimmten Benutzern zuweisen.</span><span class="sxs-lookup"><span data-stu-id="f8813-121">For example, if you enable remote user access in the global policy and site policy, you might specify a user policy that disables remote user access and then assign that user policy to specific users.</span></span> <span data-ttu-id="f8813-122">Benutzerrichtlinien werden erst mit der Zuweisung zu bestimmten Benutzern wirksam.</span><span class="sxs-lookup"><span data-stu-id="f8813-122">If you create a user policy, you must apply it to one or more users before it takes effect.</span></span>


> [!IMPORTANT]  
> <span data-ttu-id="f8813-123">Richtlinieneinstellungen, die auf einer Richtlinienebene angewendet werden, können Einstellungen überschreiben, die auf eine andere Richtlinienebene angewendet wurden.</span><span class="sxs-lookup"><span data-stu-id="f8813-123">Policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="f8813-124">Prioritätenreihenfolge für Skype for Business Server-Richtlinien: Eine Benutzerrichtlinie (größter Einfluss) hat Vorrang vor einer Standortrichtlinie, und eine Standortrichtlinie wiederum hat Vorrang vor einer globalen Richtlinie (geringster Einfluss).</span><span class="sxs-lookup"><span data-stu-id="f8813-124">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="f8813-125">Dies bedeutet Folgendes: Je näher sich die Richtlinieneinstellung am betroffenen Objekt befindet, umso mehr Einfluss auf das Objekt hat sie.</span><span class="sxs-lookup"><span data-stu-id="f8813-125">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>


<span data-ttu-id="f8813-126">Diese Optionen umfassen die folgenden Arten des externen Zugriffs:</span><span class="sxs-lookup"><span data-stu-id="f8813-126">These options include the following types of external access:</span></span>

  - <span data-ttu-id="f8813-127">**Kommunikation mit Verbundbenutzern aktivieren**   Aktivieren Sie diese Option, wenn Sie den Benutzerzugriff auf Verbundpartnerdomänen unterstützen möchten.</span><span class="sxs-lookup"><span data-stu-id="f8813-127">**Enable communications with federated users**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="f8813-128">Diese Einstellung konfiguriert die Möglichkeit für Benutzer, mit anderen SIP-Verbunddomänen sowie gehosteten Anbietern wie Microsoft Office 365 zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="f8813-128">This setting configures the ability for users to communicate with other SIP federated domains, as well as Hosted providers like Microsoft Office 365.</span></span> 


  - <span data-ttu-id="f8813-129">**Kommunikation mit Remotebenutzern aktivieren**   Aktivieren Sie diese Option, wenn Benutzer in Ihrer Organisation in der Lage sein sollen, die sich außerhalb der Firewall befinden (z. B. Telearbeiter und Benutzer auf Geschäftsreise), sich über das Internet mit Skype for Business Server verbinden zu können.</span><span class="sxs-lookup"><span data-stu-id="f8813-129">**Enable communications with remote users**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Skype for Business Server over the Internet.</span></span>

  - <span data-ttu-id="f8813-130">**Kommunikation mit öffentlichen Benutzern aktivieren**   Aktivieren Sie diese Option, wenn sich interne Benutzer mit öffentlichen Kontakten der Anbieter von Sofortnachrichtendiensten verbinden können sollen.</span><span class="sxs-lookup"><span data-stu-id="f8813-130">**Enable communications with public users**   Enable this option if you want internal users to be able to communicate with public IM provider contacts.</span></span>
   

> [!NOTE]  
> <span data-ttu-id="f8813-131">Neben dem Aktivieren der Unterstützung für den externen Benutzerzugriff müssen Sie auch Richtlinien konfigurieren, um die Verwendung des externen Benutzerzugriffs in Ihrer Organisation zu steuern, bevor den Benutzern ein beliebiger Typ des externen Benutzerzugriffs zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="f8813-131">In addition to enabling external user access support, you must also configure policies to control the use of external user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="f8813-132">Ausführliche Informationen zur Erstellung, Konfiguration und Anwendung von Richtlinien für den externen Benutzerzugriff finden Sie unter [Aktivieren oder Deaktivieren des Zugriffs durch Remotebenutzer](../access-edge/enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="f8813-132">For details about creating, configuring, and applying policies for external user access see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span>



<span data-ttu-id="f8813-133">**So zeigen Sie Richtlinien für den externen Zugriff mithilfe von Windows PowerShell-Cmdlets an**</span><span class="sxs-lookup"><span data-stu-id="f8813-133">**To view external access policies by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="f8813-134">Sie können Richtlinien für den externen Zugriff mit der Skype for Business Server-Verwaltungsshell und dem Cmdlets **Get-CsExternalAccessPolicy** anzeigen.</span><span class="sxs-lookup"><span data-stu-id="f8813-134">You can view external access policies by using Skype for Business Server Management Shell and the **Get-CsExternalAccessPolicy** cmdlet.</span></span> <span data-ttu-id="f8813-135">Sie können dieses Cmdlet aus der Skype for Business Server-Verwaltungsshell oder aus einer Remotesitzung mit Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="f8813-135">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 
    
    <span data-ttu-id="f8813-136">Um Informationen über alle Richtlinien für den externen Zugriff anzuzeigen, geben Sie den folgenden Befehl in der Lync Server-Verwaltungsshell ein, und drücken Sie die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="f8813-136">To view information about all your external access policies, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
    `Get-CsExternalAccessPolicy`
    
    <span data-ttu-id="f8813-137">Es werden etwa folgende Informationen zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="f8813-137">This command returns information similar to the following:</span></span>
    
    ```console
    Identity                          : Global
    Description                       :
    EnableFederationAccess            : False
    EnableXmppAccess                  : False
    EnablePublicCloudAccess           : False
    EnablePublicCloudAudioVideoAccess : False
    EnableOutsideAccess               : False
    ```
