---
title: Parken und Fortsetzen von Anrufen in Microsoft Teams
ms.author: serdars
author: SerdarSoysal
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
ms.openlocfilehash: 8c6f275ea1b1aac9bfa011fba76d17aeb1811e10
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2020
ms.locfileid: "46582652"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a><span data-ttu-id="95a07-103">Parken und Fortsetzen von Anrufen in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="95a07-103">Call park and retrieve in Microsoft Teams</span></span>

<span data-ttu-id="95a07-104">Parken und Abrufen ist eine Funktion, mit der Benutzer einen Anruf im Teams-Dienst in der Cloud halten können.</span><span class="sxs-lookup"><span data-stu-id="95a07-104">Call park and retrieve is a feature that lets a user place a call on hold in the Teams service in the cloud.</span></span> <span data-ttu-id="95a07-105">Wenn ein Anruf abgestellt wird, generiert der Dienst einen eindeutigen Code für den Abruf des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="95a07-105">When a call is parked, the service generates a unique code for call retrieval.</span></span> <span data-ttu-id="95a07-106">Der Benutzer, der den Anruf abgestellt hat, oder eine andere Person kann diesen Code und eine unterstützte APP oder ein unterstütztes Gerät verwenden, um den Anruf abzurufen.</span><span class="sxs-lookup"><span data-stu-id="95a07-106">The user who parked the call or someone else can then use that code and a supported app or device to retrieve the call.</span></span> 

<span data-ttu-id="95a07-107">Einige häufige Szenarien für die Verwendung von Call Park sind:</span><span class="sxs-lookup"><span data-stu-id="95a07-107">Some of the common scenarios for using call park are:</span></span> 

- <span data-ttu-id="95a07-108">Eine Empfangsdame parkt einen Anruf für jemanden, der in einer Fabrik arbeitet.</span><span class="sxs-lookup"><span data-stu-id="95a07-108">A receptionist parks a call for someone working in a factory.</span></span> <span data-ttu-id="95a07-109">Der Rezeptionist kündigt dann den Anruf und die Codenummer über das öffentliche adresssystem an.</span><span class="sxs-lookup"><span data-stu-id="95a07-109">The receptionist then announces the call and the code number over the public address system.</span></span> <span data-ttu-id="95a07-110">Der Benutzer, für den der Anruf ansteht, kann dann in der Factory-Etage ein Team Telefon aufnehmen und den Code zum Abrufen des Anrufs eingeben.</span><span class="sxs-lookup"><span data-stu-id="95a07-110">The user who the call is for can then pick up a Teams phone on the factory floor and enter the code to retrieve the call.</span></span>
- <span data-ttu-id="95a07-111">Ein Benutzer parkt einen Anruf auf einem mobilen Gerät, da der Akku des Geräts knapp wird.</span><span class="sxs-lookup"><span data-stu-id="95a07-111">A user parks a call on a mobile device because the device battery is running out of power.</span></span> <span data-ttu-id="95a07-112">Der Benutzer kann dann den Code eingeben, um den Anruf von einem Team-Tischtelefon abzurufen.</span><span class="sxs-lookup"><span data-stu-id="95a07-112">The user can then enter the code to retrieve the call from a Teams desk phone.</span></span>
- <span data-ttu-id="95a07-113">Ein Supportmitarbeiter parkt einen Kundenanruf und sendet eine Ankündigung in einem Teams-Kanal, damit ein Experte den Anruf abruft und dem Kunden hilft.</span><span class="sxs-lookup"><span data-stu-id="95a07-113">A support representative parks a customer call and sends an announcement on a Teams channel for an expert to retrieve the call and help the customer.</span></span> <span data-ttu-id="95a07-114">Ein Experte gibt den Code in Teams-Clients ein, um den Anruf abzurufen.</span><span class="sxs-lookup"><span data-stu-id="95a07-114">An expert enters the code in Teams clients to retrieve the call</span></span>

> [!IMPORTANT]
> <span data-ttu-id="95a07-115">Dieses Feature steht nur im Bereitstellungsmodus für Teams zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="95a07-115">This feature is only available in Teams Only deployment mode.</span></span> <span data-ttu-id="95a07-116">Weitere Informationen zu den Bereitstellungsmodi für Teams finden Sie Untergrund [Legendes zu Microsoft Teams und Skype for Business-Koexistenz und-Interoperabilität](teams-and-skypeforbusiness-coexistence-and-interoperability.md) .</span><span class="sxs-lookup"><span data-stu-id="95a07-116">For more information about Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="95a07-117">Lizenz erforderlich</span><span class="sxs-lookup"><span data-stu-id="95a07-117">License required</span></span>

<span data-ttu-id="95a07-118">Zum Parken und Abrufen von Anrufen muss ein Benutzer ein Enterprise-VoIP-Benutzer sein, und ein Administrator muss dem Benutzer eine Anruf Park Richtlinie erteilen.</span><span class="sxs-lookup"><span data-stu-id="95a07-118">To park and retrieve calls, a user must be an Enterprise Voice user, and an administrator must grant the user a call park policy.</span></span> <span data-ttu-id="95a07-119">Weitere Informationen zum Lizenzierungsmodell finden Sie in der [Microsoft Teams-Dienstbeschreibung](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span><span class="sxs-lookup"><span data-stu-id="95a07-119">For more information about the licensing model, see [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

## <a name="call-park-and-retrieve-feature-availability"></a><span data-ttu-id="95a07-120">Parken anrufen und Verfügbarkeit von Funktionen abrufen</span><span class="sxs-lookup"><span data-stu-id="95a07-120">Call park and retrieve feature availability</span></span>

<span data-ttu-id="95a07-121">Anruf parken und Abrufen wird derzeit von den folgenden Clients und Geräten unterstützt.</span><span class="sxs-lookup"><span data-stu-id="95a07-121">Call park and retrieve is currently supported by the following clients and devices.</span></span> <span data-ttu-id="95a07-122">(Wird im Modus "nur für Teams" mit oder ohne PSTN-Konnektivität unterstützt.)</span><span class="sxs-lookup"><span data-stu-id="95a07-122">(Supported in Teams Only mode, with or without PSTN connectivity.)</span></span>

| <span data-ttu-id="95a07-123">Funktion</span><span class="sxs-lookup"><span data-stu-id="95a07-123">Capability</span></span> | <span data-ttu-id="95a07-124">Teams-Desktop</span><span class="sxs-lookup"><span data-stu-id="95a07-124">Teams Desktop</span></span> | <span data-ttu-id="95a07-125">Mac-app für Teams</span><span class="sxs-lookup"><span data-stu-id="95a07-125">Teams Mac App</span></span> | <span data-ttu-id="95a07-126">Teams Web App (Edge)</span><span class="sxs-lookup"><span data-stu-id="95a07-126">Teams Web App (Edge)</span></span> |<span data-ttu-id="95a07-127">Teams Mobile IOS/Android-App</span><span class="sxs-lookup"><span data-stu-id="95a07-127">Teams mobile iOS/Android App</span></span> | <span data-ttu-id="95a07-128">IP-Telefon für Teams</span><span class="sxs-lookup"><span data-stu-id="95a07-128">Teams IP phone</span></span> | <span data-ttu-id="95a07-129">Skype for Business-IP-Telefon</span><span class="sxs-lookup"><span data-stu-id="95a07-129">Skype for Business IP phone</span></span> |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|-----------------------------|
| <span data-ttu-id="95a07-130">Parken eines Anrufs</span><span class="sxs-lookup"><span data-stu-id="95a07-130">Park a call</span></span> | <span data-ttu-id="95a07-131">Ja</span><span class="sxs-lookup"><span data-stu-id="95a07-131">Yes</span></span> | <span data-ttu-id="95a07-132">Ja</span><span class="sxs-lookup"><span data-stu-id="95a07-132">Yes</span></span> | <span data-ttu-id="95a07-133">Ja</span><span class="sxs-lookup"><span data-stu-id="95a07-133">Yes</span></span> | <span data-ttu-id="95a07-134">Ja</span><span class="sxs-lookup"><span data-stu-id="95a07-134">Yes</span></span> | <span data-ttu-id="95a07-135">Ja</span><span class="sxs-lookup"><span data-stu-id="95a07-135">Yes</span></span> | <span data-ttu-id="95a07-136">Nein</span><span class="sxs-lookup"><span data-stu-id="95a07-136">No</span></span> |
| <span data-ttu-id="95a07-137">Abrufen eines geparkten Anrufs</span><span class="sxs-lookup"><span data-stu-id="95a07-137">Retrieve a parked call</span></span> | <span data-ttu-id="95a07-138">Ja</span><span class="sxs-lookup"><span data-stu-id="95a07-138">Yes</span></span> | <span data-ttu-id="95a07-139">Ja</span><span class="sxs-lookup"><span data-stu-id="95a07-139">Yes</span></span> | <span data-ttu-id="95a07-140">Ja</span><span class="sxs-lookup"><span data-stu-id="95a07-140">Yes</span></span> | <span data-ttu-id="95a07-141">Ja</span><span class="sxs-lookup"><span data-stu-id="95a07-141">Yes</span></span> | <span data-ttu-id="95a07-142">Ja</span><span class="sxs-lookup"><span data-stu-id="95a07-142">Yes</span></span> | <span data-ttu-id="95a07-143">Nein</span><span class="sxs-lookup"><span data-stu-id="95a07-143">No</span></span> |
| <span data-ttu-id="95a07-144">Nicht abgerufener Anruf Ring zurück</span><span class="sxs-lookup"><span data-stu-id="95a07-144">Unretrieved call ring back</span></span> | <span data-ttu-id="95a07-145">Ja</span><span class="sxs-lookup"><span data-stu-id="95a07-145">Yes</span></span> | <span data-ttu-id="95a07-146">Ja</span><span class="sxs-lookup"><span data-stu-id="95a07-146">Yes</span></span> | <span data-ttu-id="95a07-147">Ja</span><span class="sxs-lookup"><span data-stu-id="95a07-147">Yes</span></span> | <span data-ttu-id="95a07-148">Ja</span><span class="sxs-lookup"><span data-stu-id="95a07-148">Yes</span></span> | <span data-ttu-id="95a07-149">Ja</span><span class="sxs-lookup"><span data-stu-id="95a07-149">Yes</span></span> | <span data-ttu-id="95a07-150">Nein</span><span class="sxs-lookup"><span data-stu-id="95a07-150">No</span></span> |

## <a name="configure-call-park-and-retrieve"></a><span data-ttu-id="95a07-151">Konfigurieren des Anruf Parks und Abrufen</span><span class="sxs-lookup"><span data-stu-id="95a07-151">Configure call park and retrieve</span></span>

<span data-ttu-id="95a07-152">Sie müssen ein Administrator sein, um den Anruf Park zu konfigurieren und abzurufen, und das Feature ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="95a07-152">You must be an admin to configure call park and retrieve, and the feature is disabled by default.</span></span> <span data-ttu-id="95a07-153">Sie können es für Benutzer aktivieren und Benutzergruppen mithilfe der Anruf Park Richtlinie erstellen.</span><span class="sxs-lookup"><span data-stu-id="95a07-153">You can enable it for users and create user groups using the call park policy.</span></span> <span data-ttu-id="95a07-154">Wenn Sie die gleiche Richtlinie auf eine Reihe von Benutzern anwenden, können Sie Anrufe unter sich selbst Parken und abrufen.</span><span class="sxs-lookup"><span data-stu-id="95a07-154">When you apply the same policy to a set of users, they can park and retrieve calls among themselves.</span></span> <span data-ttu-id="95a07-155">Zum Konfigurieren des Anruf Parks für Benutzer und zum Erstellen von Benutzergruppen für den Anruf Park befolgen Sie die nachstehenden Schritte zum [Zuweisen einer Anruf Park Richtlinie](#assign-a-call-park-policy) .</span><span class="sxs-lookup"><span data-stu-id="95a07-155">To configure call park for users and create call park user groups, follow the [Assign a call park policy](#assign-a-call-park-policy) procedure below.</span></span>

<span data-ttu-id="95a07-156">Informationen zum Verwenden der Funktion "Parken und abrufen" finden Sie unter [Parken eines Anrufs in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span><span class="sxs-lookup"><span data-stu-id="95a07-156">For information about how to use the call park and retrieve feature, see [Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span></span>

### <a name="enable-a-call-park-policy"></a><span data-ttu-id="95a07-157">Aktivieren einer Anruf Park Richtlinie</span><span class="sxs-lookup"><span data-stu-id="95a07-157">Enable a call park policy</span></span>

1. <span data-ttu-id="95a07-158">Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu den Richtlinien für den **VoIP**-  >  **Anruf Park**.</span><span class="sxs-lookup"><span data-stu-id="95a07-158">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="95a07-159">Wählen Sie **Hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="95a07-159">Select **Add**.</span></span>
3. <span data-ttu-id="95a07-160">Geben Sie der Richtlinie einen Namen, und wählen Sie dann "Parken **von** **anrufen zulassen** " auf ein.</span><span class="sxs-lookup"><span data-stu-id="95a07-160">Give the policy a name, and then switch **Allow call park** to **On**.</span></span>
4. <span data-ttu-id="95a07-161">Wählen Sie **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="95a07-161">Select **Save**.</span></span>

#### <a name="using-powershell"></a><span data-ttu-id="95a07-162">Verwendung von PowerShell</span><span class="sxs-lookup"><span data-stu-id="95a07-162">Using PowerShell</span></span>

<span data-ttu-id="95a07-163">Weitere Informationen finden Sie unter [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="95a07-163">See [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps).</span></span>

### <a name="edit-a-call-park-policy"></a><span data-ttu-id="95a07-164">Bearbeiten einer Anruf Park Richtlinie</span><span class="sxs-lookup"><span data-stu-id="95a07-164">Edit a call park policy</span></span>

1. <span data-ttu-id="95a07-165">Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu den Richtlinien für den **VoIP**-  >  **Anruf Park**.</span><span class="sxs-lookup"><span data-stu-id="95a07-165">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="95a07-166">Wählen Sie die Richtlinie aus, indem Sie zunächst links neben die Richtlinienbezeichnung und dann auf **Bearbeiten** klicken.</span><span class="sxs-lookup"><span data-stu-id="95a07-166">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="95a07-167">Schalten Sie den **Anruf Park** auf **aus** oder **ein**.</span><span class="sxs-lookup"><span data-stu-id="95a07-167">Switch **Allow call park** to **Off** or **On**.</span></span>
4. <span data-ttu-id="95a07-168">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="95a07-168">Click **Save**.</span></span>

#### <a name="using-powershell"></a><span data-ttu-id="95a07-169">Verwendung von PowerShell</span><span class="sxs-lookup"><span data-stu-id="95a07-169">Using PowerShell</span></span>

<span data-ttu-id="95a07-170">Weitere Informationen finden Sie unter [Satz-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="95a07-170">See [Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps).</span></span> <span data-ttu-id="95a07-171">Wenn Sie beispielsweise die Standardeinstellung ändern möchten, führen Sie die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="95a07-171">For example, to change the default setting, run the following:</span></span>

  ```PowerShell
  Set-CsTeamsCallParkPolicy -Identity Global -AllowCallPark $true
  ```

### <a name="assign-a-call-park-policy"></a><span data-ttu-id="95a07-172">Zuweisen einer Anruf Park Richtlinie</span><span class="sxs-lookup"><span data-stu-id="95a07-172">Assign a call park policy</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]
 
<span data-ttu-id="95a07-173">Siehe auch [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="95a07-173">See also [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="95a07-174">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="95a07-174">Troubleshooting</span></span>

<span data-ttu-id="95a07-175">Wenn Benutzer die Schaltfläche "Parken" oder "abrufen" nicht sehen können:</span><span class="sxs-lookup"><span data-stu-id="95a07-175">If users can't see the park or retrieve button:</span></span> 

- <span data-ttu-id="95a07-176">Überprüfen Sie, ob der Benutzer die Anruf Park Richtlinie aktiviert hat.</span><span class="sxs-lookup"><span data-stu-id="95a07-176">Check that the user has the Call Park policy enabled.</span></span> 

<span data-ttu-id="95a07-177">Wenn ein Benutzer versucht, einen Anruf abzurufen und nicht erfolgreich ist, überprüfen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="95a07-177">If a user attempts to retrieve a call and is unsuccessful, check the following:</span></span>

- <span data-ttu-id="95a07-178">Überprüfen, ob der Benutzer den Teams-Client oder ein Team fähiges Gerät/Telefon verwendet</span><span class="sxs-lookup"><span data-stu-id="95a07-178">Verify that the user is using the Teams client or a Teams-enabled device/Phone</span></span>
- <span data-ttu-id="95a07-179">Gruppieren – ist der Benutzer ein Mitglied der Gruppe "Anruf parken", die darauf basiert, dass dieselbe Teams-Anruf Park Richtlinie zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="95a07-179">Grouping – is the user a member of the call park group, which is based on having the same Teams Call Park policy assigned.</span></span> 
- <span data-ttu-id="95a07-180">Island-Modus – Parken und Abrufen von anrufen ist im Modus "Teams Island" nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="95a07-180">Island mode – Call park and retrieve is unavailable in Teams island mode.</span></span>
- <span data-ttu-id="95a07-181">Der Anruf wurde bereits abgerufen oder beendet.</span><span class="sxs-lookup"><span data-stu-id="95a07-181">The call has already been retrieved or terminated.</span></span>

## <a name="related-topics"></a><span data-ttu-id="95a07-182">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="95a07-182">Related topics</span></span>

[<span data-ttu-id="95a07-183">Parken eines Anrufs in Teams</span><span class="sxs-lookup"><span data-stu-id="95a07-183">Park a call in Teams</span></span>](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[<span data-ttu-id="95a07-184">Zuweisen von Richtlinien zu Ihren Benutzern in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="95a07-184">Assign policies to your users in Teams</span></span>](assign-policies.md)
