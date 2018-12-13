---
title: Aktualisieren des Edge-Zertifikats
ms.author: crowe
author: crowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.service:
- skype-for-business-online
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Dieser Anhang enthält detaillierte Schritte zum Aktualisieren der edgezertifikat im Rahmen der Cloud Konsolidierung für Teams und Skype für Unternehmen.
ms.openlocfilehash: bd7707add0962a827373f1d07de9f8f8f9d3ec7c
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/13/2018
ms.locfileid: "27247660"
---
# <a name="update-the-edge-certificate"></a><span data-ttu-id="9338e-103">Aktualisieren des Edge-Zertifikats</span><span class="sxs-lookup"><span data-stu-id="9338e-103">Update the edge certificate</span></span>

<span data-ttu-id="9338e-104">Aktualisieren das edgezertifikat ist der wichtigste Schritt zu gewährleisten, dass ordnungsgemäßes routing in einer Umgebung mit gemeinsam genutzten Adresse Speicherplatz auf die zwei SIP-Domänen sicher, dass eine auf Prem-Umgebung mit SipDomain1 eine Cloud-Umgebung mit SipDomain2 teilnehmen kann.</span><span class="sxs-lookup"><span data-stu-id="9338e-104">Updating the edge certificate is the key step to ensuring that an on-prem environment with SipDomain1 can join a cloud environment with SipDomain2 and ensure proper routing in a shared address space environment across the two SIP domains.</span></span> <span data-ttu-id="9338e-105">Finden Sie in Schritt 14 in der [Cloud Konsolidierung für Teams und Skype für Unternehmen](cloud-consolidation.md) Kontext, in dem Sie diesen Schritt ausführen können.</span><span class="sxs-lookup"><span data-stu-id="9338e-105">See step 14 in [Cloud consolidation for Teams and Skype for Business](cloud-consolidation.md) for context in which you might perform this step.</span></span> <span data-ttu-id="9338e-106">In unseren Beispielen ist SipDomain1 AcquiredCompany. <span>com und SipDomain2 OriginalCompany ist. <span>com.</span><span class="sxs-lookup"><span data-stu-id="9338e-106">In our examples, SipDomain1 is AcquiredCompany.<span>com and SipDomain2 is OriginalCompany.<span>com.</span></span>

<span data-ttu-id="9338e-107">Der alternative Antragstellername (SAN) des Zertifikats auf allen Edgeservern in der lokalen Umgebung muss aktualisiert werden, in den reinen online Mandanten einbezogen werden alle SIP-Domänen, die vorhanden sind (ausgenommen alle Onmicrosoft.<span> com-Domänen) im Format "Sip. \<Domäne > ".</span><span class="sxs-lookup"><span data-stu-id="9338e-107">The subject alternate name (SAN) of the certificate on all edge servers in the on-premises environment must be updated to include all SIP domains that exist in the pure online tenant (excluding any onmicrosoft.<span>com domains), in the form “sip.\<domain>”.</span></span>  <span data-ttu-id="9338e-108">In unserem Beispiel ist dies Sip. OriginalCompany. <span>com.</span><span class="sxs-lookup"><span data-stu-id="9338e-108">In our example, this is sip.OriginalCompany.<span>com.</span></span> <span data-ttu-id="9338e-109">Dieser Schritt ist wichtig, zu tun, bevor Sie alle Benutzer in die Cloud migrieren.</span><span class="sxs-lookup"><span data-stu-id="9338e-109">This step is critical to do before migrating any users to the cloud.</span></span>

<span data-ttu-id="9338e-110">**Schritte:**</span><span class="sxs-lookup"><span data-stu-id="9338e-110">**Steps:**</span></span>

1.  <span data-ttu-id="9338e-111">Abrufen ein neues externen Edge-Zertifikats für den Rand, die alle vorhandenen Einträge sowie zusätzliche Einträge im SAN für alle SIP-Domänen in der Cloudumgebung hat (ausgenommen \*. onmicrosoft.com Domänen) im Format "Sip. <DomainName>".</span><span class="sxs-lookup"><span data-stu-id="9338e-111">Obtain a new External Edge certificate for the edge that has all existing entries plus additional entries in the SAN for all SIP domains in the cloud environment (excluding \*.onmicrosoft.com domains) in the form “sip.<DomainName>”.</span></span>
2.  <span data-ttu-id="9338e-112">Installieren Sie das Zertifikat lokal auf jedem Edgeserver, und weisen Sie es des Skype-Edge-Diensts auf jedem der Edge-Dienst.</span><span class="sxs-lookup"><span data-stu-id="9338e-112">Install the certificate locally on each edge server and assign it to the Skype Edge service on each of the edge service.</span></span>  <span data-ttu-id="9338e-113">Ausführliche Schritte finden Sie im Abschnitt "Externer Edge-Schnittstelle Zertifikate" in [Skype für Business Server 2015 Edgedienst bereitstellen](https://technet.microsoft.com/en-us/library/dn951368.aspx).</span><span class="sxs-lookup"><span data-stu-id="9338e-113">For detailed steps, see the section “External Edge interface certificates” in [Deploy Edge Service in Skype for Business Server 2015](https://technet.microsoft.com/en-us/library/dn951368.aspx).</span></span>
3.  <span data-ttu-id="9338e-114">Starten Sie den Edge-Dienst auf jedem Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="9338e-114">Restart the Edge service on each of the edge servers.</span></span> <span data-ttu-id="9338e-115">Hierzu können Sie für ein einzelnes Feld mit den folgenden PowerShell-Befehlen:</span><span class="sxs-lookup"><span data-stu-id="9338e-115">You can do this for a single box with the following PowerShell commands:</span></span>

    ```
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a><span data-ttu-id="9338e-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9338e-116">See also</span></span>

[<span data-ttu-id="9338e-117">Cloud-Konsolidierung für Teams und Skype für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="9338e-117">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)