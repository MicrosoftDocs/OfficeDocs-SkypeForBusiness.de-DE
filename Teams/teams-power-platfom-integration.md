---
title: Integration von Teams in Microsoft Power Platform
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: kvivek
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: Erfahren Sie mehr über die Integration von Teams in Microsoft Power Platform-Tools, wie Power BI, Power apps, Power Automation und Power Virtual Agents.
ms.openlocfilehash: 2dfcf0dffec420e70d8f90c669bb64d2e9236c3e
ms.sourcegitcommit: 3db7c450d3afbc1049e1016d51016442e5764634
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203995"
---
# <a name="teams-integration-with-microsoft-power-platform"></a><span data-ttu-id="18eca-103">Integration von Teams in Microsoft Power Platform</span><span class="sxs-lookup"><span data-stu-id="18eca-103">Teams integration with Microsoft Power Platform</span></span>

<span data-ttu-id="18eca-104">Microsoft Power Platform unterstützt Benutzer bei der Beschleunigung ihrer Entwicklung mit Tools mit wenig Code, um Daten mithilfe von **Power BI**zu analysieren, benutzerdefinierte Apps mithilfe von **Power apps**zu erstellen, Prozesse mithilfe von **Power Automation**zu automatisieren und intelligente Bots mit **Power Virtual Agents** schneller als je zuvor zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="18eca-104">Microsoft Power Platform helps users accelerate their development with low-code tools to analyze data using **Power BI**, build custom apps using **Power Apps**, automate processes using **Power Automate**, and create intelligent bots using **Power Virtual Agents** more quickly than ever.</span></span> <span data-ttu-id="18eca-105">Mit der Verlagerung zu Remote-und Hybrid Arbeit hat Microsoft Teams Menschen auf der ganzen Welt das Erstellen, zusammenarbeiten und kommunizieren weiter ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="18eca-105">With the shift to remote and hybrid work, Microsoft Teams has enabled people around the world to continue to create, collaborate, and communicate.</span></span> <span data-ttu-id="18eca-106">Mit mehr als 75 Millionen täglichen aktiven Benutzern sind Teams dafür, wie die Mitarbeiter Arbeit erledigen.</span><span class="sxs-lookup"><span data-stu-id="18eca-106">With more than 75 million daily active users, Teams is how people are getting work done.</span></span>

:::image type="content" source="media/teams-power-platform-integration.png" alt-text="Bild Zusammenfassungs Teams und Microsoft Power Platform":::

<span data-ttu-id="18eca-108">Microsoft Power Platform bietet zahlreiche Integrationsfunktionen in Teams, in denen Sie **Power BI** -Berichte in den Arbeitsbereich "Teams" einbetten, apps, die mit **Power apps** erstellt wurden, als Registerkarte oder persönliche App einbetten, einen **Power-Automatisierungs** -Flow aus einer beliebigen Nachricht auslösen oder Adaptive Karten verwenden und ihren mit **Power Virtual Agents** erstellten bot zu Teams hinzufügen, mit denen</span><span class="sxs-lookup"><span data-stu-id="18eca-108">Microsoft Power Platform provides many integration capabilities with Teams where you can embed **Power BI** reports in the Teams workspace, embed apps created using **Power Apps** as a tab or personal app, trigger a **Power Automate** flow from any message or use adaptive cards, and add your bot created using **Power Virtual Agents** to Teams for other members of your organization to interact with.</span></span>

<span data-ttu-id="18eca-109">Ab September 2020 wurde die Integration in die Microsoft Power Platform verbessert, damit Benutzer die folgenden Aufgaben ausführen können, *ohne die Oberfläche des Teams verlassen*zu müssen:</span><span class="sxs-lookup"><span data-stu-id="18eca-109">Starting September 2020, integration with Microsoft Power Platform has improved to let users do the following *without ever leaving the Teams interface*:</span></span>

- <span data-ttu-id="18eca-110">Sie können Dashboards, Berichte und Apps mithilfe von **Power BI** erstellen und freigeben, um datengesteuerte Entscheidungen zu treffen.</span><span class="sxs-lookup"><span data-stu-id="18eca-110">Create and share dashboards, reports, and apps using **Power BI** to make data-driven decisions.</span></span>
- <span data-ttu-id="18eca-111">Erstellen und Freigeben von Anwendungen mit geringem Code, die mit einem integrierten **Power apps** Studio erstellt wurden, indem Sie eine Verbindung mit ihren Geschäftsdaten herstellen, die entweder in der neuen zugrunde liegenden Datenplattform (Project Oakdale), Microsoft 365 oder in anderen Datenquellen über Connectors gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="18eca-111">Create and share low-code, purpose-built apps using an integrated **Power Apps** studio by connecting to your business data stored either in the new underlying data platform (Project Oakdale), Microsoft 365, or in other data sources through connectors.</span></span>
- <span data-ttu-id="18eca-112">Erstellen Sie automatisierte Workflows zwischen ihren apps und Diensten, um Dateien zu synchronisieren, Benachrichtigungen zu erhalten, Daten zu sammeln und mehr mithilfe von **Power Automation**.</span><span class="sxs-lookup"><span data-stu-id="18eca-112">Create automated workflows between your apps and services to synchronize files, get notifications, collect data, and more using **Power Automate**.</span></span>
- <span data-ttu-id="18eca-113">Erstellen Sie Bots mithilfe einer geführten, nicht-Code-Grafikschnittstelle mithilfe von **Power Virtual Agents** , um mühelos digitale Assistenten innerhalb von Teams zu erstellen und diese für Ihre Kollegen zur Verfügung zu stellen, mit denen Sie chatten können.</span><span class="sxs-lookup"><span data-stu-id="18eca-113">Build bots using a guided, no-code graphical interface using **Power Virtual Agents** to easily create digital assistants within Teams and make them available to your colleagues to chat with.</span></span>

<span data-ttu-id="18eca-114">Die neuen Funktionen zum Erstellen von apps, Bots und Workflows werden durch die neue integrierte, niedrige Code-Datenplattform für Teams, [Projekt Oakdale](https://go.microsoft.com/fwlink/?linkid=2143541), die relationale Datenspeicher, umfangreiche Datentypen, unternehmensweite Governance und die Bereitstellung einer Lösung mit einem Klick bereitstellt, unterstützt.</span><span class="sxs-lookup"><span data-stu-id="18eca-114">The new capabilities to create apps, bots, and workflows are backed by the new built-in, low-code data platform for Teams, [Project Oakdale](https://go.microsoft.com/fwlink/?linkid=2143541), which provides relational data storage, rich data types, enterprise grade governance, and one-click solution deployment.</span></span> <span data-ttu-id="18eca-115">Project Oakdale ist auf dem [gemeinsamen Datendienst](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)aufgebaut.</span><span class="sxs-lookup"><span data-stu-id="18eca-115">Project Oakdale is built on top of [Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).</span></span> <span data-ttu-id="18eca-116">Mit Project Oakdale können Benutzer benutzerdefinierte, Soforteinsatz bereite Lösungen aus dem App Store für Teams suchen und installieren, in denen gängige branchenübergreifende Szenarien vorgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="18eca-116">With Project Oakdale, Teams users can find and install custom, ready-to-use solutions from the Teams app store that showcase common scenarios across industries.</span></span> <span data-ttu-id="18eca-117">Sie können diese benutzerdefinierten Lösungen anpassen und erweitern, um Sie an das Branding und die Anforderungen Ihrer Organisation anzupassen.</span><span class="sxs-lookup"><span data-stu-id="18eca-117">You can customize and extend these custom solutions to adapt to your organization's branding and requirements.</span></span>

## <a name="licensing"></a><span data-ttu-id="18eca-118">Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="18eca-118">Licensing</span></span>

<span data-ttu-id="18eca-119">Die neuen Funktionen stehen für die Auswahl von Microsoft 365-Abonnements zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="18eca-119">The new capabilities are available to the select Microsoft 365 subscriptions.</span></span>

- <span data-ttu-id="18eca-120">Weitere Informationen zu den Lizenzierungsanforderungen für Power apps, Power Automation, Power Virtual Agents und Project Oakdale finden Sie unter [Lizenzierung](https://go.microsoft.com/fwlink/?linkid=2143647).</span><span class="sxs-lookup"><span data-stu-id="18eca-120">For more information about licensing requirements for Power Apps, Power Automate, Power Virtual Agents, and Project Oakdale, see [Licensing](https://go.microsoft.com/fwlink/?linkid=2143647).</span></span>
- <span data-ttu-id="18eca-121">Weitere Informationen zu den Lizenzierungsanforderungen für Power BI finden Sie unter [Voraussetzungen](https://go.microsoft.com/fwlink/?linkid=2143490).</span><span class="sxs-lookup"><span data-stu-id="18eca-121">For more information about licensing requirements for Power BI, see [Requirements](https://go.microsoft.com/fwlink/?linkid=2143490).</span></span>
 
## <a name="how-do-i-get-started"></a><span data-ttu-id="18eca-122">Wie starte ich?</span><span class="sxs-lookup"><span data-stu-id="18eca-122">How do I get started?</span></span>

- [<span data-ttu-id="18eca-123">Power BI und Teams</span><span class="sxs-lookup"><span data-stu-id="18eca-123">Power BI and Teams</span></span>](https://aka.ms/pbi-teams-docs)
- [<span data-ttu-id="18eca-124">Power-apps und Teams</span><span class="sxs-lookup"><span data-stu-id="18eca-124">Power Apps and Teams</span></span>](https://aka.ms/pa-teams-docs)
- [<span data-ttu-id="18eca-125">Power automatisieren und Teams</span><span class="sxs-lookup"><span data-stu-id="18eca-125">Power Automate and Teams</span></span>](https://aka.ms/pauto-teams-docs)
- [<span data-ttu-id="18eca-126">Power Virtual-Agents und-Teams</span><span class="sxs-lookup"><span data-stu-id="18eca-126">Power Virtual Agents and Teams</span></span>](https://aka.ms/pva-teams-docs)
