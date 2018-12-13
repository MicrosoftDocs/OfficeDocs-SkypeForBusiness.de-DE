---
title: Deaktivieren Sie zum Abschließen der Migration zur Cloud hybrid
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
description: Dieser Anhang enthält ausführliche Schritte zum Deaktivieren von Hybriden als Teil der Cloud Konsolidierung für Teams und Skype für Unternehmen.
ms.openlocfilehash: 03c38a4482d9a0bd6e728138b3d856b552e4754a
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/13/2018
ms.locfileid: "27247668"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a><span data-ttu-id="2da58-103">Deaktivieren Sie zum Abschließen der Migration zur Cloud hybrid</span><span class="sxs-lookup"><span data-stu-id="2da58-103">Disable hybrid to complete migration to the cloud</span></span>

<span data-ttu-id="2da58-104">Nachdem Sie alle Benutzer in die Cloud aus lokalen verschoben haben, können Sie die lokalen Skype für die Business-Bereitstellung außer Betrieb nehmen.</span><span class="sxs-lookup"><span data-stu-id="2da58-104">After you have moved all users from on-premises to the cloud, you can decommission the on-premises Skype for Business deployment.</span></span> <span data-ttu-id="2da58-105">Ein wichtiger Schritt darin, neben dem Entfernen von Hardware, logisch der lokalen Bereitstellung von Office 365 getrennt durch Hybrid deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="2da58-105">Aside from removing any hardware, a critical step is to logically separate that on-premises deployment from Office 365 by disabling hybrid.</span></span> <span data-ttu-id="2da58-106">Deaktivieren von Hybriden umfasst 3 Schritte:</span><span class="sxs-lookup"><span data-stu-id="2da58-106">Disabling hybrid consists of 3 steps:</span></span>

1. <span data-ttu-id="2da58-107">Aktualisieren von DNS-Einträge So zeigen Sie auf Office 365.</span><span class="sxs-lookup"><span data-stu-id="2da58-107">Update DNS records to point to Office 365.</span></span>
2. <span data-ttu-id="2da58-108">Geteilte Domäne in Office 365-Mandanten zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="2da58-108">Disable split domain in the Office 365 tenant.</span></span>
3. <span data-ttu-id="2da58-109">Deaktivieren Sie die Möglichkeit in auf Prem Kommunikation mit Office 365.</span><span class="sxs-lookup"><span data-stu-id="2da58-109">Disable ability in on-prem to communicate with Office 365.</span></span>


<span data-ttu-id="2da58-110">Diese Schritte sollten zusammen als Einheit erfolgen.</span><span class="sxs-lookup"><span data-stu-id="2da58-110">These steps should be done together as a unit.</span></span> <span data-ttu-id="2da58-111">Ausführliche Informationen finden Sie weiter unten.</span><span class="sxs-lookup"><span data-stu-id="2da58-111">Details are provided below.</span></span>

> [!Note] 
> <span data-ttu-id="2da58-112">In seltenen Fällen verursachen ändern DNS aus lokal zu Office 365 für Ihre Organisation verweisen Verbund mit einige andere Organisationen mehr funktionieren erst, dass andere Organisation ihre Verbundkonfiguration aktualisiert werden:</span><span class="sxs-lookup"><span data-stu-id="2da58-112">In rare cases, changing DNS from pointing on premises to Office 365 for your organization may cause federation with some other organizations to stop working until that other organization updates their federation configuration:</span></span><ul><li>
<span data-ttu-id="2da58-113">Alle verbundorganisationen, die das ältere direkte Federation-Objektmodell (auch bekannt als zulässige Partnerserver) verwenden, müssen so aktualisieren Sie ihre zulässiger Domäneneinträge für ihre Organisation, um den FQDN-Proxy zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="2da58-113">Any federated organizations that are using the older Direct Federation model (also known as Allowed Partner Server) will need to update their allowed domain entries for their organization to remove the proxy FQDN.</span></span> <span data-ttu-id="2da58-114">Diese Vorversion Federation-Objektmodell basiert nicht auf DNS-SRV-Einträge, damit eine solche Konfiguration veralten wird nach Ihrer Organisation zur Cloud verschoben.</span><span class="sxs-lookup"><span data-stu-id="2da58-114">This legacy federation model is not based on DNS SRV records, so such a configuration will become out of date once your organization moves to the cloud.</span></span> </li><li><span data-ttu-id="2da58-115">Alle verbundenen Organisation, die nicht über eine aktivierte Hostinganbieter für sipfed.online.lync verfügt. <span>com, müssen Sie ihre Konfiguration zum Aktivieren, die zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="2da58-115">Any federated organization that does not have an enabled hosting provider for sipfed.online.lync.<span>com will need to update their configuration to enable that.</span></span> <span data-ttu-id="2da58-116">Dies ist nur möglich, wenn der Partnerorganisation rein lokal ist und wurde noch nie mit allen Hybrid oder online-Mandanten Verbund.</span><span class="sxs-lookup"><span data-stu-id="2da58-116">This situation is only possible if the federated organization is purely on premises and has never federated with any hybrid or online tenant.</span></span> <span data-ttu-id="2da58-117">In diesem Fall funktioniert einen Verbund mit diesen Organisationen nicht, bis sie ihre Hostinganbieter ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="2da58-117">In such a case, federation with these organizations will not work until they enable their hosting provider.</span></span></li></ul><span data-ttu-id="2da58-118">Wenn Sie annehmen, dass einige der Partner im Verbund mithilfe von direkter Verbund oder online mit einem Verbund haben oder hybridorganisation, es wird empfohlen, dass Sie dies eine Kommunikation dazu veranlassen Sie bei der Vorbereitung für die Durchführung die Migration zur Cloud.</span><span class="sxs-lookup"><span data-stu-id="2da58-118">If you suspect that any of your federated partners may be using Direct Federation or have federated with any online or hybrid organization, we suggest you send them a communication about this as you prepare to complete your migration to the cloud.</span></span>

1.  <span data-ttu-id="2da58-119">*So zeigen Sie auf Office 365 DNS zu aktualisieren.*</span><span class="sxs-lookup"><span data-stu-id="2da58-119">*Update DNS to point to Office 365.*</span></span>
<span data-ttu-id="2da58-120">Die Organisation externe DNS-Server für die lokale Organisation muss aktualisiert werden, sodass Skype für Unternehmensunterlagen zeigen Sie auf Office 365 anstelle der lokalen Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="2da58-120">The organization’s external DNS for the on-premises organization needs to be updated so that Skype for Business records point to Office 365 instead of the on-premises deployment.</span></span> <span data-ttu-id="2da58-121">Insbesondere:</span><span class="sxs-lookup"><span data-stu-id="2da58-121">Specifically:</span></span>

    |<span data-ttu-id="2da58-122">Eintragstyp</span><span class="sxs-lookup"><span data-stu-id="2da58-122">Record type</span></span>|<span data-ttu-id="2da58-123">Name</span><span class="sxs-lookup"><span data-stu-id="2da58-123">Name</span></span>|<span data-ttu-id="2da58-124">TTL</span><span class="sxs-lookup"><span data-stu-id="2da58-124">TTL</span></span>|<span data-ttu-id="2da58-125">Wert</span><span class="sxs-lookup"><span data-stu-id="2da58-125">Value</span></span>|
    |---|---|---|---|
    |<span data-ttu-id="2da58-126">SRV</span><span class="sxs-lookup"><span data-stu-id="2da58-126">SRV</span></span>|<span data-ttu-id="2da58-127">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="2da58-127">_sipfederationtls._tcp</span></span>|<span data-ttu-id="2da58-128">3600</span><span class="sxs-lookup"><span data-stu-id="2da58-128">3600</span></span>|<span data-ttu-id="2da58-129">100 1 5061 sipfed.online.lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="2da58-129">100 1 5061 sipfed.online.lync.<span>com</span></span>|
    |<span data-ttu-id="2da58-130">SRV</span><span class="sxs-lookup"><span data-stu-id="2da58-130">SRV</span></span>|<span data-ttu-id="2da58-131">_sip</span><span class="sxs-lookup"><span data-stu-id="2da58-131">_sip._tls</span></span>|<span data-ttu-id="2da58-132">3600</span><span class="sxs-lookup"><span data-stu-id="2da58-132">3600</span></span>|<span data-ttu-id="2da58-133">100 1 443 sipdir.online.lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="2da58-133">100 1 443 sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="2da58-134">CNAME</span><span class="sxs-lookup"><span data-stu-id="2da58-134">CNAME</span></span>| <span data-ttu-id="2da58-135">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="2da58-135">lyncdiscover</span></span>|   <span data-ttu-id="2da58-136">3600</span><span class="sxs-lookup"><span data-stu-id="2da58-136">3600</span></span>|   <span data-ttu-id="2da58-137">WebDir.Online.Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="2da58-137">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="2da58-138">CNAME</span><span class="sxs-lookup"><span data-stu-id="2da58-138">CNAME</span></span>| <span data-ttu-id="2da58-139">SIP</span><span class="sxs-lookup"><span data-stu-id="2da58-139">sip</span></span>|    <span data-ttu-id="2da58-140">3600</span><span class="sxs-lookup"><span data-stu-id="2da58-140">3600</span></span>|   <span data-ttu-id="2da58-141">sipdir.Online.Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="2da58-141">sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="2da58-142">CNAME</span><span class="sxs-lookup"><span data-stu-id="2da58-142">CNAME</span></span>| <span data-ttu-id="2da58-143">erfüllen</span><span class="sxs-lookup"><span data-stu-id="2da58-143">meet</span></span>|   <span data-ttu-id="2da58-144">3600</span><span class="sxs-lookup"><span data-stu-id="2da58-144">3600</span></span>|   <span data-ttu-id="2da58-145">WebDir.Online.Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="2da58-145">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="2da58-146">CNAME</span><span class="sxs-lookup"><span data-stu-id="2da58-146">CNAME</span></span>| <span data-ttu-id="2da58-147">Dialin</span><span class="sxs-lookup"><span data-stu-id="2da58-147">dialin</span></span>  |<span data-ttu-id="2da58-148">3600</span><span class="sxs-lookup"><span data-stu-id="2da58-148">3600</span></span>|  <span data-ttu-id="2da58-149">WebDir.Online.Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="2da58-149">webdir.online.lync.<span>com</span></span>|

2.  <span data-ttu-id="2da58-150">*Deaktivieren von freigegebenen SIP-Adressraums in Office 365-Mandanten.*</span><span class="sxs-lookup"><span data-stu-id="2da58-150">*Disable shared SIP address space in Office 365 tenant.*</span></span>
<span data-ttu-id="2da58-151">Geben Sie folgenden Befehl muss über einen Skype für Business Online-PowerShell-Fenster ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2da58-151">The command below needs to be done from a Skype for Business Online PowerShell window.</span></span>

    `Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false`
 
3.  <span data-ttu-id="2da58-152">*Deaktivieren Sie die Möglichkeit in auf Prem Kommunikation mit Office 365.*</span><span class="sxs-lookup"><span data-stu-id="2da58-152">*Disable ability in on-prem to communicate with Office 365.*</span></span>  
<span data-ttu-id="2da58-153">Geben Sie folgenden Befehl muss über eine lokale PowerShell-Fenster ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2da58-153">The command below needs to be done from an on-premises PowerShell window.</span></span>  <span data-ttu-id="2da58-154">Wenn Sie bereits einen Skype für Business Online-Sitzung importiert haben, starten Sie eine neue Skype für Business PowerShell-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="2da58-154">If you have previously imported a Skype for Business Online session, start a new Skype for Business PowerShell session.</span></span>

    `Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false`

## <a name="see-also"></a><span data-ttu-id="2da58-155">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2da58-155">See also</span></span>

[<span data-ttu-id="2da58-156">Cloud-Konsolidierung für Teams und Skype für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="2da58-156">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)