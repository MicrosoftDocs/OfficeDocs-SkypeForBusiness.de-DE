---
title: Ausführen eines Berichts zur Anzeige der aktiven StaffHub-Verwendung
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Hier erfahren Sie, wie Sie einen Bericht ausführen, um eine Liste der aktiven StaffHub-Benutzer in Ihrer Organisation abzurufen.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: eb337fdb79c0977f4bcacd782d6705947b5b8466
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235386"
---
# <a name="run-a-report-to-show-active-staffhub-usage"></a><span data-ttu-id="8fe02-103">Ausführen eines Berichts zur Anzeige der aktiven StaffHub-Verwendung</span><span class="sxs-lookup"><span data-stu-id="8fe02-103">Run a report to show active StaffHub usage</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8fe02-104">Ab dem 1. Oktober 2019 wird Microsoft StaffHub eingestellt.</span><span class="sxs-lookup"><span data-stu-id="8fe02-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="8fe02-105">Wir erstellen StaffHub-Funktionen in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8fe02-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="8fe02-106">Heute umfasst Teams die Schicht-App für die Terminplanung, und zusätzliche Funktionen werden im Laufe der Zeit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="8fe02-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="8fe02-107">StaffHub wird für alle Benutzer am 1. Oktober 2019 nicht mehr funktionieren.</span><span class="sxs-lookup"><span data-stu-id="8fe02-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="8fe02-108">Jede Person, die versucht, StaffHub zu öffnen, wird eine Meldung angezeigt, die Sie zum Herunterladen von Teams anweist.</span><span class="sxs-lookup"><span data-stu-id="8fe02-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="8fe02-109">Weitere Informationen finden Sie unter [Microsoft StaffHub](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="8fe02-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="8fe02-110">Führen Sie die Schritte in diesem Artikel aus, um einen Bericht auszuführen, um eine Liste der aktiven StaffHub-Benutzer in Ihrer Organisation abzurufen.</span><span class="sxs-lookup"><span data-stu-id="8fe02-110">Use the steps in this article to run a report to get a list of active StaffHub users in your organization.</span></span> <span data-ttu-id="8fe02-111">Diese Informationen sind möglicherweise praktisch, wenn Sie sich vorbereiten, [Ihre StaffHub-Teams in Microsoft Teams zu verschieben](move-staffhub-teams-to-shifts-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="8fe02-111">This information may come in handy when you prepare to [move your StaffHub teams to Microsoft Teams](move-staffhub-teams-to-shifts-in-teams.md).</span></span> <span data-ttu-id="8fe02-112">Aus dem Bericht Wissen Sie, wer Sie in Ihre Kommunikation einbeziehen müssen, wenn Sie den Wechsel von StaffHub zu Teams durchführen.</span><span class="sxs-lookup"><span data-stu-id="8fe02-112">From the report, you'll know who you need to include in your communications when you make the switch from StaffHub to Teams.</span></span>

<span data-ttu-id="8fe02-113">Sie müssen Azure AD Premium haben, um die Schritte in diesem Artikel ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="8fe02-113">You need to have Azure AD Premium to perform the steps in this article.</span></span>

1. <span data-ttu-id="8fe02-114">Anmelden beim Azure-Portal.</span><span class="sxs-lookup"><span data-stu-id="8fe02-114">Sign in to the Azure portal.</span></span>
2. <span data-ttu-id="8fe02-115">Klicken Sie im linken Bereich auf die **Azure Active Directory** -Ressource.</span><span class="sxs-lookup"><span data-stu-id="8fe02-115">In the left pane, click the **Azure Active Directory** resource.</span></span>
3. <span data-ttu-id="8fe02-116">Klicken Sie unter **Überwachung**auf **Anmeldungen**.</span><span class="sxs-lookup"><span data-stu-id="8fe02-116">Under **Monitoring**, click **Sign-ins**.</span></span>
4. <span data-ttu-id="8fe02-117">Geben \*\*\*\* Sie unter Anwendung **Microsoft StaffHub**.</span><span class="sxs-lookup"><span data-stu-id="8fe02-117">Under **Application**, type **Microsoft StaffHub**.</span></span>
5. <span data-ttu-id="8fe02-118">Legen Sie den gewünschten Datumsbereich für den Bericht fest, und klicken Sie dann auf über **nehmen**.</span><span class="sxs-lookup"><span data-stu-id="8fe02-118">Set the date range that you want for the report, and then click **Apply**.</span></span> 

    ![Screenshot mit Schritten zur Anzeige der aktiven StaffHub-Verwendung](../../media/staffhub-active-usage-report.png)

## <a name="related-topics"></a><span data-ttu-id="8fe02-120">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="8fe02-120">Related topics</span></span>

- [<span data-ttu-id="8fe02-121">Verschieben Ihrer Microsoft StaffHub-Teams in die Schichten in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8fe02-121">Move your Microsoft StaffHub teams to Shifts in Microsoft Teams</span></span>](move-staffhub-teams-to-shifts-in-teams.md)
