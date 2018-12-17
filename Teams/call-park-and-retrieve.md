---
title: Parken und fortsetzen in Microsoft-Teams
ms.author: lolaj
author: lolaj
manager: serdars
ms.date: 12/17/2018
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service:
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Verwenden Sie Parken und fortsetzen, um einen Anruf in der Warteschleife im Dienst Teams in der Cloud.
ms.openlocfilehash: 004a5b12e178a6460ef05f7c6f5c5738c8ced042
ms.sourcegitcommit: 0e671e6e6fdd25227068c7e3a3a5509b6536d2b1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/17/2018
ms.locfileid: "27294188"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a><span data-ttu-id="6f3d2-103">Parken und fortsetzen in Microsoft-Teams</span><span class="sxs-lookup"><span data-stu-id="6f3d2-103">Call park and retrieve in Microsoft Teams</span></span>

<span data-ttu-id="6f3d2-104">Parken und Fortsetzen von Anrufen ist ein Feature, in dem einen Benutzer einen Anruf in der Warteschleife im Dienst Teams in der Cloud.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-104">Call park and retrieve is a feature that lets a user place a call on hold in the Teams service in the cloud.</span></span> <span data-ttu-id="6f3d2-105">Wenn Sie ein Anruf geparkt wurde, erstellt der Dienst einen eindeutigen Code für den Abruf von Anrufen.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-105">When a call is parked, the service generates a unique code for call retrieval.</span></span> <span data-ttu-id="6f3d2-106">Der Benutzer, der den Anruf oder eine andere Person geparkt kann dann Code und einen unterstützten app oder ein Gerät verwenden, um den Anruf abzurufen.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-106">The user who parked the call or someone else can then use that code and a supported app or device to retrieve the call.</span></span> 

<span data-ttu-id="6f3d2-107">Einige häufigen Szenarien für die Verwendung des Parkens von Anrufen werden:</span><span class="sxs-lookup"><span data-stu-id="6f3d2-107">Some of the common scenarios for using call park are:</span></span> 

- <span data-ttu-id="6f3d2-108">Ein Empfangsmitarbeiter parks einen Anruf nach einer Person in einer Factory arbeiten.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-108">A receptionist parks a call for someone working in a factory.</span></span> <span data-ttu-id="6f3d2-109">Die Empfangsmitarbeiter Ankündigung klicken Sie dann den Anruf und die Anzahl von Code über das öffentliche Adresse-System.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-109">The receptionist then announces the call and the code number over the public address system.</span></span> <span data-ttu-id="6f3d2-110">Klicken Sie dann kann der Benutzer, die der Anruf ist ein Telefon Teams werksseitige aufzunehmen und geben Sie den Code, um den Anruf entgegenzunehmen.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-110">The user who the call is for can then pick up a Teams phone on the factory floor and enter the code to retrieve the call.</span></span>
- <span data-ttu-id="6f3d2-111">Ein Benutzer parks ein Anrufs auf einem mobilen Gerät, da die Batterie Gerät nicht mehr genug Power vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-111">A user parks a call on a mobile device because the device battery is running out of power.</span></span> <span data-ttu-id="6f3d2-112">Der Benutzer kann dann geben Sie dann code zum Abrufen des Anrufs von einem Telefonapparat Teams.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-112">The user can then enter then code to retrieve the call from a Teams desk phone.</span></span>
- <span data-ttu-id="6f3d2-113">Eine repräsentative Parks Unterstützung ein Kunden aufrufen und sendet eine Ankündigung in einem Kanal Teams für einen Experten So rufen Sie den Anruf und helfen Sie dem Kunden.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-113">A support representative parks a customer call and sends an announcement on a Teams channel for an expert to retrieve the call and help the customer.</span></span> <span data-ttu-id="6f3d2-114">Gibt den Code ein Experte in Teams-Clients, um den Anruf</span><span class="sxs-lookup"><span data-stu-id="6f3d2-114">An expert enters the code in Teams clients to retrieve the call</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6f3d2-115">Dieses Feature ist nur im Modus nur Teams Bereitstellung zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-115">This feature is only available in Teams Only deployment mode.</span></span> <span data-ttu-id="6f3d2-116">Weitere Informationen zu Bereitstellungsmethoden Teams finden Sie unter [Grundlegendes zu Microsoft-Teams und Skype für Interoperabilität und Koexistenz Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="6f3d2-116">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="6f3d2-117">Lizenz erforderlich</span><span class="sxs-lookup"><span data-stu-id="6f3d2-117">License required</span></span>

<span data-ttu-id="6f3d2-118">Um Parken und Anrufe wiederaufnehmen, muss ein Benutzer einen Enterprise-VoIP-Benutzer sein, und ein Administrator muss dem Benutzer eine Anruf Parken Richtlinie erteilen.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-118">To park and retrieve calls, a user must be an Enterprise Voice user, and an administrator must grant the user a call park policy.</span></span> <span data-ttu-id="6f3d2-119">Weitere Details zur am Lizenzierungsmodell finden Sie unter [Office 365-Lizenzierung für Microsoft-Teams](office-365-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="6f3d2-119">For additional details on the licensing model, See [Office 365 licensing for Microsoft Teams](office-365-licensing.md).</span></span>

## <a name="call-park-and-retrieve-feature-availability"></a><span data-ttu-id="6f3d2-120">Parken und Fortsetzen der Verfügbarkeit von Features</span><span class="sxs-lookup"><span data-stu-id="6f3d2-120">Call park and retrieve feature availability</span></span>

<span data-ttu-id="6f3d2-121">Parken und fortsetzen wird durch die folgenden Clients und Geräten derzeit unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-121">Call park and retrieve is currently supported by the following clients and devices.</span></span> <span data-ttu-id="6f3d2-122">(Unterstützt nur Teams Modus mit oder ohne PSTN-Anbindung.)</span><span class="sxs-lookup"><span data-stu-id="6f3d2-122">(Supported in Teams Only mode, with or without PSTN connectivity.)</span></span>

| <span data-ttu-id="6f3d2-123">Funktion</span><span class="sxs-lookup"><span data-stu-id="6f3d2-123">Capability</span></span> | <span data-ttu-id="6f3d2-124">Teams Desktop</span><span class="sxs-lookup"><span data-stu-id="6f3d2-124">Teams Desktop</span></span> | <span data-ttu-id="6f3d2-125">Teams Mac-App</span><span class="sxs-lookup"><span data-stu-id="6f3d2-125">Teams Mac App</span></span> | <span data-ttu-id="6f3d2-126">Teams Web App (Edge)</span><span class="sxs-lookup"><span data-stu-id="6f3d2-126">Teams Web App (Edge)</span></span> |<span data-ttu-id="6f3d2-127">Mobile-iOS/Android-App-Teams</span><span class="sxs-lookup"><span data-stu-id="6f3d2-127">Teams mobile iOS/Android App</span></span> | <span data-ttu-id="6f3d2-128">Teams IP-Telefon</span><span class="sxs-lookup"><span data-stu-id="6f3d2-128">Teams IP phone</span></span> | <span data-ttu-id="6f3d2-129">Skype für Business IP-Telefon</span><span class="sxs-lookup"><span data-stu-id="6f3d2-129">Skype for Business IP phone</span></span> |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|-----------------------------|
| <span data-ttu-id="6f3d2-130">Parken eines Anrufs</span><span class="sxs-lookup"><span data-stu-id="6f3d2-130">Park a call</span></span> | <span data-ttu-id="6f3d2-131">Ja</span><span class="sxs-lookup"><span data-stu-id="6f3d2-131">Yes</span></span> | <span data-ttu-id="6f3d2-132">Ja</span><span class="sxs-lookup"><span data-stu-id="6f3d2-132">Yes</span></span> | <span data-ttu-id="6f3d2-133">Ja</span><span class="sxs-lookup"><span data-stu-id="6f3d2-133">Yes</span></span> | <span data-ttu-id="6f3d2-134">In Kürze verfügbar</span><span class="sxs-lookup"><span data-stu-id="6f3d2-134">Coming soon</span></span> | <span data-ttu-id="6f3d2-135">In Kürze verfügbar</span><span class="sxs-lookup"><span data-stu-id="6f3d2-135">Coming soon</span></span>| <span data-ttu-id="6f3d2-136">Nein</span><span class="sxs-lookup"><span data-stu-id="6f3d2-136">No</span></span> |
| <span data-ttu-id="6f3d2-137">Abrufen eines geparkten Anrufs</span><span class="sxs-lookup"><span data-stu-id="6f3d2-137">Retrieve a parked call</span></span> | <span data-ttu-id="6f3d2-138">Ja</span><span class="sxs-lookup"><span data-stu-id="6f3d2-138">Yes</span></span> | <span data-ttu-id="6f3d2-139">Ja</span><span class="sxs-lookup"><span data-stu-id="6f3d2-139">Yes</span></span> | <span data-ttu-id="6f3d2-140">Ja</span><span class="sxs-lookup"><span data-stu-id="6f3d2-140">Yes</span></span> | <span data-ttu-id="6f3d2-141">In Kürze verfügbar</span><span class="sxs-lookup"><span data-stu-id="6f3d2-141">Coming soon</span></span> | <span data-ttu-id="6f3d2-142">In Kürze verfügbar</span><span class="sxs-lookup"><span data-stu-id="6f3d2-142">Coming soon</span></span>| <span data-ttu-id="6f3d2-143">Nein</span><span class="sxs-lookup"><span data-stu-id="6f3d2-143">No</span></span> |
| <span data-ttu-id="6f3d2-144">Wieder aufgehoben abgerufenen Anruf ring</span><span class="sxs-lookup"><span data-stu-id="6f3d2-144">Un-retrieved call ring back</span></span> | <span data-ttu-id="6f3d2-145">Ja</span><span class="sxs-lookup"><span data-stu-id="6f3d2-145">Yes</span></span> | <span data-ttu-id="6f3d2-146">Ja</span><span class="sxs-lookup"><span data-stu-id="6f3d2-146">Yes</span></span> | <span data-ttu-id="6f3d2-147">Ja</span><span class="sxs-lookup"><span data-stu-id="6f3d2-147">Yes</span></span> | <span data-ttu-id="6f3d2-148">In Kürze verfügbar</span><span class="sxs-lookup"><span data-stu-id="6f3d2-148">Coming soon</span></span> | <span data-ttu-id="6f3d2-149">In Kürze verfügbar</span><span class="sxs-lookup"><span data-stu-id="6f3d2-149">Coming soon</span></span>| <span data-ttu-id="6f3d2-150">Nein</span><span class="sxs-lookup"><span data-stu-id="6f3d2-150">No</span></span> |

## <a name="configuring-call-park-and-retrieve"></a><span data-ttu-id="6f3d2-151">Konfigurieren von Parken und fortsetzen</span><span class="sxs-lookup"><span data-stu-id="6f3d2-151">Configuring call park and retrieve</span></span>

<span data-ttu-id="6f3d2-152">Sie müssen ein Administrator konfigurieren Parken und fortsetzen sein, und das Feature ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-152">You must be an administrator to configure call park and retrieve, and the feature is disabled by default.</span></span> <span data-ttu-id="6f3d2-153">Sie können diese für Benutzer aktivieren und Benutzergruppen mit der Anruf Parken Richtlinie erstellen.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-153">You can enable it for users and create user groups using the call park policy.</span></span> <span data-ttu-id="6f3d2-154">Wenn Sie die gleiche Richtlinie auf eine Gruppe von Benutzern anwenden, werden sie Parken und anrufen untereinander abrufen können.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-154">When you apply the same policy to a set of users, they will be able to park and retrieve calls among themselves.</span></span> <span data-ttu-id="6f3d2-155">Zum Konfigurieren des Parkens von Anrufen für Benutzer, und Anruf Parken Benutzergruppen erstellen, befolgen Sie die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-155">To configure call park for users and create call park user groups, follow the procedure below.</span></span>

<span data-ttu-id="6f3d2-156">Informationen zum Verwenden der Parken und Abrufen von Feature finden Sie unter [Parken eines Anrufs in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span><span class="sxs-lookup"><span data-stu-id="6f3d2-156">For information about how to use the call park and retrieve feature, see [Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span></span>

### <a name="configure-call-park-and-retrieve-with-powershell"></a><span data-ttu-id="6f3d2-157">Konfigurieren Sie des Parkens von Anrufen, und rufen Sie mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="6f3d2-157">Configure call park and retrieve with PowerShell</span></span>

<span data-ttu-id="6f3d2-158">Verwenden Sie das [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps) PowerShell-Cmdlet eine Anruf Parken Richtlinie erstellen.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-158">Use the [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet to create a call park policy.</span></span>

<span data-ttu-id="6f3d2-159">Verwenden Sie das [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) PowerShell-Cmdlet, um eine Anruf Parken Richtlinie zu erteilen.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-159">Use the [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet to grant a call park policy.</span></span>

<span data-ttu-id="6f3d2-160">Sie können die Standardeinstellung mit [Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps) wie folgt ändern:</span><span class="sxs-lookup"><span data-stu-id="6f3d2-160">You can change the default setting by using [Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps) as follows:</span></span>

`Set-CsTeamsCallParkPolicy -Identity Global -AllowCallPark $true`


## <a name="troubleshooting"></a><span data-ttu-id="6f3d2-161">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="6f3d2-161">Troubleshooting</span></span>

<span data-ttu-id="6f3d2-162">Wenn Benutzer nicht finden Sie unter der Park oder Schaltfläche abzurufen:</span><span class="sxs-lookup"><span data-stu-id="6f3d2-162">If users can’t see the park or retrieve button:</span></span> 

- <span data-ttu-id="6f3d2-163">Überprüfen Sie, dass der Benutzer die Richtlinie zum Parken von Anrufen aktiviert hat.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-163">Check that the user has the Call Park policy enabled.</span></span> 

<span data-ttu-id="6f3d2-164">Wenn ein Benutzer versucht, einen Anruf abzurufen und nicht erfolgreich ist, überprüfen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="6f3d2-164">If a user attempts to retrieve a call and is unsuccessful, check the following:</span></span>

- <span data-ttu-id="6f3d2-165">Stellen Sie sicher, dass der Benutzer den Client Teams oder ein Teams-aktivierten Gerät/Telefon verwendet wird</span><span class="sxs-lookup"><span data-stu-id="6f3d2-165">Verify that the user is using the Teams client or a Teams-enabled device/Phone</span></span>
- <span data-ttu-id="6f3d2-166">Gruppierung – ist der Benutzer ein Mitglied der Gruppe der Anruf Parken.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-166">Grouping – is the user a member of the call park group?</span></span>
- <span data-ttu-id="6f3d2-167">Island-Modus – Parken und fortsetzen ist im Teams Island Modus nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-167">Island mode – Call park and retrieve is unavailable in Teams island mode.</span></span>
- <span data-ttu-id="6f3d2-168">Der Anruf wurde bereits abgerufen oder beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-168">The call has already been retrieved or terminated.</span></span>

## <a name="more-information"></a><span data-ttu-id="6f3d2-169">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6f3d2-169">More information</span></span>

<span data-ttu-id="6f3d2-170">[Parken eines Anrufs in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span><span class="sxs-lookup"><span data-stu-id="6f3d2-170">[Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span></span>