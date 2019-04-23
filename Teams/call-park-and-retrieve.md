---
title: Parken und Fortsetzen von Anrufen in Microsoft Teams
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 04/12/2019
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Verwenden Sie Parken und fortsetzen, um einen Anruf in der Warteschleife im Dienst Teams in der Cloud.
ms.openlocfilehash: 798e53ef9a0638be659da8567419b7bd3d3c3555
ms.sourcegitcommit: 920a7dbdc2a0ede94d0a4bd573c01a1ccd838b7e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "31993502"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a><span data-ttu-id="f3a71-103">Parken und Fortsetzen von Anrufen in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f3a71-103">Call park and retrieve in Microsoft Teams</span></span>

<span data-ttu-id="f3a71-104">Parken und Fortsetzen von Anrufen ist ein Feature, in dem einen Benutzer einen Anruf in der Warteschleife im Dienst Teams in der Cloud.</span><span class="sxs-lookup"><span data-stu-id="f3a71-104">Call park and retrieve is a feature that lets a user place a call on hold in the Teams service in the cloud.</span></span> <span data-ttu-id="f3a71-105">Wenn Sie ein Anruf geparkt wurde, erstellt der Dienst einen eindeutigen Code für den Abruf von Anrufen.</span><span class="sxs-lookup"><span data-stu-id="f3a71-105">When a call is parked, the service generates a unique code for call retrieval.</span></span> <span data-ttu-id="f3a71-106">Der Benutzer, der den Anruf oder eine andere Person geparkt kann dann Code und einen unterstützten app oder ein Gerät verwenden, um den Anruf abzurufen.</span><span class="sxs-lookup"><span data-stu-id="f3a71-106">The user who parked the call or someone else can then use that code and a supported app or device to retrieve the call.</span></span> 

<span data-ttu-id="f3a71-107">Einige häufigen Szenarien für die Verwendung des Parkens von Anrufen werden:</span><span class="sxs-lookup"><span data-stu-id="f3a71-107">Some of the common scenarios for using call park are:</span></span> 

- <span data-ttu-id="f3a71-108">Ein Empfangsmitarbeiter parks einen Anruf nach einer Person in einer Factory arbeiten.</span><span class="sxs-lookup"><span data-stu-id="f3a71-108">A receptionist parks a call for someone working in a factory.</span></span> <span data-ttu-id="f3a71-109">Die Empfangsmitarbeiter Ankündigung klicken Sie dann den Anruf und die Anzahl von Code über das öffentliche Adresse-System.</span><span class="sxs-lookup"><span data-stu-id="f3a71-109">The receptionist then announces the call and the code number over the public address system.</span></span> <span data-ttu-id="f3a71-110">Klicken Sie dann kann der Benutzer, die der Anruf ist ein Telefon Teams werksseitige aufzunehmen und geben Sie den Code, um den Anruf entgegenzunehmen.</span><span class="sxs-lookup"><span data-stu-id="f3a71-110">The user who the call is for can then pick up a Teams phone on the factory floor and enter the code to retrieve the call.</span></span>
- <span data-ttu-id="f3a71-111">Ein Benutzer parks ein Anrufs auf einem mobilen Gerät, da die Batterie Gerät nicht mehr genug Power vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="f3a71-111">A user parks a call on a mobile device because the device battery is running out of power.</span></span> <span data-ttu-id="f3a71-112">Der Benutzer kann dann den Code zum Abrufen des Anrufs von einem Telefonapparat Teams eingeben.</span><span class="sxs-lookup"><span data-stu-id="f3a71-112">The user can then enter the code to retrieve the call from a Teams desk phone.</span></span>
- <span data-ttu-id="f3a71-113">Eine repräsentative Parks Unterstützung ein Kunden aufrufen und sendet eine Ankündigung in einem Kanal Teams für einen Experten So rufen Sie den Anruf und helfen Sie dem Kunden.</span><span class="sxs-lookup"><span data-stu-id="f3a71-113">A support representative parks a customer call and sends an announcement on a Teams channel for an expert to retrieve the call and help the customer.</span></span> <span data-ttu-id="f3a71-114">Gibt den Code ein Experte in Teams-Clients, um den Anruf</span><span class="sxs-lookup"><span data-stu-id="f3a71-114">An expert enters the code in Teams clients to retrieve the call</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f3a71-115">Dieses Feature ist nur im Modus nur Teams Bereitstellung zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="f3a71-115">This feature is only available in Teams Only deployment mode.</span></span> <span data-ttu-id="f3a71-116">Weitere Informationen zu Bereitstellungsmethoden Teams finden Sie unter [Grundlegendes zu Microsoft-Teams und Skype für Interoperabilität und Koexistenz Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="f3a71-116">For more information about Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="f3a71-117">Lizenz erforderlich</span><span class="sxs-lookup"><span data-stu-id="f3a71-117">License required</span></span>

<span data-ttu-id="f3a71-118">Um Parken und Anrufe wiederaufnehmen, muss ein Benutzer einen Enterprise-VoIP-Benutzer sein, und ein Administrator muss dem Benutzer eine Anruf Parken Richtlinie erteilen.</span><span class="sxs-lookup"><span data-stu-id="f3a71-118">To park and retrieve calls, a user must be an Enterprise Voice user, and an administrator must grant the user a call park policy.</span></span> <span data-ttu-id="f3a71-119">Weitere Informationen zu am Lizenzierungsmodell finden Sie unter [Office 365-Lizenzierung für Microsoft-Teams](office-365-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="f3a71-119">For more information about the licensing model, see [Office 365 licensing for Microsoft Teams](office-365-licensing.md).</span></span>

## <a name="call-park-and-retrieve-feature-availability"></a><span data-ttu-id="f3a71-120">Parken und Fortsetzen der Verfügbarkeit von Features</span><span class="sxs-lookup"><span data-stu-id="f3a71-120">Call park and retrieve feature availability</span></span>

<span data-ttu-id="f3a71-121">Parken und fortsetzen wird durch die folgenden Clients und Geräten derzeit unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f3a71-121">Call park and retrieve is currently supported by the following clients and devices.</span></span> <span data-ttu-id="f3a71-122">(Unterstützt nur Teams Modus mit oder ohne PSTN-Anbindung.)</span><span class="sxs-lookup"><span data-stu-id="f3a71-122">(Supported in Teams Only mode, with or without PSTN connectivity.)</span></span>

| <span data-ttu-id="f3a71-123">Funktion</span><span class="sxs-lookup"><span data-stu-id="f3a71-123">Capability</span></span> | <span data-ttu-id="f3a71-124">Teams Desktop</span><span class="sxs-lookup"><span data-stu-id="f3a71-124">Teams Desktop</span></span> | <span data-ttu-id="f3a71-125">Teams Mac-App</span><span class="sxs-lookup"><span data-stu-id="f3a71-125">Teams Mac App</span></span> | <span data-ttu-id="f3a71-126">Teams Web App (Edge)</span><span class="sxs-lookup"><span data-stu-id="f3a71-126">Teams Web App (Edge)</span></span> |<span data-ttu-id="f3a71-127">Mobile-iOS/Android-App-Teams</span><span class="sxs-lookup"><span data-stu-id="f3a71-127">Teams mobile iOS/Android App</span></span> | <span data-ttu-id="f3a71-128">Teams IP-Telefon</span><span class="sxs-lookup"><span data-stu-id="f3a71-128">Teams IP phone</span></span> | <span data-ttu-id="f3a71-129">Skype für Business IP-Telefon</span><span class="sxs-lookup"><span data-stu-id="f3a71-129">Skype for Business IP phone</span></span> |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|-----------------------------|
| <span data-ttu-id="f3a71-130">Parken eines Anrufs</span><span class="sxs-lookup"><span data-stu-id="f3a71-130">Park a call</span></span> | <span data-ttu-id="f3a71-131">Ja</span><span class="sxs-lookup"><span data-stu-id="f3a71-131">Yes</span></span> | <span data-ttu-id="f3a71-132">Ja</span><span class="sxs-lookup"><span data-stu-id="f3a71-132">Yes</span></span> | <span data-ttu-id="f3a71-133">Ja</span><span class="sxs-lookup"><span data-stu-id="f3a71-133">Yes</span></span> | <span data-ttu-id="f3a71-134">Ja</span><span class="sxs-lookup"><span data-stu-id="f3a71-134">Yes</span></span> | <span data-ttu-id="f3a71-135">In Kürze verfügbar</span><span class="sxs-lookup"><span data-stu-id="f3a71-135">Coming soon</span></span>| <span data-ttu-id="f3a71-136">Nein</span><span class="sxs-lookup"><span data-stu-id="f3a71-136">No</span></span> |
| <span data-ttu-id="f3a71-137">Abrufen eines geparkten Anrufs</span><span class="sxs-lookup"><span data-stu-id="f3a71-137">Retrieve a parked call</span></span> | <span data-ttu-id="f3a71-138">Ja</span><span class="sxs-lookup"><span data-stu-id="f3a71-138">Yes</span></span> | <span data-ttu-id="f3a71-139">Ja</span><span class="sxs-lookup"><span data-stu-id="f3a71-139">Yes</span></span> | <span data-ttu-id="f3a71-140">Ja</span><span class="sxs-lookup"><span data-stu-id="f3a71-140">Yes</span></span> | <span data-ttu-id="f3a71-141">Ja</span><span class="sxs-lookup"><span data-stu-id="f3a71-141">Yes</span></span> | <span data-ttu-id="f3a71-142">In Kürze verfügbar</span><span class="sxs-lookup"><span data-stu-id="f3a71-142">Coming soon</span></span>| <span data-ttu-id="f3a71-143">Nein</span><span class="sxs-lookup"><span data-stu-id="f3a71-143">No</span></span> |
| <span data-ttu-id="f3a71-144">Nicht abgerufen Anruf Ring zurück</span><span class="sxs-lookup"><span data-stu-id="f3a71-144">Unretrieved call ring back</span></span> | <span data-ttu-id="f3a71-145">Ja</span><span class="sxs-lookup"><span data-stu-id="f3a71-145">Yes</span></span> | <span data-ttu-id="f3a71-146">Ja</span><span class="sxs-lookup"><span data-stu-id="f3a71-146">Yes</span></span> | <span data-ttu-id="f3a71-147">Ja</span><span class="sxs-lookup"><span data-stu-id="f3a71-147">Yes</span></span> | <span data-ttu-id="f3a71-148">Ja</span><span class="sxs-lookup"><span data-stu-id="f3a71-148">Yes</span></span> | <span data-ttu-id="f3a71-149">In Kürze verfügbar</span><span class="sxs-lookup"><span data-stu-id="f3a71-149">Coming soon</span></span>| <span data-ttu-id="f3a71-150">Nein</span><span class="sxs-lookup"><span data-stu-id="f3a71-150">No</span></span> |

## <a name="configuring-call-park-and-retrieve"></a><span data-ttu-id="f3a71-151">Konfigurieren von Parken und fortsetzen</span><span class="sxs-lookup"><span data-stu-id="f3a71-151">Configuring call park and retrieve</span></span>

<span data-ttu-id="f3a71-152">Sie müssen ein Administrator konfigurieren Parken und fortsetzen sein, und das Feature ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="f3a71-152">You must be an administrator to configure call park and retrieve, and the feature is disabled by default.</span></span> <span data-ttu-id="f3a71-153">Sie können diese für Benutzer aktivieren und Benutzergruppen mit der Anruf Parken Richtlinie erstellen.</span><span class="sxs-lookup"><span data-stu-id="f3a71-153">You can enable it for users and create user groups using the call park policy.</span></span> <span data-ttu-id="f3a71-154">Wenn Sie eine Gruppe von Benutzern die gleiche Richtlinie zuweisen, können sie Parken und Anrufe zwischen selbst abzurufen.</span><span class="sxs-lookup"><span data-stu-id="f3a71-154">When you apply the same policy to a set of users, they can park and retrieve calls among themselves.</span></span> <span data-ttu-id="f3a71-155">Zum Konfigurieren des Parkens von Anrufen für Benutzer und Benutzergruppen zum Parken von Anrufen zu erstellen, gehen Sie folgendermaßen [Zuweisen einer Richtlinie auf Anruf Parken](#assign-a-call-park-policy) .</span><span class="sxs-lookup"><span data-stu-id="f3a71-155">To configure call park for users and create call park user groups, follow the [Assign a call park policy](#assign-a-call-park-policy) procedure below.</span></span>

<span data-ttu-id="f3a71-156">Informationen zum Verwenden der Parken und Abrufen von Feature finden Sie unter [Parken eines Anrufs in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span><span class="sxs-lookup"><span data-stu-id="f3a71-156">For information about how to use the call park and retrieve feature, see [Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span></span>

### <a name="enable-a-call-park-policy"></a><span data-ttu-id="f3a71-157">Aktivieren Sie die Richtlinie ein Anruf Parken</span><span class="sxs-lookup"><span data-stu-id="f3a71-157">Enable a call park policy</span></span>

<span data-ttu-id="f3a71-158">Führen Sie diese Schritte, um eine Anruf Parken Richtlinie zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="f3a71-158">Follow these steps to enable a call park policy:</span></span>

1. <span data-ttu-id="f3a71-159">Navigieren Sie zum **Microsoft-Teams, Administrationscenter** > **VoIP** > **Richtlinien für das Parken von Anrufen**.</span><span class="sxs-lookup"><span data-stu-id="f3a71-159">Go to **Microsoft Teams admin center** > **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="f3a71-160">Wählen Sie **neue Richtlinie**aus.</span><span class="sxs-lookup"><span data-stu-id="f3a71-160">Select **New policy**.</span></span>
3. <span data-ttu-id="f3a71-161">Benennen Sie der Richtlinie, und wechseln Sie auf **aktiviert** **Park aufrufen können** .</span><span class="sxs-lookup"><span data-stu-id="f3a71-161">Give the policy a name, and then switch **Allow Call park** to **On**.</span></span>
4. <span data-ttu-id="f3a71-162">Wählen Sie **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="f3a71-162">Select **Save**.</span></span>

### <a name="assign-a-call-park-policy"></a><span data-ttu-id="f3a71-163">Zuweisen einer Richtlinie auf Anruf Parken</span><span class="sxs-lookup"><span data-stu-id="f3a71-163">Assign a call park policy</span></span>

<span data-ttu-id="f3a71-164">Führen Sie diese Schritte, um einen oder mehrere Benutzer eine Anruf Parken Richtlinie zuweisen:</span><span class="sxs-lookup"><span data-stu-id="f3a71-164">Follow these steps to assign a call park policy to one or more users:</span></span>

1. <span data-ttu-id="f3a71-165">Navigieren Sie zum **Microsoft-Teams, Administrationscenter** > **VoIP** > **Richtlinien für das Parken von Anrufen**.</span><span class="sxs-lookup"><span data-stu-id="f3a71-165">Go to **Microsoft Teams admin center** > **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="f3a71-166">Wählen Sie die Richtlinie, indem Sie auf links neben den Namen der Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="f3a71-166">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="f3a71-167">Wählen Sie **Benutzer verwalten**.</span><span class="sxs-lookup"><span data-stu-id="f3a71-167">Select **Manage users**.</span></span>
4. <span data-ttu-id="f3a71-168">Klicken Sie im Bereich **Benutzer verwalten** Suche für den Benutzer nach Anzeigename oder nach Benutzernamen, wählen Sie den Namen, und wählen Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="f3a71-168">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="f3a71-169">Wiederholen Sie diesen Schritt für jeden Benutzer, die Sie hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="f3a71-169">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="f3a71-170">Wenn Sie die Benutzer hinzugefügt haben, wählen Sie **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="f3a71-170">When you are finished adding users, select **Save**.</span></span>
 
### <a name="configure-call-park-and-retrieve-with-powershell"></a><span data-ttu-id="f3a71-171">Konfigurieren Sie des Parkens von Anrufen, und rufen Sie mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="f3a71-171">Configure call park and retrieve with PowerShell</span></span>

<span data-ttu-id="f3a71-172">Verwenden Sie das [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps) PowerShell-Cmdlet eine Anruf Parken Richtlinie erstellen.</span><span class="sxs-lookup"><span data-stu-id="f3a71-172">Use the [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet to create a call park policy.</span></span>

<span data-ttu-id="f3a71-173">Verwenden Sie das [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) PowerShell-Cmdlet, um eine Anruf Parken Richtlinie zu erteilen.</span><span class="sxs-lookup"><span data-stu-id="f3a71-173">Use the [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet to grant a call park policy.</span></span>

<span data-ttu-id="f3a71-174">Sie können die Standardeinstellung mit [Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps) wie folgt ändern:</span><span class="sxs-lookup"><span data-stu-id="f3a71-174">You can change the default setting by using [Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps) as follows:</span></span>

`Set-CsTeamsCallParkPolicy -Identity Global -AllowCallPark $true`


## <a name="troubleshooting"></a><span data-ttu-id="f3a71-175">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="f3a71-175">Troubleshooting</span></span>

<span data-ttu-id="f3a71-176">Wenn Benutzer nicht finden Sie unter der Park oder Schaltfläche abzurufen:</span><span class="sxs-lookup"><span data-stu-id="f3a71-176">If users can’t see the park or retrieve button:</span></span> 

- <span data-ttu-id="f3a71-177">Überprüfen Sie, dass der Benutzer die Richtlinie zum Parken von Anrufen aktiviert hat.</span><span class="sxs-lookup"><span data-stu-id="f3a71-177">Check that the user has the Call Park policy enabled.</span></span> 

<span data-ttu-id="f3a71-178">Wenn ein Benutzer versucht, einen Anruf abzurufen und nicht erfolgreich ist, überprüfen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="f3a71-178">If a user attempts to retrieve a call and is unsuccessful, check the following:</span></span>

- <span data-ttu-id="f3a71-179">Stellen Sie sicher, dass der Benutzer den Client Teams oder ein Teams-aktivierten Gerät/Telefon verwendet wird</span><span class="sxs-lookup"><span data-stu-id="f3a71-179">Verify that the user is using the Teams client or a Teams-enabled device/Phone</span></span>
- <span data-ttu-id="f3a71-180">Gruppierung – ist der Benutzer ein Mitglied der Gruppe der Anruf Parken.</span><span class="sxs-lookup"><span data-stu-id="f3a71-180">Grouping – is the user a member of the call park group?</span></span>
- <span data-ttu-id="f3a71-181">Island-Modus – Parken und fortsetzen ist im Teams Island Modus nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f3a71-181">Island mode – Call park and retrieve is unavailable in Teams island mode.</span></span>
- <span data-ttu-id="f3a71-182">Der Anruf wurde bereits abgerufen oder beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="f3a71-182">The call has already been retrieved or terminated.</span></span>

## <a name="more-information"></a><span data-ttu-id="f3a71-183">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f3a71-183">More information</span></span>

<span data-ttu-id="f3a71-184">[Parken eines Anrufs in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span><span class="sxs-lookup"><span data-stu-id="f3a71-184">[Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span></span>