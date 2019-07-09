---
title: Teams-Updates
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 05/13/2019
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: annaray
search.appverid: MET150
description: Erfahren Sie, wie der Desktop Client von Teams aktualisiert wird.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 436a2a3175cd057082c0e658ea5ab6d3db0364cc
ms.sourcegitcommit: 2f12e0d4dc2ef8e848a63bf3a9c63e07e4439cf5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2019
ms.locfileid: "35588183"
---
# <a name="teams-update-process"></a><span data-ttu-id="62875-103">Updateprozess für Teams</span><span class="sxs-lookup"><span data-stu-id="62875-103">Teams update process</span></span>

<span data-ttu-id="62875-104">Die Team-Web-App wird wöchentlich aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="62875-104">The Teams web app is updated weekly.</span></span>

<span data-ttu-id="62875-105">Updates für Teams-Desktop Clients werden alle zwei Wochen nach rigoroser interner Prüfung und Validierung über unser Technologie Adoptionsprogramm (Tap) veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="62875-105">Teams desktop client updates are released every two weeks after rigorous internal testing and validation through our Technology Adoption Program (TAP).</span></span> <span data-ttu-id="62875-106">Dies erfolgt in der Regel an einem Dienstag.</span><span class="sxs-lookup"><span data-stu-id="62875-106">This usually takes place on a Tuesday.</span></span> <span data-ttu-id="62875-107">Wenn ein wichtiges Update erforderlich ist, werden die Teams diesen Zeitplan umgehen und das Update freigeben, sobald es verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="62875-107">If a critical update is required, Teams will bypass this schedule and release the update as soon as it’s available.</span></span>

<span data-ttu-id="62875-108">Der Desktop-Client wird automatisch aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="62875-108">The desktop client updates itself automatically.</span></span> <span data-ttu-id="62875-109">Teams überprüft alle paar Stunden hinter den Kulissen, ob Updates vorhanden sind, lädt Sie herunter, und wartet dann, bis sich der Computer im Leerlauf befindet, bevor das Update automatisch installiert wird.</span><span class="sxs-lookup"><span data-stu-id="62875-109">Teams checks for updates every few hours behind the scenes, downloads it, and then waits for the computer to be idle before silently installing the update.</span></span>

<span data-ttu-id="62875-110">Benutzer können Updates auch manuell herunterladen, indem Sie im Dropdownmenü **Profil** oben rechts in der APP auf auf **Updates überprüfen** klicken.</span><span class="sxs-lookup"><span data-stu-id="62875-110">Users can also manually download updates by clicking **Check for updates** on the **Profile** drop-down menu on the top right of the app.</span></span> <span data-ttu-id="62875-111">Wenn ein Update verfügbar ist, wird es heruntergeladen und automatisch installiert, wenn sich der Computer im Leerlauf befindet.</span><span class="sxs-lookup"><span data-stu-id="62875-111">If an update is available, it will be downloaded and silently installed when the computer is idle.</span></span>

<span data-ttu-id="62875-112">Benutzer müssen angemeldet sein, damit Updates heruntergeladen werden können.</span><span class="sxs-lookup"><span data-stu-id="62875-112">Users need to be signed in for updates to be downloaded.</span></span> <span data-ttu-id="62875-113">Ab dem 9. Juli 2019 verwenden Teams-Clientupdates während des Updates deutlich geringere Netzwerkbandbreite.</span><span class="sxs-lookup"><span data-stu-id="62875-113">Starting July 9, 2019, Teams client updates use significantly lower network bandwidth during the update.</span></span> <span data-ttu-id="62875-114">Dies ist standardmäßig aktiviert und erfordert keine Aktion von Administratoren oder Benutzern.</span><span class="sxs-lookup"><span data-stu-id="62875-114">This is turned on by default and requires no action from admins or users.</span></span>


## <a name="what-about-updates-to-office-365-proplus"></a><span data-ttu-id="62875-115">Was ist mit Updates für Office 365 ProPlus?</span><span class="sxs-lookup"><span data-stu-id="62875-115">What about updates to Office 365 ProPlus?</span></span>

<span data-ttu-id="62875-116">Teams wird standardmäßig mit neuen Installationen von Office 365 ProPlus installiert, wie unter [Bereitstellen von Microsoft Teams mit Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/teams-install)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="62875-116">Teams is installed by default with new installations of Office 365 ProPlus as described in [Deploy Microsoft Teams with Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/teams-install).</span></span> 

<span data-ttu-id="62875-117">Teams folgt seinen eigenen Aktualisierungsprozess, wie oben beschrieben, und nicht den Updateprozess für die anderen Office-Apps wie Word und Excel.</span><span class="sxs-lookup"><span data-stu-id="62875-117">Teams follows its own update process as outlined above, and not the update process for the other Offices apps, such as Word and Excel.</span></span> <span data-ttu-id="62875-118">Weitere Informationen finden Sie unter [Übersicht über die Update Kanäle für Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus) .</span><span class="sxs-lookup"><span data-stu-id="62875-118">To learn more, read [Overview of update channels for Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus)</span></span>

## <a name="what-about-updates-to-teams-on-vdi"></a><span data-ttu-id="62875-119">Was ist mit Updates für Teams auf VDI?</span><span class="sxs-lookup"><span data-stu-id="62875-119">What about updates to Teams on VDI?</span></span>

<span data-ttu-id="62875-120">Teams-Clients in der Virtual Desktop Infrastructure (VDI) werden nicht automatisch so aktualisiert, wie es Clients von nicht-VDI-Teams sind.</span><span class="sxs-lookup"><span data-stu-id="62875-120">Teams clients on Virtual Desktop Infrastructure (VDI) aren't automatically updated the way that non-VDI Teams clients are.</span></span> <span data-ttu-id="62875-121">Sie müssen das VM-Abbild aktualisieren, indem Sie eine neue MSI-Datei installieren, wie in den Anleitungen zum [Installieren von Teams auf VDI](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="62875-121">You have to update the VM image by installing a new MSI as described in the instructions to [Install Teams on VDI](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi).</span></span> <span data-ttu-id="62875-122">Sie müssen die aktuelle Version deinstallieren, um Sie auf eine neuere Version zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="62875-122">You must uninstall the current version to update to a newer version.</span></span>

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a><span data-ttu-id="62875-123">Können Administratoren Updates anstelle der automatischen Aktualisierung von Teams bereitstellen?</span><span class="sxs-lookup"><span data-stu-id="62875-123">Can admins deploy updates instead of Teams auto-updating?</span></span>

<span data-ttu-id="62875-124">Teams bietet Administratoren keine Möglichkeit zum Bereitstellen von Updates über einen beliebigen Übermittlungsmechanismus.</span><span class="sxs-lookup"><span data-stu-id="62875-124">Teams does not give admins the ability to deploy updates through any delivery mechanism.</span></span>
