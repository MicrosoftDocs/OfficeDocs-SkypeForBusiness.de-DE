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
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 49091f7d8ada565adea61bf8219c6da828358893
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "37569663"
---
# <a name="run-a-report-to-show-active-staffhub-usage"></a><span data-ttu-id="5375b-103">Ausführen eines Berichts zum Anzeigen der aktiven StaffHub-Nutzung</span><span class="sxs-lookup"><span data-stu-id="5375b-103">Run a report to show active StaffHub usage</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5375b-104">2019, 31. Dezember, wird Microsoft StaffHub eingestellt.</span><span class="sxs-lookup"><span data-stu-id="5375b-104">Effective December 31, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="5375b-105">Wir erstellen StaffHub-Funktionen in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5375b-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="5375b-106">Heute umfasst Teams die Schicht-App für die Terminplanung, und zusätzliche Funktionen werden im Laufe der Zeit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="5375b-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="5375b-107">StaffHub wird am 31. Dezember 2019 nicht mehr für alle Benutzer funktionieren.</span><span class="sxs-lookup"><span data-stu-id="5375b-107">StaffHub will stop working for all users on December 31, 2019.</span></span> <span data-ttu-id="5375b-108">Jede Person, die versucht, StaffHub zu öffnen, wird eine Meldung angezeigt, die Sie zum Herunterladen von Teams anweist.</span><span class="sxs-lookup"><span data-stu-id="5375b-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="5375b-109">Weitere Informationen finden Sie unter [Microsoft StaffHub](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="5375b-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="5375b-110">Führen Sie die Schritte in diesem Artikel aus, um einen Bericht auszuführen, um eine Liste der aktiven StaffHub-Benutzer in Ihrer Organisation abzurufen.</span><span class="sxs-lookup"><span data-stu-id="5375b-110">Use the steps in this article to run a report to get a list of active StaffHub users in your organization.</span></span> <span data-ttu-id="5375b-111">Diese Informationen sind möglicherweise praktisch, wenn Sie sich vorbereiten, [Ihre StaffHub-Teams in Microsoft Teams zu verschieben](move-staffhub-teams-to-shifts-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="5375b-111">This information may come in handy when you prepare to [move your StaffHub teams to Microsoft Teams](move-staffhub-teams-to-shifts-in-teams.md).</span></span> <span data-ttu-id="5375b-112">Aus dem Bericht Wissen Sie, wer Sie in Ihre Kommunikation einbeziehen müssen, wenn Sie den Wechsel von StaffHub zu Teams durchführen.</span><span class="sxs-lookup"><span data-stu-id="5375b-112">From the report, you'll know who you need to include in your communications when you make the switch from StaffHub to Teams.</span></span>

<span data-ttu-id="5375b-113">Sie müssen Azure AD Premium haben, um die Schritte in diesem Artikel ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="5375b-113">You need to have Azure AD Premium to perform the steps in this article.</span></span>

1. <span data-ttu-id="5375b-114">Anmelden beim Azure-Portal.</span><span class="sxs-lookup"><span data-stu-id="5375b-114">Sign in to the Azure portal.</span></span>
2. <span data-ttu-id="5375b-115">Klicken Sie im linken Bereich auf die **Azure Active Directory** -Ressource.</span><span class="sxs-lookup"><span data-stu-id="5375b-115">In the left pane, click the **Azure Active Directory** resource.</span></span>
3. <span data-ttu-id="5375b-116">Klicken Sie unter **Überwachung**auf **Anmeldungen**.</span><span class="sxs-lookup"><span data-stu-id="5375b-116">Under **Monitoring**, click **Sign-ins**.</span></span>
4. <span data-ttu-id="5375b-117">Geben \*\*\*\* Sie unter Anwendung **Microsoft StaffHub**.</span><span class="sxs-lookup"><span data-stu-id="5375b-117">Under **Application**, type **Microsoft StaffHub**.</span></span>
5. <span data-ttu-id="5375b-118">Legen Sie den gewünschten Datumsbereich für den Bericht fest, und klicken Sie dann auf über **nehmen**.</span><span class="sxs-lookup"><span data-stu-id="5375b-118">Set the date range that you want for the report, and then click **Apply**.</span></span> 

    ![Screenshot mit Schritten zum Anzeigen der Verwendung von Active StaffHub](../../media/staffhub-active-usage-report.png)

## <a name="related-topics"></a><span data-ttu-id="5375b-120">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="5375b-120">Related topics</span></span>

- [<span data-ttu-id="5375b-121">Verschieben Ihrer Microsoft StaffHub-Teams in die Schichten in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5375b-121">Move your Microsoft StaffHub teams to Shifts in Microsoft Teams</span></span>](move-staffhub-teams-to-shifts-in-teams.md)
