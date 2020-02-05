---
title: Aktualisieren des Edge-Zertifikats
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Dieser Anhang enthält detaillierte Schritte zum Aktualisieren des Edge-Zertifikats im Rahmen der Cloud-Konsolidierung für Teams und Skype for Business.
ms.openlocfilehash: c4339eec5fa303429fdf8f42a7273c8f20f94e5b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762853"
---
# <a name="update-the-edge-certificate"></a><span data-ttu-id="4233d-103">Aktualisieren des Edge-Zertifikats</span><span class="sxs-lookup"><span data-stu-id="4233d-103">Update the edge certificate</span></span>

<span data-ttu-id="4233d-104">Das Aktualisieren des Edge-Zertifikats ist der wichtigste Schritt, um sicherzustellen, dass eine on-Prem-Umgebung mit SipDomain1 einer Cloud-Umgebung mit SipDomain2 beitreten kann und dass das ordnungsgemäße Routing in einer freigegebenen Adressraum Umgebung über die beiden SIP-Domänen hinweg gewährleistet ist.</span><span class="sxs-lookup"><span data-stu-id="4233d-104">Updating the edge certificate is the key step to ensuring that an on-prem environment with SipDomain1 can join a cloud environment with SipDomain2 and ensure proper routing in a shared address space environment across the two SIP domains.</span></span> <span data-ttu-id="4233d-105">Weitere Informationen finden Sie unter Schritt 14 bei der [Cloud-Konsolidierung für Teams und Skype for Business](cloud-consolidation.md) für den Kontext, in dem Sie diesen Schritt ausführen können.</span><span class="sxs-lookup"><span data-stu-id="4233d-105">See step 14 in [Cloud consolidation for Teams and Skype for Business](cloud-consolidation.md) for context in which you might perform this step.</span></span> <span data-ttu-id="4233d-106">In unseren Beispielen ist SipDomain1 AcquiredCompany. <span>com und SipDomain2 ist OriginalCompany. <span>com.</span><span class="sxs-lookup"><span data-stu-id="4233d-106">In our examples, SipDomain1 is AcquiredCompany.<span>com and SipDomain2 is OriginalCompany.<span>com.</span></span>

<span data-ttu-id="4233d-107">Der Alternative Antragstellername (San) des Zertifikats auf allen Edge-Servern in der lokalen Umgebung muss so aktualisiert werden, dass er alle SIP-Domänen enthält, die im reinen Online Mandanten vorhanden sind<span> (ohne onmicrosoft. com-Domänen) im Format "SIP. \<Domänen> ".</span><span class="sxs-lookup"><span data-stu-id="4233d-107">The subject alternate name (SAN) of the certificate on all edge servers in the on-premises environment must be updated to include all SIP domains that exist in the pure online tenant (excluding any onmicrosoft.<span>com domains), in the form “sip.\<domain>”.</span></span>  <span data-ttu-id="4233d-108">In unserem Beispiel ist dies SIP. OriginalCompany. <span>com.</span><span class="sxs-lookup"><span data-stu-id="4233d-108">In our example, this is sip.OriginalCompany.<span>com.</span></span> <span data-ttu-id="4233d-109">Dieser Schritt ist wichtig, bevor Sie alle Benutzer in die Cloud migrieren.</span><span class="sxs-lookup"><span data-stu-id="4233d-109">This step is critical to do before migrating any users to the cloud.</span></span>

<span data-ttu-id="4233d-110">**Schritte**</span><span class="sxs-lookup"><span data-stu-id="4233d-110">**Steps:**</span></span>

1.  <span data-ttu-id="4233d-111">Beziehen Sie ein neues externes Edge-Zertifikat für den Edge mit allen vorhandenen Einträgen sowie zusätzliche Einträge im San für alle SIP-Domänen in der Cloud-Umgebung (außer \*. onmicrosoft.com Domänen) im Format "SIP. <DomainName>".</span><span class="sxs-lookup"><span data-stu-id="4233d-111">Obtain a new External Edge certificate for the edge that has all existing entries plus additional entries in the SAN for all SIP domains in the cloud environment (excluding \*.onmicrosoft.com domains) in the form “sip.<DomainName>”.</span></span>
2.  <span data-ttu-id="4233d-112">Installieren Sie das Zertifikat lokal auf jedem Edgeserver, und weisen Sie es dem Skype-Edgedienst auf jedem Edge-Dienst zu.</span><span class="sxs-lookup"><span data-stu-id="4233d-112">Install the certificate locally on each edge server and assign it to the Skype Edge service on each of the edge service.</span></span>  <span data-ttu-id="4233d-113">Ausführliche Anweisungen finden Sie im Abschnitt "externe Edge-Schnittstellen Zertifikate" unter [Deploy Edge Service in Skype for Business Server 2015](https://technet.microsoft.com/library/dn951368.aspx).</span><span class="sxs-lookup"><span data-stu-id="4233d-113">For detailed steps, see the section “External Edge interface certificates” in [Deploy Edge Service in Skype for Business Server 2015](https://technet.microsoft.com/library/dn951368.aspx).</span></span>
3.  <span data-ttu-id="4233d-114">Starten Sie den Edgedienst auf jedem Edgeserver neu.</span><span class="sxs-lookup"><span data-stu-id="4233d-114">Restart the Edge service on each of the edge servers.</span></span> <span data-ttu-id="4233d-115">Sie können dies für ein einzelnes Feld mit den folgenden PowerShell-Befehlen ausführen:</span><span class="sxs-lookup"><span data-stu-id="4233d-115">You can do this for a single box with the following PowerShell commands:</span></span>

    ```PowerShell
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a><span data-ttu-id="4233d-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4233d-116">See also</span></span>

[<span data-ttu-id="4233d-117">Cloud-Konsolidierung für Teams und Skype for Business</span><span class="sxs-lookup"><span data-stu-id="4233d-117">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)
