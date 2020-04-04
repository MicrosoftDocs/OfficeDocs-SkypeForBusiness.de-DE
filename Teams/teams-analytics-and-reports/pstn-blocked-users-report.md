---
title: Microsoft Teams-Bericht "PSTN-blockierte Benutzer"
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-rifer
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
MS.collection:
- M365-voice
description: Verwenden Sie den Bericht "PSTN-blockierte Benutzer" im Microsoft Teams Admin Center, um sich einen Überblick über die Team Benutzer Ihrer Organisation zu verschaffen, die für das tätigen von PSTN-anrufen gesperrt sind.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e6055533138f08bafbdc9c39b03350612075840f
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/03/2020
ms.locfileid: "43140686"
---
# <a name="microsoft-teams-pstn-blocked-users-report"></a><span data-ttu-id="62d72-103">Microsoft Teams-Bericht "PSTN-blockierte Benutzer"</span><span class="sxs-lookup"><span data-stu-id="62d72-103">Microsoft Teams PSTN blocked users report</span></span>

<span data-ttu-id="62d72-104">Der Bericht "PSTN-blockierte Benutzer" im Microsoft Teams Admin Center zeigt die Benutzer in Ihrer Organisation an, die für das tätigen von PSTN-anrufen in Teams gesperrt sind.</span><span class="sxs-lookup"><span data-stu-id="62d72-104">The PSTN blocked users report in the Microsoft Teams admin center shows you the users in your organization who are blocked from making PSTN calls in Teams.</span></span> <span data-ttu-id="62d72-105">Sie können weitere Informationen zu den einzelnen blockierten Benutzern anzeigen, einschließlich ihrer zugewiesenen Telefonnummer und dem Grund, warum Sie keine Anrufe tätigen konnten.</span><span class="sxs-lookup"><span data-stu-id="62d72-105">You can view more information about each blocked user, including their assigned phone number and the reason they were blocked from making calls.</span></span>

## <a name="view-the-report"></a><span data-ttu-id="62d72-106">Anzeigen des Berichts</span><span class="sxs-lookup"><span data-stu-id="62d72-106">View the report</span></span>

<span data-ttu-id="62d72-107">Klicken Sie in der linken Navigationsleiste des Microsoft Teams admin Centers auf **Analytics & Berichte** > **Nutzungsberichte**.</span><span class="sxs-lookup"><span data-stu-id="62d72-107">In the left navigation of the Microsoft Teams admin center, click **Analytics & reports** > **Usage reports**.</span></span> <span data-ttu-id="62d72-108">Wählen Sie auf der Registerkarte **Berichte anzeigen** unter **Bericht**die Option **PSTN-blockierte Benutzer**aus, und klicken Sie dann auf **Bericht ausführen**.</span><span class="sxs-lookup"><span data-stu-id="62d72-108">On the **View reports** tab, under **Report**, select **PSTN blocked users**, and then click **Run report**.</span></span>

<span data-ttu-id="62d72-109">![Screenshot des Berichts "PSTN-blockierte Benutzer" im Admin Center](../media/teams-reports-pstn-blocked-users-with-callouts.png "Screenshot des Berichts "PSTN-blockierte Benutzer" im Microsoft Teams Admin Center mit nummerierten Beschriftungen")</span><span class="sxs-lookup"><span data-stu-id="62d72-109">![Screenshot of the PSTN blocked users report report in the admin center](../media/teams-reports-pstn-blocked-users-with-callouts.png "Screenshot of the PSTN blocked users report in the Microsoft Teams admin center with numbered callouts")</span></span>

## <a name="interpret-the-report"></a><span data-ttu-id="62d72-110">Interpretieren des Berichts</span><span class="sxs-lookup"><span data-stu-id="62d72-110">Interpret the report</span></span>

|<span data-ttu-id="62d72-111">Beschriftung</span><span class="sxs-lookup"><span data-stu-id="62d72-111">Callout</span></span> |<span data-ttu-id="62d72-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="62d72-112">Description</span></span>  |
|--------|-------------|
|<span data-ttu-id="62d72-113">**1**</span><span class="sxs-lookup"><span data-stu-id="62d72-113">**1**</span></span>   |<span data-ttu-id="62d72-114">Jeder Bericht hat ein Datum, zu dem er generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="62d72-114">Each report has a date for when it was generated.</span></span> <span data-ttu-id="62d72-115">Die Berichte weisen in der Regel eine Latenz von 24 bis 48 Stunden ab dem Zeitpunkt der Aktivität auf.</span><span class="sxs-lookup"><span data-stu-id="62d72-115">The reports usually reflect a 24 to 48 hour latency from time of activity.</span></span> |
|<span data-ttu-id="62d72-116">**2**</span><span class="sxs-lookup"><span data-stu-id="62d72-116">**2**</span></span>   |<span data-ttu-id="62d72-117">Die X-Achse ist das Datum.</span><span class="sxs-lookup"><span data-stu-id="62d72-117">The X axis is the date.</span></span> <span data-ttu-id="62d72-118">Bei der Y-Achse handelt es sich um die Anzahl der Benutzer.</span><span class="sxs-lookup"><span data-stu-id="62d72-118">The Y axis is the number of users.</span></span> <br><span data-ttu-id="62d72-119">Zeigen Sie auf den Punkt an einem bestimmten Datum, um zu sehen, wie viele Benutzer an diesem Datum blockiert sind.</span><span class="sxs-lookup"><span data-stu-id="62d72-119">Hover over the dot on a given date to see the number of users blocked on that date.</span></span> |
|<span data-ttu-id="62d72-120">**3**</span><span class="sxs-lookup"><span data-stu-id="62d72-120">**3**</span></span>   |<span data-ttu-id="62d72-121">Die Tabelle enthält eine Aufschlüsselung aller Benutzer, die keine PSTN-Anrufe tätigen können.</span><span class="sxs-lookup"><span data-stu-id="62d72-121">The table gives a breakdown of all users who are blocked from making PSTN calls.</span></span>  <span data-ttu-id="62d72-122">Sie zeigt alle Benutzer an, denen Telefon System-oder Audiokonferenzen zugewiesen sind, und gibt Ihnen weitere Informationen zu den einzelnen Benutzern.</span><span class="sxs-lookup"><span data-stu-id="62d72-122">It shows all users who have Phone System or Audio Conferencing assigned and gives you more information about each user.</span></span> <ul><li><span data-ttu-id="62d72-123">**Anzeigename** ist der Anzeigename des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="62d72-123">**Display name** is the display name of the user.</span></span> <span data-ttu-id="62d72-124">Sie können auf den Anzeigenamen klicken, um zur Einstellungsseite des Benutzers im Microsoft Teams Admin Center zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="62d72-124">You can click the display name to go to the user's setting page in the Microsoft Teams admin center.</span></span> </li> <li><span data-ttu-id="62d72-125">**Telefon** ist die Nummer, die dem Benutzer zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="62d72-125">**Phone** is the number that's assigned to the user.</span></span></li> <li><span data-ttu-id="62d72-126">**Blockierter Grund** ist der Grund dafür, dass der Benutzer keine Anrufe tätigen kann.</span><span class="sxs-lookup"><span data-stu-id="62d72-126">**Blocked reason** is the reason the user is blocked from making calls.</span></span></li><li><span data-ttu-id="62d72-127">**Blockierte Aktion** zeigt an, ob der Benutzer blockiert oder freigegeben wurde, um in Teams PSTN-Anrufe zu tätigen.</span><span class="sxs-lookup"><span data-stu-id="62d72-127">**Blocked action**  tells you whether the user is blocked or unblocked from making PSTN calls in Teams.</span></span></li> <li><span data-ttu-id="62d72-128">**Blockierte Zeit** ist das Datum und die Uhrzeit (UTC), an dem der Benutzer für das tätigen von Anrufen gesperrt wurde.</span><span class="sxs-lookup"><span data-stu-id="62d72-128">**Blocked time** is the date and time (UTC) that the user was blocked from making calls.</span></span></li></li> </ul><span data-ttu-id="62d72-129">Um in der Tabelle die gewünschten Informationen anzuzeigen, stellen Sie sicher, dass Sie der Tabelle die entsprechenden Spalten hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="62d72-129">To see the information that you want in the table, make sure to add the columns to the table.</span></span> |
|<span data-ttu-id="62d72-130">**4**</span><span class="sxs-lookup"><span data-stu-id="62d72-130">**4**</span></span>   |<span data-ttu-id="62d72-131">Wählen Sie **Spalten bearbeiten** aus, um Spalten zur Tabelle hinzuzufügen oder daraus zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="62d72-131">Select **Edit columns** to add or remove columns in the table.</span></span>|
|<span data-ttu-id="62d72-132">**5**</span><span class="sxs-lookup"><span data-stu-id="62d72-132">**5**</span></span>   |<span data-ttu-id="62d72-133">Wählen Sie **Vollbild** aus, um den Bericht im Vollbildmodus anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="62d72-133">Select **Full screen** to view the report in full screen mode.</span></span>|

## <a name="related-topics"></a><span data-ttu-id="62d72-134">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="62d72-134">Related topics</span></span>

- [<span data-ttu-id="62d72-135">Teams – Analyse und Berichterstellung</span><span class="sxs-lookup"><span data-stu-id="62d72-135">Teams analytics and reporting</span></span>](teams-reporting-reference.md)