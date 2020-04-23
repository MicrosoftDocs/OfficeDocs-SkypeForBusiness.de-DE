---
title: Deaktivieren der Hybridbereitstellung zur Durchführung der Migration in die Cloud
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
description: Dieser Anhang enthält detaillierte Schritte zum Deaktivieren von Hybriden im Rahmen der Cloud-Konsolidierung für Teams und Skype for Business.
ms.openlocfilehash: 053d632b5a07b7ce7cca8ef7a1ddf45a673bcf59
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780144"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a><span data-ttu-id="53c87-103">Deaktivieren der Hybridbereitstellung zur Durchführung der Migration in die Cloud</span><span class="sxs-lookup"><span data-stu-id="53c87-103">Disable hybrid to complete migration to the cloud</span></span>

<span data-ttu-id="53c87-104">Nachdem Sie alle Benutzer von lokal in die Cloud verschoben haben, können Sie die lokale Skype for Business-Bereitstellung außer Betrieb nehmen.</span><span class="sxs-lookup"><span data-stu-id="53c87-104">After you have moved all users from on-premises to the cloud, you can decommission the on-premises Skype for Business deployment.</span></span> <span data-ttu-id="53c87-105">Abgesehen davon, dass Hardware entfernt wird, besteht ein wichtiger Schritt darin, die lokale Bereitstellung von Office 365 durch Deaktivieren der Hybridbereitstellung zu trennen.</span><span class="sxs-lookup"><span data-stu-id="53c87-105">Aside from removing any hardware, a critical step is to logically separate that on-premises deployment from Office 365 by disabling hybrid.</span></span> <span data-ttu-id="53c87-106">Das Deaktivieren von Hybriden besteht aus drei Schritten:</span><span class="sxs-lookup"><span data-stu-id="53c87-106">Disabling hybrid consists of 3 steps:</span></span>

1. <span data-ttu-id="53c87-107">Aktualisieren Ihrer DNS-Einträge derart, dass sie auf Office 365 verweisen.</span><span class="sxs-lookup"><span data-stu-id="53c87-107">Update DNS records to point to Office 365.</span></span>

2. <span data-ttu-id="53c87-108">Deaktivieren Sie die geteilte Domäne in der Office 365 Organisation.</span><span class="sxs-lookup"><span data-stu-id="53c87-108">Disable split domain in the Office 365 organization.</span></span>

3. <span data-ttu-id="53c87-109">Deaktivieren Sie die Möglichkeit in der lokalen Kommunikation mit Office 365.</span><span class="sxs-lookup"><span data-stu-id="53c87-109">Disable the ability in on-premises to communicate with Office 365.</span></span>

<span data-ttu-id="53c87-110">Diese Schritte sollten zusammen als Einheit ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="53c87-110">These steps should be done together as a unit.</span></span> <span data-ttu-id="53c87-111">Details finden Sie weiter unten.</span><span class="sxs-lookup"><span data-stu-id="53c87-111">Details are provided below.</span></span> <span data-ttu-id="53c87-112">Darüber hinaus werden Richtlinien für die Verwaltung von Telefonnummern für migrierte Benutzer bereitgestellt, sobald die lokale Bereitstellung getrennt wird.</span><span class="sxs-lookup"><span data-stu-id="53c87-112">In addition, guidelines are provided for managing phone numbers for migrated users once the on-premises deployment is disconnected.</span></span>

> [!Note] 
> <span data-ttu-id="53c87-113">In seltenen Fällen kann es dazu führen, dass der Verbund mit einigen anderen Organisationen nicht mehr funktionsfähig ist, wenn das Ändern von DNS von einem Standort auf einen Office 365 für Ihre Organisation erfolgt, bis eine andere Organisation ihre Verbund Konfiguration aktualisiert:</span><span class="sxs-lookup"><span data-stu-id="53c87-113">In rare cases, changing DNS from pointing on premises to Office 365 for your organization may cause federation with some other organizations to stop working until that other organization updates their federation configuration:</span></span><ul><li>
<span data-ttu-id="53c87-114">Alle Verbundorganisationen, die das ältere direkte Verbundmodell (auch als zulässiger Partner Server bezeichnet) verwenden, müssen ihre zulässigen Domäneneinträge für Ihre Organisation aktualisieren, um den Proxy-FQDN zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="53c87-114">Any federated organizations that are using the older Direct Federation model (also known as Allowed Partner Server) will need to update their allowed domain entries for their organization to remove the proxy FQDN.</span></span> <span data-ttu-id="53c87-115">Dieses Legacy-Verbundmodell basiert nicht auf DNS-SRV-Einträgen, daher wird eine solche Konfiguration veraltet, sobald Ihre Organisation in die Cloud wechselt.</span><span class="sxs-lookup"><span data-stu-id="53c87-115">This legacy federation model is not based on DNS SRV records, so such a configuration will become out of date once your organization moves to the cloud.</span></span> </li><li><span data-ttu-id="53c87-116">Jede Partnerorganisation, die über keinen aktivierten Hostinganbieter für sipfed. online. lync verfügt. <span>com muss Ihre Konfiguration aktualisieren, um dies zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="53c87-116">Any federated organization that does not have an enabled hosting provider for sipfed.online.lync.<span>com will need to update their configuration to enable that.</span></span> <span data-ttu-id="53c87-117">Diese Situation ist nur möglich, wenn die Verbundorganisation ausschließlich lokal ist und nie mit einem hybriden oder Online-Mandanten verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="53c87-117">This situation is only possible if the federated organization is purely on premises and has never federated with any hybrid or online tenant.</span></span> <span data-ttu-id="53c87-118">In einem solchen Fall funktioniert der Partnerverbund mit diesen Organisationen erst, wenn er seinen Hostinganbieter aktiviert.</span><span class="sxs-lookup"><span data-stu-id="53c87-118">In such a case, federation with these organizations will not work until they enable their hosting provider.</span></span></li></ul><span data-ttu-id="53c87-119">Wenn Sie vermuten, dass einer ihrer Verbundpartner möglicherweise einen direkten Partnerverbund verwendet oder mit einer Online-oder Hybrid Organisation verbunden ist, empfehlen wir Ihnen, Ihnen beim Vorbereiten der Migration zur Cloud eine entsprechende Mitteilung zu senden.</span><span class="sxs-lookup"><span data-stu-id="53c87-119">If you suspect that any of your federated partners may be using Direct Federation or have federated with any online or hybrid organization, we suggest you send them a communication about this as you prepare to complete your migration to the cloud.</span></span>

1.  <span data-ttu-id="53c87-120">*Aktualisieren Sie DNS so, dass es auf Office 365 zeigt.*</span><span class="sxs-lookup"><span data-stu-id="53c87-120">*Update DNS to point to Office 365.*</span></span>
<span data-ttu-id="53c87-121">Das externe DNS der Organisation für die lokale Organisation muss so aktualisiert werden, dass Skype for Business Datensätze auf Office 365 statt auf die lokale Bereitstellung deuten.</span><span class="sxs-lookup"><span data-stu-id="53c87-121">The organization’s external DNS for the on-premises organization needs to be updated so that Skype for Business records point to Office 365 instead of the on-premises deployment.</span></span> <span data-ttu-id="53c87-122">Insbesondere gilt:</span><span class="sxs-lookup"><span data-stu-id="53c87-122">Specifically:</span></span>

    |<span data-ttu-id="53c87-123">Eintragstyp</span><span class="sxs-lookup"><span data-stu-id="53c87-123">Record type</span></span>|<span data-ttu-id="53c87-124">Name</span><span class="sxs-lookup"><span data-stu-id="53c87-124">Name</span></span>|<span data-ttu-id="53c87-125">TTL</span><span class="sxs-lookup"><span data-stu-id="53c87-125">TTL</span></span>|<span data-ttu-id="53c87-126">Wert</span><span class="sxs-lookup"><span data-stu-id="53c87-126">Value</span></span>|
    |---|---|---|---|
    |<span data-ttu-id="53c87-127">SRV</span><span class="sxs-lookup"><span data-stu-id="53c87-127">SRV</span></span>|<span data-ttu-id="53c87-128">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="53c87-128">_sipfederationtls._tcp</span></span>|<span data-ttu-id="53c87-129">3600</span><span class="sxs-lookup"><span data-stu-id="53c87-129">3600</span></span>|<span data-ttu-id="53c87-130">100 1 5061 sipfed. online. lync. <span>com-</span><span class="sxs-lookup"><span data-stu-id="53c87-130">100 1 5061 sipfed.online.lync.<span>com</span></span>|
    |<span data-ttu-id="53c87-131">SRV</span><span class="sxs-lookup"><span data-stu-id="53c87-131">SRV</span></span>|<span data-ttu-id="53c87-132">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="53c87-132">_sip._tls</span></span>|<span data-ttu-id="53c87-133">3600</span><span class="sxs-lookup"><span data-stu-id="53c87-133">3600</span></span>|<span data-ttu-id="53c87-134">100 1 443 sipdir. online. lync. <span>com-</span><span class="sxs-lookup"><span data-stu-id="53c87-134">100 1 443 sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="53c87-135">CNAME</span><span class="sxs-lookup"><span data-stu-id="53c87-135">CNAME</span></span>| <span data-ttu-id="53c87-136">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="53c87-136">lyncdiscover</span></span>|   <span data-ttu-id="53c87-137">3600</span><span class="sxs-lookup"><span data-stu-id="53c87-137">3600</span></span>|   <span data-ttu-id="53c87-138">WebDir. online. lync. <span>com-</span><span class="sxs-lookup"><span data-stu-id="53c87-138">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="53c87-139">CNAME</span><span class="sxs-lookup"><span data-stu-id="53c87-139">CNAME</span></span>| <span data-ttu-id="53c87-140">sip</span><span class="sxs-lookup"><span data-stu-id="53c87-140">sip</span></span>|    <span data-ttu-id="53c87-141">3600</span><span class="sxs-lookup"><span data-stu-id="53c87-141">3600</span></span>|   <span data-ttu-id="53c87-142">sipdir. online. lync. <span>com-</span><span class="sxs-lookup"><span data-stu-id="53c87-142">sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="53c87-143">CNAME</span><span class="sxs-lookup"><span data-stu-id="53c87-143">CNAME</span></span>| <span data-ttu-id="53c87-144">erfüllen</span><span class="sxs-lookup"><span data-stu-id="53c87-144">meet</span></span>|   <span data-ttu-id="53c87-145">3600</span><span class="sxs-lookup"><span data-stu-id="53c87-145">3600</span></span>|   <span data-ttu-id="53c87-146">WebDir. online. lync. <span>com-</span><span class="sxs-lookup"><span data-stu-id="53c87-146">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="53c87-147">CNAME</span><span class="sxs-lookup"><span data-stu-id="53c87-147">CNAME</span></span>| <span data-ttu-id="53c87-148">Dialin</span><span class="sxs-lookup"><span data-stu-id="53c87-148">dialin</span></span>  |<span data-ttu-id="53c87-149">3600</span><span class="sxs-lookup"><span data-stu-id="53c87-149">3600</span></span>|  <span data-ttu-id="53c87-150">WebDir. online. lync. <span>com-</span><span class="sxs-lookup"><span data-stu-id="53c87-150">webdir.online.lync.<span>com</span></span>|

2.  <span data-ttu-id="53c87-151">*Deaktivieren Sie den freigegebenen SIP-Adressraum in Office 365 Organisation.*</span><span class="sxs-lookup"><span data-stu-id="53c87-151">*Disable shared SIP address space in Office 365 organization.*</span></span>
<span data-ttu-id="53c87-152">Der folgende Befehl muss in einem Skype for Business Online PowerShell-Fenster ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="53c87-152">The command below needs to be done from a Skype for Business Online PowerShell window.</span></span>

    ```PowerShell
    Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
    ```
 
3.  <span data-ttu-id="53c87-153">*Deaktivieren der Fähigkeit in der lokalen Umgebung zur Kommunikation mit Office 365.*</span><span class="sxs-lookup"><span data-stu-id="53c87-153">*Disable ability in on-premises to communicate with Office 365.*</span></span>  
<span data-ttu-id="53c87-154">Der folgende Befehl muss über ein lokales PowerShell-Fenster ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="53c87-154">The command below needs to be done from an on-premises PowerShell window:</span></span>
```PowerShell
    Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
```

### <a name="manage-phone-numbers-for-users-who-were-migrated-from-on-premises"></a><span data-ttu-id="53c87-155">Verwalten von Telefonnummern für Benutzer, die von lokal migriert wurden</span><span class="sxs-lookup"><span data-stu-id="53c87-155">Manage phone numbers for users who were migrated from on-premises</span></span>

<span data-ttu-id="53c87-156">Administratoren können Benutzer verwalten, die zuvor von einem lokalen Skype for Business Server in die Cloud verschoben wurden, auch wenn die lokale Bereitstellung außer Betrieb genommen wurde.</span><span class="sxs-lookup"><span data-stu-id="53c87-156">Administrators can manage users who were previously moved from an on-premises Skype for Business Server to the cloud, even after the on-premises deployment is decommissioned.</span></span> <span data-ttu-id="53c87-157">Es gibt zwei verschiedene Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="53c87-157">There are two different possibilities:</span></span>

- <span data-ttu-id="53c87-158">Der Benutzer hat vor dem Wechsel keinen Wert für LineURI lokal bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="53c87-158">The user did not have a value for LineURI on-premises before the move.</span></span> 

  <span data-ttu-id="53c87-159">In diesem Fall können Sie die LineURI mithilfe der-onpremLineUri-Parameter im Cmdlet " [CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) " im Skype for Business Online PowerShell-Modul ändern.</span><span class="sxs-lookup"><span data-stu-id="53c87-159">In this case, you can modify the LineURI using the -onpremLineUri parameters in the [Set-CsUser cmdlet](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) in the Skype for Business Online PowerShell module.</span></span>

- <span data-ttu-id="53c87-160">Der Benutzer hatte eine lokale LineURI vor dem Wechsel (vermutlich, weil der Benutzer für Enterprise-VoIP aktiviert wurde).</span><span class="sxs-lookup"><span data-stu-id="53c87-160">The user had a LineURI on-premises before the move (presumably because the user was enabled for Enterprise Voice).</span></span> 

  <span data-ttu-id="53c87-161">Wenn Sie das LineURI ändern möchten, müssen Sie dies in der lokalen Active Directory durchführen und den Wert auf Azure AD übernehmen.</span><span class="sxs-lookup"><span data-stu-id="53c87-161">If you want to change the LineURI, you must do this in the on-premises Active Directory and let the value flow up to Azure AD.</span></span> <span data-ttu-id="53c87-162">Dies erfordert keine lokale Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="53c87-162">This does NOT require on-premises Skype for Business Server.</span></span> <span data-ttu-id="53c87-163">Dieses Attribut, msRTCSIP, kann vielmehr direkt im lokalen Active Directory bearbeitet werden, indem entweder das MMC-Snap-in Active Directory Benutzer und Computer oder die PowerShell verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="53c87-163">Rather, this attribute, msRTCSIP-Line, can be edited directly in the on-premises Active Directory, using either the Active Directory Users and Computers MMC snap-in, or by using PowerShell.</span></span> <span data-ttu-id="53c87-164">Wenn Sie das MMC-Snap-in verwenden, öffnen Sie die Seite Eigenschaften des Benutzers, klicken Sie auf Registerkarte Attribut-Editor, und suchen Sie nach msRTCSIP-Reihe.</span><span class="sxs-lookup"><span data-stu-id="53c87-164">If you are using the MMC snap-in, open to the properties page of the user, click Attribute Editor tab, and find msRTCSIP-Line.</span></span>

  ![Tool zum Active Directory von Benutzern und Computern](../media/disable-hybrid-1.png)

## <a name="see-also"></a><span data-ttu-id="53c87-166">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="53c87-166">See also</span></span>

[<span data-ttu-id="53c87-167">Cloud-Konsolidierung für Teams und Skype for Business</span><span class="sxs-lookup"><span data-stu-id="53c87-167">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)
