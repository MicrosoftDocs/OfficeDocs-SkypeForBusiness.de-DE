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
ms.openlocfilehash: d441d9fcc5e4f2cec495efabdbea423eaaec882c
ms.sourcegitcommit: 7920c47eb73e665dad4bf7214b28541d357bce25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2019
ms.locfileid: "37962053"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a><span data-ttu-id="de3c2-103">Deaktivieren der hybridbereitstellung zur vollständigen Migration in die Cloud</span><span class="sxs-lookup"><span data-stu-id="de3c2-103">Disable hybrid to complete migration to the cloud</span></span>

<span data-ttu-id="de3c2-104">Nachdem Sie alle Benutzer aus der lokalen Umgebung in die Cloud verschoben haben, können Sie die lokale Skype for Business Bereitstellung außer Betrieb nehmen.</span><span class="sxs-lookup"><span data-stu-id="de3c2-104">After you have moved all users from on-premises to the cloud, you can decommission the on-premises Skype for Business deployment.</span></span> <span data-ttu-id="de3c2-105">Neben dem Entfernen von Hardware besteht ein wichtiger Schritt darin, die lokale Bereitstellung logisch von Office 365 durch Deaktivieren von Hybrid zu trennen.</span><span class="sxs-lookup"><span data-stu-id="de3c2-105">Aside from removing any hardware, a critical step is to logically separate that on-premises deployment from Office 365 by disabling hybrid.</span></span> <span data-ttu-id="de3c2-106">Das Deaktivieren von Hybriden besteht aus drei Schritten:</span><span class="sxs-lookup"><span data-stu-id="de3c2-106">Disabling hybrid consists of 3 steps:</span></span>

1. <span data-ttu-id="de3c2-107">Aktualisieren Sie die DNS-Einträge so, dass Sie auf Office 365 deuten.</span><span class="sxs-lookup"><span data-stu-id="de3c2-107">Update DNS records to point to Office 365.</span></span>

2. <span data-ttu-id="de3c2-108">Deaktivieren Sie die geteilte Domäne im Office 365 Mandanten.</span><span class="sxs-lookup"><span data-stu-id="de3c2-108">Disable split domain in the Office 365 tenant.</span></span>

3. <span data-ttu-id="de3c2-109">Deaktivieren Sie die Möglichkeit in der lokalen Kommunikation mit Office 365.</span><span class="sxs-lookup"><span data-stu-id="de3c2-109">Disable the ability in on-premises to communicate with Office 365.</span></span>

<span data-ttu-id="de3c2-110">Diese Schritte sollten zusammen als Einheit ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="de3c2-110">These steps should be done together as a unit.</span></span> <span data-ttu-id="de3c2-111">Details finden Sie weiter unten.</span><span class="sxs-lookup"><span data-stu-id="de3c2-111">Details are provided below.</span></span> <span data-ttu-id="de3c2-112">Darüber hinaus werden Richtlinien für die Verwaltung von Telefonnummern für migrierte Benutzer bereitgestellt, sobald die lokale Bereitstellung getrennt wird.</span><span class="sxs-lookup"><span data-stu-id="de3c2-112">In addition, guidelines are provided for managing phone numbers for migrated users once the on-premises deployment is disconnected.</span></span>

> [!Note] 
> <span data-ttu-id="de3c2-113">In seltenen Fällen kann es dazu führen, dass der Verbund mit einigen anderen Organisationen nicht mehr funktionsfähig ist, wenn das Ändern von DNS von einem Standort auf einen Office 365 für Ihre Organisation erfolgt, bis eine andere Organisation ihre Verbund Konfiguration aktualisiert:</span><span class="sxs-lookup"><span data-stu-id="de3c2-113">In rare cases, changing DNS from pointing on premises to Office 365 for your organization may cause federation with some other organizations to stop working until that other organization updates their federation configuration:</span></span><ul><li>
<span data-ttu-id="de3c2-114">Alle Verbundorganisationen, die das ältere direkte Verbundmodell (auch als zulässiger Partner Server bezeichnet) verwenden, müssen ihre zulässigen Domäneneinträge für Ihre Organisation aktualisieren, um den Proxy-FQDN zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="de3c2-114">Any federated organizations that are using the older Direct Federation model (also known as Allowed Partner Server) will need to update their allowed domain entries for their organization to remove the proxy FQDN.</span></span> <span data-ttu-id="de3c2-115">Dieses Legacy-Verbundmodell basiert nicht auf DNS-SRV-Einträgen, daher wird eine solche Konfiguration veraltet, sobald Ihre Organisation in die Cloud wechselt.</span><span class="sxs-lookup"><span data-stu-id="de3c2-115">This legacy federation model is not based on DNS SRV records, so such a configuration will become out of date once your organization moves to the cloud.</span></span> </li><li><span data-ttu-id="de3c2-116">Jede Partnerorganisation, die über keinen aktivierten Hostinganbieter für sipfed. online. lync verfügt. <span>com muss Ihre Konfiguration aktualisieren, um dies zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="de3c2-116">Any federated organization that does not have an enabled hosting provider for sipfed.online.lync.<span>com will need to update their configuration to enable that.</span></span> <span data-ttu-id="de3c2-117">Diese Situation ist nur möglich, wenn die Verbundorganisation ausschließlich lokal ist und nie mit einem hybriden oder Online-Mandanten verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="de3c2-117">This situation is only possible if the federated organization is purely on premises and has never federated with any hybrid or online tenant.</span></span> <span data-ttu-id="de3c2-118">In einem solchen Fall funktioniert der Partnerverbund mit diesen Organisationen erst, wenn er seinen Hostinganbieter aktiviert.</span><span class="sxs-lookup"><span data-stu-id="de3c2-118">In such a case, federation with these organizations will not work until they enable their hosting provider.</span></span></li></ul><span data-ttu-id="de3c2-119">Wenn Sie vermuten, dass einer ihrer Verbundpartner möglicherweise einen direkten Partnerverbund verwendet oder mit einer Online-oder Hybrid Organisation verbunden ist, empfehlen wir Ihnen, Ihnen beim Vorbereiten der Migration zur Cloud eine entsprechende Mitteilung zu senden.</span><span class="sxs-lookup"><span data-stu-id="de3c2-119">If you suspect that any of your federated partners may be using Direct Federation or have federated with any online or hybrid organization, we suggest you send them a communication about this as you prepare to complete your migration to the cloud.</span></span>

1.  <span data-ttu-id="de3c2-120">*Aktualisieren Sie DNS so, dass es auf Office 365 zeigt.*</span><span class="sxs-lookup"><span data-stu-id="de3c2-120">*Update DNS to point to Office 365.*</span></span>
<span data-ttu-id="de3c2-121">Das externe DNS der Organisation für die lokale Organisation muss so aktualisiert werden, dass Skype for Business Datensätze auf Office 365 statt auf die lokale Bereitstellung deuten.</span><span class="sxs-lookup"><span data-stu-id="de3c2-121">The organization’s external DNS for the on-premises organization needs to be updated so that Skype for Business records point to Office 365 instead of the on-premises deployment.</span></span> <span data-ttu-id="de3c2-122">Insbesondere gilt:</span><span class="sxs-lookup"><span data-stu-id="de3c2-122">Specifically:</span></span>

    |<span data-ttu-id="de3c2-123">Eintragstyp</span><span class="sxs-lookup"><span data-stu-id="de3c2-123">Record type</span></span>|<span data-ttu-id="de3c2-124">Name</span><span class="sxs-lookup"><span data-stu-id="de3c2-124">Name</span></span>|<span data-ttu-id="de3c2-125">TTL</span><span class="sxs-lookup"><span data-stu-id="de3c2-125">TTL</span></span>|<span data-ttu-id="de3c2-126">Wert</span><span class="sxs-lookup"><span data-stu-id="de3c2-126">Value</span></span>|
    |---|---|---|---|
    |<span data-ttu-id="de3c2-127">SRV</span><span class="sxs-lookup"><span data-stu-id="de3c2-127">SRV</span></span>|<span data-ttu-id="de3c2-128">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="de3c2-128">_sipfederationtls._tcp</span></span>|<span data-ttu-id="de3c2-129">3600</span><span class="sxs-lookup"><span data-stu-id="de3c2-129">3600</span></span>|<span data-ttu-id="de3c2-130">100 1 5061 sipfed. online. lync. <span>com-</span><span class="sxs-lookup"><span data-stu-id="de3c2-130">100 1 5061 sipfed.online.lync.<span>com</span></span>|
    |<span data-ttu-id="de3c2-131">SRV</span><span class="sxs-lookup"><span data-stu-id="de3c2-131">SRV</span></span>|<span data-ttu-id="de3c2-132">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="de3c2-132">_sip._tls</span></span>|<span data-ttu-id="de3c2-133">3600</span><span class="sxs-lookup"><span data-stu-id="de3c2-133">3600</span></span>|<span data-ttu-id="de3c2-134">100 1 443 sipdir. online. lync. <span>com-</span><span class="sxs-lookup"><span data-stu-id="de3c2-134">100 1 443 sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="de3c2-135">CNAME</span><span class="sxs-lookup"><span data-stu-id="de3c2-135">CNAME</span></span>| <span data-ttu-id="de3c2-136">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="de3c2-136">lyncdiscover</span></span>|   <span data-ttu-id="de3c2-137">3600</span><span class="sxs-lookup"><span data-stu-id="de3c2-137">3600</span></span>|   <span data-ttu-id="de3c2-138">WebDir. online. lync. <span>com-</span><span class="sxs-lookup"><span data-stu-id="de3c2-138">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="de3c2-139">CNAME</span><span class="sxs-lookup"><span data-stu-id="de3c2-139">CNAME</span></span>| <span data-ttu-id="de3c2-140">sip</span><span class="sxs-lookup"><span data-stu-id="de3c2-140">sip</span></span>|    <span data-ttu-id="de3c2-141">3600</span><span class="sxs-lookup"><span data-stu-id="de3c2-141">3600</span></span>|   <span data-ttu-id="de3c2-142">sipdir. online. lync. <span>com-</span><span class="sxs-lookup"><span data-stu-id="de3c2-142">sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="de3c2-143">CNAME</span><span class="sxs-lookup"><span data-stu-id="de3c2-143">CNAME</span></span>| <span data-ttu-id="de3c2-144">erfüllen</span><span class="sxs-lookup"><span data-stu-id="de3c2-144">meet</span></span>|   <span data-ttu-id="de3c2-145">3600</span><span class="sxs-lookup"><span data-stu-id="de3c2-145">3600</span></span>|   <span data-ttu-id="de3c2-146">WebDir. online. lync. <span>com-</span><span class="sxs-lookup"><span data-stu-id="de3c2-146">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="de3c2-147">CNAME</span><span class="sxs-lookup"><span data-stu-id="de3c2-147">CNAME</span></span>| <span data-ttu-id="de3c2-148">Dialin</span><span class="sxs-lookup"><span data-stu-id="de3c2-148">dialin</span></span>  |<span data-ttu-id="de3c2-149">3600</span><span class="sxs-lookup"><span data-stu-id="de3c2-149">3600</span></span>|  <span data-ttu-id="de3c2-150">WebDir. online. lync. <span>com-</span><span class="sxs-lookup"><span data-stu-id="de3c2-150">webdir.online.lync.<span>com</span></span>|

2.  <span data-ttu-id="de3c2-151">*Deaktivieren Sie den freigegebenen SIP-Adressraum in Office 365 Mandanten.*</span><span class="sxs-lookup"><span data-stu-id="de3c2-151">*Disable shared SIP address space in Office 365 tenant.*</span></span>
<span data-ttu-id="de3c2-152">Der folgende Befehl muss in einem Skype for Business Online PowerShell-Fenster ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="de3c2-152">The command below needs to be done from a Skype for Business Online PowerShell window.</span></span>

    ```
    Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
    ```
 
3.  <span data-ttu-id="de3c2-153">*Deaktivieren der Fähigkeit in "on-Prem" zur Kommunikation mit Office 365.*</span><span class="sxs-lookup"><span data-stu-id="de3c2-153">*Disable ability in on-prem to communicate with Office 365.*</span></span>  
<span data-ttu-id="de3c2-154">Der folgende Befehl muss über ein lokales PowerShell-Fenster ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="de3c2-154">The command below needs to be done from an on-premises PowerShell window.</span></span>  <span data-ttu-id="de3c2-155">Wenn Sie zuvor eine Skype for Business Online Sitzung importiert haben, starten Sie eine neue Skype for Business PowerShell-Sitzung wie folgt:</span><span class="sxs-lookup"><span data-stu-id="de3c2-155">If you have previously imported a Skype for Business Online session, start a new Skype for Business PowerShell session as follows:</span></span>

```
    Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
```

### <a name="manage-phone-numbers-for-users-who-were-migrated-from-on-premises"></a><span data-ttu-id="de3c2-156">Verwalten von Telefonnummern für Benutzer, die von lokal migriert wurden</span><span class="sxs-lookup"><span data-stu-id="de3c2-156">Manage phone numbers for users who were migrated from on-premises</span></span>

<span data-ttu-id="de3c2-157">Administratoren können Benutzer verwalten, die zuvor von einem lokalen Skype for Business Server in die Cloud verschoben wurden, auch wenn die lokale Bereitstellung außer Betrieb genommen wurde.</span><span class="sxs-lookup"><span data-stu-id="de3c2-157">Administrators can manage users who were previously moved from an on-premises Skype for Business Server to the cloud, even after the on-premises deployment is decommissioned.</span></span> <span data-ttu-id="de3c2-158">Es gibt zwei verschiedene Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="de3c2-158">There are two different possibilities:</span></span>

- <span data-ttu-id="de3c2-159">Der Benutzer hat vor dem Wechsel keinen Wert für LineUri lokal bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="de3c2-159">The user did not have a value for lineURI on-premises before the move.</span></span> 

  <span data-ttu-id="de3c2-160">In diesem Fall können Sie die LineURI mithilfe der-onpremLineUri-Parameter im Cmdlet " [Csuser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) " im Skype for Business Online PowerShell-Modul ändern.</span><span class="sxs-lookup"><span data-stu-id="de3c2-160">In this case, you can modify the LineURI using the -onpremLineUri parameters in the [Set-Csuser cmdlet](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) in the Skype for Business Online Powershell module.</span></span>

- <span data-ttu-id="de3c2-161">Der Benutzer hatte eine lokale LineUri vor dem Wechsel (vermutlich, weil der Benutzer für Enterprise-VoIP aktiviert wurde).</span><span class="sxs-lookup"><span data-stu-id="de3c2-161">The user had a lineURI on-premises before the move (presumably because the user was enabled for Enterprise Voice).</span></span> 

  <span data-ttu-id="de3c2-162">Wenn Sie das lineURI ändern möchten, müssen Sie dies in der lokalen Active Directory durchführen und den Wert auf Azure AD übernehmen.</span><span class="sxs-lookup"><span data-stu-id="de3c2-162">If you want to change the lineURI, you must do this in the on-premises Active Directory and let the value flow up to Azure AD.</span></span> <span data-ttu-id="de3c2-163">Dies erfordert keine lokale Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="de3c2-163">This does NOT require on-premises Skype for Business Server.</span></span> <span data-ttu-id="de3c2-164">Dieses Attribut, msRTCSIP, kann vielmehr direkt im lokalen Active Directory bearbeitet werden, indem entweder das MMC-Snap-in Active Directory Benutzer und Computer oder die PowerShell verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="de3c2-164">Rather, this attribute, msRTCSIP-Line, can be edited directly in the on-premises Active Directory, using either the Active Directory Users and Computers MMC snap-in, or by using PowerShell.</span></span> <span data-ttu-id="de3c2-165">Wenn Sie das MMC-Snap-in verwenden, öffnen Sie die Seite Eigenschaften des Benutzers, klicken Sie auf Registerkarte Attribut-Editor, und suchen Sie nach msRTCSIP-Reihe.</span><span class="sxs-lookup"><span data-stu-id="de3c2-165">If you are using the MMC snap-in, open to the properties page of the user, click Attribute Editor tab, and find msRTCSIP-Line.</span></span>

  ![Tool zum Active Directory von Benutzern und Computern](../media/disable-hybrid-1.png)

## <a name="see-also"></a><span data-ttu-id="de3c2-167">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="de3c2-167">See also</span></span>

[<span data-ttu-id="de3c2-168">Cloud-Konsolidierung für Teams und Skype for Business</span><span class="sxs-lookup"><span data-stu-id="de3c2-168">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)
