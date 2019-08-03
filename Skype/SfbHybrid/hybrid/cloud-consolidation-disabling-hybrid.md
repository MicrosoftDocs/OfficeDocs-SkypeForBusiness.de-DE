---
title: Deaktivieren der hybridbereitstellung zur vollständigen Migration in die Cloud
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
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Dieser Anhang enthält detaillierte Schritte zum Deaktivieren von Hybriden im Rahmen der Cloud-Konsolidierung für Teams und Skype for Business.
ms.openlocfilehash: 805010aa16ca8159b5e274847ca7ca2b296f214d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "36160586"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a><span data-ttu-id="c64bc-103">Deaktivieren der hybridbereitstellung zur vollständigen Migration in die Cloud</span><span class="sxs-lookup"><span data-stu-id="c64bc-103">Disable hybrid to complete migration to the cloud</span></span>

<span data-ttu-id="c64bc-104">Nachdem Sie alle Benutzer aus der lokalen Umgebung in die Cloud verschoben haben, können Sie die lokale Skype for Business Bereitstellung außer Betrieb nehmen.</span><span class="sxs-lookup"><span data-stu-id="c64bc-104">After you have moved all users from on-premises to the cloud, you can decommission the on-premises Skype for Business deployment.</span></span> <span data-ttu-id="c64bc-105">Neben dem Entfernen von Hardware besteht ein wichtiger Schritt darin, die lokale Bereitstellung logisch von Office 365 durch Deaktivieren von Hybrid zu trennen.</span><span class="sxs-lookup"><span data-stu-id="c64bc-105">Aside from removing any hardware, a critical step is to logically separate that on-premises deployment from Office 365 by disabling hybrid.</span></span> <span data-ttu-id="c64bc-106">Das Deaktivieren von Hybriden besteht aus drei Schritten:</span><span class="sxs-lookup"><span data-stu-id="c64bc-106">Disabling hybrid consists of 3 steps:</span></span>

1. <span data-ttu-id="c64bc-107">Aktualisieren Sie die DNS-Einträge so, dass Sie auf Office 365 deuten.</span><span class="sxs-lookup"><span data-stu-id="c64bc-107">Update DNS records to point to Office 365.</span></span>
2. <span data-ttu-id="c64bc-108">Deaktivieren Sie die geteilte Domäne im Office 365 Mandanten.</span><span class="sxs-lookup"><span data-stu-id="c64bc-108">Disable split domain in the Office 365 tenant.</span></span>
3. <span data-ttu-id="c64bc-109">Deaktivieren der Fähigkeit in "on-Prem" zur Kommunikation mit Office 365.</span><span class="sxs-lookup"><span data-stu-id="c64bc-109">Disable ability in on-prem to communicate with Office 365.</span></span>


<span data-ttu-id="c64bc-110">Diese Schritte sollten zusammen als Einheit ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c64bc-110">These steps should be done together as a unit.</span></span> <span data-ttu-id="c64bc-111">Details finden Sie weiter unten.</span><span class="sxs-lookup"><span data-stu-id="c64bc-111">Details are provided below.</span></span>

> [!Note] 
> <span data-ttu-id="c64bc-112">In seltenen Fällen kann es dazu führen, dass der Verbund mit einigen anderen Organisationen nicht mehr funktionsfähig ist, wenn das Ändern von DNS von einem Standort auf einen Office 365 für Ihre Organisation erfolgt, bis eine andere Organisation ihre Verbund Konfiguration aktualisiert:</span><span class="sxs-lookup"><span data-stu-id="c64bc-112">In rare cases, changing DNS from pointing on premises to Office 365 for your organization may cause federation with some other organizations to stop working until that other organization updates their federation configuration:</span></span><ul><li>
<span data-ttu-id="c64bc-113">Alle Verbundorganisationen, die das ältere direkte Verbundmodell (auch als zulässiger Partner Server bezeichnet) verwenden, müssen ihre zulässigen Domäneneinträge für Ihre Organisation aktualisieren, um den Proxy-FQDN zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="c64bc-113">Any federated organizations that are using the older Direct Federation model (also known as Allowed Partner Server) will need to update their allowed domain entries for their organization to remove the proxy FQDN.</span></span> <span data-ttu-id="c64bc-114">Dieses Legacy-Verbundmodell basiert nicht auf DNS-SRV-Einträgen, daher wird eine solche Konfiguration veraltet, sobald Ihre Organisation in die Cloud wechselt.</span><span class="sxs-lookup"><span data-stu-id="c64bc-114">This legacy federation model is not based on DNS SRV records, so such a configuration will become out of date once your organization moves to the cloud.</span></span> </li><li><span data-ttu-id="c64bc-115">Jede Partnerorganisation, die über keinen aktivierten Hostinganbieter für sipfed. online. lync verfügt. <span>com muss Ihre Konfiguration aktualisieren, um dies zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="c64bc-115">Any federated organization that does not have an enabled hosting provider for sipfed.online.lync.<span>com will need to update their configuration to enable that.</span></span> <span data-ttu-id="c64bc-116">Diese Situation ist nur möglich, wenn die Verbundorganisation ausschließlich lokal ist und nie mit einem hybriden oder Online-Mandanten verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="c64bc-116">This situation is only possible if the federated organization is purely on premises and has never federated with any hybrid or online tenant.</span></span> <span data-ttu-id="c64bc-117">In einem solchen Fall funktioniert der Partnerverbund mit diesen Organisationen erst, wenn er seinen Hostinganbieter aktiviert.</span><span class="sxs-lookup"><span data-stu-id="c64bc-117">In such a case, federation with these organizations will not work until they enable their hosting provider.</span></span></li></ul><span data-ttu-id="c64bc-118">Wenn Sie vermuten, dass einer ihrer Verbundpartner möglicherweise einen direkten Partnerverbund verwendet oder mit einer Online-oder Hybrid Organisation verbunden ist, empfehlen wir Ihnen, Ihnen beim Vorbereiten der Migration zur Cloud eine entsprechende Mitteilung zu senden.</span><span class="sxs-lookup"><span data-stu-id="c64bc-118">If you suspect that any of your federated partners may be using Direct Federation or have federated with any online or hybrid organization, we suggest you send them a communication about this as you prepare to complete your migration to the cloud.</span></span>

1.  <span data-ttu-id="c64bc-119">*Aktualisieren Sie DNS so, dass es auf Office 365 zeigt.*</span><span class="sxs-lookup"><span data-stu-id="c64bc-119">*Update DNS to point to Office 365.*</span></span>
<span data-ttu-id="c64bc-120">Das externe DNS der Organisation für die lokale Organisation muss so aktualisiert werden, dass Skype for Business Datensätze auf Office 365 statt auf die lokale Bereitstellung deuten.</span><span class="sxs-lookup"><span data-stu-id="c64bc-120">The organization’s external DNS for the on-premises organization needs to be updated so that Skype for Business records point to Office 365 instead of the on-premises deployment.</span></span> <span data-ttu-id="c64bc-121">Insbesondere gilt:</span><span class="sxs-lookup"><span data-stu-id="c64bc-121">Specifically:</span></span>

    |<span data-ttu-id="c64bc-122">Eintragstyp</span><span class="sxs-lookup"><span data-stu-id="c64bc-122">Record type</span></span>|<span data-ttu-id="c64bc-123">Name</span><span class="sxs-lookup"><span data-stu-id="c64bc-123">Name</span></span>|<span data-ttu-id="c64bc-124">TTL</span><span class="sxs-lookup"><span data-stu-id="c64bc-124">TTL</span></span>|<span data-ttu-id="c64bc-125">Wert</span><span class="sxs-lookup"><span data-stu-id="c64bc-125">Value</span></span>|
    |---|---|---|---|
    |<span data-ttu-id="c64bc-126">SRV</span><span class="sxs-lookup"><span data-stu-id="c64bc-126">SRV</span></span>|<span data-ttu-id="c64bc-127">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="c64bc-127">_sipfederationtls._tcp</span></span>|<span data-ttu-id="c64bc-128">3600</span><span class="sxs-lookup"><span data-stu-id="c64bc-128">3600</span></span>|<span data-ttu-id="c64bc-129">100 1 5061 sipfed. online. lync. <span>com-</span><span class="sxs-lookup"><span data-stu-id="c64bc-129">100 1 5061 sipfed.online.lync.<span>com</span></span>|
    |<span data-ttu-id="c64bc-130">SRV</span><span class="sxs-lookup"><span data-stu-id="c64bc-130">SRV</span></span>|<span data-ttu-id="c64bc-131">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="c64bc-131">_sip._tls</span></span>|<span data-ttu-id="c64bc-132">3600</span><span class="sxs-lookup"><span data-stu-id="c64bc-132">3600</span></span>|<span data-ttu-id="c64bc-133">100 1 443 sipdir. online. lync. <span>com-</span><span class="sxs-lookup"><span data-stu-id="c64bc-133">100 1 443 sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="c64bc-134">CNAME</span><span class="sxs-lookup"><span data-stu-id="c64bc-134">CNAME</span></span>| <span data-ttu-id="c64bc-135">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="c64bc-135">lyncdiscover</span></span>|   <span data-ttu-id="c64bc-136">3600</span><span class="sxs-lookup"><span data-stu-id="c64bc-136">3600</span></span>|   <span data-ttu-id="c64bc-137">WebDir. online. lync. <span>com-</span><span class="sxs-lookup"><span data-stu-id="c64bc-137">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="c64bc-138">CNAME</span><span class="sxs-lookup"><span data-stu-id="c64bc-138">CNAME</span></span>| <span data-ttu-id="c64bc-139">sip</span><span class="sxs-lookup"><span data-stu-id="c64bc-139">sip</span></span>|    <span data-ttu-id="c64bc-140">3600</span><span class="sxs-lookup"><span data-stu-id="c64bc-140">3600</span></span>|   <span data-ttu-id="c64bc-141">sipdir. online. lync. <span>com-</span><span class="sxs-lookup"><span data-stu-id="c64bc-141">sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="c64bc-142">CNAME</span><span class="sxs-lookup"><span data-stu-id="c64bc-142">CNAME</span></span>| <span data-ttu-id="c64bc-143">erfüllen</span><span class="sxs-lookup"><span data-stu-id="c64bc-143">meet</span></span>|   <span data-ttu-id="c64bc-144">3600</span><span class="sxs-lookup"><span data-stu-id="c64bc-144">3600</span></span>|   <span data-ttu-id="c64bc-145">WebDir. online. lync. <span>com-</span><span class="sxs-lookup"><span data-stu-id="c64bc-145">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="c64bc-146">CNAME</span><span class="sxs-lookup"><span data-stu-id="c64bc-146">CNAME</span></span>| <span data-ttu-id="c64bc-147">Dialin</span><span class="sxs-lookup"><span data-stu-id="c64bc-147">dialin</span></span>  |<span data-ttu-id="c64bc-148">3600</span><span class="sxs-lookup"><span data-stu-id="c64bc-148">3600</span></span>|  <span data-ttu-id="c64bc-149">WebDir. online. lync. <span>com-</span><span class="sxs-lookup"><span data-stu-id="c64bc-149">webdir.online.lync.<span>com</span></span>|

2.  <span data-ttu-id="c64bc-150">*Deaktivieren Sie den freigegebenen SIP-Adressraum in Office 365 Mandanten.*</span><span class="sxs-lookup"><span data-stu-id="c64bc-150">*Disable shared SIP address space in Office 365 tenant.*</span></span>
<span data-ttu-id="c64bc-151">Der folgende Befehl muss in einem Skype for Business Online PowerShell-Fenster ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c64bc-151">The command below needs to be done from a Skype for Business Online PowerShell window.</span></span>

    `Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false`
 
3.  <span data-ttu-id="c64bc-152">*Deaktivieren der Fähigkeit in "on-Prem" zur Kommunikation mit Office 365.*</span><span class="sxs-lookup"><span data-stu-id="c64bc-152">*Disable ability in on-prem to communicate with Office 365.*</span></span>  
<span data-ttu-id="c64bc-153">Der folgende Befehl muss über ein lokales PowerShell-Fenster ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c64bc-153">The command below needs to be done from an on-premises PowerShell window.</span></span>  <span data-ttu-id="c64bc-154">Wenn Sie zuvor eine Skype for Business Online Sitzung importiert haben, starten Sie eine neue Skype for Business PowerShell-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="c64bc-154">If you have previously imported a Skype for Business Online session, start a new Skype for Business PowerShell session.</span></span>

    `Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false`

## <a name="see-also"></a><span data-ttu-id="c64bc-155">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c64bc-155">See also</span></span>

[<span data-ttu-id="c64bc-156">Cloud-Konsolidierung für Teams und Skype for Business</span><span class="sxs-lookup"><span data-stu-id="c64bc-156">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)