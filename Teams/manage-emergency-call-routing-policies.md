---
title: Verwalten von Notfall-Anrufweiterleitungsrichtlinien
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Hier erfahren Sie, wie Sie in Microsoft Teams Notruf-Routing Richtlinien verwenden und verwalten, um Notrufnummern einzurichten und festzulegen, wie Notrufe weitergeleitet werden.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.openlocfilehash: 67ef3bb5700c223f3057ef0ba44c9df07a2e7be6
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217696"
---
# <a name="manage-emergency-call-routing-policies-in-microsoft-teams"></a><span data-ttu-id="1d1d9-103">Verwalten von Notfall Anruf-Routing Richtlinien in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1d1d9-103">Manage emergency call routing policies in Microsoft Teams</span></span>

<span data-ttu-id="1d1d9-104">Wenn Sie in Ihrer Organisation ein [Direktes Routing für Telefonsysteme](direct-routing-landing-page.md) bereitgestellt haben, können Sie in Microsoft Teams Notfall-Anruf Weiterleitungsrichtlinien verwenden, um Notrufnummern einzurichten und festzulegen, wie Notrufe weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="1d1d9-104">If you've deployed [Phone System Direct Routing](direct-routing-landing-page.md) in your organization, you can use emergency call routing policies in Microsoft Teams to set up emergency numbers and specify how emergency calls are routed.</span></span> <span data-ttu-id="1d1d9-105">Eine Notruf Routing-Richtlinie legt fest, ob erweiterte Notfalldienste für Benutzer aktiviert sind, denen die Richtlinie zugewiesen ist, die Nummern, mit denen Notrufdienste aufgerufen werden (beispielsweise 911 in den USA) und wie Anrufe an Notfalldienste weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="1d1d9-105">An emergency call routing policy determines whether enhanced emergency services is enabled for users who are assigned the policy, the numbers used to call emergency services (for example, 911 in the United States), and how calls to emergency services are routed.</span></span>

<span data-ttu-id="1d1d9-106">Sie verwalten Notruf Routing Richtlinien, indem Sie **Voice**  >  im Microsoft Teams Admin Center oder mithilfe von Windows PowerShell zu VoIP-**Notfall Richtlinien** wechseln.</span><span class="sxs-lookup"><span data-stu-id="1d1d9-106">You manage emergency call routing policies by going to **Voice** > **Emergency policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span> <span data-ttu-id="1d1d9-107">Die Richtlinien können Benutzern und [Netzwerk Websites](cloud-voice-network-settings.md)zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="1d1d9-107">The policies can be assigned to users and [network sites](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="1d1d9-108">Für Benutzer können Sie die globale (organisationsweite Standardrichtlinie) verwenden oder benutzerdefinierte Richtlinien erstellen und zuweisen.</span><span class="sxs-lookup"><span data-stu-id="1d1d9-108">For users, you can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="1d1d9-109">Benutzer erhalten automatisch die globale Richtlinie, es sei denn, Sie erstellen eine benutzerdefinierte Richtlinie und weisen diese zu.</span><span class="sxs-lookup"><span data-stu-id="1d1d9-109">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="1d1d9-110">Beachten Sie, dass Sie die Einstellungen in der globalen Richtlinie bearbeiten, aber nicht umbenennen oder löschen können.</span><span class="sxs-lookup"><span data-stu-id="1d1d9-110">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span> <span data-ttu-id="1d1d9-111">Für Netzwerk Websites erstellen und zuweisen Sie benutzerdefinierte Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="1d1d9-111">For network sites, you create and assign custom policies.</span></span>

<span data-ttu-id="1d1d9-112">Wenn Sie einer Netzwerk Website und einem Benutzer eine Notfall Anruf-Routing Richtlinie zugewiesen haben und sich dieser Benutzer an dieser Netzwerk Website befindet, überschreibt die der Netzwerk Website zugewiesene Richtlinie die Richtlinie, die dem Benutzer zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="1d1d9-112">If you assigned an emergency call routing policy to a network site and to a user and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="create-a-custom-emergency-call-routing-policy"></a><span data-ttu-id="1d1d9-113">Erstellen einer benutzerdefinierten Routing Richtlinie für Notfallanrufe</span><span class="sxs-lookup"><span data-stu-id="1d1d9-113">Create a custom emergency call routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="1d1d9-114">Verwenden des Microsoft Teams Admin Centers</span><span class="sxs-lookup"><span data-stu-id="1d1d9-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="1d1d9-115">Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **VoIP**-  >  **Notfall Richtlinien**, und klicken Sie dann auf die Registerkarte **Anruf Weiterleitungsrichtlinien** .</span><span class="sxs-lookup"><span data-stu-id="1d1d9-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Call routing policies** tab.</span></span>
2. <span data-ttu-id="1d1d9-116">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="1d1d9-116">Click **Add**.</span></span>
3. <span data-ttu-id="1d1d9-117">Geben Sie eine Bezeichnung und eine Beschreibung für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="1d1d9-117">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="1d1d9-118">Aktivieren Sie **dynamische**Notrufe, um dynamische Notrufe zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="1d1d9-118">To enable dynamic emergency calling, turn on **Dynamic emergency calling**.</span></span> <span data-ttu-id="1d1d9-119">Wenn dynamische Notrufe aktiviert sind, ruft Teams Richtlinien-und Standortinformationen vom Dienst ab und enthält diese Informationen im Rahmen des Notrufs.</span><span class="sxs-lookup"><span data-stu-id="1d1d9-119">When dynamic emergency calling is enabled, Teams retrieves policy and location information from the service and includes that information as part of the emergency call.</span></span>
5. <span data-ttu-id="1d1d9-120">Definieren Sie eine oder mehrere Notfallnummern.</span><span class="sxs-lookup"><span data-stu-id="1d1d9-120">Define one or more emergency numbers.</span></span> <span data-ttu-id="1d1d9-121">Klicken Sie dazu unter **Notrufnummern**auf **Hinzufügen**, und gehen Sie dann folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="1d1d9-121">To do this, under **Emergency numbers**, click **Add**, and then do the following:</span></span>
    1. <span data-ttu-id="1d1d9-122">**Notfall Wahl Zeichenfolge**: Geben Sie die Notrufnummer ein.</span><span class="sxs-lookup"><span data-stu-id="1d1d9-122">**Emergency dial string**: Enter the emergency dial string.</span></span> <span data-ttu-id="1d1d9-123">Diese Wählzeichenfolge zeigt an, dass ein Anruf ein Notruf ist.</span><span class="sxs-lookup"><span data-stu-id="1d1d9-123">This dial string indicates that a call is an emergency call.</span></span>
        > [!NOTE]
        > <span data-ttu-id="1d1d9-124">Für das direkte Routing wechseln wir von Teams-Clients, die Notrufe mit einem "+" vor der Notruf Zeichenfolge senden.</span><span class="sxs-lookup"><span data-stu-id="1d1d9-124">For Direct Routing, we're transitioning away from Teams clients sending emergency calls with a "+" in front of the emergency dial string.</span></span> <span data-ttu-id="1d1d9-125">Bis zum Abschluss des Übergangs sollte das VoIP-Routenmuster einer Notruf Zeichenfolge entsprechen, um sicherzustellen, dass Zeichenfolgen mit einem vorangehenden "+", wie 911 und + 911, übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="1d1d9-125">Until the transition is completed, the voice route pattern to match an emergency dial string should ensure a match is made for strings that have and don't have a preceding "+", such as 911 and +911.</span></span> <span data-ttu-id="1d1d9-126">Beispiel: ^ \\ +? 911 oder. \*.</span><span class="sxs-lookup"><span data-stu-id="1d1d9-126">For example, ^\\+?911 or .\*.</span></span>
    2. <span data-ttu-id="1d1d9-127">**Notfall-Wähl Maske**: Sie können für jede Notrufnummer NULL oder mehr Notrufnummern angeben.</span><span class="sxs-lookup"><span data-stu-id="1d1d9-127">**Emergency dial mask**: For each emergency number, you can specify zero or more emergency dial masks.</span></span> <span data-ttu-id="1d1d9-128">Eine Wähl Maske ist die Nummer, die Sie in den Wert der Notruf-Wählzeichenfolge übersetzen möchten.</span><span class="sxs-lookup"><span data-stu-id="1d1d9-128">A dial mask is the number that you want to translate into the value of the emergency dial string.</span></span> <span data-ttu-id="1d1d9-129">Auf diese Weise können alternative Notrufnummern gewählt werden, und der Anruf kann auch Notfalldienste erreichen.</span><span class="sxs-lookup"><span data-stu-id="1d1d9-129">This allows for alternate emergency numbers to be dialed and still have the call reach emergency services.</span></span> <br><span data-ttu-id="1d1d9-130">Beispielsweise fügen Sie 112 als Notruf Maske hinzu, bei der es sich um die Notrufnummer für die meisten Europa und 911 als Notruf Zeichenfolge handelt.</span><span class="sxs-lookup"><span data-stu-id="1d1d9-130">For example, you add 112 as the emergency dial mask, which is the emergency service number for most of Europe, and 911 as the emergency dial string.</span></span> <span data-ttu-id="1d1d9-131">Ein Team Nutzer aus Europa, der gerade besucht, weiß möglicherweise nicht, dass 911 die Notrufnummer in den Vereinigten Staaten ist, und wenn Sie 112 wählen, wird der Anruf an 911 durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="1d1d9-131">A Teams user from Europe who is visiting may not know that 911 is the emergency number in the United States, and when they dial 112, the call is made to 911.</span></span> <span data-ttu-id="1d1d9-132">Wenn Sie mehrere Wähl Masken definieren möchten, trennen Sie die einzelnen Werte durch ein Semikolon.</span><span class="sxs-lookup"><span data-stu-id="1d1d9-132">To define multiple dial masks, separate each value by a semicolon.</span></span> <span data-ttu-id="1d1d9-133">Beispiel: 112; 212.</span><span class="sxs-lookup"><span data-stu-id="1d1d9-133">For example, 112;212.</span></span>
    3. <span data-ttu-id="1d1d9-134">**PSTN-Verwendungsdaten Satz**: Wählen Sie den Eintrag für die öffentliche Telefonnetz Nutzung (PSTN) aus.</span><span class="sxs-lookup"><span data-stu-id="1d1d9-134">**PSTN usage record**: Select the Public Switched Telephone Network (PSTN) usage record.</span></span> <span data-ttu-id="1d1d9-135">Der PSTN-Nutzungsdaten Satz wird verwendet, um zu ermitteln, welche Route zur Weiterleitung von Notrufen von Benutzern verwendet wird, die zur Verwendung autorisiert sind.</span><span class="sxs-lookup"><span data-stu-id="1d1d9-135">The PSTN usage record is used to determine which route is used to route emergency calls from users who are authorized to use them.</span></span> <span data-ttu-id="1d1d9-136">Die Route, die mit dieser Verwendung verknüpft ist, sollte auf einen SIP-Stamm (Session Initiation Protocol) verweisen, der für Notrufe vorgesehen ist, oder für ein Notfall-Standort-ID (Elin)-Gateway, das Notrufe an den nächstgelegenen öffentlichen Sicherheits Beantwortungs Punkt (PSAP) weiterleitet.</span><span class="sxs-lookup"><span data-stu-id="1d1d9-136">The route associated with this usage should point to a Session Initiation Protocol (SIP) trunk dedicated to emergency calls or to an Emergency Location Identification Number (ELIN) gateway that routes emergency calls to the nearest Public Safety Answering Point (PSAP).</span></span>

    > [!NOTE]
    > <span data-ttu-id="1d1d9-137">Wählzeichenfolgen und Wähl Masken müssen innerhalb einer Richtlinie eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="1d1d9-137">Dial strings and dial masks must be unique within a policy.</span></span> <span data-ttu-id="1d1d9-138">Das bedeutet, dass Sie für eine Richtlinie mehrere Notfallnummern definieren können, und Sie können mehrere Wähl Masken für eine Wählzeichenfolge festlegen, aber jede Wählzeichenfolge und Wähl Maske darf nur einmal verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1d1d9-138">This means that for a policy, you can define multiple emergency numbers and you can set multiple dial masks for a dial string, but each dial string and dial mask must only be used one time.</span></span>

6. <span data-ttu-id="1d1d9-139">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="1d1d9-139">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="1d1d9-140">Verwendung von PowerShell</span><span class="sxs-lookup"><span data-stu-id="1d1d9-140">Using PowerShell</span></span>

<span data-ttu-id="1d1d9-141">Weitere Informationen finden Sie unter [New-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="1d1d9-141">See [New-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallroutingpolicy).</span></span>

## <a name="edit-an-emergency-call-routing-policy"></a><span data-ttu-id="1d1d9-142">Bearbeiten einer Notfall Anruf-Routing Richtlinie</span><span class="sxs-lookup"><span data-stu-id="1d1d9-142">Edit an emergency call routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="1d1d9-143">Verwenden des Microsoft Teams Admin Centers</span><span class="sxs-lookup"><span data-stu-id="1d1d9-143">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="1d1d9-144">Sie können die globale Standardrichtlinie bearbeiten oder eine von Ihnen erstellte, benutzerdefinierte Richtlinie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="1d1d9-144">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="1d1d9-145">Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **VoIP**-  >  **Notfall Richtlinien**, und klicken Sie dann auf die Registerkarte **Anruf Weiterleitungsrichtlinien** .</span><span class="sxs-lookup"><span data-stu-id="1d1d9-145">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Call routing policies** tab.</span></span>
2. <span data-ttu-id="1d1d9-146">Wählen Sie die Richtlinie aus, indem Sie zunächst links neben die Richtlinienbezeichnung und dann auf **Bearbeiten** klicken.</span><span class="sxs-lookup"><span data-stu-id="1d1d9-146">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="1d1d9-147">Nehmen Sie die gewünschten Änderungen vor, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="1d1d9-147">Make the changes that you want, and then click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="1d1d9-148">Verwendung von PowerShell</span><span class="sxs-lookup"><span data-stu-id="1d1d9-148">Using PowerShell</span></span>

<span data-ttu-id="1d1d9-149">Weitere Informationen finden Sie unter [Satz-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="1d1d9-149">See [Set-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallroutingpolicy).</span></span>

## <a name="assign-a-custom-emergency-call-routing-policy-to-users"></a><span data-ttu-id="1d1d9-150">Zuweisen einer benutzerdefinierten Notfall Routing Richtlinie für Benutzer</span><span class="sxs-lookup"><span data-stu-id="1d1d9-150">Assign a custom emergency call routing policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="1d1d9-151">Siehe auch [Grant-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="1d1d9-151">See also [Grant-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallroutingpolicy).</span></span>

## <a name="assign-a-custom-emergency-call-routing-policy-to-a-network-site"></a><span data-ttu-id="1d1d9-152">Zuweisen einer benutzerdefinierten Notfall Routing Richtlinie zu einer Netzwerk Website</span><span class="sxs-lookup"><span data-stu-id="1d1d9-152">Assign a custom emergency call routing policy to a network site</span></span>

<span data-ttu-id="1d1d9-153">Verwenden Sie das Cmdlet " [CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) ", um einer Netzwerk Website eine Notfall Anruf-Routing Richtlinie zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="1d1d9-153">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) cmdlet to assign an emergency calling routing policy to a network site.</span></span>

<span data-ttu-id="1d1d9-154">In diesem Beispiel wird gezeigt, wie der site1-Website eine Richtlinie namens "Emergency Call Routing Policy 1" zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="1d1d9-154">This example shows how to assign a policy called Emergency Call Routing Policy 1 to the Site1 site.</span></span>

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```

## <a name="related-topics"></a><span data-ttu-id="1d1d9-155">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="1d1d9-155">Related topics</span></span>

[<span data-ttu-id="1d1d9-156">Verwalten von Notruf Richtlinien in Teams</span><span class="sxs-lookup"><span data-stu-id="1d1d9-156">Manage emergency calling policies in Teams</span></span>](manage-emergency-calling-policies.md)

[<span data-ttu-id="1d1d9-157">Übersicht über PowerShell für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1d1d9-157">Teams PowerShell overview</span></span>](teams-powershell-overview.md)

[<span data-ttu-id="1d1d9-158">Zuweisen von Richtlinien zu Ihren Benutzern in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1d1d9-158">Assign policies to your users in Teams</span></span>](assign-policies.md)
