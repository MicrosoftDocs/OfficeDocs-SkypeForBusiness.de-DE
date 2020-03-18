---
title: Erstellen von Personen-Manager-Teams in Microsoft Teams
ms.reviewer: pbethi
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: Hier erfahren Sie, wie Sie ein PowerShell-Skript verwenden, um ein Team für jeden Manager zu erstellen, dessen Direct-Teammitglieder sind.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: eb6cd6ed74bebd0cbd729b828c152b9f04d1fc1f
ms.sourcegitcommit: cfaae3ecbf853766de788b4825a86e04f68868ca
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/18/2020
ms.locfileid: "42796198"
---
# <a name="create-people-manager-teams-in-microsoft-teams"></a><span data-ttu-id="4abcc-103">Erstellen von Personen-Manager-Teams in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4abcc-103">Create people manager teams in Microsoft Teams</span></span>


<span data-ttu-id="4abcc-104">Wenn Sie Microsoft Teams ausrollen, anstatt mit einem "leeren Schiefer" (keine Teams oder Kanäle) zu starten, wird dringend empfohlen, ein Basisframework für Teams und Kanäle einzurichten.</span><span class="sxs-lookup"><span data-stu-id="4abcc-104">When you roll out Microsoft Teams, rather than launching with a "blank slate" (no teams or channels), we strongly recommend that you set up a base framework of teams and channels.</span></span> <span data-ttu-id="4abcc-105">Auf diese Weise können Sie die "Team-Ausbreitung" verhindern, bei der Benutzerzahl reiche Teams erstellen, wenn Sie Kanäle in vorhandenen Teams erstellen sollten.</span><span class="sxs-lookup"><span data-stu-id="4abcc-105">This helps to prevent "team sprawl," where users create numerous teams when they should be creating channels in existing teams.</span></span> <span data-ttu-id="4abcc-106">Um Ihnen den Einstieg in eine gut durchdachte Teams-und Kanalstruktur zu erleichtern, haben wir ein PowerShell-Skript erstellt, das ein Team für jeden Ihrer ersten und zweiten Personen Manager erstellt, wobei die direkten Berichte jedes Managers als Teammitglieder erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="4abcc-106">To help you get started with a well-designed teams and channels structure, we've created a PowerShell script that creates a team for each of your first and second line people managers, with each manager's direct reports as team members.</span></span> <span data-ttu-id="4abcc-107">Hierbei handelt es sich um ein "Point-in-Time"-Skript (es werden Ihre Teams oder Kanäle nicht automatisch aktualisiert, wenn Personen zu einer Organisation hinzugefügt oder daraus entfernt werden).</span><span class="sxs-lookup"><span data-stu-id="4abcc-107">This is a "point-in-time" script (it doesn't update your teams or channels automatically when people are added or removed from an organization).</span></span> <span data-ttu-id="4abcc-108">Aber es ist ein wertvolles Tool, mit dem Sie von Anfang an eine bestimmte Reihenfolge für Ihre Teamstruktur aufzwingen können.</span><span class="sxs-lookup"><span data-stu-id="4abcc-108">But it's a valuable tool you can use to impose some order on your Teams structure from the start.</span></span> <span data-ttu-id="4abcc-109">Dieses Skript liest Ihre Azure AD, ruft eine Liste der Manager und deren direkte Berichte ab.</span><span class="sxs-lookup"><span data-stu-id="4abcc-109">This script reads your Azure AD, gets a list of managers and their direct reports.</span></span> <span data-ttu-id="4abcc-110">In dieser Liste wird ein Team pro Personalmanager erstellt.</span><span class="sxs-lookup"><span data-stu-id="4abcc-110">It uses this list to create one team per people manager.</span></span> 

## <a name="how-to-use-the-powershell-script"></a><span data-ttu-id="4abcc-111">Verwenden des PowerShell-Skripts</span><span class="sxs-lookup"><span data-stu-id="4abcc-111">How to use the PowerShell script</span></span> 

<span data-ttu-id="4abcc-112">Beginnen Sie mit der Ausführung der [Export Manager und Ihres Direct-Skripts](scripts/powershell-script-create-teams-from-managers-export-managers.md) (wobei davon ausgegangen wird, dass Sie die PowerShell [-Module Connect-AzureAd](https://docs.microsoft.com/powershell/module/azuread/connect-azuread?view=azureadps-2.0) und [Connect-Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps) bereits ausgeführt haben).</span><span class="sxs-lookup"><span data-stu-id="4abcc-112">Start by running the [Export managers and their directs script](scripts/powershell-script-create-teams-from-managers-export-managers.md) (which assumes you've already run the [Connect-AzureAd](https://docs.microsoft.com/powershell/module/azuread/connect-azuread?view=azureadps-2.0) and [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps) PowerShell modules).</span></span> <span data-ttu-id="4abcc-113">Die *Export Manager und Ihr directs* -Skript erstellen eine durch Tabstopps getrennte Datei (ExportedManagerDirects. txt), in der alle Manager mit ihren direkten Berichten aufgelistet sind.</span><span class="sxs-lookup"><span data-stu-id="4abcc-113">The *Export managers and their directs* script creates a tab-delimited file (ExportedManagerDirects.txt) that lists all managers with their direct reports.</span></span> 

<span data-ttu-id="4abcc-114">Führen Sie dann das [Skript "neue Personen-Manager-Teams erstellen](scripts/powershell-script-create-teams-from-managers-new-teams.md)" aus.</span><span class="sxs-lookup"><span data-stu-id="4abcc-114">Then, run the [Create new people manager teams script](scripts/powershell-script-create-teams-from-managers-new-teams.md).</span></span> <span data-ttu-id="4abcc-115">Dieses Skript liest in der Datei "ExportedManagerDirects. txt" und erstellt ein Team für jeden Manager, dessen direkte Berichte dieser Manager als Mitglieder sind.</span><span class="sxs-lookup"><span data-stu-id="4abcc-115">This script reads in the ExportedManagerDirects.txt file and creates a team for each manager, with that manager's direct reports as members.</span></span> <span data-ttu-id="4abcc-116">Wenn Manager oder Direct für Teams nicht aktiviert ist, werden Sie vom Skript übersprungen, und es wird kein Team erstellt.</span><span class="sxs-lookup"><span data-stu-id="4abcc-116">If any manager or direct isn't enabled for Teams, the script skips them and doesn't create a team.</span></span> <span data-ttu-id="4abcc-117">(Überprüfen Sie den Bericht, und führen Sie dann das Skript erneut aus, nachdem Sie die Teams für alle Benutzer aktiviert haben, die Sie benötigen.</span><span class="sxs-lookup"><span data-stu-id="4abcc-117">(Review the report, then rerun the script after you've turned on Teams for anybody who needs it.</span></span> <span data-ttu-id="4abcc-118">Das Skript erstellt kein zweites Team für einen Manager, für den es bereits ein Team erstellt hat.)</span><span class="sxs-lookup"><span data-stu-id="4abcc-118">The script won't create a second team for any manager it's already created a team for.)</span></span>

<span data-ttu-id="4abcc-119">Für jedes Team erstellt das Skript einen allgemeinen und "nur für Spaß"-Kanal.</span><span class="sxs-lookup"><span data-stu-id="4abcc-119">For each team, the script creates a General and "Just for fun" channel.</span></span> 

## <a name="best-practices"></a><span data-ttu-id="4abcc-120">Bewährte Methoden</span><span class="sxs-lookup"><span data-stu-id="4abcc-120">Best practices</span></span>

- <span data-ttu-id="4abcc-121">Bitten Sie jeden Personen Manager, die Website für die Krisenkommunikation Ihrer Organisation als Registerkarte zum Kanal "Allgemein" für jedes Team hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="4abcc-121">Ask each people manager to add your organization's crisis communications website as a tab to the General channel for each team.</span></span> 

- <span data-ttu-id="4abcc-122">Schauen Sie sich die neue APP für Krisenkommunikation an, indem Sie diesen Blogbeitrag vom 8. März 2020: [koordinieren der Krisenkommunikation mit Microsoft Teams + Power Platform](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715).</span><span class="sxs-lookup"><span data-stu-id="4abcc-122">Check out the new Crisis Communications app by reading this March 8, 2020 blog post: [Coordinate crisis communications using Microsoft Teams + Power Platform](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715).</span></span>

## <a name="related-topics"></a><span data-ttu-id="4abcc-123">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="4abcc-123">Related topics</span></span>

[<span data-ttu-id="4abcc-124">Bewährte Methoden zum Organisieren von Teams</span><span class="sxs-lookup"><span data-stu-id="4abcc-124">Best practices for organizing teams</span></span>](best-practices-organizing.md)

[<span data-ttu-id="4abcc-125">Erstellen eines organisationsweiten Teams in Teams</span><span class="sxs-lookup"><span data-stu-id="4abcc-125">Create an org-wide team in Teams</span></span>](create-an-org-wide-team.md)
