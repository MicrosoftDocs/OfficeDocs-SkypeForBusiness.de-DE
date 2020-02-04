---
title: Nicht zugewiesene Telefonnummer
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.VoiceFeaVacantNumMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24eca749-a9f3-40e7-839b-d21c3ef7d533
ROBOTS: NOINDEX, NOFOLLOW
description: Nicht zugewiesene Nummern sind Rufnummern, die für Ihre Organisation gültig sind, jedoch keinem Benutzer oder Telefon zugewiesen sind. In der Tabelle mit den nicht zugewiesenen Nummern ist angegeben, wie Anrufe bei nicht zugewiesenen Nummern behandelt werden sollen.
ms.openlocfilehash: 910b83f18350bc2a26da281f2e0660e8aa8913b9
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41690390"
---
# <a name="unassigned-phone-number"></a><span data-ttu-id="de989-104">Nicht zugewiesene Telefonnummer</span><span class="sxs-lookup"><span data-stu-id="de989-104">Unassigned Phone Number</span></span>

> [!NOTE]
> <span data-ttu-id="de989-105">Exchange um bleibt in Skype for Business Server 2019 verfügbar, wenn Sie Skype for Business 2019 mit Exchange 2013 oder Exchange 2016 integrieren.</span><span class="sxs-lookup"><span data-stu-id="de989-105">Exchange UM remains available in Skype for Business Server 2019 when you integrate Skype for Business 2019 with Exchange 2013 or Exchange 2016.</span></span> <span data-ttu-id="de989-106">Aufgrund von Änderungen an der Unterstützung in Exchange 2019 wird die Exchange um-Integration zu Gunsten der Features Cloud Voicemail und Cloud-automatische Telefonzentrale de-hervorgehoben.</span><span class="sxs-lookup"><span data-stu-id="de989-106">Due to changes in support in Exchange 2019, Exchange UM integration is being de-emphasized in favor of Cloud Voicemail and Cloud Auto Attendant features.</span></span>

<span data-ttu-id="de989-p103">Nicht zugewiesene Nummern sind Rufnummern, die für Ihre Organisation gültig sind, jedoch keinem Benutzer oder Telefon zugewiesen sind. In der Tabelle mit den nicht zugewiesenen Nummern ist angegeben, wie Anrufe bei nicht zugewiesenen Nummern behandelt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="de989-p103">Unassigned numbers are phone numbers that are valid for your organization but are not assigned to a user or a phone. The unassigned number table identifies how you want calls to unassigned numbers to be treated.</span></span>

<span data-ttu-id="de989-p104">Wie Sie die Tabelle nicht zugewiesener Rufnummern konfigurieren, richtet sich danach, wie Sie diese verwenden möchten. Sie können die Tabelle mit allen gültigen Durchwahlnummern für Ihre Organisation konfigurieren, nur mit nicht zugewiesenen Durchwahlnummern oder als eine Kombination beider Nummerntypen. Die Tabelle nicht zugewiesener Rufnummern kann sowohl zugewiesene als auch nicht zugewiesene Rufnummern enthalten, wird jedoch nur ausgelöst, wenn ein Anrufer eine derzeit nicht zugewiesene Rufnummer wählt. Wenn Sie alle gültigen Durchwahlnummern in die Tabelle nicht zugewiesener Nummern aufnehmen, können Sie eine Aktion angeben, die bei Ausscheiden eines Mitarbeiters aus der Organisation ausgeführt werden soll. In diesem Fall ist eine Neukonfiguration der Tabelle nicht erforderlich. Wenn Sie nicht zugewiesene Durchwahlnummern in die Tabelle aufnehmen, können Sie die Aktion anpassen, die für bestimmte Nummern ausgeführt wird. Wenn Sie beispielsweise die Durchwahlnummer für Ihren Kundendienst ändern, können Sie die alte Rufnummer des Kundendiensts in die Tabelle aufnehmen und ihr eine Ansage zuweisen, in der die neue Rufnummer bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="de989-p104">How you configure the unassigned number table depends on how you want to use it. You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers. The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned. If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table. If you include unassigned extensions in the table, you can tailor the action that occurs for specific numbers. For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and assign it to an announcement that provides the new number.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="de989-115">Bevor Sie die Tabelle nicht zugewiesener Nummern konfigurieren, müssen Sie bereits eine oder mehrere Ansagen definiert oder eine automatische Telefonzentrale von Exchange eingerichtet haben.</span><span class="sxs-lookup"><span data-stu-id="de989-115">Before you configure the unassigned number table, you must have already either defined one or more announcements or set up an Exchange UM Auto Attendant.</span></span>

<span data-ttu-id="de989-116">Auf der Seite **Nicht zugewiesene Nummer** wird eine Liste mit den nicht zugewiesenen Nummernbereichen Ihrer Organisation angezeigt.</span><span class="sxs-lookup"><span data-stu-id="de989-116">The **Unassigned Number** page displays a list of the unassigned numbers ranges defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="de989-117">Mögliche Aufgaben</span><span class="sxs-lookup"><span data-stu-id="de989-117">Tasks you can perform</span></span>

<span data-ttu-id="de989-118">Auf der Seite **Nicht zugewiesene Nummer** können Sie die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="de989-118">You can perform the following tasks from the **Unassigned Number** page:</span></span>

- <span data-ttu-id="de989-119">Erstellen eines neuen Bereichs nicht zugewiesener Nummern</span><span class="sxs-lookup"><span data-stu-id="de989-119">Create a new unassigned number range</span></span>

- <span data-ttu-id="de989-120">Ändern eines Bereichs nicht zugewiesener Nummern</span><span class="sxs-lookup"><span data-stu-id="de989-120">Change an existing unassigned number range</span></span>

- <span data-ttu-id="de989-121">Löschen eines Bereichs nicht zugewiesener Nummern</span><span class="sxs-lookup"><span data-stu-id="de989-121">Delete an unassigned number range</span></span>

- <span data-ttu-id="de989-122">Ändern der Reihenfolge eines Bereichs nicht zugewiesener Nummern, um zu ermitteln, welche Aktion bei einer nicht zugewiesenen Nummer zuerst auf einen eingehenden Anruf angewendet werden soll</span><span class="sxs-lookup"><span data-stu-id="de989-122">Change the order of the unassigned number ranges to determine which action should be applied first to an incoming call that matches an unassigned number.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="de989-123">Referenz zur Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="de989-123">UI Reference</span></span>

<span data-ttu-id="de989-124">In der folgenden Liste werden die Befehle der Seite beschrieben.</span><span class="sxs-lookup"><span data-stu-id="de989-124">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="de989-125">**Neu** Startet einen neuen nicht zugewiesenen Nummernbereich.</span><span class="sxs-lookup"><span data-stu-id="de989-125">**New** Starts a new unassigned number range.</span></span>

- <span data-ttu-id="de989-126">**Bearbeiten** von Öffnet den ausgewählten nicht zugewiesenen Nummernbereich für die Bearbeitung, wählt alle nicht zugewiesenen Nummernbereiche in der Liste aus oder löscht den ausgewählten nicht zugewiesenen Nummernbereich.</span><span class="sxs-lookup"><span data-stu-id="de989-126">**Edit** Opens the selected unassigned number range for editing, selects all the unassigned number ranges in the list, or deletes the selected unassigned number range.</span></span>

- <span data-ttu-id="de989-127">Nach **oben** Verschiebt den ausgewählten nicht zugewiesenen Nummernbereich in der Liste nach oben, sodass er von Skype for Business Server früher gefunden wird, und wendet die angegebene Aktion an, bevor die für andere Bereiche in der Liste angegebenen Aktionen angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="de989-127">**Move up** Moves the selected unassigned number range up in the list so that Skype for Business Server finds it sooner and applies the specified action before applying actions specified for other ranges in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="de989-128">Skype for Business Server durchsucht die Tabelle nicht zugewiesene Nummern von oben nach unten und verwendet den ersten Bereich, der der nicht zugewiesenen Zahl entspricht.</span><span class="sxs-lookup"><span data-stu-id="de989-128">Skype for Business Server searches the unassigned number table from top to bottom and uses the first range that matches the unassigned number.</span></span> <span data-ttu-id="de989-129">Wenn Sie z. B. über einen Bereich verfügen, auf den als letzte Aktion zurückgegriffen werden soll, platzieren Sie diesen Bereich ganz unten in der Liste.</span><span class="sxs-lookup"><span data-stu-id="de989-129">For example, if you have a range that specifies a last resort action, make sure that range is at the bottom of the list.</span></span>

- <span data-ttu-id="de989-130">**Nach unten** Verschiebt den ausgewählten nicht zugewiesenen Nummernbereich in der Liste nach unten.</span><span class="sxs-lookup"><span data-stu-id="de989-130">**Move down** Moves the selected unassigned number range down in the list.</span></span>

- <span data-ttu-id="de989-131">**Alle** übernehmen Speichert alle Änderungen, die Sie an nicht zugewiesenen Nummernbereichen vorgenommen haben.</span><span class="sxs-lookup"><span data-stu-id="de989-131">**Commit all** Saves all the changes you made to unassigned number ranges.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="de989-132">Mit diesem Befehl werden alle Änderungen gespeichert, die Sie auf der Seite **Neue nicht zugewiesene Nummer** und der Seite **Nicht zugewiesene Nummer bearbeiten** vorgenommen haben.</span><span class="sxs-lookup"><span data-stu-id="de989-132">This command saves all the changes that you made on the **New Unassigned Number** page and the **Edit Unassigned Number** page.</span></span>

- <span data-ttu-id="de989-133">**Aktualisieren** Aktualisiert die Liste der nicht zugewiesenen Nummernbereiche.</span><span class="sxs-lookup"><span data-stu-id="de989-133">**Refresh** Refreshes the list of unassigned number ranges.</span></span>

<span data-ttu-id="de989-134">In der folgenden Liste werden die Felder der Seite beschrieben.</span><span class="sxs-lookup"><span data-stu-id="de989-134">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="de989-135">**Name** Der eindeutige Name, der den nicht zugewiesenen Nummernbereich identifiziert.</span><span class="sxs-lookup"><span data-stu-id="de989-135">**Name** The unique name that identifies the unassigned number range.</span></span>

- <span data-ttu-id="de989-136">**Bundesland** Zeigt, welche Nummernbereiche in der Datenbank gespeichert wurden und welche nicht.</span><span class="sxs-lookup"><span data-stu-id="de989-136">**State** Shows which number ranges have been saved to the database and which have not.</span></span>

- <span data-ttu-id="de989-137">**Start Bereich** Die Anfangszahl des nicht zugewiesenen Nummernbereichs.</span><span class="sxs-lookup"><span data-stu-id="de989-137">**Start range** The beginning number of the unassigned number range.</span></span>

- <span data-ttu-id="de989-138">**Endbereich** Die letzte Nummer des nicht zugewiesenen Nummernbereichs.</span><span class="sxs-lookup"><span data-stu-id="de989-138">**End range** The ending number of the unassigned number range.</span></span>

- <span data-ttu-id="de989-139">**Ziel** Die Dienst-ID des Anwendungsdiensts, der die Ankündigungs Anwendung hostet, die eingehende Anrufe an diesen Bereich nicht zugewiesener Nummern abwickeln soll.</span><span class="sxs-lookup"><span data-stu-id="de989-139">**Destination** The service ID of the Application service that hosts the Announcement application that will handle incoming calls to this range of unassigned numbers.</span></span>

- <span data-ttu-id="de989-140">**Ankündigung** Die Ansage, die für diesen Bereich nicht zugewiesener Nummern abgespielt wird.</span><span class="sxs-lookup"><span data-stu-id="de989-140">**Announcement** The announcement that will be played for this range of unassigned numbers.</span></span>

<span data-ttu-id="de989-141">Details zu Ankündigungs Features und-Funktionen finden Sie unter [Planen der Ankündigungs Anwendung in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="de989-141">For details about Announcement features and capabilities, see [Plan for the Announcement application in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) in the Planning documentation.</span></span> <span data-ttu-id="de989-142">Ausführliche Informationen zur Verwendung von Bereichen nicht zugewiesener Nummern finden Sie in der Betriebsdokumentation unter [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx).</span><span class="sxs-lookup"><span data-stu-id="de989-142">For details about working with unassigned number ranges, see [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) in the Operations documentation.</span></span>


