---
title: Nicht zugewiesene Telefonnummer
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaVacantNumMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24eca749-a9f3-40e7-839b-d21c3ef7d533
description: Nicht zugewiesene Nummern sind Rufnummern, die für Ihre Organisation gültig sind, jedoch keinem Benutzer oder Telefon zugewiesen sind. In der Tabelle mit den nicht zugewiesenen Nummern ist angegeben, wie Anrufe bei nicht zugewiesenen Nummern behandelt werden sollen.
ms.openlocfilehash: da019253c0ed76446e0bb385e58e21c027628802
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/20/2018
ms.locfileid: "19968328"
---
# <a name="unassigned-phone-number"></a><span data-ttu-id="f1432-104">Nicht zugewiesene Telefonnummer</span><span class="sxs-lookup"><span data-stu-id="f1432-104">Unassigned Phone Number</span></span>
 
<span data-ttu-id="f1432-p102">Nicht zugewiesene Nummern sind Rufnummern, die für Ihre Organisation gültig sind, jedoch keinem Benutzer oder Telefon zugewiesen sind. In der Tabelle mit den nicht zugewiesenen Nummern ist angegeben, wie Anrufe bei nicht zugewiesenen Nummern behandelt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f1432-p102">Unassigned numbers are phone numbers that are valid for your organization but are not assigned to a user or a phone. The unassigned number table identifies how you want calls to unassigned numbers to be treated.</span></span>
  
<span data-ttu-id="f1432-p103">Wie Sie die Tabelle nicht zugewiesener Rufnummern konfigurieren, richtet sich danach, wie Sie diese verwenden möchten. Sie können die Tabelle mit allen gültigen Durchwahlnummern für Ihre Organisation konfigurieren, nur mit nicht zugewiesenen Durchwahlnummern oder als eine Kombination beider Nummerntypen. Die Tabelle nicht zugewiesener Rufnummern kann sowohl zugewiesene als auch nicht zugewiesene Rufnummern enthalten, wird jedoch nur ausgelöst, wenn ein Anrufer eine derzeit nicht zugewiesene Rufnummer wählt. Wenn Sie alle gültigen Durchwahlnummern in die Tabelle nicht zugewiesener Nummern aufnehmen, können Sie eine Aktion angeben, die bei Ausscheiden eines Mitarbeiters aus der Organisation ausgeführt werden soll. In diesem Fall ist eine Neukonfiguration der Tabelle nicht erforderlich. Wenn Sie nicht zugewiesene Durchwahlnummern in die Tabelle aufnehmen, können Sie die Aktion anpassen, die für bestimmte Nummern ausgeführt wird. Wenn Sie beispielsweise die Durchwahlnummer für Ihren Kundendienst ändern, können Sie die alte Rufnummer des Kundendiensts in die Tabelle aufnehmen und ihr eine Ansage zuweisen, in der die neue Rufnummer bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="f1432-p103">How you configure the unassigned number table depends on how you want to use it. You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers. The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned. If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table. If you include unassigned extensions in the table, you can tailor the action that occurs for specific numbers. For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and assign it to an announcement that provides the new number.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f1432-113">Bevor Sie die Tabelle nicht zugewiesener Nummern konfigurieren, müssen Sie bereits eine oder mehrere Ansagen definiert oder eine automatische Telefonzentrale von Exchange eingerichtet haben.</span><span class="sxs-lookup"><span data-stu-id="f1432-113">Before you configure the unassigned number table, you must have already either defined one or more announcements or set up an Exchange UM Auto Attendant.</span></span> 
  
<span data-ttu-id="f1432-114">Auf der Seite **Nicht zugewiesene Nummer** wird eine Liste mit den nicht zugewiesenen Nummernbereichen Ihrer Organisation angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f1432-114">The **Unassigned Number** page displays a list of the unassigned numbers ranges defined for your organization.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="f1432-115">Mögliche Aufgaben</span><span class="sxs-lookup"><span data-stu-id="f1432-115">Tasks you can perform</span></span>

<span data-ttu-id="f1432-116">Auf der Seite **Nicht zugewiesene Nummer** können Sie die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="f1432-116">You can perform the following tasks from the **Unassigned Number** page:</span></span>
  
- <span data-ttu-id="f1432-117">Erstellen eines neuen Bereichs nicht zugewiesener Nummern</span><span class="sxs-lookup"><span data-stu-id="f1432-117">Create a new unassigned number range</span></span>
    
- <span data-ttu-id="f1432-118">Ändern eines Bereichs nicht zugewiesener Nummern</span><span class="sxs-lookup"><span data-stu-id="f1432-118">Change an existing unassigned number range</span></span>
    
- <span data-ttu-id="f1432-119">Löschen eines Bereichs nicht zugewiesener Nummern</span><span class="sxs-lookup"><span data-stu-id="f1432-119">Delete an unassigned number range</span></span>
    
- <span data-ttu-id="f1432-120">Ändern der Reihenfolge eines Bereichs nicht zugewiesener Nummern, um zu ermitteln, welche Aktion bei einer nicht zugewiesenen Nummer zuerst auf einen eingehenden Anruf angewendet werden soll</span><span class="sxs-lookup"><span data-stu-id="f1432-120">Change the order of the unassigned number ranges to determine which action should be applied first to an incoming call that matches an unassigned number.</span></span> 
    
## <a name="ui-reference"></a><span data-ttu-id="f1432-121">Referenz zur Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="f1432-121">UI Reference</span></span>

<span data-ttu-id="f1432-122">In der folgenden Liste sind die Befehle der Seite beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f1432-122">The following list describes the commands on the page.</span></span>
  
- <span data-ttu-id="f1432-123">**Neue** Startet einen neuen Bereichs nicht zugewiesenen Nummern an.</span><span class="sxs-lookup"><span data-stu-id="f1432-123">**New** Starts a new unassigned number range.</span></span>
    
- <span data-ttu-id="f1432-124">**Bearbeiten** Öffnet den ausgewählten nicht zugewiesenen Nummernbereich zur Bearbeitung, wählt alle nicht zugewiesenen Nummernbereiche in der Liste oder löscht den ausgewählten Bereich nicht zugewiesenen Nummern.</span><span class="sxs-lookup"><span data-stu-id="f1432-124">**Edit** Opens the selected unassigned number range for editing, selects all the unassigned number ranges in the list, or deletes the selected unassigned number range.</span></span>
    
- <span data-ttu-id="f1432-125">**Nach oben verschieben** Verschiebt den ausgewählten Bereichs nicht zugewiesenen Nummern oben in der Liste an, sodass Skype für Business Server früher ermittelt und wendet die angegebene Aktion vor dem Anwenden von Aktionen für andere Bereiche in der Liste angegeben.</span><span class="sxs-lookup"><span data-stu-id="f1432-125">**Move up** Moves the selected unassigned number range up in the list so that Skype for Business Server finds it sooner and applies the specified action before applying actions specified for other ranges in the list.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f1432-126">Skype für Business Server sucht den Tabelle nicht zugewiesenen Nummern von oben nach unten und verwendet den ersten Bereich, der nicht zugewiesene Nummer entspricht.</span><span class="sxs-lookup"><span data-stu-id="f1432-126">Skype for Business Server searches the unassigned number table from top to bottom and uses the first range that matches the unassigned number.</span></span> <span data-ttu-id="f1432-127">Wenn Sie z. B. über einen Bereich verfügen, auf den als letzte Aktion zurückgegriffen werden soll, platzieren Sie diesen Bereich ganz unten in der Liste.</span><span class="sxs-lookup"><span data-stu-id="f1432-127">For example, if you have a range that specifies a last resort action, make sure that range is at the bottom of the list.</span></span> 
  
- <span data-ttu-id="f1432-128">**Nach unten verschieben** Verschiebt den ausgewählten Bereich nicht zugewiesenen Nummern in der Liste nach unten.</span><span class="sxs-lookup"><span data-stu-id="f1432-128">**Move down** Moves the selected unassigned number range down in the list.</span></span>
    
- <span data-ttu-id="f1432-129">**Alle Commit** Speichert alle nicht zugewiesenen Nummernbereiche vorgenommenen Änderungen.</span><span class="sxs-lookup"><span data-stu-id="f1432-129">**Commit all** Saves all the changes you made to unassigned number ranges.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="f1432-130">Mit diesem Befehl werden alle Änderungen gespeichert, die Sie auf der Seite **Neue nicht zugewiesene Nummer** und der Seite **Nicht zugewiesene Nummer bearbeiten** vorgenommen haben.</span><span class="sxs-lookup"><span data-stu-id="f1432-130">This command saves all the changes that you made on the **New Unassigned Number** page and the **Edit Unassigned Number** page.</span></span>
  
- <span data-ttu-id="f1432-131">**Aktualisieren** Aktualisiert die Liste der nicht zugewiesenen Nummernbereiche.</span><span class="sxs-lookup"><span data-stu-id="f1432-131">**Refresh** Refreshes the list of unassigned number ranges.</span></span>
    
<span data-ttu-id="f1432-132">In der folgenden Liste werden die Felder der Seite beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f1432-132">The following list describes the fields on the page.</span></span>
  
- <span data-ttu-id="f1432-133">**Name** Der eindeutige Name, der den Bereich nicht zugewiesener Nummern.</span><span class="sxs-lookup"><span data-stu-id="f1432-133">**Name** The unique name that identifies the unassigned number range.</span></span>
    
- <span data-ttu-id="f1432-134">**Zustand** Mit der Datenbank und die keinen wurden dargestellt, welche Nummernbereiche gespeichert.</span><span class="sxs-lookup"><span data-stu-id="f1432-134">**State** Shows which number ranges have been saved to the database and which have not.</span></span>
    
- <span data-ttu-id="f1432-135">**Anfangsbereich gibt** Die Anfangsnummer des Bereichs nicht zugewiesener Nummern.</span><span class="sxs-lookup"><span data-stu-id="f1432-135">**Start range** The beginning number of the unassigned number range.</span></span>
    
- <span data-ttu-id="f1432-136">**Endbereich** Die Endnummer des Bereichs nicht zugewiesener Nummern.</span><span class="sxs-lookup"><span data-stu-id="f1432-136">**End range** The ending number of the unassigned number range.</span></span>
    
- <span data-ttu-id="f1432-137">**Ziel** Die Dienst-ID des Anwendungsdiensts, die die ankündigungsanwendung hostet, die eingehende Anrufe für diesen Bereich nicht zugewiesener Nummern behandelt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f1432-137">**Destination** The service ID of the Application service that hosts the Announcement application that will handle incoming calls to this range of unassigned numbers.</span></span>
    
- <span data-ttu-id="f1432-138">**Ankündigung** Die Ankündigung, die für diesen Bereich nicht zugewiesener Nummern wiedergegeben werden.</span><span class="sxs-lookup"><span data-stu-id="f1432-138">**Announcement** The announcement that will be played for this range of unassigned numbers.</span></span>
    
<span data-ttu-id="f1432-139">Ausführliche Informationen zur Ankündigung Features und Funktionen finden Sie unter [Planen für die ankündigungsanwendung in Skype für Unternehmen](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="f1432-139">For details about Announcement features and capabilities, see [Plan for the Announcement application in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) in the Planning documentation.</span></span> <span data-ttu-id="f1432-140">Ausführliche Informationen zur Verwendung von nicht zugewiesenen Nummernbereiche finden Sie unter [Konfigurieren von Routing von nicht zugewiesenen Telefonnummern](http://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="f1432-140">For details about working with unassigned number ranges, see [Configure Routing of Unassigned Phone Numbers](http://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) in the Operations documentation.</span></span>
  

