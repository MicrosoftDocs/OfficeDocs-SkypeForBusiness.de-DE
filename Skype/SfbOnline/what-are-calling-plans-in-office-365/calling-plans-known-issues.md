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
f1keywords: None
ms.custom:
- Calling Plans
description: 'Learn known issues with the calling plan for Office 365 (PSTN Calling) and what you can do about them. '
ms.openlocfilehash: 9a6f97a93aa6c7b4e847ba1cb3280a21c473db0c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299524"
---
# <a name="calling-plans-known-issues"></a><span data-ttu-id="f821c-103">Bekannte Probleme von Anrufplänen</span><span class="sxs-lookup"><span data-stu-id="f821c-103">Calling Plans known issues</span></span>

<span data-ttu-id="f821c-104">Anrufpläne in Office 365 sind ein neues Feature, das in Skype for Business Online zu finden ist.</span><span class="sxs-lookup"><span data-stu-id="f821c-104">Calling Plans in Office 365 are a new feature found in Skype for Business Online.</span></span> <span data-ttu-id="f821c-105">Im folgenden finden Sie aktuelle Probleme, die nachverfolgt und aktiv untersucht werden.</span><span class="sxs-lookup"><span data-stu-id="f821c-105">The following are current issues that are being tracked and actively investigated.</span></span> <span data-ttu-id="f821c-106">Sie werden möglicherweise aufgelöst, wenn das Feature in zukünftigen Builds in Office 365 und Skype for Business Online aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="f821c-106">They will be potentially resolved when the feature is updated in future builds in Office 365 and Skype for Business Online.</span></span>
  
## <a name="calling-plans-known-issues"></a><span data-ttu-id="f821c-107">Bekannte Probleme von Anrufplänen</span><span class="sxs-lookup"><span data-stu-id="f821c-107">Calling Plans known issues</span></span>

|<span data-ttu-id="f821c-108">**Bekanntes Problem**</span><span class="sxs-lookup"><span data-stu-id="f821c-108">**Known issue**</span></span>|<span data-ttu-id="f821c-109">**Anmerkungen**</span><span class="sxs-lookup"><span data-stu-id="f821c-109">**Comments**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f821c-110">Durch den Übergang von technischen Preview-Lizenzen zu Produktionslizenzen für Anrufpläne wird die Lizenz nicht automatisch aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="f821c-110">Transitioning from Tech Preview licenses to production licenses for Calling Plans don't automatically update the license.</span></span>  <br/> |<span data-ttu-id="f821c-111">Erwerben Sie zunächst Ihre neuen Lizenzen, damit diese für die Zuweisung zu Ihren Nutzern bereitstehen.</span><span class="sxs-lookup"><span data-stu-id="f821c-111">Purchase your new licenses first so they are ready to be assigned to your users.</span></span> <span data-ttu-id="f821c-112">Entfernen Sie die Promo-Lizenz (Tech Preview) von einem Benutzer, und weisen Sie dem Benutzer **sofort** den neuen Tarif für **Inlandsanrufe** und/oder Lizenzen für **Inlands-und Auslandsgespräche** zu.</span><span class="sxs-lookup"><span data-stu-id="f821c-112">Remove the promo (Tech Preview) license from a user, and then **IMMEDIATELY** assign the new **Domestic Calling Plan** and/or **Domestic and International Calling Plan** licenses to the user.</span></span> <br/> <span data-ttu-id="f821c-113">Falls Sie Lizenzen für mehrere Benutzer entfernen und hinzufügen, ist es äußerst wichtig, dass Sie zunächst mithilfe von Windows PowerShell die Lizenzen aller Benutzer entfernen und dann **UNMITTELBAR** danach ebenfalls mit Windows PowerShell die Lizenzen für alle Benutzer zuweisen.</span><span class="sxs-lookup"><span data-stu-id="f821c-113">If you are removing and adding licenses for multiple users, it is extremely important that you remove the licenses from all of the users using Windows PowerShell and then **IMMEDIATELY** assign the licenses for all of the users also using Windows PowerShell.</span></span> <span data-ttu-id="f821c-114">Auf diese Weise wird sichergestellt, dass bei der Behandlung großer Mengen von Benutzerlizenz Zuweisungen keine Unterbrechungen beim Service auftreten.</span><span class="sxs-lookup"><span data-stu-id="f821c-114">Doing this will ensure that there is no disruption in service when handling large volumes of user license assignments.</span></span> <span data-ttu-id="f821c-115">Beispiele für PowerShell-Skripts finden Sie unter [Zuweisen von Skype for Business-und Microsoft Teams-Lizenzen](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="f821c-115">For sample PowerShell scripts, see [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>  <br/> <span data-ttu-id="f821c-116">**Hinweis:** Wenn Sie lokale PSTN-Konnektivität für Hybrid Benutzer verwenden, müssen Sie *nur* eine **Telefon System** Lizenz zuweisen.</span><span class="sxs-lookup"><span data-stu-id="f821c-116">**Note:** If you are using on-premises PSTN connectivity for hybrid users, you  *only*  need to assign a **Phone System** license.</span></span> <span data-ttu-id="f821c-117">Sie sollten auch **keinen** sprach Tarif zuweisen.</span><span class="sxs-lookup"><span data-stu-id="f821c-117">You should **NOT** also assign a voice Calling Plan.</span></span> <span data-ttu-id="f821c-118">Wenn Sie jedoch Anrufpläne in Office 365 für Benutzer in Office 365 aktivieren, müssen Sie diesen Benutzern weiterhin einen **Plan für Inlandsanrufe** oder eine Lizenz für **Inlands-und Auslandsanrufe** zuweisen.</span><span class="sxs-lookup"><span data-stu-id="f821c-118">However, if you are enabling Calling Plans in Office 365 for users that are in Office 365, you need to still assign a **Domestic Calling Plan** or a **Domestic and International Calling Plan** license for those users.</span></span> <span data-ttu-id="f821c-119">Siehe [Zuweisen von Skype for Business- und Microsoft Teams-Lizenzen](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="f821c-119">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

> [!NOTE]
> <span data-ttu-id="f821c-120">Wenn Sie weitere Telefonnummern erhalten möchten, wenden Sie sich bitte [an den Support für Business-Produkte – Administratorhilfe](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) .         |</span><span class="sxs-lookup"><span data-stu-id="f821c-120">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="f821c-121">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="f821c-121">Related topics</span></span>
[<span data-ttu-id="f821c-122">Allgemeine Fragen zum Übertragen von Telefonnummern</span><span class="sxs-lookup"><span data-stu-id="f821c-122">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="f821c-123">Verschiedene Arten von Telefonnummern, die für Anrufpläne verwendet werden</span><span class="sxs-lookup"><span data-stu-id="f821c-123">Different kinds of phone numbers used for Calling Plans</span></span>](/MicrosoftTeams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="f821c-124">Verwalten von Telefonnummern für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="f821c-124">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="f821c-125">Nutzungsbedingungen für Notrufe</span><span class="sxs-lookup"><span data-stu-id="f821c-125">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="f821c-126">[Skype for Business Online: Aufkleber mit Haftungsausschluss für Notrufe](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="f821c-126">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 