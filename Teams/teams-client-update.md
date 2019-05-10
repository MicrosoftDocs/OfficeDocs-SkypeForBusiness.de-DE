---
title: Aktualisierungsvorgang Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 05/08/2019
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: annaray
search.appverid: MET150
description: Hier erfahren Sie, wie der Teams Desktopclient aktualisiert wird.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 04b7d1e66905e7859139605b90b3093a48e8afbd
ms.sourcegitcommit: b072148ea13f4d4f6035204a48bedd287fb90ebd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2019
ms.locfileid: "33829096"
---
# <a name="teams-update-process"></a><span data-ttu-id="04866-103">Aktualisierungsvorgang Teams</span><span class="sxs-lookup"><span data-stu-id="04866-103">Teams update process</span></span>

<span data-ttu-id="04866-104">Die Teams Web App wird wöchentlich aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="04866-104">The Teams Web App is updated weekly.</span></span>

<span data-ttu-id="04866-105">Teams Desktopclient Updates sind zwei Wochen nach strengen internen Tests und Validierung über unsere Technologie Annahme Program (TAP) zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="04866-105">Teams desktop client updates are released every two weeks after rigorous internal testing and validation through our Technology Adoption Program (TAP).</span></span> <span data-ttu-id="04866-106">Dies erfolgt in der Regel an einem Dienstag.</span><span class="sxs-lookup"><span data-stu-id="04866-106">This usually takes place on a Tuesday.</span></span> <span data-ttu-id="04866-107">Wenn ein wichtiges Update erforderlich ist, werden Teams dieser Zeitplan zu umgehen und das Update freigeben, sobald sie verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="04866-107">If a critical update is required, Teams will bypass this schedule and release the update as soon as it’s available.</span></span>

<span data-ttu-id="04866-108">Der Desktopclient aktualisiert sich automatisch aus.</span><span class="sxs-lookup"><span data-stu-id="04866-108">The desktop client updates itself automatically.</span></span> <span data-ttu-id="04866-109">Teams überprüft, ob alle paar Stunden im Hintergrund aktualisiert, heruntergeladen und dann wartet darauf, dass der Computer im Leerlauf sein, bevor das Update automatisch installiert.</span><span class="sxs-lookup"><span data-stu-id="04866-109">Teams checks for updates every few hours behind the scenes, downloads it, and then waits for the computer to be idle before silently installing the update.</span></span>

<span data-ttu-id="04866-110">Benutzer können auch manuell Updates herunterladen, indem Sie die **nach Updates suchen** im **Profil** Dropdown-Menü oben rechts von der app.</span><span class="sxs-lookup"><span data-stu-id="04866-110">Users can also manually download updates by clicking **Check for updates** on the **Profile** drop-down menu on the top right of the app.</span></span> <span data-ttu-id="04866-111">Wenn ein Update verfügbar ist, wird es heruntergeladen und im Hintergrund installiert, wenn der Computer inaktiv ist.</span><span class="sxs-lookup"><span data-stu-id="04866-111">If an update is available, it will be downloaded and silently installed when the computer is idle.</span></span>

<span data-ttu-id="04866-112">Benutzer müssen für Updates heruntergeladen werden angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="04866-112">Users need to be signed in for updates to be downloaded.</span></span>

## <a name="what-about-updates-to-office-365-proplus"></a><span data-ttu-id="04866-113">Was geschieht mit Updates für Office 365 ProPlus?</span><span class="sxs-lookup"><span data-stu-id="04866-113">What about updates to Office 365 ProPlus?</span></span>

<span data-ttu-id="04866-114">Teams wird standardmäßig mit neuen Installationen von Office 365 ProPlus installiert, wie beschrieben in [Microsoft-Teams mit Office 365 ProPlus bereitstellen](https://docs.microsoft.com/DeployOffice/teams-install).</span><span class="sxs-lookup"><span data-stu-id="04866-114">Teams is installed by default with new installations of Office 365 ProPlus as described in [Deploy Microsoft Teams with Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/teams-install).</span></span> 

<span data-ttu-id="04866-115">Teams folgt eine eigene Aktualisierungsprozess wie oben beschrieben, und nicht der Aktualisierungsprozess für die anderen Büros-apps, wie Word und Excel.</span><span class="sxs-lookup"><span data-stu-id="04866-115">Teams follows its own update process as outlined above, and not the update process for the other Offices apps, such as Word and Excel.</span></span>

## <a name="what-about-updates-to-teams-on-vdi"></a><span data-ttu-id="04866-116">Was geschieht mit Updates Teams VDI?</span><span class="sxs-lookup"><span data-stu-id="04866-116">What about updates to Teams on VDI?</span></span>

<span data-ttu-id="04866-117">Teams Clients auf Virtual Desktop Infrastructure (VDI) werden nicht die Möglichkeit, die nicht - VDI-Teams Clients sind, automatisch aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="04866-117">Teams clients on Virtual Desktop Infrastructure (VDI) aren't automatically updated the way that non-VDI Teams clients are.</span></span> <span data-ttu-id="04866-118">Sie müssen das Bild VM aktualisieren, indem Sie eine neue MSI-Datei installieren, gemäß den Anweisungen zum [Installieren von Teams auf VDI](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi).</span><span class="sxs-lookup"><span data-stu-id="04866-118">You have to update the VM image by installing a new MSI as described in the instructions to [Install Teams on VDI](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi).</span></span> <span data-ttu-id="04866-119">Sie müssen die aktuelle Version auf eine neuere Version aktualisieren deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="04866-119">You must uninstall the current version to update to a newer version.</span></span>

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a><span data-ttu-id="04866-120">Können Administratoren Bereitstellen von Updates anstelle von Teams Automatisches Aktualisieren?</span><span class="sxs-lookup"><span data-stu-id="04866-120">Can admins deploy updates instead of Teams auto-updating?</span></span>

<span data-ttu-id="04866-121">Teams wird kein ermöglicht Administratoren die Möglichkeit zum Bereitstellen von Updates durch jeder Mechanismus.</span><span class="sxs-lookup"><span data-stu-id="04866-121">Teams does not give admins the ability to deploy updates through any delivery mechanism.</span></span>
