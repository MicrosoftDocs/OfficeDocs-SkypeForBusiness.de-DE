---
title: Bekannte Probleme von Anrufplänen
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: baa3645a-0518-472e-942e-971c63ba4ca0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Calling Plans
description: Informieren Sie sich über bekannte Probleme mit dem Anrufplan für PSTN-Anrufe und was Sie dagegen tun können.
ms.openlocfilehash: 3a97057f61c154ded83b85becbfcf53dc2b4bc78
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220735"
---
# <a name="calling-plans-known-issues"></a><span data-ttu-id="4a1b5-103">Bekannte Probleme von Anrufplänen</span><span class="sxs-lookup"><span data-stu-id="4a1b5-103">Calling Plans known issues</span></span>

<span data-ttu-id="4a1b5-104">Anrufpläne sind ein neues Feature, das in Skype for Business Online zu finden ist.</span><span class="sxs-lookup"><span data-stu-id="4a1b5-104">Calling Plans are a new feature found in Skype for Business Online.</span></span> <span data-ttu-id="4a1b5-105">Im folgenden finden Sie aktuelle Probleme, die nachverfolgt und aktiv untersucht werden.</span><span class="sxs-lookup"><span data-stu-id="4a1b5-105">The following are current issues that are being tracked and actively investigated.</span></span> <span data-ttu-id="4a1b5-106">Sie werden möglicherweise aufgelöst, wenn das Feature in zukünftigen Builds aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="4a1b5-106">They will be potentially resolved when the feature is updated in future builds.</span></span>
  
## <a name="calling-plans-known-issues"></a><span data-ttu-id="4a1b5-107">Bekannte Probleme von Anrufplänen</span><span class="sxs-lookup"><span data-stu-id="4a1b5-107">Calling Plans known issues</span></span>

|<span data-ttu-id="4a1b5-108">**Bekanntes Problem**</span><span class="sxs-lookup"><span data-stu-id="4a1b5-108">**Known issue**</span></span>|<span data-ttu-id="4a1b5-109">**Anmerkungen**</span><span class="sxs-lookup"><span data-stu-id="4a1b5-109">**Comments**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4a1b5-110">Durch den Übergang von technischen Preview-Lizenzen zu Produktionslizenzen für Anrufpläne wird die Lizenz nicht automatisch aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="4a1b5-110">Transitioning from Tech Preview licenses to production licenses for Calling Plans don't automatically update the license.</span></span>  <br/> |<span data-ttu-id="4a1b5-111">Erwerben Sie zunächst Ihre neuen Lizenzen, damit diese für die Zuweisung zu Ihren Nutzern bereitstehen.</span><span class="sxs-lookup"><span data-stu-id="4a1b5-111">Purchase your new licenses first so they are ready to be assigned to your users.</span></span> <span data-ttu-id="4a1b5-112">Entfernen Sie die Promo-Lizenz (Tech Preview) von einem Benutzer, und weisen Sie dem Benutzer **sofort** den neuen Tarif für **Inlandsanrufe** und/oder Lizenzen für **Inlands-und Auslandsgespräche** zu.</span><span class="sxs-lookup"><span data-stu-id="4a1b5-112">Remove the promo (Tech Preview) license from a user, and then **IMMEDIATELY** assign the new **Domestic Calling Plan** and/or **Domestic and International Calling Plan** licenses to the user.</span></span> <br/> <span data-ttu-id="4a1b5-113">Falls Sie Lizenzen für mehrere Benutzer entfernen und hinzufügen, ist es äußerst wichtig, dass Sie zunächst mithilfe von Windows PowerShell die Lizenzen aller Benutzer entfernen und dann **UNMITTELBAR** danach ebenfalls mit Windows PowerShell die Lizenzen für alle Benutzer zuweisen.</span><span class="sxs-lookup"><span data-stu-id="4a1b5-113">If you are removing and adding licenses for multiple users, it is extremely important that you remove the licenses from all of the users using Windows PowerShell and then **IMMEDIATELY** assign the licenses for all of the users also using Windows PowerShell.</span></span> <span data-ttu-id="4a1b5-114">Auf diese Weise wird sichergestellt, dass bei der Behandlung großer Mengen von Benutzerlizenz Zuweisungen keine Unterbrechungen beim Service auftreten.</span><span class="sxs-lookup"><span data-stu-id="4a1b5-114">Doing this will ensure that there is no disruption in service when handling large volumes of user license assignments.</span></span> <span data-ttu-id="4a1b5-115">Beispiele für PowerShell-Skripts finden Sie unter [Zuweisen von Skype for Business-und Microsoft Teams-Lizenzen](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="4a1b5-115">For sample PowerShell scripts, see [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>  <br/> <span data-ttu-id="4a1b5-116">**Hinweis:** Wenn Sie lokale PSTN-Konnektivität für Hybrid Benutzer verwenden, müssen Sie *nur* eine **Telefon System** Lizenz zuweisen.</span><span class="sxs-lookup"><span data-stu-id="4a1b5-116">**Note:** If you are using on-premises PSTN connectivity for hybrid users, you *only* need to assign a **Phone System** license.</span></span> <span data-ttu-id="4a1b5-117">Sie sollten auch **keinen** sprach Tarif zuweisen.</span><span class="sxs-lookup"><span data-stu-id="4a1b5-117">You should **NOT** also assign a voice Calling Plan.</span></span> <span data-ttu-id="4a1b5-118">Wenn Sie jedoch Anrufpläne in Microsoft 365 oder Office 365 für Benutzer in Microsoft 365 oder Office 365 aktivieren, müssen Sie diesen Benutzern weiterhin einen **Plan für Inlandsanrufe** oder eine Lizenz für den **nationalen und internationalen** Tarif zuweisen.</span><span class="sxs-lookup"><span data-stu-id="4a1b5-118">However, if you are enabling Calling Plans in Microsoft 365 or Office 365 for users that are in Microsoft 365 or Office 365, you need to still assign a **Domestic Calling Plan** or a **Domestic and International Calling Plan** license for those users.</span></span> <span data-ttu-id="4a1b5-119">Siehe [Zuweisen von Skype for Business- und Microsoft Teams-Lizenzen](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="4a1b5-119">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

> [!NOTE]
> <span data-ttu-id="4a1b5-120">Wenn Sie weitere Telefonnummern erhalten möchten, wenden Sie sich bitte [an den Support für Business-Produkte – Administratorhilfe](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) .         |</span><span class="sxs-lookup"><span data-stu-id="4a1b5-120">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="4a1b5-121">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="4a1b5-121">Related topics</span></span>
[<span data-ttu-id="4a1b5-122">Übertragen von Telefonnummern – häufig gestellte Fragen</span><span class="sxs-lookup"><span data-stu-id="4a1b5-122">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="4a1b5-123">Verschiedene Arten von Telefonnummern, die für Anrufpläne verwendet werden</span><span class="sxs-lookup"><span data-stu-id="4a1b5-123">Different kinds of phone numbers used for Calling Plans</span></span>](/MicrosoftTeams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="4a1b5-124">Verwalten von Telefonnummern für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="4a1b5-124">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="4a1b5-125">Nutzungsbedingungen für Notrufe</span><span class="sxs-lookup"><span data-stu-id="4a1b5-125">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="4a1b5-126">[Skype for Business Online: Aufkleber mit Haftungsausschluss für Notrufe](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="4a1b5-126">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 
