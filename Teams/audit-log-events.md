---
title: "Suchen nach Überwachungsprotokoll für Ereignisse in Microsoft Teams | Microsoft-Support"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Hier erfahren Sie, wie Microsoft Teams-Daten aus dem Überwachungsprotokoll abgerufen werden."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 9d1a1c274ace1e680f890d7fe8abdea52886b073
ms.sourcegitcommit: 9756856140ea56a94e986c134c5c04e53e5c0fa6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2017
---
<a name="search-the-audit-log-for-events-in-microsoft-teams"></a><span data-ttu-id="2cff2-103">Suchen nach Überwachungsprotokoll für Ereignisse in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2cff2-103">Search the audit log for events in Microsoft Teams</span></span>
==================================================

<span data-ttu-id="2cff2-p101">Das Überwachungsprotokoll bietet Ad-hoc-Suchfunktionen für wichtige Ereignisse in allen Office 365-Diensten. Beispiele für in Microsoft Teams spezifische Ereignisse finden Sie unten:</span><span class="sxs-lookup"><span data-stu-id="2cff2-p101">The Audit Log provides ad-hoc search capabilities into notable events across Office 365 services. For Microsoft Teams specifically, below are a few examples of events captured:</span></span>

-   <span data-ttu-id="2cff2-106">Teamerstellung</span><span class="sxs-lookup"><span data-stu-id="2cff2-106">Team Creation</span></span>

-   <span data-ttu-id="2cff2-107">Teamlöschung</span><span class="sxs-lookup"><span data-stu-id="2cff2-107">Team Deletion</span></span>

-   <span data-ttu-id="2cff2-108">Hinzugefügter Kanal</span><span class="sxs-lookup"><span data-stu-id="2cff2-108">Added Channel</span></span>

-   <span data-ttu-id="2cff2-109">Geänderte Einstellung</span><span class="sxs-lookup"><span data-stu-id="2cff2-109">Changed Setting</span></span>

<span data-ttu-id="2cff2-110">Die vollständige Ereignisliste für Office 365 ist sehr umfangreich und steht [hier](https://support.office.com/en-us/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c?ui=en-US&rs=en-US&ad=US#ID0EABAAA=Audited_activities) zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="2cff2-110">The complete event list across Office 365 is quite extensive and can be found [here](https://support.office.com/en-us/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c?ui=en-US&rs=en-US&ad=US#ID0EABAAA=Audited_activities).</span></span>

<span data-ttu-id="2cff2-p102">Bevor Sie sich einen näheren Einblick verschaffen ist die Aktivierung der Überwachung erforderlich. Um die Überwachung zu aktivieren, navigieren Sie zum Admin Center *Sicherheit und Compliance*. Klicken Sie unter *Nach Aktivität suchen* auf **Aufzeichnung jetzt beginnen**. Nach 24 Stunden stehen Überprüfungsdaten über *Überwachungsprotokollsuche* unter der Registerkarte *Suche und Untersuchung* zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="2cff2-p102">Before you can dig into audit insights, auditing must first be enabled. To enable Auditing, navigate to the *Security & Compliance* Admin Center. Under *Search for activity*, click on **Start recording now**. After 24hrs, audit data will be available via *Audit Log Search* located under the *Search & Investigation* tab.</span></span>


| |  |
|---------|---------|
|![Screenshot der Homepage im Security & Compliance Center](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image1.png)<br></br><span data-ttu-id="2cff2-116">Wichtig</span><span class="sxs-lookup"><span data-stu-id="2cff2-116">Important</span></span>     |<span data-ttu-id="2cff2-117">Überwachungsdaten sind erst ab dem Zeitpunkt verfügbar, an dem die Überwachung aktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="2cff2-117">Audit data is only available from the point at which Auditing was enabled.</span></span>         |

![Screenshot der Seite „Überwachungsprotokollsuche“ im Security & Compliance Center](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image2.png)

<span data-ttu-id="2cff2-119">Sehen wir uns nun an, wie Microsoft Teams-Daten aus dem Überwachungsprotokoll abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="2cff2-119">Now, let’s look at how to retrieve Microsoft Teams data from the Audit Log:</span></span>

1.  <span data-ttu-id="2cff2-p103">Um die Überwachungprotokolldaten abzurufen, navigieren Sie zum [Admin Center „Sicherheit und Compliance“](https://go.microsoft.com/fwlink/?linkid=855775). Wählen Sie unter *Suche und Untersuchung* die Option **Überwachungsprotokollsuche** aus.</span><span class="sxs-lookup"><span data-stu-id="2cff2-p103">To retrieve Audit Log information, navigate to the [Security & Compliance Admin Center](https://go.microsoft.com/fwlink/?linkid=855775). Under *Search & Investigation*, select **Audit log search.**</span></span>

    <span data-ttu-id="2cff2-p104">a. Microsoft Teams hat Überwachungsaktivitäten definiert, die wie unten gezeigt ausgewählt werden können.</span><span class="sxs-lookup"><span data-stu-id="2cff2-p104">a.  Microsoft Teams has defined audit activities that can be selected as shown below.</span></span>

![Screenshot der Seite „Überwachungsprotokollsuche“ im Security & Compliance Center](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image3.png)

2.  <span data-ttu-id="2cff2-p105">Geben Sie nach Auswahl der gewünschten Aktivitäten einen Datumsbereich sowie die Benutzer an, für die Microsoft Teams-Daten abgerufen werden sollen. Klicken Sie auf **Suchen**, um die Ergebnisse abzurufen.</span><span class="sxs-lookup"><span data-stu-id="2cff2-p105">After selecting the activities of interest, supply a date range and users to retrieve Microsoft Teams information from. Click **Search** to retrieve the results.</span></span>

3.  <span data-ttu-id="2cff2-127">Diese Informationen können nach Excel exportiert und nach Bedarf gefiltert werden.</span><span class="sxs-lookup"><span data-stu-id="2cff2-127">This information can be exported to Excel and filtered as needed.</span></span>


|  | |
|---------|---------|
|![Ausrufezeichensymbol](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image1.png)<br></br><span data-ttu-id="2cff2-129">Wichtig</span><span class="sxs-lookup"><span data-stu-id="2cff2-129">Important</span></span> |<span data-ttu-id="2cff2-130">Wenn die Überprüfung zuvor nicht aktiviert war, müssen Sie diesen Vorgang nachholen, damit die Daten im Überprüfungsprotokoll angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="2cff2-130">If auditing has not been enabled previously, that needs to be enabled before data will appear in the Audit Log.</span></span>         |
