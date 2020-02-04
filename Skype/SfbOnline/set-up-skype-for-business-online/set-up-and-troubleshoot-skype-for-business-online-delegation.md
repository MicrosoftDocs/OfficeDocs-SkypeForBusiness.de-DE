---
title: Einrichten von und Problembehandlung bei Skype for Business Online-Delegierung
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: e676b911-5f82-41d8-b4ce-3d0d45c3cd04
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
- Setup
description: In diesem Artikel wird erläutert, wie Sie die Skype for Business Online-Delegierung einrichten und beheben. Dieser Artikel enthält Anleitungen für Setup Empfehlungen, bewährte Methoden und Schritte zur Problembehandlung.
ms.openlocfilehash: fac2b68deec94825d57fd06b436d00feaa924a5c
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41706480"
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a><span data-ttu-id="fb3c8-104">Einrichten von und Problembehandlung bei Skype for Business Online-Delegierung</span><span class="sxs-lookup"><span data-stu-id="fb3c8-104">Set up and troubleshoot Skype for Business Online delegation</span></span>

<span data-ttu-id="fb3c8-105">In diesem Artikel wird erläutert, wie Sie die Skype for Business Online-Delegierung einrichten und beheben.</span><span class="sxs-lookup"><span data-stu-id="fb3c8-105">This article explains how to set up and troubleshoot Skype for Business Online delegation.</span></span> <span data-ttu-id="fb3c8-106">Dieser Artikel enthält Anleitungen für Setup Empfehlungen, bewährte Methoden und Schritte zur Problembehandlung.</span><span class="sxs-lookup"><span data-stu-id="fb3c8-106">This article gives you guidance for setup recommendations, best practices, and troubleshooting steps.</span></span>
  
## <a name="guidelines-and-requirements"></a><span data-ttu-id="fb3c8-107">Richtlinien und Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fb3c8-107">Guidelines and requirements</span></span>

### <a name="guidelines-for-delegation"></a><span data-ttu-id="fb3c8-108">Richtlinien für die Delegierung</span><span class="sxs-lookup"><span data-stu-id="fb3c8-108">Guidelines for delegation</span></span>

<span data-ttu-id="fb3c8-109">Die Einrichtung und die ordnungsgemäße Funktionsweise der Delegierung hängen davon ab, wie Sie diesen Richtlinien folgen:</span><span class="sxs-lookup"><span data-stu-id="fb3c8-109">Setting up and getting delegation to work correctly depends on you following these guidelines:</span></span>
  
- <span data-ttu-id="fb3c8-110">Sie müssen den Skype for Business 2015-voll Client mit den neuesten Updates oder dem vollständigen Skype for Business 2016-Client verwenden.</span><span class="sxs-lookup"><span data-stu-id="fb3c8-110">You must be using the Skype for Business 2015 full client with the latest updates or the Skype for Business 2016 full client.</span></span>
    
- <span data-ttu-id="fb3c8-111">Sie müssen den Outlook 2013-Client mit den neuesten Updates oder dem Outlook 2016-Client verwenden.</span><span class="sxs-lookup"><span data-stu-id="fb3c8-111">You must be using the Outlook 2013 client with the latest updates or the Outlook 2016 client.</span></span>
    
- <span data-ttu-id="fb3c8-112">Stellen Sie sicher, dass der delegator-und stell Vertretungs Computer über ein Outlook-e-Mail-Profil verfügt, das das primäre oder Standardprofil darstellt.</span><span class="sxs-lookup"><span data-stu-id="fb3c8-112">Make sure that the delegator and delegate computers have one Outlook mail profile that is the primary or the default profile.</span></span> <span data-ttu-id="fb3c8-113">Dieses e-Mail-Profil sollte nur ein Konto enthalten.</span><span class="sxs-lookup"><span data-stu-id="fb3c8-113">That mail profile should contain only one account.</span></span>
    
- <span data-ttu-id="fb3c8-114">Skype for Business für den delegierenden und den Stellvertreter sollten Online-Benutzer sein.</span><span class="sxs-lookup"><span data-stu-id="fb3c8-114">Skype for Business for the delegator and the delegate should be Online users.</span></span> <span data-ttu-id="fb3c8-115">Außerdem müssen die Exchange Server-Postfächer für jedes Konto entweder online sein oder beide lokal sein.</span><span class="sxs-lookup"><span data-stu-id="fb3c8-115">Also, the Exchange Server mailboxes for each account must either both be Online or both be on-premises.</span></span>
    
- <span data-ttu-id="fb3c8-116">Sowohl der delegator als auch der Delegat sollten dieselbe Hauptversion von Outlook verwenden.</span><span class="sxs-lookup"><span data-stu-id="fb3c8-116">Both the delegator and delegate should be using the same major version of Outlook.</span></span>
    
- <span data-ttu-id="fb3c8-117">Der **EnableExchangeDelegateSync** -Attributwert sollte in der Clientrichtlinie auf " **true** " festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="fb3c8-117">The **EnableExchangeDelegateSync** attribute value should be set to **true** in the client policy.</span></span> <span data-ttu-id="fb3c8-118">Sie können diese Einstellung überprüfen, indem Sie das Cmdlet " **Get-CSClientPolicy** " im PowerShell-Modul von Skype for Business Online ausführen.</span><span class="sxs-lookup"><span data-stu-id="fb3c8-118">You can verify this setting by running the **Get-CSClientPolicy** cmdlet in the Skype for Business Online PowerShell module.</span></span>
    
- <span data-ttu-id="fb3c8-119">Sowohl der delegator als auch der Delegat müssen bei Skype for Business und Outlook gleichzeitig auf unterschiedlichen Workstations angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="fb3c8-119">Both the delegator and delegate must be signed in to Skype for Business and Outlook at the same time on different workstations.</span></span>
    
- <span data-ttu-id="fb3c8-120">Freigegebene Postfächer werden für die Skype for Business Online-Delegation nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fb3c8-120">Shared mailboxes aren't supported for Skype for Business Online delegation.</span></span> <span data-ttu-id="fb3c8-121">Dies liegt daran, dass das freigegebene Postfach nicht über die **sendonbehalf** -Zugriffssteuerungsliste (ACL) verfügt.</span><span class="sxs-lookup"><span data-stu-id="fb3c8-121">This is because the shared mailbox doesn't have the **sendonbehalf** access control list (ACL).</span></span>
    
### <a name="skype-for-business-client-version-support"></a><span data-ttu-id="fb3c8-122">Support für Skype for Business-Client Version</span><span class="sxs-lookup"><span data-stu-id="fb3c8-122">Skype for Business client version support</span></span>

||<span data-ttu-id="fb3c8-123">**Outlook 2013**</span><span class="sxs-lookup"><span data-stu-id="fb3c8-123">**Outlook 2013**</span></span>|<span data-ttu-id="fb3c8-124">**Outlook 2016**</span><span class="sxs-lookup"><span data-stu-id="fb3c8-124">**Outlook 2016**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fb3c8-125">**Lync/Skype for Business-Basis Client**</span><span class="sxs-lookup"><span data-stu-id="fb3c8-125">**Lync/Skype for Business Basic Client**</span></span>| <span data-ttu-id="fb3c8-126">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="fb3c8-126">Not supported</span></span> |<span data-ttu-id="fb3c8-127">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="fb3c8-127">Not supported</span></span>
|<span data-ttu-id="fb3c8-128">**Skype for Business 2015**</span><span class="sxs-lookup"><span data-stu-id="fb3c8-128">**Skype for Business 2015**</span></span>|<span data-ttu-id="fb3c8-129">Unterstützt </span><span class="sxs-lookup"><span data-stu-id="fb3c8-129">Supported</span></span>| <span data-ttu-id="fb3c8-130">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="fb3c8-130">Supported</span></span>|
|<span data-ttu-id="fb3c8-131">**Skype for Business 2016**</span><span class="sxs-lookup"><span data-stu-id="fb3c8-131">**Skype for Business 2016**</span></span>|<span data-ttu-id="fb3c8-132">Unterstützt </span><span class="sxs-lookup"><span data-stu-id="fb3c8-132">Supported</span></span>| <span data-ttu-id="fb3c8-133">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="fb3c8-133">Supported</span></span>|

   
### <a name="licensing-requirements"></a><span data-ttu-id="fb3c8-134">Lizenzierungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="fb3c8-134">Licensing requirements</span></span>

<span data-ttu-id="fb3c8-135">**Enterprise E3-Lizenzierungs Szenario**</span><span class="sxs-lookup"><span data-stu-id="fb3c8-135">**Enterprise E3 licensing scenario**</span></span>

|<span data-ttu-id="fb3c8-136">**Lizenz**</span><span class="sxs-lookup"><span data-stu-id="fb3c8-136">**License**</span></span>|<span data-ttu-id="fb3c8-137">**Clients**</span><span class="sxs-lookup"><span data-stu-id="fb3c8-137">**Clients**</span></span>|<span data-ttu-id="fb3c8-138">**Hinweise**</span><span class="sxs-lookup"><span data-stu-id="fb3c8-138">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fb3c8-139">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="fb3c8-139">Enterprise E3</span></span>  <br/> |<span data-ttu-id="fb3c8-140">Lync 2013 (Skype for Business 2015), verwendet mit Outlook 2013 oder Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fb3c8-140">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="fb3c8-141">Skype for Business 2016, verwendet mit Outlook 2013 oder Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fb3c8-141">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="fb3c8-142">Der Skype for Business Basic-Client unterstützt keine Delegierung.</span><span class="sxs-lookup"><span data-stu-id="fb3c8-142">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="fb3c8-143">Für Mac-Clients können Sie Anrufe, aber nicht Besprechungen delegieren.</span><span class="sxs-lookup"><span data-stu-id="fb3c8-143">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="fb3c8-144">Enterprise E3 mit Office 365 Phone System + Office 365 xCalling-Plan</span><span class="sxs-lookup"><span data-stu-id="fb3c8-144">Enterprise E3 with Office 365 Phone System + Office 365 xCalling Plan</span></span>  <br/> |<span data-ttu-id="fb3c8-145">Lync 2013 (Skype for Business 2015), verwendet mit Outlook 2013 oder Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fb3c8-145">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="fb3c8-146">Skype for Business 2016, verwendet mit Outlook 2013 oder Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fb3c8-146">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="fb3c8-147">Lync für Mac 2011</span><span class="sxs-lookup"><span data-stu-id="fb3c8-147">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="fb3c8-148">Der Skype for Business Basic-Client unterstützt keine Delegierung.</span><span class="sxs-lookup"><span data-stu-id="fb3c8-148">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="fb3c8-149">Für Mac-Clients können Sie Anrufe, aber nicht Besprechungen delegieren.</span><span class="sxs-lookup"><span data-stu-id="fb3c8-149">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
<span data-ttu-id="fb3c8-150">**Enterprise E5-Lizenzierungs Szenario**</span><span class="sxs-lookup"><span data-stu-id="fb3c8-150">**Enterprise E5 licensing scenario**</span></span>

|<span data-ttu-id="fb3c8-151">**Lizenz**</span><span class="sxs-lookup"><span data-stu-id="fb3c8-151">**License**</span></span>|<span data-ttu-id="fb3c8-152">**Clients**</span><span class="sxs-lookup"><span data-stu-id="fb3c8-152">**Clients**</span></span>|<span data-ttu-id="fb3c8-153">**Hinweise**</span><span class="sxs-lookup"><span data-stu-id="fb3c8-153">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fb3c8-154">Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="fb3c8-154">Enterprise E5</span></span>  <br/> |<span data-ttu-id="fb3c8-155">Lync 2013 (Skype for Business 2015) wird in Verbindung mit Outlook 2013 oder Outlook 2016 verwendet.</span><span class="sxs-lookup"><span data-stu-id="fb3c8-155">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016.</span></span>  <br/> <span data-ttu-id="fb3c8-156">Skype for Business 2016, verwendet mit Outlook 2013 oder Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fb3c8-156">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="fb3c8-157">Der Skype for Business Basic-Client unterstützt keine Delegierung.</span><span class="sxs-lookup"><span data-stu-id="fb3c8-157">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="fb3c8-158">Für Mac-Clients können Sie Anrufe, aber nicht Besprechungen delegieren.</span><span class="sxs-lookup"><span data-stu-id="fb3c8-158">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="fb3c8-159">Enterprise E5 Plus Office 365-Anrufplan</span><span class="sxs-lookup"><span data-stu-id="fb3c8-159">Enterprise E5 plus Office 365 Calling Plan</span></span>  <br/> |<span data-ttu-id="fb3c8-160">Skype for Business für Mac 2016</span><span class="sxs-lookup"><span data-stu-id="fb3c8-160">Skype for Business for Mac 2016</span></span>  <br/> <span data-ttu-id="fb3c8-161">Lync 2013 (Skype for Business 2015), verwendet mit Outlook 2013 oder Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fb3c8-161">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="fb3c8-162">Skype for Business 2016, verwendet mit Outlook 2013 oder Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fb3c8-162">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="fb3c8-163">Lync für Mac 2011</span><span class="sxs-lookup"><span data-stu-id="fb3c8-163">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="fb3c8-164">Der Skype for Business Basic-Client unterstützt keine Delegierung.</span><span class="sxs-lookup"><span data-stu-id="fb3c8-164">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="fb3c8-165">Für Mac-Clients können Sie Anrufe, aber nicht Besprechungen delegieren.</span><span class="sxs-lookup"><span data-stu-id="fb3c8-165">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
## <a name="set-up-and-verify-delegation"></a><span data-ttu-id="fb3c8-166">Einrichten und Überprüfen der Delegierung</span><span class="sxs-lookup"><span data-stu-id="fb3c8-166">Set up and verify delegation</span></span>

<span data-ttu-id="fb3c8-167">Führen Sie die folgenden Schritte aus, um die Skype for Business Online-Delegierung einzurichten:</span><span class="sxs-lookup"><span data-stu-id="fb3c8-167">To set up Skype for Business Online delegation, follow these steps:</span></span>
  
### <a name="for-windows-clients"></a><span data-ttu-id="fb3c8-168">Für Windows-Clients</span><span class="sxs-lookup"><span data-stu-id="fb3c8-168">For Windows clients</span></span>

 <span data-ttu-id="fb3c8-169">**Registerkarte "Anrufweiterleitung"**</span><span class="sxs-lookup"><span data-stu-id="fb3c8-169">**Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="fb3c8-170">Wählen Sie **Extras** > **Optionen** > **Anrufweiterleitungseinstellungen**aus.</span><span class="sxs-lookup"><span data-stu-id="fb3c8-170">Select **Tools** > **Options** > **Call Forwarding Settings**.</span></span>
    
2. <span data-ttu-id="fb3c8-171">Wählen Sie **meine Stell Vertretungs Mitglieder bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="fb3c8-171">Select **Edit my delegate members**.</span></span>
    
3. <span data-ttu-id="fb3c8-172">Wählen Sie **Hinzufügen**aus, wählen Sie die Stellvertretung aus, die Sie hinzufügen möchten, und wählen Sie dann **OK**aus.</span><span class="sxs-lookup"><span data-stu-id="fb3c8-172">Select **Add**, select the delegate that you want to add, and then select **OK**.</span></span>
    
 <span data-ttu-id="fb3c8-173">**Keine Registerkarte "Anrufweiterleitung"**</span><span class="sxs-lookup"><span data-stu-id="fb3c8-173">**No Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="fb3c8-174">Wählen Sie in Outlook **Datei** > **Kontoeinstellungen** > **Stellvertreterzugriff** > **Hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="fb3c8-174">In Outlook, select **File** > **Account Settings** > **Delegate Access** > **Add**.</span></span>
    
2. <span data-ttu-id="fb3c8-175">Suchen Sie den Namen der Person, die die Stellvertretung sein soll, und fügen Sie Sie hinzu.</span><span class="sxs-lookup"><span data-stu-id="fb3c8-175">Locate and then add the name of the person who is going to be the delegate.</span></span>
    
3. <span data-ttu-id="fb3c8-176">Wählen Sie das Menü **Kalender** aus, und wählen Sie dann **Editor (kann Elemente lesen, erstellen und ändern)** aus.</span><span class="sxs-lookup"><span data-stu-id="fb3c8-176">Select the **Calendar** menu, and then select **Editor (can read, create, and modify items)**.</span></span>
    
### <a name="for-mac-clients---lync"></a><span data-ttu-id="fb3c8-177">Für Mac-Clients – lync</span><span class="sxs-lookup"><span data-stu-id="fb3c8-177">For Mac clients - Lync</span></span>

 <span data-ttu-id="fb3c8-178">**Registerkarte "Anrufweiterleitung"**</span><span class="sxs-lookup"><span data-stu-id="fb3c8-178">**Call Forwarding tab**</span></span>
  
- <span data-ttu-id="fb3c8-179">Wenn der Client keine Registerkarte " **Anrufweiterleitung** " hat, die über den Link " **meine Stell Vertretungs Mitglieder bearbeiten** " verfügt und sich der delegator auf einem Mac-Computer befindet, muss sich der Delegat bei einem Windows-basierten Computer anmelden, um die Delegierung einzurichten.</span><span class="sxs-lookup"><span data-stu-id="fb3c8-179">If the client doesn't have a **Call Forwarding** tab that has the **Edit my Delegate Members** link, and the delegator is located on a Mac computer, the delegator must sign in to a Windows-based computer in order to set up the delegation.</span></span> <span data-ttu-id="fb3c8-180">Dies liegt daran, dass Mac-Clients keine MAPI-Verbindungen herstellen können und dies eine Voraussetzung für die Einrichtung von Skype for Business-Delegierung aus Outlook ist.</span><span class="sxs-lookup"><span data-stu-id="fb3c8-180">This is because Mac clients can't make MAPI connections, and this is a requirement to establish Skype for Business delegation from Outlook.</span></span>
    
### <a name="verify-success"></a><span data-ttu-id="fb3c8-181">Überprüfen des Erfolgs</span><span class="sxs-lookup"><span data-stu-id="fb3c8-181">Verify success</span></span>

<span data-ttu-id="fb3c8-182">Wenn die Einrichtung erfolgreich ist, sollte die Stellvertretung sehen, dass **Sie als Stellvertretung für #a0 Name>Nachricht hinzugefügt wurden** , und dass die Personen, die **ich Anrufe für die Gruppe verwalte** , erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="fb3c8-182">If the setup is successful, the delegate should see the **You were added as a delegate for < Name>** message and also that the **People I Manage Calls For** group is created.</span></span> <span data-ttu-id="fb3c8-183">Der Delegat sollte sehen, dass die Gruppe **Stellvertretungen** erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="fb3c8-183">The delegator should see that the **Delegates** group is created.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fb3c8-184">Delegierungsberechtigungen werden in der Regel innerhalb von 30 Minuten nach dem Setupvorgang angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fb3c8-184">Delegation permissions usually appear within 30 minutes of the setup process.</span></span> <span data-ttu-id="fb3c8-185">Dieser Vorgang kann jedoch bis zu 24 Stunden dauern.</span><span class="sxs-lookup"><span data-stu-id="fb3c8-185">However, this process can take up to 24 hours to complete.</span></span> 
  
## <a name="troubleshooting"></a><span data-ttu-id="fb3c8-186">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="fb3c8-186">Troubleshooting</span></span>

### <a name="common-issues"></a><span data-ttu-id="fb3c8-187">Häufig auftretende Probleme</span><span class="sxs-lookup"><span data-stu-id="fb3c8-187">Common issues</span></span>

- > <span data-ttu-id="fb3c8-188">**Ausgabe 1** Der Delegat-Eintrag wird weiterhin in den Personen angezeigt, die **ich für die Gruppe Anrufe verwalten** , nachdem der Delegat den Delegaten aus dem Outlook-Client entfernt hat.</span><span class="sxs-lookup"><span data-stu-id="fb3c8-188">**Issue 1** The delegate entry continues to appear in the **People I Manage Calls For** group after the delegator has removed the delegate from the Outlook client.</span></span>
    
  - > <span data-ttu-id="fb3c8-189">**Auflösung 1** Klicken Sie im Skype for Business-Client mit der rechten Maustaste auf den Stellvertreter in der Gruppe **Stellvertretungen** , und wählen Sie dann **aus Gruppe entfernen aus**.</span><span class="sxs-lookup"><span data-stu-id="fb3c8-189">**Resolution 1** On the Skype for Business client, right-click the delegate in the **Delegates** group, and then select **Remove from Group**.</span></span>
    
- > <span data-ttu-id="fb3c8-190">**Problem 2** Nachdem der Zugriff auf die Stellvertretung über den Outlook-Client gewährt wurde, werden weder die Bestätigungsnachricht noch die Personen, die **ich für** die Gruppe verwaltet, für die Stellvertretung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fb3c8-190">**Issue 2** After delegate access is granted through the Outlook client, neither the confirmation message nor the **People I Manage Calls For** group appear for the delegate.</span></span>
    
  - > <span data-ttu-id="fb3c8-191">**Auflösung 2** Entfernen Sie die Delegierung aus dem Outlook-Client, warten Sie etwa 15 Minuten für die Replikation, und fügen Sie dann die Stellvertretung erneut hinzu.</span><span class="sxs-lookup"><span data-stu-id="fb3c8-191">**Resolution 2** Remove the delegation from the Outlook client, wait about 15 minutes for replication, and then add the delegate again.</span></span>
    
### <a name="other-common-issues"></a><span data-ttu-id="fb3c8-192">Andere häufige Probleme</span><span class="sxs-lookup"><span data-stu-id="fb3c8-192">Other common issues</span></span>

- <span data-ttu-id="fb3c8-193">Die Delegierung funktioniert nicht, wenn der Schwellenwert von 25 Delegaten und 25 Stellvertretungen überschritten wird.</span><span class="sxs-lookup"><span data-stu-id="fb3c8-193">Delegation doesn't work if the threshold of 25 delegators and 25 delegates is exceeded.</span></span>
    
- <span data-ttu-id="fb3c8-194">Der Skype for Business Basic-Client wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fb3c8-194">The Skype for Business Basic client isn't supported.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fb3c8-195">Wenn Sie den Skype for Business Basic-Client installieren, wird die Delegierung entfernt und unterbrochen.</span><span class="sxs-lookup"><span data-stu-id="fb3c8-195">If you install the Skype for Business Basic client, it will remove and break delegation.</span></span> 
  
- <span data-ttu-id="fb3c8-196">Wenn der **MAPI-Status** Wert nicht in **Ordnung**ist, stellen Sie sicher, dass die **SIP** -und **SMTP-** Werte übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="fb3c8-196">If the **MAPI Status** value isn't **OK**, make sure that the **SIP** and **SMTP** values match.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fb3c8-197">Es kann einige Minuten dauern, bis der MAPI-Status nach dem ersten Start von Skype for Business und Outlook als **"OK"** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="fb3c8-197">It can take several minutes for the MAPI status to display as **OK** after you first start Skype for Business and Outlook.</span></span>
  
- <span data-ttu-id="fb3c8-198">Das Erstellen einer Sicherheitsgruppe und das Hinzufügen von Delegierungsberechtigungen für diese Sicherheitsgruppe werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fb3c8-198">Creating a security group and adding delegation permissions for that security group isn't supported.</span></span>
    
- <span data-ttu-id="fb3c8-199">MAPI steht nicht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="fb3c8-199">MAPI is unavailable.</span></span> <span data-ttu-id="fb3c8-200">Lesen Sie [den Fehler "MAPI-nicht verfügbar" in Skype for Business 2016-Client](https://support.microsoft.com/en-us/help/3147130).</span><span class="sxs-lookup"><span data-stu-id="fb3c8-200">See ["MAPI unavailable" error in Skype for Business 2016 client](https://support.microsoft.com/en-us/help/3147130).</span></span>
    
- <span data-ttu-id="fb3c8-201">Auf das Exchange Online-Postfach kann über den Skype for Business-Client nicht zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="fb3c8-201">The Exchange Online mailbox isn't accessible through the Skype for Business client.</span></span> <span data-ttu-id="fb3c8-202">Wenn dies der Fall ist, führen Sie den [Outlook-Verbindungstest](https://testconnectivity.microsoft.com/) aus, um sicherzustellen, dass er verläuft.</span><span class="sxs-lookup"><span data-stu-id="fb3c8-202">If this occurs, run the [Outlook connectivity test](https://testconnectivity.microsoft.com/) to make sure that it passes.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="fb3c8-203">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="fb3c8-203">Related topics</span></span>
[<span data-ttu-id="fb3c8-204">Einrichten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="fb3c8-204">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="fb3c8-205">Zulassen, dass Skype for Business-Benutzer Skype-Kontakte hinzufügen</span><span class="sxs-lookup"><span data-stu-id="fb3c8-205">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
