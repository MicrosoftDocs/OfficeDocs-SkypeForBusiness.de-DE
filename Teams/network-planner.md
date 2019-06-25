---
title: Verwenden von Network Planner für Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 06/24/2019
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
description: Erfahren Sie, wie Sie mithilfe des Netzwerk Planers Netzwerkanforderungen für Microsoft Teams ermitteln.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: aaf2c2c7242c594d67af131d3a15224ddf16419c
ms.sourcegitcommit: a388aec386b1a72b44c24d5f189a8c1cd401f706
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2019
ms.locfileid: "35214823"
---
# <a name="use-the-network-planner-for-microsoft-teams"></a><span data-ttu-id="c23f2-103">Verwenden von Network Planner für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c23f2-103">Use the Network Planner for Microsoft Teams</span></span>

<span data-ttu-id="c23f2-104">Willkommen beim Netzwerk Planner.</span><span class="sxs-lookup"><span data-stu-id="c23f2-104">Welcome to the Network Planner.</span></span> <span data-ttu-id="c23f2-105">Mit nur wenigen Schritten kann der Netzwerk Planner Ihnen dabei helfen, die Netzwerkanforderungen für die Verbindung von Microsoft Teams-Benutzern in Ihrer Organisation zu ermitteln und zu organisieren.</span><span class="sxs-lookup"><span data-stu-id="c23f2-105">In just a few steps, the Network Planner can help you determine and organize network requirements for connecting Microsoft Teams users across your organization.</span></span> <span data-ttu-id="c23f2-106">Wenn Sie Ihre Netzwerkdetails und die Verwendung von Teams angeben, berechnet der Netzwerk Planner Ihre Netzwerkanforderungen für die Bereitstellung von Teams und Cloud-VoIP über die physischen Standorte Ihrer Organisation hinweg.</span><span class="sxs-lookup"><span data-stu-id="c23f2-106">When you provide your network details and Teams usage, the Network Planner calculates your network requirements for deploying Teams and cloud voice across your organization’s physical locations.</span></span>

![Screenshot von Network Planner](media/network-planner.png)

<span data-ttu-id="c23f2-108">Network Planner bietet Ihnen folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="c23f2-108">Network Planner allows you to:</span></span>

- <span data-ttu-id="c23f2-109">Erstellen Sie Darstellungen Ihrer Organisation mithilfe von Websites und von Microsoft empfohlenen Personas (Office-Mitarbeitern, Remotemitarbeitern und Teams Room System).</span><span class="sxs-lookup"><span data-stu-id="c23f2-109">Create representations of your organization using sites and Microsoft recommended personas (office workers, remote workers, and Teams room system).</span></span>

    > [!NOTE]
    > <span data-ttu-id="c23f2-110">Die empfohlenen Personas wurden auf der Grundlage von Daten aus Teams entwickelt, die am besten verwendet werden, sowie typische Verwendungsmuster.</span><span class="sxs-lookup"><span data-stu-id="c23f2-110">The recommended personas were developed based on data from Teams best use scenarios and typical usage patterns.</span></span> <span data-ttu-id="c23f2-111">Sie können jedoch zusätzlich zu den drei empfohlenen Personas bis zu drei benutzerdefinierte Personas erstellen.</span><span class="sxs-lookup"><span data-stu-id="c23f2-111">However, you can create up to three custom personas in addition to the three recommended personas.</span></span>

- <span data-ttu-id="c23f2-112">Generieren von Berichten und Berechnen der Bandbreitenanforderungen für die Verwendung durch Teams.</span><span class="sxs-lookup"><span data-stu-id="c23f2-112">Generate reports and calculate bandwidth requirements for Teams usage.</span></span>

## <a name="create-a-custom-persona"></a><span data-ttu-id="c23f2-113">Erstellen einer benutzerdefinierten Rolle</span><span class="sxs-lookup"><span data-stu-id="c23f2-113">Create a custom persona</span></span>

<span data-ttu-id="c23f2-114">Führen Sie die folgenden Schritte aus, um eine benutzerdefinierte Rolle zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="c23f2-114">Follow these steps to create a custom persona:</span></span>

1. <span data-ttu-id="c23f2-115">Wechseln Sie im Microsoft Teams Admin Center zum Netzwerk Planner.</span><span class="sxs-lookup"><span data-stu-id="c23f2-115">Go to the Network Planner in the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="c23f2-116">Klicken Sie \*\*\*\* auf der Registerkarte Personas auf **+ benutzerdefinierte Rolle**.</span><span class="sxs-lookup"><span data-stu-id="c23f2-116">On the **Personas** tab, click **+ Custom persona**.</span></span> 

3. <span data-ttu-id="c23f2-117">Fügen Sie im Bereich **neue benutzerdefinierte Rolle** einen Namen und eine Beschreibung für die neue Person hinzu.</span><span class="sxs-lookup"><span data-stu-id="c23f2-117">In the **New custom persona** pane, add a name and description for the new persona.</span></span>

4. <span data-ttu-id="c23f2-118">Wählen Sie die Berechtigungen aus, die diese Person innerhalb der Organisation verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="c23f2-118">Select the permissions that this persona will use within the organization.</span></span>

5. <span data-ttu-id="c23f2-119">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="c23f2-119">Click **Save**.</span></span>

## <a name="build-your-plan"></a><span data-ttu-id="c23f2-120">Erstellen Ihres Plans</span><span class="sxs-lookup"><span data-stu-id="c23f2-120">Build your plan</span></span>

<span data-ttu-id="c23f2-121">Führen Sie die folgenden Schritte aus, um mit dem Erstellen Ihres Netzwerkplans zu beginnen:</span><span class="sxs-lookup"><span data-stu-id="c23f2-121">Follow these steps to begin building your network plan:</span></span>

1. <span data-ttu-id="c23f2-122">Wechseln Sie im Microsoft Teams Admin Center zum Netzwerk Planner.</span><span class="sxs-lookup"><span data-stu-id="c23f2-122">Go to the Network Planner in the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="c23f2-123">Klicken Sie auf der Registerkarte **Netzwerkplan** auf **Netzwerkplan hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="c23f2-123">On the **Network Plan** tab, click **Add a network plan**.</span></span>

3. <span data-ttu-id="c23f2-124">Geben Sie einen Namen und eine Beschreibung für Ihren Netzwerkplan ein.</span><span class="sxs-lookup"><span data-stu-id="c23f2-124">Enter a name and description for your network plan.</span></span> <span data-ttu-id="c23f2-125">Der Netzwerkplan wird in der Liste der verfügbaren Pläne angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c23f2-125">The network plan will appear in the list of available plans.</span></span>

4. <span data-ttu-id="c23f2-126">Klicken Sie auf den Plan Namen, um den neuen Plan auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="c23f2-126">Click the plan name to select the new plan.</span></span>

5. <span data-ttu-id="c23f2-127">Fügen Sie Websites hinzu, um eine Darstellung des Netzwerk Setups Ihrer Organisation zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c23f2-127">Add sites to create a representation of your organization’s network setup.</span></span>

    <span data-ttu-id="c23f2-128">Je nach Netzwerk Ihrer Organisation möchten Sie möglicherweise Websites verwenden, um ein Gebäude, einen Office-Standort oder etwas anderes darzustellen.</span><span class="sxs-lookup"><span data-stu-id="c23f2-128">Depending on your organization’s network, you may want to use sites to represent a building, an office location, or something else.</span></span> <span data-ttu-id="c23f2-129">Websites können über ein WAN verbunden sein, um die Freigabe von Internet-und/oder PSTN-Verbindungen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="c23f2-129">Sites might be connected by a WAN to allow sharing of internet and/or PSTN connections.</span></span> <span data-ttu-id="c23f2-130">Um optimale Ergebnisse zu erzielen, erstellen Sie Websites mit lokalen Verbindungen, bevor Sie Websites erstellen, die eine Remoteverbindung mit dem Internet oder PSTN herstellen.</span><span class="sxs-lookup"><span data-stu-id="c23f2-130">For best results, create sites with local connections before you create sites that remotely connect to the internet or PSTN.</span></span>

    <span data-ttu-id="c23f2-131">So erstellen Sie eine Website:</span><span class="sxs-lookup"><span data-stu-id="c23f2-131">To create a site:</span></span>

    1. <span data-ttu-id="c23f2-132">Fügen Sie einen Namen und eine Beschreibung für Ihre Website hinzu.</span><span class="sxs-lookup"><span data-stu-id="c23f2-132">Add a name and description for your site.</span></span>

    2. <span data-ttu-id="c23f2-133">Fügen Sie unter **Netzwerkeinstellungen**die Anzahl der Netzwerkbenutzer auf dieser Website hinzu (erforderlich).</span><span class="sxs-lookup"><span data-stu-id="c23f2-133">Under **Network settings**, add the number of network users at that site (required).</span></span>

    3. <span data-ttu-id="c23f2-134">Hinzufügen von Netzwerkdetails: WAN-fähig, WAN-Kapazität, Internet-Ausstieg (**lokal** oder **Remote**) und PSTN-Ausgang (keine, lokal oder Remote).</span><span class="sxs-lookup"><span data-stu-id="c23f2-134">Add network details: WAN-enabled, WAN capacity, internet egress (**Local** or **Remote**), and PSTN egress (none, local, or remote).</span></span>

      > [!NOTE]
      > <span data-ttu-id="c23f2-135">Sie müssen WAN-und Internet Kapazitäts Nummern hinzufügen, um bestimmte Bandbreiten Empfehlungen anzuzeigen, wenn Sie einen Bericht generieren.</span><span class="sxs-lookup"><span data-stu-id="c23f2-135">You must add WAN and internet capacity numbers to see specific bandwidth recommendations when you generate a report.</span></span>

    4. <span data-ttu-id="c23f2-136">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="c23f2-136">Click **Save**.</span></span>

## <a name="create-a-report"></a><span data-ttu-id="c23f2-137">Erstellen eines Berichts</span><span class="sxs-lookup"><span data-stu-id="c23f2-137">Create a report</span></span>

<span data-ttu-id="c23f2-138">Nachdem Sie alle Websites hinzugefügt haben, können Sie einen Bericht wie folgt erstellen.</span><span class="sxs-lookup"><span data-stu-id="c23f2-138">After you add all sites, you can create a report, as follows.</span></span>

1. <span data-ttu-id="c23f2-139">Klicken Sie auf der Registerkarte **Berichte** auf **Bericht starten**.</span><span class="sxs-lookup"><span data-stu-id="c23f2-139">On the **Reports** tab, click **Start a report**.</span></span>

2. <span data-ttu-id="c23f2-140">Verteilen Sie für jede Website, die Sie erstellen, die Anzahl der Benutzer auf die verfügbaren Personas.</span><span class="sxs-lookup"><span data-stu-id="c23f2-140">For each site you create, distribute the number of users across the available personas.</span></span> <span data-ttu-id="c23f2-141">Wenn Sie die Microsoft Recommended Personas verwenden, wird die Nummer automatisch verteilt (80% Office Worker und 20% Remote Worker).</span><span class="sxs-lookup"><span data-stu-id="c23f2-141">If you use the Microsoft recommended personas, the number will be distributed automatically (80% office worker and 20% remote worker).</span></span>

3. <span data-ttu-id="c23f2-142">Nachdem Sie die Verteilung abgeschlossen haben, klicken Sie auf **Bericht generieren**.</span><span class="sxs-lookup"><span data-stu-id="c23f2-142">After you complete the distribution, click **Generate report**.</span></span>

    <span data-ttu-id="c23f2-143">Der generierte Bericht zeigt die Bandbreitenanforderungen in verschiedenen Ansichten an, sodass Sie die Ausgabe klar verstehen können:</span><span class="sxs-lookup"><span data-stu-id="c23f2-143">The generated report will show the bandwidth requirements in several different views so that you can clearly understand the output:</span></span>
    - <span data-ttu-id="c23f2-144">Eine Tabelle mit einzelnen Berechnungen zeigt die Bandbreitenanforderungen für die einzelnen zulässigen Aktivitäten an.</span><span class="sxs-lookup"><span data-stu-id="c23f2-144">A table with individual calculations will display bandwidth requirements for each permitted activity.</span></span>
    - <span data-ttu-id="c23f2-145">In einer zusätzlichen Ansicht werden die gesamten Anforderungen an die Bandbreite mit Empfehlungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c23f2-145">An additional view will show the overall bandwidth needs with recommendations.</span></span>

4. <span data-ttu-id="c23f2-146">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="c23f2-146">Click **Save**.</span></span> <span data-ttu-id="c23f2-147">Ihr Bericht steht in der Liste Berichte zur späteren Anzeige zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="c23f2-147">Your report will be available on the reports list for later viewing.</span></span>
