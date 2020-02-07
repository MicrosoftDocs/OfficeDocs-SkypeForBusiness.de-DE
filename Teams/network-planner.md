---
title: Verwenden von Network Planner für Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 06/24/2019
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
audience: admin
description: Erfahren Sie, wie Sie mithilfe des Netzwerk Planers Netzwerkanforderungen für Microsoft Teams ermitteln.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.networkplanner.overview
- ms.teamsadmincenter.networkplanner.personas
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1e27979bc4f440fee58f97ffb647cdd5465fb326
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41832705"
---
# <a name="use-the-network-planner-for-microsoft-teams"></a><span data-ttu-id="7e2c9-103">Verwenden von Network Planner für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7e2c9-103">Use the Network Planner for Microsoft Teams</span></span>

<span data-ttu-id="7e2c9-104">Network Planner ist ein neues Tool, das im Team Admin Center zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="7e2c9-104">Network Planner is a new tool that is available in the Teams admin center.</span></span> <span data-ttu-id="7e2c9-105">Sie finden ihn unter **Planner** > **Network Planner**.</span><span class="sxs-lookup"><span data-stu-id="7e2c9-105">It can be found by going to **Planner** > **Network planner**.</span></span> <span data-ttu-id="7e2c9-106">Mit nur wenigen Schritten kann der Netzwerk Planner Ihnen dabei helfen, die Netzwerkanforderungen für die Verbindung von Microsoft Teams-Benutzern in Ihrer Organisation zu ermitteln und zu organisieren.</span><span class="sxs-lookup"><span data-stu-id="7e2c9-106">In just a few steps, the Network Planner can help you determine and organize network requirements for connecting Microsoft Teams users across your organization.</span></span> <span data-ttu-id="7e2c9-107">Wenn Sie Ihre Netzwerkdetails und die Verwendung von Teams angeben, berechnet der Netzwerk Planner Ihre Netzwerkanforderungen für die Bereitstellung von Teams und Cloud-VoIP über die physischen Standorte Ihrer Organisation hinweg.</span><span class="sxs-lookup"><span data-stu-id="7e2c9-107">When you provide your network details and Teams usage, the Network Planner calculates your network requirements for deploying Teams and cloud voice across your organization’s physical locations.</span></span>

![Screenshot von Network Planner](media/network-planner.png)

<span data-ttu-id="7e2c9-109">Network Planner bietet Ihnen folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="7e2c9-109">Network Planner allows you to:</span></span>

- <span data-ttu-id="7e2c9-110">Erstellen Sie Darstellungen Ihrer Organisation mithilfe von Websites und von Microsoft empfohlenen Personas (Office-Mitarbeitern, Remotemitarbeitern und Teams Room System).</span><span class="sxs-lookup"><span data-stu-id="7e2c9-110">Create representations of your organization using sites and Microsoft recommended personas (office workers, remote workers, and Teams room system).</span></span>

    > [!NOTE]
    > <span data-ttu-id="7e2c9-111">Die empfohlenen Personas wurden auf der Grundlage von Daten aus Teams entwickelt, die am besten verwendet werden, sowie typische Verwendungsmuster.</span><span class="sxs-lookup"><span data-stu-id="7e2c9-111">The recommended personas were developed based on data from Teams best use scenarios and typical usage patterns.</span></span> <span data-ttu-id="7e2c9-112">Sie können jedoch zusätzlich zu den drei empfohlenen Personas bis zu drei benutzerdefinierte Personas erstellen.</span><span class="sxs-lookup"><span data-stu-id="7e2c9-112">However, you can create up to three custom personas in addition to the three recommended personas.</span></span>

- <span data-ttu-id="7e2c9-113">Generieren von Berichten und Berechnen der Bandbreitenanforderungen für die Verwendung durch Teams.</span><span class="sxs-lookup"><span data-stu-id="7e2c9-113">Generate reports and calculate bandwidth requirements for Teams usage.</span></span>

<span data-ttu-id="7e2c9-114">Um Network Planner verwenden zu können, müssen Sie ein globaler Administrator, Team Dienstadministrator oder Teams-Kommunikations Administrator sein.</span><span class="sxs-lookup"><span data-stu-id="7e2c9-114">To use Network Planner, you must be a Global Administrator, Teams Service Administrator, or Teams Communications Administrator.</span></span>

## <a name="create-a-custom-persona"></a><span data-ttu-id="7e2c9-115">Erstellen einer benutzerdefinierten Rolle</span><span class="sxs-lookup"><span data-stu-id="7e2c9-115">Create a custom persona</span></span>

<span data-ttu-id="7e2c9-116">Führen Sie die folgenden Schritte aus, um eine benutzerdefinierte Rolle zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="7e2c9-116">Follow these steps to create a custom persona:</span></span>

1. <span data-ttu-id="7e2c9-117">Wechseln Sie im Microsoft Teams Admin Center zum Netzwerk Planner.</span><span class="sxs-lookup"><span data-stu-id="7e2c9-117">Go to the Network Planner in the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="7e2c9-118">Klicken Sie auf der Registerkarte **Personas** auf **+ benutzerdefinierte Rolle**.</span><span class="sxs-lookup"><span data-stu-id="7e2c9-118">On the **Personas** tab, click **+ Custom persona**.</span></span> 

3. <span data-ttu-id="7e2c9-119">Fügen Sie im Bereich **neue benutzerdefinierte Rolle** einen Namen und eine Beschreibung für die neue Person hinzu.</span><span class="sxs-lookup"><span data-stu-id="7e2c9-119">In the **New custom persona** pane, add a name and description for the new persona.</span></span>

4. <span data-ttu-id="7e2c9-120">Wählen Sie die Berechtigungen aus, die diese Person innerhalb der Organisation verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="7e2c9-120">Select the permissions that this persona will use within the organization.</span></span>

5. <span data-ttu-id="7e2c9-121">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="7e2c9-121">Click **Save**.</span></span>

## <a name="build-your-plan"></a><span data-ttu-id="7e2c9-122">Erstellen Ihres Plans</span><span class="sxs-lookup"><span data-stu-id="7e2c9-122">Build your plan</span></span>

<span data-ttu-id="7e2c9-123">Führen Sie die folgenden Schritte aus, um mit dem Erstellen Ihres Netzwerkplans zu beginnen:</span><span class="sxs-lookup"><span data-stu-id="7e2c9-123">Follow these steps to begin building your network plan:</span></span>

1. <span data-ttu-id="7e2c9-124">Wechseln Sie im Microsoft Teams Admin Center zum Netzwerk Planner.</span><span class="sxs-lookup"><span data-stu-id="7e2c9-124">Go to the Network Planner in the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="7e2c9-125">Klicken Sie auf der Registerkarte **Netzwerkplan** auf **Netzwerkplan hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="7e2c9-125">On the **Network Plan** tab, click **Add a network plan**.</span></span>

3. <span data-ttu-id="7e2c9-126">Geben Sie einen Namen und eine Beschreibung für Ihren Netzwerkplan ein.</span><span class="sxs-lookup"><span data-stu-id="7e2c9-126">Enter a name and description for your network plan.</span></span> <span data-ttu-id="7e2c9-127">Der Netzwerkplan wird in der Liste der verfügbaren Pläne angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7e2c9-127">The network plan will appear in the list of available plans.</span></span>

4. <span data-ttu-id="7e2c9-128">Klicken Sie auf den Plan Namen, um den neuen Plan auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="7e2c9-128">Click the plan name to select the new plan.</span></span>

5. <span data-ttu-id="7e2c9-129">Fügen Sie Websites hinzu, um eine Darstellung des Netzwerk Setups Ihrer Organisation zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7e2c9-129">Add sites to create a representation of your organization’s network setup.</span></span>

    <span data-ttu-id="7e2c9-130">Je nach Netzwerk Ihrer Organisation möchten Sie möglicherweise Websites verwenden, um ein Gebäude, einen Office-Standort oder etwas anderes darzustellen.</span><span class="sxs-lookup"><span data-stu-id="7e2c9-130">Depending on your organization’s network, you may want to use sites to represent a building, an office location, or something else.</span></span> <span data-ttu-id="7e2c9-131">Websites können über ein WAN verbunden sein, um die Freigabe von Internet-und/oder PSTN-Verbindungen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="7e2c9-131">Sites might be connected by a WAN to allow sharing of internet and/or PSTN connections.</span></span> <span data-ttu-id="7e2c9-132">Um optimale Ergebnisse zu erzielen, erstellen Sie Websites mit lokalen Verbindungen, bevor Sie Websites erstellen, die eine Remoteverbindung mit dem Internet oder PSTN herstellen.</span><span class="sxs-lookup"><span data-stu-id="7e2c9-132">For best results, create sites with local connections before you create sites that remotely connect to the internet or PSTN.</span></span>

    <span data-ttu-id="7e2c9-133">So erstellen Sie eine Website:</span><span class="sxs-lookup"><span data-stu-id="7e2c9-133">To create a site:</span></span>

    1. <span data-ttu-id="7e2c9-134">Fügen Sie einen Namen und eine Beschreibung für Ihre Website hinzu.</span><span class="sxs-lookup"><span data-stu-id="7e2c9-134">Add a name and description for your site.</span></span>

    2. <span data-ttu-id="7e2c9-135">Fügen Sie unter **Netzwerkeinstellungen**die Anzahl der Netzwerkbenutzer auf dieser Website hinzu (erforderlich).</span><span class="sxs-lookup"><span data-stu-id="7e2c9-135">Under **Network settings**, add the number of network users at that site (required).</span></span>

    3. <span data-ttu-id="7e2c9-136">Hinzufügen von Netzwerkdetails: WAN-fähig, WAN-Kapazität, Internet-Ausstieg (**lokal** oder **Remote**) und PSTN-Ausgang (keine, lokal oder Remote).</span><span class="sxs-lookup"><span data-stu-id="7e2c9-136">Add network details: WAN-enabled, WAN capacity, internet egress (**Local** or **Remote**), and PSTN egress (none, local, or remote).</span></span>

      > [!NOTE]
      > <span data-ttu-id="7e2c9-137">Sie müssen WAN-und Internet Kapazitäts Nummern hinzufügen, um bestimmte Bandbreiten Empfehlungen anzuzeigen, wenn Sie einen Bericht generieren.</span><span class="sxs-lookup"><span data-stu-id="7e2c9-137">You must add WAN and internet capacity numbers to see specific bandwidth recommendations when you generate a report.</span></span>

    4. <span data-ttu-id="7e2c9-138">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="7e2c9-138">Click **Save**.</span></span>

## <a name="create-a-report"></a><span data-ttu-id="7e2c9-139">Erstellen eines Berichts</span><span class="sxs-lookup"><span data-stu-id="7e2c9-139">Create a report</span></span>

<span data-ttu-id="7e2c9-140">Nachdem Sie alle Websites hinzugefügt haben, können Sie einen Bericht wie folgt erstellen.</span><span class="sxs-lookup"><span data-stu-id="7e2c9-140">After you add all sites, you can create a report, as follows.</span></span>

1. <span data-ttu-id="7e2c9-141">Klicken Sie auf der Registerkarte **Berichte** auf **Bericht starten**.</span><span class="sxs-lookup"><span data-stu-id="7e2c9-141">On the **Reports** tab, click **Start a report**.</span></span>

2. <span data-ttu-id="7e2c9-142">Verteilen Sie für jede Website, die Sie erstellen, die Anzahl der Benutzer auf die verfügbaren Personas.</span><span class="sxs-lookup"><span data-stu-id="7e2c9-142">For each site you create, distribute the number of users across the available personas.</span></span> <span data-ttu-id="7e2c9-143">Wenn Sie die Microsoft Recommended Personas verwenden, wird die Nummer automatisch verteilt (80% Office Worker und 20% Remote Worker).</span><span class="sxs-lookup"><span data-stu-id="7e2c9-143">If you use the Microsoft recommended personas, the number will be distributed automatically (80% office worker and 20% remote worker).</span></span>

3. <span data-ttu-id="7e2c9-144">Nachdem Sie die Verteilung abgeschlossen haben, klicken Sie auf **Bericht generieren**.</span><span class="sxs-lookup"><span data-stu-id="7e2c9-144">After you complete the distribution, click **Generate report**.</span></span>

    <span data-ttu-id="7e2c9-145">Der generierte Bericht zeigt die Bandbreitenanforderungen in verschiedenen Ansichten an, sodass Sie die Ausgabe klar verstehen können:</span><span class="sxs-lookup"><span data-stu-id="7e2c9-145">The generated report will show the bandwidth requirements in several different views so that you can clearly understand the output:</span></span>
    - <span data-ttu-id="7e2c9-146">Eine Tabelle mit einzelnen Berechnungen zeigt die Bandbreitenanforderungen für die einzelnen zulässigen Aktivitäten an.</span><span class="sxs-lookup"><span data-stu-id="7e2c9-146">A table with individual calculations will display bandwidth requirements for each permitted activity.</span></span>
    - <span data-ttu-id="7e2c9-147">In einer zusätzlichen Ansicht werden die gesamten Anforderungen an die Bandbreite mit Empfehlungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7e2c9-147">An additional view will show the overall bandwidth needs with recommendations.</span></span>

4. <span data-ttu-id="7e2c9-148">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="7e2c9-148">Click **Save**.</span></span> <span data-ttu-id="7e2c9-149">Ihr Bericht steht in der Liste Berichte zur späteren Anzeige zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="7e2c9-149">Your report will be available on the reports list for later viewing.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="7e2c9-150">Beispielszenario</span><span class="sxs-lookup"><span data-stu-id="7e2c9-150">Example scenario</span></span>

<span data-ttu-id="7e2c9-151">Ein Beispiel für die Verwendung des Netzwerk Planner zum Einrichten eines Netzwerkplans und zum Generieren eines Berichts mithilfe dieser Schritte finden Sie unter Herunterladen des Network Planner [-PowerPoint-Deck](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true) Blatts (nur Englisch).</span><span class="sxs-lookup"><span data-stu-id="7e2c9-151">For an example of how to use the Network Planner to set up a network plan and generate a report using these steps, download the [Network Planner How-To PowerPoint deck](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true) (English only).</span></span>
