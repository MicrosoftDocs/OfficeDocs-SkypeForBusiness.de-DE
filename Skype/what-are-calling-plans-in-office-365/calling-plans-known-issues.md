---
title: "Aufrufen von Plänen bekannte Probleme"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: baa3645a-0518-472e-942e-971c63ba4ca0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Calling Plans
description: "Hier erfahren Sie, bekannte Probleme bei der aufrufenden Plan für Office 365 (aufrufen, PSTN) und was Sie über diese möglich ist. "
ms.openlocfilehash: 42b282bce7ba65dc4e053020970a02e71c98b5bd
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2017
---
# <a name="calling-plans-known-issues"></a><span data-ttu-id="37a2c-103">Aufrufen von Plänen bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="37a2c-103">Calling Plans known issues</span></span>

<span data-ttu-id="37a2c-104">Aufrufen von Plänen in Office 365 sind ein neues Feature in Skype für Business Online gefunden.</span><span class="sxs-lookup"><span data-stu-id="37a2c-104">Calling Plans in Office 365 are a new feature found in Skype for Business Online.</span></span> <span data-ttu-id="37a2c-105">Im folgenden sind aktuelle Probleme, die werden nachverfolgt und aktiv untersucht.</span><span class="sxs-lookup"><span data-stu-id="37a2c-105">The following are current issues that are being tracked and actively investigated.</span></span> <span data-ttu-id="37a2c-106">Sie werden potenziell aufgelöst werden, wenn das Feature für Business Online in zukünftigen Builds in Office 365 und Skype aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="37a2c-106">They will be potentially resolved when the feature is updated in future builds in Office 365 and Skype for Business Online.</span></span>
  
## <a name="calling-plans-known-issues"></a><span data-ttu-id="37a2c-107">Aufrufen von Plänen bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="37a2c-107">Calling Plans known issues</span></span>

|<span data-ttu-id="37a2c-108">**Bekanntes Problem**</span><span class="sxs-lookup"><span data-stu-id="37a2c-108">**Known issue**</span></span>|<span data-ttu-id="37a2c-109">**Kommentare**</span><span class="sxs-lookup"><span data-stu-id="37a2c-109">**Comments**</span></span>|
|:-----|:-----|
|<span data-ttu-id="37a2c-110">Übergang von Tech Preview aktualisieren nicht Softwarelizenzen zur Produktion Lizenzen für aufrufen plant automatisch die Lizenz.</span><span class="sxs-lookup"><span data-stu-id="37a2c-110">Transitioning from Tech Preview licenses to production licenses for Calling Plans don't automatically update the license.</span></span>  <br/> |<span data-ttu-id="37a2c-111">Zunächst erwerben Sie Ihre neuen Lizenzen, damit sie Ihren Benutzern zugewiesen werden können.</span><span class="sxs-lookup"><span data-stu-id="37a2c-111">Purchase your new licenses first so they are ready to be assigned to your users.</span></span> <span data-ttu-id="37a2c-112">Entfernen der Lizenzvertrags Promotion (Tech Preview) von einem Benutzer, und weisen Sie **sofort** die neuen **Nationalen aufrufen planen** und/oder **in- und International planen Aufrufen von** Lizenzen für den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="37a2c-112">Remove the promo (Tech Preview) license from a user, and then **IMMEDIATELY** assign the new **Domestic Calling Plan** and/or **Domestic and International Calling Plan** licenses to the user.</span></span> <br/> <span data-ttu-id="37a2c-113">Wenn Sie entfernen und Hinzufügen von Lizenzen für mehrere Benutzer, ist es sehr wichtig, dass Sie die Lizenzen aus alle Benutzer von Windows PowerShell entfernen und dann **sofort** zuweisen die Lizenzen für alle Benutzer auch mithilfe von Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="37a2c-113">If you are removing and adding licenses for multiple users, it is extremely important that you remove the licenses from all of the users using Windows PowerShell and then **IMMEDIATELY** assign the licenses for all of the users also using Windows PowerShell.</span></span> <span data-ttu-id="37a2c-114">Dadurch wird sichergestellt, dass bei der Behandlung von großer Mengen an Benutzer Lizenz Zuordnungen wird nicht unterbrochen im Dienst.</span><span class="sxs-lookup"><span data-stu-id="37a2c-114">Doing this will ensure that there is no disruption in service when handling large volumes of user license assignments.</span></span> <span data-ttu-id="37a2c-115">PowerShell-Skriptbeispiele finden Sie unter [Skype für Geschäfts- und Microsoft-Teams, Lizenzen zuweisen](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="37a2c-115">For sample PowerShell scripts, see [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>  <br/> <span data-ttu-id="37a2c-116">**Hinweis:** Bei Verwendung von lokalen PSTN-Anbindung für hybridbenutzer müssen Sie *nur* eine **Telefonsystem** Lizenz zuweisen.</span><span class="sxs-lookup"><span data-stu-id="37a2c-116">**Note:** If you are using on-premises PSTN connectivity for hybrid users, you  *only*  need to assign a **Phone System** license.</span></span> <span data-ttu-id="37a2c-117">Sie sollten **nicht** auch Zuweisen einer VoIP planen aufrufen.</span><span class="sxs-lookup"><span data-stu-id="37a2c-117">You should **NOT** also assign a voice Calling Plan.</span></span> <span data-ttu-id="37a2c-118">Wenn Sie aufrufen in Office 365-Pläne für Benutzer, die in Office 365 sind aktivieren, müssen Sie jedoch weiterhin eine **Nationalen aufrufen planen** oder keine Lizenz **in- und International aufrufen planen** , für die Benutzer zuweisen.</span><span class="sxs-lookup"><span data-stu-id="37a2c-118">However, if you are enabling Calling Plans in Office 365 for users that are in Office 365, you need to still assign a **Domestic Calling Plan** or a **Domestic and International Calling Plan** license for those users.</span></span> <span data-ttu-id="37a2c-119">Finden Sie unter [Skype für Geschäfts- und Microsoft-Teams, Lizenzen zuweisen](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="37a2c-119">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

> [!NOTE]
> <span data-ttu-id="37a2c-120">Wenn Sie weitere Telefonnummern als dieser erhalten möchten müssen, wenden Sie [Unterstützung für Business-Produkte – Admin Hilfe](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |</span><span class="sxs-lookup"><span data-stu-id="37a2c-120">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="37a2c-121">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="37a2c-121">Related topics</span></span>
[<span data-ttu-id="37a2c-122">Transferring phone numbers common questions</span><span class="sxs-lookup"><span data-stu-id="37a2c-122">Transferring phone numbers common questions</span></span>](transferring-phone-numbers-common-questions.md)

[<span data-ttu-id="37a2c-123">Verschiedene Arten von Telefonnummern für den Aufruf von plant verwendet</span><span class="sxs-lookup"><span data-stu-id="37a2c-123">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="37a2c-124">Telefonnummern für Ihre Organisation verwalten</span><span class="sxs-lookup"><span data-stu-id="37a2c-124">Manage phone numbers for your organization</span></span>](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[<span data-ttu-id="37a2c-125">Nutzungsbedingungen für Notrufe</span><span class="sxs-lookup"><span data-stu-id="37a2c-125">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)

[<span data-ttu-id="37a2c-126">Skype for Business Online: Aufkleber mit Haftungsausschluss für Notrufe</span><span class="sxs-lookup"><span data-stu-id="37a2c-126">Skype for Business Online: Emergency Calling disclaimer label</span></span>](https://go.microsoft.com/fwlink/?LinkID=692099)
