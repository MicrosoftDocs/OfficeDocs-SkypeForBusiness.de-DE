---
title: Ausführen eines Berichts zum Anzeigen der aktiven StaffHub-Nutzung
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Hier erfahren Sie, wie Sie einen Bericht ausführen, um eine Liste der aktiven StaffHub-Benutzer in Ihrer Organisation abzurufen.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5701e508440a338e0f0ba1fd133dac98ec35d57f
ms.sourcegitcommit: ee2b4c207b3c9f993309f66cf8016e137c001c7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/23/2020
ms.locfileid: "44349629"
---
# <a name="run-a-report-to-show-active-staffhub-usage"></a><span data-ttu-id="7a881-103">Ausführen eines Berichts zum Anzeigen der aktiven StaffHub-Nutzung</span><span class="sxs-lookup"><span data-stu-id="7a881-103">Run a report to show active StaffHub usage</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7a881-104">Gültig 30. Juni 2020, Microsoft StaffHub wird eingestellt.</span><span class="sxs-lookup"><span data-stu-id="7a881-104">Effective June 30, 2020, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="7a881-105">Einige StaffHub-Funktionen werden in Microsoft Teams integriert.</span><span class="sxs-lookup"><span data-stu-id="7a881-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="7a881-106">Heute umfasst Microsoft Teams die App "Schichten" für die Zeitplanverwaltung, und im Laufe der Zeit werden zusätzliche Funktionen bereit stehen.</span><span class="sxs-lookup"><span data-stu-id="7a881-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="7a881-107">StaffHub wird am 30. Juni 2020 nicht mehr für alle Benutzer funktionieren.</span><span class="sxs-lookup"><span data-stu-id="7a881-107">StaffHub will stop working for all users on June 30, 2020.</span></span> <span data-ttu-id="7a881-108">Jedem Benutzer, der StaffHub zu öffnen versucht, wird eine Meldung angezeigt, die ihn zum Microsoft Teams-Download leitet.</span><span class="sxs-lookup"><span data-stu-id="7a881-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="7a881-109">Weitere Informationen finden Sie unter [Microsoft StaffHub wird eingestellt](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="7a881-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="7a881-110">Führen Sie die Schritte in diesem Artikel aus, um einen Bericht auszuführen, um eine Liste der aktiven StaffHub-Benutzer in Ihrer Organisation abzurufen.</span><span class="sxs-lookup"><span data-stu-id="7a881-110">Use the steps in this article to run a report to get a list of active StaffHub users in your organization.</span></span> <span data-ttu-id="7a881-111">Diese Informationen sind möglicherweise praktisch, wenn Sie sich vorbereiten, [Ihre StaffHub-Teams in Microsoft Teams zu verschieben](move-staffhub-teams-to-shifts-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="7a881-111">This information may come in handy when you prepare to [move your StaffHub teams to Microsoft Teams](move-staffhub-teams-to-shifts-in-teams.md).</span></span> <span data-ttu-id="7a881-112">Aus dem Bericht Wissen Sie, wer Sie in Ihre Kommunikation einbeziehen müssen, wenn Sie den Wechsel von StaffHub zu Teams durchführen.</span><span class="sxs-lookup"><span data-stu-id="7a881-112">From the report, you'll know who you need to include in your communications when you make the switch from StaffHub to Teams.</span></span>

<span data-ttu-id="7a881-113">Sie müssen Azure AD Premium haben, um die Schritte in diesem Artikel ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="7a881-113">You need to have Azure AD Premium to perform the steps in this article.</span></span>

1. <span data-ttu-id="7a881-114">Anmelden beim Azure-Portal.</span><span class="sxs-lookup"><span data-stu-id="7a881-114">Sign in to the Azure portal.</span></span>
2. <span data-ttu-id="7a881-115">Klicken Sie im linken Bereich auf die **Azure Active Directory** -Ressource.</span><span class="sxs-lookup"><span data-stu-id="7a881-115">In the left pane, click the **Azure Active Directory** resource.</span></span>
3. <span data-ttu-id="7a881-116">Klicken Sie unter **Überwachung**auf **Anmeldungen**.</span><span class="sxs-lookup"><span data-stu-id="7a881-116">Under **Monitoring**, click **Sign-ins**.</span></span>
4. <span data-ttu-id="7a881-117">Geben **Application**Sie unter Anwendung **Microsoft StaffHub**.</span><span class="sxs-lookup"><span data-stu-id="7a881-117">Under **Application**, type **Microsoft StaffHub**.</span></span>
5. <span data-ttu-id="7a881-118">Legen Sie den gewünschten Datumsbereich für den Bericht fest, und klicken Sie dann auf über **nehmen**.</span><span class="sxs-lookup"><span data-stu-id="7a881-118">Set the date range that you want for the report, and then click **Apply**.</span></span> 

    ![Screenshot mit Schritten zum Anzeigen der Verwendung von Active StaffHub](../../media/staffhub-active-usage-report.png)

## <a name="related-topics"></a><span data-ttu-id="7a881-120">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="7a881-120">Related topics</span></span>

- [<span data-ttu-id="7a881-121">Verschieben Ihrer Microsoft StaffHub-Teams in die Schichten in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7a881-121">Move your Microsoft StaffHub teams to Shifts in Microsoft Teams</span></span>](move-staffhub-teams-to-shifts-in-teams.md)
