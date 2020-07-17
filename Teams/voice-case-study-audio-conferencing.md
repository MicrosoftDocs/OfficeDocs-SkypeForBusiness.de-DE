---
title: Teams Voice Contoso-Fallstudie
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Teams Voice Case Study für Multi-National Corporation
appliesto:
- Microsoft Teams
ms.openlocfilehash: f58f3518202fd836ff962374e8f3b3a00ab71817
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786037"
---
# <a name="contoso-case-study-audio-conferencing"></a><span data-ttu-id="e4aa2-103">Contoso-Fallstudie: Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="e4aa2-103">Contoso case study: Audio Conferencing</span></span>

<span data-ttu-id="e4aa2-104">Wenn Sie eine Vorstellung von Audiokonferenzen gewinnen möchten, was es &mdash; ist, was es kostet, die Verfügbarkeit und wie es funktioniert, hat &mdash; contoso [Audiokonferenzen in Office 365](deploy-audio-conferencing-teams-landing-page.md)bewertet.</span><span class="sxs-lookup"><span data-stu-id="e4aa2-104">To gain an understanding of audio conferencing&mdash;what it is, what it costs, availability, and how it works&mdash;Contoso reviewed [Audio Conferencing in Office 365](deploy-audio-conferencing-teams-landing-page.md).</span></span> 

## <a name="overview"></a><span data-ttu-id="e4aa2-105">Übersicht</span><span class="sxs-lookup"><span data-stu-id="e4aa2-105">Overview</span></span> 

<span data-ttu-id="e4aa2-106">Für Audiokonferenzen verwendet Contoso Telefonnummern, die sowohl innerhalb der Organisation als auch extern bekannt sind.</span><span class="sxs-lookup"><span data-stu-id="e4aa2-106">For audio conferencing, Contoso used phone numbers that are well known within the organization as well as externally.</span></span> <span data-ttu-id="e4aa2-107">Da Contoso diese Nummern nach Möglichkeit beibehalten wollte, haben Sie die Informationen zum Zuweisen von dedizierten und freigegebenen Telefonnummern zur Audiokonferenz-Brücke überprüft.</span><span class="sxs-lookup"><span data-stu-id="e4aa2-107">Because Contoso wanted to maintain these numbers where possible, they reviewed the information on assigning dedicated and shared phone numbers to the audio conferencing bridge.</span></span> 

<span data-ttu-id="e4aa2-108">Basierend auf Ihren Recherchen hat Contoso die folgenden Entscheidungen getroffen:</span><span class="sxs-lookup"><span data-stu-id="e4aa2-108">Based on their research, Contoso made the following decisions:</span></span> 

- <span data-ttu-id="e4aa2-109">Nur ein Bevölkerungssegment, das regelmäßig Audiokonferenz-Anrufe hostet, erhält Audiokonferenz-Lizenzen.</span><span class="sxs-lookup"><span data-stu-id="e4aa2-109">Only a segment of the population that regularly host audio conferencing calls would receive Audio Conferencing licenses.</span></span> 

- <span data-ttu-id="e4aa2-110">Contoso würde dedizierte Telefonnummern verwenden und Ihre vorhandenen Nummern für die Verwendung mit Audiokonferenzen portieren.</span><span class="sxs-lookup"><span data-stu-id="e4aa2-110">Contoso would use dedicated phone numbers and port their existing numbers for use with Audio Conferencing.</span></span>   

<span data-ttu-id="e4aa2-111">Da Contoso-Benutzer Skype for Business verwenden und die Postfächer aller Benutzer online sind, haben viele Benutzer bereits Besprechungen geplant.</span><span class="sxs-lookup"><span data-stu-id="e4aa2-111">Because Contoso users were using Skype for Business and all users' mailboxes reside online, many users have existing meetings scheduled.</span></span> <span data-ttu-id="e4aa2-112">Contoso liest [mithilfe des Besprechungs Migrations Diensts (MMS)](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) , um zu erfahren, dass vorhandene Besprechungen automatisch für Contoso aktualisiert werden, wenn Sie den Endbenutzer in den TeamsOnly-Modus ändern.</span><span class="sxs-lookup"><span data-stu-id="e4aa2-112">Contoso read [Using the Meeting Migration Service (MMS)](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) to learn that existing meetings are updated automatically for Contoso when they change the end user to TeamsOnly mode.</span></span>  


## <a name="configuration"></a><span data-ttu-id="e4aa2-113">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="e4aa2-113">Configuration</span></span>

<span data-ttu-id="e4aa2-114">Telefonnummern, die mit Audiokonferenzen verknüpft sind, werden im Telefon System als Dienstnummern bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="e4aa2-114">Phone numbers that are associated with audio conferencing are referred to as service numbers within Phone System.</span></span> 

- <span data-ttu-id="e4aa2-115">Bei Speicherorten mit Anrufplänen, um Ihre vorhandenen Telefonnummern von Ihrem Telefonanbieter zu Office 365 zu portieren, folgte Contoso den Schritten unter [Abrufen von Telefonnummern für Dienstleistungen](getting-service-phone-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="e4aa2-115">For locations using Calling Plans, to port their existing phone numbers from their phone carrier to Office 365, Contoso followed the steps in [Getting service phone numbers](getting-service-phone-numbers.md).</span></span>

- <span data-ttu-id="e4aa2-116">Wenn Sie die Audiokonferenz-Lizenz dem Endbenutzer im technischen Pilotprojekt zuweisen möchten, folgte der Contoso-Administrator den Schritten unter [Verwalten der audiokonferenzeinstellungen für Ihre Organisation](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="e4aa2-116">To assign the Audio Conferencing license to the end user in the technical pilot, the Contoso administrator followed the steps in [Manage the Audio Conferencing settings for your organization](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md).</span></span> 

- <span data-ttu-id="e4aa2-117">Für den Geschäfts Pilot und die Migration verwendete Contoso die Gruppenbasierte Lizenzierung, indem Sie die Schritte unter [Zuweisen von Lizenzen zu Benutzern durch Gruppenmitgliedschaft in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)befolgten.</span><span class="sxs-lookup"><span data-stu-id="e4aa2-117">For the business pilot and migration, Contoso used group-based licensing by following the steps in [Assign licenses to users by group membership in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>  

 

 