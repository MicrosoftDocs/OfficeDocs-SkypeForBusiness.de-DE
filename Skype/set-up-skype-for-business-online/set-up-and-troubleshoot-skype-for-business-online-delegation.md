---
title: "Richten Sie ein und Problembehandlung bei Skype für Business Online Delegierung"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: e676b911-5f82-41d8-b4ce-3d0d45c3cd04
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Setup
description: "In diesem Artikel wird erläutert, wie eingerichtet und Problembehandlung bei Skype für Business Online Delegierung. Dieser Artikel enthält eine Anleitung für Setup Empfehlungen, bewährte Methoden und Schritte zur Problembehandlung."
ms.openlocfilehash: bf3bf61a633366408e2584a89dfee9ad771ce78e
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2017
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a><span data-ttu-id="d4102-104">Richten Sie ein und Problembehandlung bei Skype für Business Online Delegierung</span><span class="sxs-lookup"><span data-stu-id="d4102-104">Set up and troubleshoot Skype for Business Online delegation</span></span>

<span data-ttu-id="d4102-105">In diesem Artikel wird erläutert, wie eingerichtet und Problembehandlung bei Skype für Business Online Delegierung.</span><span class="sxs-lookup"><span data-stu-id="d4102-105">This article explains how to set up and troubleshoot Skype for Business Online delegation.</span></span> <span data-ttu-id="d4102-106">Dieser Artikel enthält eine Anleitung für Setup Empfehlungen, bewährte Methoden und Schritte zur Problembehandlung.</span><span class="sxs-lookup"><span data-stu-id="d4102-106">This article gives you guidance for setup recommendations, best practices, and troubleshooting steps.</span></span>
  
## <a name="guidelines-and-requirements"></a><span data-ttu-id="d4102-107">Richtlinien und Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d4102-107">Guidelines and requirements</span></span>

### <a name="guidelines-for-delegation"></a><span data-ttu-id="d4102-108">Richtlinien für die Delegierung</span><span class="sxs-lookup"><span data-stu-id="d4102-108">Guidelines for delegation</span></span>

<span data-ttu-id="d4102-109">Einrichten und erste Delegierung ordnungsgemäß funktioniert, hängt Sie die folgenden Richtlinien:</span><span class="sxs-lookup"><span data-stu-id="d4102-109">Setting up and getting delegation to work correctly depends on you following these guidelines:</span></span>
  
- <span data-ttu-id="d4102-110">Sie müssen die Skype für vollständige Business 2015-Client mit den neuesten Updates oder die Skype für Business 2016 vollständige Client verwenden werden.</span><span class="sxs-lookup"><span data-stu-id="d4102-110">You must be using the Skype for Business 2015 full client with the latest updates or the Skype for Business 2016 full client.</span></span>
    
- <span data-ttu-id="d4102-111">Sie müssen die Outlook 2013-Clients mit den neuesten Updates oder Outlook 2016 Clients verwenden.</span><span class="sxs-lookup"><span data-stu-id="d4102-111">You must be using the Outlook 2013 client with the latest updates or the Outlook 2016 client.</span></span>
    
- <span data-ttu-id="d4102-112">Stellen Sie sicher, dass die Delegator und stellvertretercomputern einem Outlook-Mail-Profil, das die primäre ist oder das Standardprofil verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d4102-112">Make sure that the delegator and delegate computers have one Outlook mail profile that is the primary or the default profile.</span></span> <span data-ttu-id="d4102-113">Diese e-Mail-Profil sollte nur ein Konto enthalten.</span><span class="sxs-lookup"><span data-stu-id="d4102-113">That mail profile should contain only one account.</span></span>
    
- <span data-ttu-id="d4102-114">Skype für Unternehmen für Stellvertreters und den Delegaten sollte Online-Benutzer sein.</span><span class="sxs-lookup"><span data-stu-id="d4102-114">Skype for Business for the delegator and the delegate should be Online users.</span></span> <span data-ttu-id="d4102-115">Darüber hinaus die Exchange Server Postfächer für jedes Konto müssen entweder beide Online oder beide lokalen sein.</span><span class="sxs-lookup"><span data-stu-id="d4102-115">Also, the Exchange Server mailboxes for each account must either both be Online or both be on-premises.</span></span>
    
- <span data-ttu-id="d4102-116">Sowohl die Delegator auch der Stellvertreter sollten die gleiche Hauptversion von Outlook verwenden.</span><span class="sxs-lookup"><span data-stu-id="d4102-116">Both the delegator and delegate should be using the same major version of Outlook.</span></span>
    
- <span data-ttu-id="d4102-117">Der Attributwert **EnableExchangeDelegateSync** sollte auf **true fest,** in die Clientrichtlinie festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="d4102-117">The **EnableExchangeDelegateSync** attribute value should be set to **true** in the client policy.</span></span> <span data-ttu-id="d4102-118">Sie können diese Einstellung überprüfen, indem Sie das Cmdlet **Get-CSClientPolicy** in der Skype für Business Online-PowerShell-Modul ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d4102-118">You can verify this setting by running the **Get-CSClientPolicy** cmdlet in the Skype for Business Online PowerShell module.</span></span>
    
- <span data-ttu-id="d4102-119">Sowohl die Delegator auch der Stellvertreter müssen Skype für Unternehmen und Outlook gleichzeitig auf verschiedenen Arbeitsstationen anmelden, um.</span><span class="sxs-lookup"><span data-stu-id="d4102-119">Both the delegator and delegate must be signed in to Skype for Business and Outlook at the same time on different workstations.</span></span>
    
- <span data-ttu-id="d4102-120">Freigegebene Postfächer werden für die Business Online Delegierung für Skype nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d4102-120">Shared mailboxes aren't supported for Skype for Business Online delegation.</span></span> <span data-ttu-id="d4102-121">Dies ist, da das freigegebene Postfach die Zugriffssteuerungsliste (ACL) für das **sendonbehalf werden standardmäßig** keine.</span><span class="sxs-lookup"><span data-stu-id="d4102-121">This is because the shared mailbox doesn't have the **sendonbehalf** access control list (ACL).</span></span>
    
### <a name="skype-for-business-client-version-support"></a><span data-ttu-id="d4102-122">Skype für Business Version Clientunterstützung</span><span class="sxs-lookup"><span data-stu-id="d4102-122">Skype for Business client version support</span></span>

||<span data-ttu-id="d4102-123">**Outlook 2013**</span><span class="sxs-lookup"><span data-stu-id="d4102-123">**Outlook 2013**</span></span>|<span data-ttu-id="d4102-124">**Outlook 2016**</span><span class="sxs-lookup"><span data-stu-id="d4102-124">**Outlook 2016**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d4102-125">**Lync/Skype für grundlegende Business-Client**</span><span class="sxs-lookup"><span data-stu-id="d4102-125">**Lync/Skype for Business Basic Client**</span></span>| <span data-ttu-id="d4102-126">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="d4102-126">Not supported</span></span> |<span data-ttu-id="d4102-127">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="d4102-127">Not supported</span></span>
|<span data-ttu-id="d4102-128">**Skype für Business 2015**</span><span class="sxs-lookup"><span data-stu-id="d4102-128">**Skype for Business 2015**</span></span>|<span data-ttu-id="d4102-129">Unterstützt </span><span class="sxs-lookup"><span data-stu-id="d4102-129">Supported</span></span>| <span data-ttu-id="d4102-130">Unterstützt </span><span class="sxs-lookup"><span data-stu-id="d4102-130">Supported</span></span>|
|<span data-ttu-id="d4102-131">**Skype für Business 2016**</span><span class="sxs-lookup"><span data-stu-id="d4102-131">**Skype for Business 2016**</span></span>|<span data-ttu-id="d4102-132">Unterstützt </span><span class="sxs-lookup"><span data-stu-id="d4102-132">Supported</span></span>| <span data-ttu-id="d4102-133">Unterstützt </span><span class="sxs-lookup"><span data-stu-id="d4102-133">Supported</span></span>|

   
### <a name="licensing-requirements"></a><span data-ttu-id="d4102-134">Lizenzanforderungen</span><span class="sxs-lookup"><span data-stu-id="d4102-134">Licensing requirements</span></span>

<span data-ttu-id="d4102-135">**Lizenzierung Enterprise E3-Szenario**</span><span class="sxs-lookup"><span data-stu-id="d4102-135">**Enterprise E3 licensing scenario**</span></span>

|<span data-ttu-id="d4102-136">**Lizenz**</span><span class="sxs-lookup"><span data-stu-id="d4102-136">**License**</span></span>|<span data-ttu-id="d4102-137">**Clients**</span><span class="sxs-lookup"><span data-stu-id="d4102-137">**Clients**</span></span>|<span data-ttu-id="d4102-138">**Notizen**</span><span class="sxs-lookup"><span data-stu-id="d4102-138">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d4102-139">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="d4102-139">Enterprise E3</span></span>  <br/> |<span data-ttu-id="d4102-140">Lync 2013 (Skype für Business 2015) mit Outlook 2013 oder Outlook 2016 verwendet</span><span class="sxs-lookup"><span data-stu-id="d4102-140">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="d4102-141">Skype für Outlook 2013 oder Outlook 2016 verwendete Business 2016</span><span class="sxs-lookup"><span data-stu-id="d4102-141">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="d4102-142">Skype für Business Basic-Client unterstützt keine Delegierung.</span><span class="sxs-lookup"><span data-stu-id="d4102-142">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="d4102-143">Für Macintosh-Clients können Sie Anrufe jedoch nicht in Besprechungen delegieren.</span><span class="sxs-lookup"><span data-stu-id="d4102-143">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="d4102-144">Enterprise-E3 mit Office 365-Telefonsystem + Office 365 xCalling Plan</span><span class="sxs-lookup"><span data-stu-id="d4102-144">Enterprise E3 with Office 365 Phone System + Office 365 xCalling Plan</span></span>  <br/> |<span data-ttu-id="d4102-145">Lync 2013 (Skype für Business 2015) mit Outlook 2013 oder Outlook 2016 verwendet</span><span class="sxs-lookup"><span data-stu-id="d4102-145">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="d4102-146">Skype für Outlook 2013 oder Outlook 2016 verwendete Business 2016</span><span class="sxs-lookup"><span data-stu-id="d4102-146">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="d4102-147">Lync für Mac 2011</span><span class="sxs-lookup"><span data-stu-id="d4102-147">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="d4102-148">Skype für Business Basic-Client unterstützt keine Delegierung.</span><span class="sxs-lookup"><span data-stu-id="d4102-148">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="d4102-149">Für Macintosh-Clients können Sie Anrufe jedoch nicht in Besprechungen delegieren.</span><span class="sxs-lookup"><span data-stu-id="d4102-149">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
<span data-ttu-id="d4102-150">**Lizenzierung E5 Enterprise-Szenario**</span><span class="sxs-lookup"><span data-stu-id="d4102-150">**Enterprise E5 licensing scenario**</span></span>

|<span data-ttu-id="d4102-151">**Lizenz**</span><span class="sxs-lookup"><span data-stu-id="d4102-151">**License**</span></span>|<span data-ttu-id="d4102-152">**Clients**</span><span class="sxs-lookup"><span data-stu-id="d4102-152">**Clients**</span></span>|<span data-ttu-id="d4102-153">**Notizen**</span><span class="sxs-lookup"><span data-stu-id="d4102-153">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d4102-154">Enterprise-E5</span><span class="sxs-lookup"><span data-stu-id="d4102-154">Enterprise E5</span></span>  <br/> |<span data-ttu-id="d4102-155">Lync 2013 (Skype für Business 2015) mit Outlook 2013 oder Outlook 2016.</span><span class="sxs-lookup"><span data-stu-id="d4102-155">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016.</span></span>  <br/> <span data-ttu-id="d4102-156">Skype für Outlook 2013 oder Outlook 2016 verwendete Business 2016</span><span class="sxs-lookup"><span data-stu-id="d4102-156">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="d4102-157">Skype für Business Basic-Client unterstützt keine Delegierung.</span><span class="sxs-lookup"><span data-stu-id="d4102-157">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="d4102-158">Für Macintosh-Clients können Sie Anrufe jedoch nicht in Besprechungen delegieren.</span><span class="sxs-lookup"><span data-stu-id="d4102-158">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="d4102-159">Enterprise-E5 plus Office 365 aufrufen Plan</span><span class="sxs-lookup"><span data-stu-id="d4102-159">Enterprise E5 plus Office 365 Calling Plan</span></span>  <br/> |<span data-ttu-id="d4102-160">Skype für Unternehmen für Mac 2016</span><span class="sxs-lookup"><span data-stu-id="d4102-160">Skype for Business for Mac 2016</span></span>  <br/> <span data-ttu-id="d4102-161">Lync 2013 (Skype für Business 2015) mit Outlook 2013 oder Outlook 2016 verwendet</span><span class="sxs-lookup"><span data-stu-id="d4102-161">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="d4102-162">Skype für Outlook 2013 oder Outlook 2016 verwendete Business 2016</span><span class="sxs-lookup"><span data-stu-id="d4102-162">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="d4102-163">Lync für Mac 2011</span><span class="sxs-lookup"><span data-stu-id="d4102-163">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="d4102-164">Skype für Business Basic-Client unterstützt keine Delegierung.</span><span class="sxs-lookup"><span data-stu-id="d4102-164">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="d4102-165">Für Macintosh-Clients können Sie Anrufe jedoch nicht in Besprechungen delegieren.</span><span class="sxs-lookup"><span data-stu-id="d4102-165">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
## <a name="set-up-and-verify-delegation"></a><span data-ttu-id="d4102-166">Einrichten und Überprüfen der Delegierung</span><span class="sxs-lookup"><span data-stu-id="d4102-166">Set up and verify delegation</span></span>

<span data-ttu-id="d4102-167">Um Skype für Business Online Delegierung einzurichten, gehen Sie folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="d4102-167">To set up Skype for Business Online delegation, follow these steps:</span></span>
  
### <a name="for-windows-clients"></a><span data-ttu-id="d4102-168">Für Windows-clients</span><span class="sxs-lookup"><span data-stu-id="d4102-168">For Windows clients</span></span>

 <span data-ttu-id="d4102-169">**Registerkarte für die anrufweiterleitung**</span><span class="sxs-lookup"><span data-stu-id="d4102-169">**Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="d4102-170">Wählen Sie **Extras** > **Optionen** > **Einstellungen der Anrufweiterleitung**.</span><span class="sxs-lookup"><span data-stu-id="d4102-170">Select **Tools** > **Options** > **Call Forwarding Settings**.</span></span>
    
2. <span data-ttu-id="d4102-171">Wählen Sie **Stellvertretungen bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="d4102-171">Select **Edit my delegate members**.</span></span>
    
3. <span data-ttu-id="d4102-172">Wählen Sie **Hinzufügen**, wählen Sie die Stellvertretung, die Sie hinzufügen möchten, und wählen Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="d4102-172">Select **Add**, select the delegate that you want to add, and then select **OK**.</span></span>
    
 <span data-ttu-id="d4102-173">**Keine Registerkarte Anrufweiterleitung**</span><span class="sxs-lookup"><span data-stu-id="d4102-173">**No Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="d4102-174">Wählen Sie in Outlook die **Datei** > **Kontoeinstellungen** > **Stellvertretungszugriff** > **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="d4102-174">In Outlook, select **File** > **Account Settings** > **Delegate Access** > **Add**.</span></span>
    
2. <span data-ttu-id="d4102-175">Suchen Sie nach, und fügen Sie den Namen der Person ein, die die Stellvertretung sein soll.</span><span class="sxs-lookup"><span data-stu-id="d4102-175">Locate and then add the name of the person who is going to be the delegate.</span></span>
    
3. <span data-ttu-id="d4102-176">Wählen Sie im Menü **Kalender** aus, und wählen Sie **Editor (können lesen, erstellen und Ändern von Elementen)**.</span><span class="sxs-lookup"><span data-stu-id="d4102-176">Select the **Calendar** menu, and then select **Editor (can read, create, and modify items)**.</span></span>
    
### <a name="for-mac-clients---lync"></a><span data-ttu-id="d4102-177">Für Macintosh-Clients – Lync</span><span class="sxs-lookup"><span data-stu-id="d4102-177">For Mac clients - Lync</span></span>

 <span data-ttu-id="d4102-178">**Registerkarte für die anrufweiterleitung**</span><span class="sxs-lookup"><span data-stu-id="d4102-178">**Call Forwarding tab**</span></span>
  
- <span data-ttu-id="d4102-179">Wenn der Client verfügt nicht über eine Registerkarte für die **Anrufweiterleitung** , die über den Link **Stellvertretungen bearbeiten** und Stellvertreters sich auf einem Mac befindet, muss Stellvertreters auf einem Windows-basierten Computer anmelden, um die Delegierung einrichten.</span><span class="sxs-lookup"><span data-stu-id="d4102-179">If the client doesn't have a **Call Forwarding** tab that has the **Edit my Delegate Members** link, and the delegator is located on a Mac computer, the delegator must sign in to a Windows-based computer in order to set up the delegation.</span></span> <span data-ttu-id="d4102-180">Dies ist, da Macintosh-Clients können keine MAPI-Verbindungen stellen, und dies ist eine Voraussetzung für die Business-Delegierung aus Outlook Skype herstellen.</span><span class="sxs-lookup"><span data-stu-id="d4102-180">This is because Mac clients can't make MAPI connections, and this is a requirement to establish Skype for Business delegation from Outlook.</span></span>
    
### <a name="verify-success"></a><span data-ttu-id="d4102-181">Überprüfen des Erfolgs des Updates</span><span class="sxs-lookup"><span data-stu-id="d4102-181">Verify success</span></span>

<span data-ttu-id="d4102-182">Wenn die Installation erfolgreich ist, die Stellvertretung sollte angezeigt werden die **Sie als Stellvertreter für < Name > hinzugefügt wurden** Meldung und außerdem, die die **Personen, für die ich Anrufe verwalte** -Gruppe wird erstellt.</span><span class="sxs-lookup"><span data-stu-id="d4102-182">If the setup is successful, the delegate should see the **You were added as a delegate for < Name>** message and also that the **People I Manage Calls For** group is created.</span></span> <span data-ttu-id="d4102-183">Stellvertreters sollte angezeigt werden, dass die Gruppe **Stellvertretungen** erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="d4102-183">The delegator should see that the **Delegates** group is created.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d4102-184">Delegierungsberechtigungen werden in der Regel innerhalb von 30 Minuten der Installation angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d4102-184">Delegation permissions usually appear within 30 minutes of the setup process.</span></span> <span data-ttu-id="d4102-185">Dieser Vorgang kann jedoch bis zu 24 Stunden dauern.</span><span class="sxs-lookup"><span data-stu-id="d4102-185">However, this process can take up to 24 hours to complete.</span></span> 
  
## <a name="troubleshooting"></a><span data-ttu-id="d4102-186">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="d4102-186">Troubleshooting</span></span>

### <a name="common-issues"></a><span data-ttu-id="d4102-187">Häufige Probleme</span><span class="sxs-lookup"><span data-stu-id="d4102-187">Common issues</span></span>

- > <span data-ttu-id="d4102-188">**Problem 1** Der Eintrag Delegat wird weiterhin in der Gruppe **Personen, für die ich Anrufe verwalte** angezeigt, nachdem Stellvertreters des Delegaten aus der Outlook-Client entfernt wurde.</span><span class="sxs-lookup"><span data-stu-id="d4102-188">**Issue 1** The delegate entry continues to appear in the **People I Manage Calls For** group after the delegator has removed the delegate from the Outlook client.</span></span>
    
  - > <span data-ttu-id="d4102-189">**Lösung 1** Auf der Skype für Business-Client mit der rechten Maustaste der stellvertretungs in der Gruppe **Stellvertretungen** , und wählen Sie dann auf **aus Gruppe entfernen**.</span><span class="sxs-lookup"><span data-stu-id="d4102-189">**Resolution 1** On the Skype for Business client, right-click the delegate in the **Delegates** group, and then select **Remove from Group**.</span></span>
    
- > <span data-ttu-id="d4102-190">**Problem 2** Nachdem Delegieren des Zugriffs über den Outlook-Client gewährt wurde, werden für die Stellvertretung die Meldung zur Bestätigung weder der **Personen, für die ich Anrufe verwalte** Gruppe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d4102-190">**Issue 2** After delegate access is granted through the Outlook client, neither the confirmation message nor the **People I Manage Calls For** group appear for the delegate.</span></span>
    
  - > <span data-ttu-id="d4102-191">**Lösung 2** Entfernen Sie die Stellvertretung aus der Outlook-Client, warten Sie 15 Minuten für die Replikation, und fügen Sie die Stellvertretung erneut.</span><span class="sxs-lookup"><span data-stu-id="d4102-191">**Resolution 2** Remove the delegation from the Outlook client, wait about 15 minutes for replication, and then add the delegate again.</span></span>
    
### <a name="other-common-issues"></a><span data-ttu-id="d4102-192">Andere allgemeine Probleme</span><span class="sxs-lookup"><span data-stu-id="d4102-192">Other common issues</span></span>

- <span data-ttu-id="d4102-193">Delegierung funktioniert nicht, wenn der Schwellenwert von 25 Delegators und 25 Delegaten überschritten wird.</span><span class="sxs-lookup"><span data-stu-id="d4102-193">Delegation doesn't work if the threshold of 25 delegators and 25 delegates is exceeded.</span></span>
    
- <span data-ttu-id="d4102-194">Die Skype für Business Basic-Client wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d4102-194">The Skype for Business Basic client isn't supported.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d4102-195">Wenn Sie die Skype für Business Basic-Client installieren, entfernt und Delegierung aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="d4102-195">If you install the Skype for Business Basic client, it will remove and break delegation.</span></span> 
  
- <span data-ttu-id="d4102-196">Wenn der Wert des **MAPI-Status** nicht **OK**ist, stellen Sie sicher, dass die **SIP-** und **SMTP** -Werten entsprechen.</span><span class="sxs-lookup"><span data-stu-id="d4102-196">If the **MAPI Status** value isn't **OK**, make sure that the **SIP** and **SMTP** values match.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d4102-197">Es kann mehrere Minuten dauern für den MAPI-Status als **OK** angezeigt, nach dem ersten Skype für Unternehmen und Outlook Start.</span><span class="sxs-lookup"><span data-stu-id="d4102-197">It can take several minutes for the MAPI status to display as **OK** after you first start Skype for Business and Outlook.</span></span>
  
- <span data-ttu-id="d4102-198">Erstellen einer Sicherheitsgruppe und Hinzufügen von Delegierungsberechtigungen für diese Sicherheitsgruppe wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d4102-198">Creating a security group and adding delegation permissions for that security group isn't supported.</span></span>
    
- <span data-ttu-id="d4102-199">MAPI ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d4102-199">MAPI is unavailable.</span></span> <span data-ttu-id="d4102-200">[Fehler in Skype für Business 2016 Client "MAPI nicht verfügbar"](https://support.microsoft.com/en-us/help/3147130)angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d4102-200">See ["MAPI unavailable" error in Skype for Business 2016 client](https://support.microsoft.com/en-us/help/3147130).</span></span>
    
- <span data-ttu-id="d4102-201">Exchange Online-Postfach ist nicht verfügbar, über die Skype für Business-Client.</span><span class="sxs-lookup"><span data-stu-id="d4102-201">The Exchange Online mailbox isn't accessible through the Skype for Business client.</span></span> <span data-ttu-id="d4102-202">Wenn dies der Fall ist, führen Sie den [Outlook-Verbindungstest](https://testconnectivity.microsoft.com/) dafür sorgen, dass er übergibt.</span><span class="sxs-lookup"><span data-stu-id="d4102-202">If this occurs, run the [Outlook connectivity test](https://testconnectivity.microsoft.com/) to make sure that it passes.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="d4102-203">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="d4102-203">Related topics</span></span>
[<span data-ttu-id="d4102-204">Einrichten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="d4102-204">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="d4102-205">Können Sie Skype für Unternehmensbenutzer Skype-Kontakte hinzufügen</span><span class="sxs-lookup"><span data-stu-id="d4102-205">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)
