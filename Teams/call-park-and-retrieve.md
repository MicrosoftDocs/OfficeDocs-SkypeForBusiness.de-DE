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
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.callparkpolicies.overview
- seo-marvel-apr2020
description: Hier erfahren Sie, wie Sie den Anruf Park verwenden und abrufen, um einen Anruf im Teams-Dienst in der Cloud zu halten.
ms.openlocfilehash: e36690c4059ceae67c8615b1e910051439ca8e78
ms.sourcegitcommit: 09ff11f8e4f6a93cedc34a5d732a133163df79a0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44042962"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a><span data-ttu-id="0d2ef-103">Parken und Fortsetzen von Anrufen in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0d2ef-103">Call park and retrieve in Microsoft Teams</span></span>

<span data-ttu-id="0d2ef-104">Parken und Abrufen ist eine Funktion, mit der Benutzer einen Anruf im Teams-Dienst in der Cloud halten können.</span><span class="sxs-lookup"><span data-stu-id="0d2ef-104">Call park and retrieve is a feature that lets a user place a call on hold in the Teams service in the cloud.</span></span> <span data-ttu-id="0d2ef-105">Wenn ein Anruf abgestellt wird, generiert der Dienst einen eindeutigen Code für den Abruf des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="0d2ef-105">When a call is parked, the service generates a unique code for call retrieval.</span></span> <span data-ttu-id="0d2ef-106">Der Benutzer, der den Anruf abgestellt hat, oder eine andere Person kann diesen Code und eine unterstützte APP oder ein unterstütztes Gerät verwenden, um den Anruf abzurufen.</span><span class="sxs-lookup"><span data-stu-id="0d2ef-106">The user who parked the call or someone else can then use that code and a supported app or device to retrieve the call.</span></span> 

<span data-ttu-id="0d2ef-107">Einige häufige Szenarien für die Verwendung von Call Park sind:</span><span class="sxs-lookup"><span data-stu-id="0d2ef-107">Some of the common scenarios for using call park are:</span></span> 

- <span data-ttu-id="0d2ef-108">Eine Empfangsdame parkt einen Anruf für jemanden, der in einer Fabrik arbeitet.</span><span class="sxs-lookup"><span data-stu-id="0d2ef-108">A receptionist parks a call for someone working in a factory.</span></span> <span data-ttu-id="0d2ef-109">Der Rezeptionist kündigt dann den Anruf und die Codenummer über das öffentliche adresssystem an.</span><span class="sxs-lookup"><span data-stu-id="0d2ef-109">The receptionist then announces the call and the code number over the public address system.</span></span> <span data-ttu-id="0d2ef-110">Der Benutzer, für den der Anruf ansteht, kann dann in der Factory-Etage ein Team Telefon aufnehmen und den Code zum Abrufen des Anrufs eingeben.</span><span class="sxs-lookup"><span data-stu-id="0d2ef-110">The user who the call is for can then pick up a Teams phone on the factory floor and enter the code to retrieve the call.</span></span>
- <span data-ttu-id="0d2ef-111">Ein Benutzer parkt einen Anruf auf einem mobilen Gerät, da der Akku des Geräts knapp wird.</span><span class="sxs-lookup"><span data-stu-id="0d2ef-111">A user parks a call on a mobile device because the device battery is running out of power.</span></span> <span data-ttu-id="0d2ef-112">Der Benutzer kann dann den Code eingeben, um den Anruf von einem Team-Tischtelefon abzurufen.</span><span class="sxs-lookup"><span data-stu-id="0d2ef-112">The user can then enter the code to retrieve the call from a Teams desk phone.</span></span>
- <span data-ttu-id="0d2ef-113">Ein Supportmitarbeiter parkt einen Kundenanruf und sendet eine Ankündigung in einem Teams-Kanal, damit ein Experte den Anruf abruft und dem Kunden hilft.</span><span class="sxs-lookup"><span data-stu-id="0d2ef-113">A support representative parks a customer call and sends an announcement on a Teams channel for an expert to retrieve the call and help the customer.</span></span> <span data-ttu-id="0d2ef-114">Ein Experte gibt den Code in Teams-Clients ein, um den Anruf abzurufen.</span><span class="sxs-lookup"><span data-stu-id="0d2ef-114">An expert enters the code in Teams clients to retrieve the call</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0d2ef-115">Dieses Feature steht nur im Bereitstellungsmodus für Teams zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="0d2ef-115">This feature is only available in Teams Only deployment mode.</span></span> <span data-ttu-id="0d2ef-116">Weitere Informationen zu den Bereitstellungsmodi für Teams finden Sie Untergrund [Legendes zu Microsoft Teams und Skype for Business-Koexistenz und-Interoperabilität](teams-and-skypeforbusiness-coexistence-and-interoperability.md) .</span><span class="sxs-lookup"><span data-stu-id="0d2ef-116">For more information about Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="0d2ef-117">Lizenz erforderlich</span><span class="sxs-lookup"><span data-stu-id="0d2ef-117">License required</span></span>

<span data-ttu-id="0d2ef-118">Zum Parken und Abrufen von Anrufen muss ein Benutzer ein Enterprise-VoIP-Benutzer sein, und ein Administrator muss dem Benutzer eine Anruf Park Richtlinie erteilen.</span><span class="sxs-lookup"><span data-stu-id="0d2ef-118">To park and retrieve calls, a user must be an Enterprise Voice user, and an administrator must grant the user a call park policy.</span></span> <span data-ttu-id="0d2ef-119">Weitere Informationen zum Lizenzierungsmodell finden Sie in der [Microsoft Teams-Dienstbeschreibung](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span><span class="sxs-lookup"><span data-stu-id="0d2ef-119">For more information about the licensing model, see [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

## <a name="call-park-and-retrieve-feature-availability"></a><span data-ttu-id="0d2ef-120">Parken anrufen und Verfügbarkeit von Funktionen abrufen</span><span class="sxs-lookup"><span data-stu-id="0d2ef-120">Call park and retrieve feature availability</span></span>

<span data-ttu-id="0d2ef-121">Anruf parken und Abrufen wird derzeit von den folgenden Clients und Geräten unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0d2ef-121">Call park and retrieve is currently supported by the following clients and devices.</span></span> <span data-ttu-id="0d2ef-122">(Wird im Modus "nur für Teams" mit oder ohne PSTN-Konnektivität unterstützt.)</span><span class="sxs-lookup"><span data-stu-id="0d2ef-122">(Supported in Teams Only mode, with or without PSTN connectivity.)</span></span>

| <span data-ttu-id="0d2ef-123">Funktion</span><span class="sxs-lookup"><span data-stu-id="0d2ef-123">Capability</span></span> | <span data-ttu-id="0d2ef-124">Teams-Desktop</span><span class="sxs-lookup"><span data-stu-id="0d2ef-124">Teams Desktop</span></span> | <span data-ttu-id="0d2ef-125">Mac-app für Teams</span><span class="sxs-lookup"><span data-stu-id="0d2ef-125">Teams Mac App</span></span> | <span data-ttu-id="0d2ef-126">Teams Web App (Edge)</span><span class="sxs-lookup"><span data-stu-id="0d2ef-126">Teams Web App (Edge)</span></span> |<span data-ttu-id="0d2ef-127">Teams Mobile IOS/Android-App</span><span class="sxs-lookup"><span data-stu-id="0d2ef-127">Teams mobile iOS/Android App</span></span> | <span data-ttu-id="0d2ef-128">IP-Telefon für Teams</span><span class="sxs-lookup"><span data-stu-id="0d2ef-128">Teams IP phone</span></span> | <span data-ttu-id="0d2ef-129">Skype for Business-IP-Telefon</span><span class="sxs-lookup"><span data-stu-id="0d2ef-129">Skype for Business IP phone</span></span> |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|-----------------------------|
| <span data-ttu-id="0d2ef-130">Parken eines Anrufs</span><span class="sxs-lookup"><span data-stu-id="0d2ef-130">Park a call</span></span> | <span data-ttu-id="0d2ef-131">Ja</span><span class="sxs-lookup"><span data-stu-id="0d2ef-131">Yes</span></span> | <span data-ttu-id="0d2ef-132">Ja</span><span class="sxs-lookup"><span data-stu-id="0d2ef-132">Yes</span></span> | <span data-ttu-id="0d2ef-133">Ja</span><span class="sxs-lookup"><span data-stu-id="0d2ef-133">Yes</span></span> | <span data-ttu-id="0d2ef-134">Ja</span><span class="sxs-lookup"><span data-stu-id="0d2ef-134">Yes</span></span> | <span data-ttu-id="0d2ef-135">In Kürze verfügbar</span><span class="sxs-lookup"><span data-stu-id="0d2ef-135">Coming soon</span></span>| <span data-ttu-id="0d2ef-136">Nein</span><span class="sxs-lookup"><span data-stu-id="0d2ef-136">No</span></span> |
| <span data-ttu-id="0d2ef-137">Abrufen eines geparkten Anrufs</span><span class="sxs-lookup"><span data-stu-id="0d2ef-137">Retrieve a parked call</span></span> | <span data-ttu-id="0d2ef-138">Ja</span><span class="sxs-lookup"><span data-stu-id="0d2ef-138">Yes</span></span> | <span data-ttu-id="0d2ef-139">Ja</span><span class="sxs-lookup"><span data-stu-id="0d2ef-139">Yes</span></span> | <span data-ttu-id="0d2ef-140">Ja</span><span class="sxs-lookup"><span data-stu-id="0d2ef-140">Yes</span></span> | <span data-ttu-id="0d2ef-141">Ja</span><span class="sxs-lookup"><span data-stu-id="0d2ef-141">Yes</span></span> | <span data-ttu-id="0d2ef-142">In Kürze verfügbar</span><span class="sxs-lookup"><span data-stu-id="0d2ef-142">Coming soon</span></span>| <span data-ttu-id="0d2ef-143">Nein</span><span class="sxs-lookup"><span data-stu-id="0d2ef-143">No</span></span> |
| <span data-ttu-id="0d2ef-144">Nicht abgerufener Anruf Ring zurück</span><span class="sxs-lookup"><span data-stu-id="0d2ef-144">Unretrieved call ring back</span></span> | <span data-ttu-id="0d2ef-145">Ja</span><span class="sxs-lookup"><span data-stu-id="0d2ef-145">Yes</span></span> | <span data-ttu-id="0d2ef-146">Ja</span><span class="sxs-lookup"><span data-stu-id="0d2ef-146">Yes</span></span> | <span data-ttu-id="0d2ef-147">Ja</span><span class="sxs-lookup"><span data-stu-id="0d2ef-147">Yes</span></span> | <span data-ttu-id="0d2ef-148">Ja</span><span class="sxs-lookup"><span data-stu-id="0d2ef-148">Yes</span></span> | <span data-ttu-id="0d2ef-149">In Kürze verfügbar</span><span class="sxs-lookup"><span data-stu-id="0d2ef-149">Coming soon</span></span>| <span data-ttu-id="0d2ef-150">Nein</span><span class="sxs-lookup"><span data-stu-id="0d2ef-150">No</span></span> |

## <a name="configuring-call-park-and-retrieve"></a><span data-ttu-id="0d2ef-151">Konfigurieren des Anruf Parks und Abrufen</span><span class="sxs-lookup"><span data-stu-id="0d2ef-151">Configuring call park and retrieve</span></span>

<span data-ttu-id="0d2ef-152">Sie müssen ein Administrator sein, um den Anruf Park zu konfigurieren und abzurufen, und das Feature ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="0d2ef-152">You must be an administrator to configure call park and retrieve, and the feature is disabled by default.</span></span> <span data-ttu-id="0d2ef-153">Sie können es für Benutzer aktivieren und Benutzergruppen mithilfe der Anruf Park Richtlinie erstellen.</span><span class="sxs-lookup"><span data-stu-id="0d2ef-153">You can enable it for users and create user groups using the call park policy.</span></span> <span data-ttu-id="0d2ef-154">Wenn Sie die gleiche Richtlinie auf eine Reihe von Benutzern anwenden, können Sie Anrufe unter sich selbst Parken und abrufen.</span><span class="sxs-lookup"><span data-stu-id="0d2ef-154">When you apply the same policy to a set of users, they can park and retrieve calls among themselves.</span></span> <span data-ttu-id="0d2ef-155">Zum Konfigurieren des Anruf Parks für Benutzer und zum Erstellen von Benutzergruppen für den Anruf Park befolgen Sie die nachstehenden Schritte zum [Zuweisen einer Anruf Park Richtlinie](#assign-a-call-park-policy) .</span><span class="sxs-lookup"><span data-stu-id="0d2ef-155">To configure call park for users and create call park user groups, follow the [Assign a call park policy](#assign-a-call-park-policy) procedure below.</span></span>

<span data-ttu-id="0d2ef-156">Informationen zum Verwenden der Funktion "Parken und abrufen" finden Sie unter [Parken eines Anrufs in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span><span class="sxs-lookup"><span data-stu-id="0d2ef-156">For information about how to use the call park and retrieve feature, see [Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span></span>

### <a name="enable-a-call-park-policy"></a><span data-ttu-id="0d2ef-157">Aktivieren einer Anruf Park Richtlinie</span><span class="sxs-lookup"><span data-stu-id="0d2ef-157">Enable a call park policy</span></span>

<span data-ttu-id="0d2ef-158">Führen Sie die folgenden Schritte aus, um eine Anruf Park Richtlinie zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="0d2ef-158">Follow these steps to enable a call park policy:</span></span>

1. <span data-ttu-id="0d2ef-159">Wechseln Sie zu den Richtlinien für**VoIP** > -**Anruf Park des** **Microsoft Teams Admin Center** > .</span><span class="sxs-lookup"><span data-stu-id="0d2ef-159">Go to **Microsoft Teams admin center** > **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="0d2ef-160">Wählen Sie **neue Richtlinie**aus.</span><span class="sxs-lookup"><span data-stu-id="0d2ef-160">Select **New policy**.</span></span>
3. <span data-ttu-id="0d2ef-161">Geben Sie der Richtlinie einen Namen, und wählen Sie dann "Parken **von** **anrufen zulassen** " auf ein.</span><span class="sxs-lookup"><span data-stu-id="0d2ef-161">Give the policy a name, and then switch **Allow Call park** to **On**.</span></span>
4. <span data-ttu-id="0d2ef-162">Wählen Sie **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="0d2ef-162">Select **Save**.</span></span>

### <a name="assign-a-call-park-policy"></a><span data-ttu-id="0d2ef-163">Zuweisen einer Anruf Park Richtlinie</span><span class="sxs-lookup"><span data-stu-id="0d2ef-163">Assign a call park policy</span></span>

<span data-ttu-id="0d2ef-164">Führen Sie die folgenden Schritte aus, um einem oder mehreren Benutzern eine Anruf Park Richtlinie zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="0d2ef-164">Follow these steps to assign a call park policy to one or more users:</span></span>

1. <span data-ttu-id="0d2ef-165">Wechseln Sie zu den Richtlinien für**VoIP** > -**Anruf Park des** **Microsoft Teams Admin Center** > .</span><span class="sxs-lookup"><span data-stu-id="0d2ef-165">Go to **Microsoft Teams admin center** > **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="0d2ef-166">Wählen Sie die gewünschte Richtlinie aus, indem Sie links neben die Richtlinienbezeichnung klicken.</span><span class="sxs-lookup"><span data-stu-id="0d2ef-166">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="0d2ef-167">Wählen Sie **Benutzer verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="0d2ef-167">Select **Manage users**.</span></span>
4. <span data-ttu-id="0d2ef-168">Suchen Sie im Bereich **Benutzer verwalten** anhand des Anzeigenamens oder des Benutzernamens nach dem Benutzer, wählen Sie den Namen aus, und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="0d2ef-168">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="0d2ef-169">Wiederholen Sie diesen Schritt für jeden Benutzer, den Sie hinzufügen wollen.</span><span class="sxs-lookup"><span data-stu-id="0d2ef-169">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="0d2ef-170">Wenn Sie fertig sind, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="0d2ef-170">When you are finished adding users, select **Save**.</span></span>
 
### <a name="configure-call-park-and-retrieve-with-powershell"></a><span data-ttu-id="0d2ef-171">Konfigurieren des Anruf Parks und Abrufen mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="0d2ef-171">Configure call park and retrieve with PowerShell</span></span>

<span data-ttu-id="0d2ef-172">Verwenden Sie das PowerShell [-Cmdlet New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps) , um eine Anruf Park Richtlinie zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0d2ef-172">Use the [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet to create a call park policy.</span></span>

<span data-ttu-id="0d2ef-173">Verwenden Sie das PowerShell [-Cmdlet Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) , um eine Anruf Park Richtlinie zu erteilen.</span><span class="sxs-lookup"><span data-stu-id="0d2ef-173">Use the [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet to grant a call park policy.</span></span>

<span data-ttu-id="0d2ef-174">Sie können die Standardeinstellung mithilfe von [CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps) wie folgt ändern:</span><span class="sxs-lookup"><span data-stu-id="0d2ef-174">You can change the default setting by using [Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps) as follows:</span></span>

`Set-CsTeamsCallParkPolicy -Identity Global -AllowCallPark $true`


## <a name="troubleshooting"></a><span data-ttu-id="0d2ef-175">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="0d2ef-175">Troubleshooting</span></span>

<span data-ttu-id="0d2ef-176">Wenn Benutzer die Schaltfläche "Parken" oder "abrufen" nicht sehen können:</span><span class="sxs-lookup"><span data-stu-id="0d2ef-176">If users can't see the park or retrieve button:</span></span> 

- <span data-ttu-id="0d2ef-177">Überprüfen Sie, ob der Benutzer die Anruf Park Richtlinie aktiviert hat.</span><span class="sxs-lookup"><span data-stu-id="0d2ef-177">Check that the user has the Call Park policy enabled.</span></span> 

<span data-ttu-id="0d2ef-178">Wenn ein Benutzer versucht, einen Anruf abzurufen und nicht erfolgreich ist, überprüfen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="0d2ef-178">If a user attempts to retrieve a call and is unsuccessful, check the following:</span></span>

- <span data-ttu-id="0d2ef-179">Überprüfen, ob der Benutzer den Teams-Client oder ein Team fähiges Gerät/Telefon verwendet</span><span class="sxs-lookup"><span data-stu-id="0d2ef-179">Verify that the user is using the Teams client or a Teams-enabled device/Phone</span></span>
- <span data-ttu-id="0d2ef-180">Gruppieren – ist der Benutzer ein Mitglied der Gruppe "Anruf parken", die darauf basiert, dass dieselbe Teams-Anruf Park Richtlinie zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="0d2ef-180">Grouping – is the user a member of the call park group, which is based on having the same Teams Call Park policy assigned.</span></span> 
- <span data-ttu-id="0d2ef-181">Island-Modus – Parken und Abrufen von anrufen ist im Modus "Teams Island" nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0d2ef-181">Island mode – Call park and retrieve is unavailable in Teams island mode.</span></span>
- <span data-ttu-id="0d2ef-182">Der Anruf wurde bereits abgerufen oder beendet.</span><span class="sxs-lookup"><span data-stu-id="0d2ef-182">The call has already been retrieved or terminated.</span></span>

## <a name="more-information"></a><span data-ttu-id="0d2ef-183">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0d2ef-183">More information</span></span>

<span data-ttu-id="0d2ef-184">[Parken eines Anrufs in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span><span class="sxs-lookup"><span data-stu-id="0d2ef-184">[Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span></span>
