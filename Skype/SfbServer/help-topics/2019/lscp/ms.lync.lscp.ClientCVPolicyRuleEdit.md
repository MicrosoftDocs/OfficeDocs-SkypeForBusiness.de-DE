---
title: Clientversionsregel
ms.author: dianef
author: dianef77
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVPolicyRuleEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6e7e94c2-1475-4334-b8da-716b24a4c255
description: Eine Clientversionsrichtlinie besteht aus einer Gruppe von Clientversionsregeln. Mit diesen Regeln werden die Aktionen definiert, die ausgeführt werden sollen, wenn Benutzer sich mit bestimmten Clients und Clientversionen anmelden möchten.
ms.openlocfilehash: 8f2e969b2724ed1239f7531bd4be03552be9039b
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/21/2018
ms.locfileid: "19991501"
---
# <a name="client-version-rule"></a><span data-ttu-id="2462a-104">Clientversionsregel</span><span class="sxs-lookup"><span data-stu-id="2462a-104">Client Version Rule</span></span>
 
<span data-ttu-id="2462a-p102">Eine Clientversionsrichtlinie besteht aus einer Gruppe von Clientversionsregeln. Mit diesen Regeln werden die Aktionen definiert, die ausgeführt werden sollen, wenn Benutzer sich mit bestimmten Clients und Clientversionen anmelden möchten.</span><span class="sxs-lookup"><span data-stu-id="2462a-p102">A client version policy is made up of a set of client version rules. These rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="2462a-107">Mögliche Aufgaben</span><span class="sxs-lookup"><span data-stu-id="2462a-107">Tasks you can perform</span></span>

<span data-ttu-id="2462a-108">Auf der Seite **Neue Clientversionskonfiguration erstellen** oder **Clientversionskonfiguration bearbeiten** können Sie die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="2462a-108">You can perform the following tasks on the **New Client Version Configuration** or **Edit Client Version Configuration** page:</span></span>
  
- <span data-ttu-id="2462a-109">Hinzufügen neuer Regeln zu einer Clientversionsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="2462a-109">Add new rules to a client version policy.</span></span>
    
- <span data-ttu-id="2462a-110">Ändern der Regeln, aus denen eine vorhandene Clientversionsrichtlinie besteht</span><span class="sxs-lookup"><span data-stu-id="2462a-110">Modify the rules that make up an existing client version policy</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="2462a-111">Referenz zur Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="2462a-111">UI Reference</span></span>

<span data-ttu-id="2462a-112">In den folgenden Listen werden die Menüs, Befehle, Felder und Eigenschaften der Seite beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2462a-112">The following lists describe the menus, command, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="2462a-113">**Benutzer-agent** Sie können einen Clienttyp aus der Liste auswählen.</span><span class="sxs-lookup"><span data-stu-id="2462a-113">**User agent** You can select a client type from the list.</span></span> <span data-ttu-id="2462a-114">In der folgenden Tabelle sind die Codes der Benutzer-Agents definiert.</span><span class="sxs-lookup"><span data-stu-id="2462a-114">The following table defines user agent codes.</span></span>
    
|<span data-ttu-id="2462a-115">**Clientname**</span><span class="sxs-lookup"><span data-stu-id="2462a-115">**Client Name**</span></span>|<span data-ttu-id="2462a-116">**Benutzer-Agent**</span><span class="sxs-lookup"><span data-stu-id="2462a-116">**User Agent**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2462a-117">Lync 2013, Lync 2010, Officecommunicator</span><span class="sxs-lookup"><span data-stu-id="2462a-117">Lync 2013, Lync 2010, Office Communicator</span></span>  <br/> |<span data-ttu-id="2462a-118">OC</span><span class="sxs-lookup"><span data-stu-id="2462a-118">OC</span></span>  <br/> |
|<span data-ttu-id="2462a-119">Lync Web App, Communicator Web Access</span><span class="sxs-lookup"><span data-stu-id="2462a-119">Lync Web App, Communicator Web Access</span></span>  <br/> |<span data-ttu-id="2462a-120">CWA</span><span class="sxs-lookup"><span data-stu-id="2462a-120">CWA</span></span>  <br/> |
|<span data-ttu-id="2462a-121">Office Communicator Phone Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="2462a-121">Lync Phone Edition, Office Communicator Phone</span></span>  <br/> |<span data-ttu-id="2462a-122">OCPhone</span><span class="sxs-lookup"><span data-stu-id="2462a-122">OCPhone</span></span>  <br/> |
|<span data-ttu-id="2462a-123">Communicator Phone Edition-Plattform</span><span class="sxs-lookup"><span data-stu-id="2462a-123">Communicator Phone Edition Platform</span></span>  <br/> |<span data-ttu-id="2462a-124">CPE</span><span class="sxs-lookup"><span data-stu-id="2462a-124">CPE</span></span>  <br/> |
|<span data-ttu-id="2462a-125">Unified Communications-Plattform</span><span class="sxs-lookup"><span data-stu-id="2462a-125">Unified Communications Platform</span></span>  <br/> |<span data-ttu-id="2462a-126">UCCP</span><span class="sxs-lookup"><span data-stu-id="2462a-126">UCCP</span></span>  <br/> |
|<span data-ttu-id="2462a-127">Lync 2010-Teilnehmer</span><span class="sxs-lookup"><span data-stu-id="2462a-127">Lync 2010 Attendee</span></span>  <br/> |<span data-ttu-id="2462a-128">AOC</span><span class="sxs-lookup"><span data-stu-id="2462a-128">AOC</span></span>  <br/> |
|<span data-ttu-id="2462a-129">Live Meeting-Add-In</span><span class="sxs-lookup"><span data-stu-id="2462a-129">Live Meeting Add-In</span></span>  <br/> |<span data-ttu-id="2462a-130">LiveMeetingAddins</span><span class="sxs-lookup"><span data-stu-id="2462a-130">LiveMeetingAddins</span></span>  <br/> |
|<span data-ttu-id="2462a-131">Office Live Meeting</span><span class="sxs-lookup"><span data-stu-id="2462a-131">Office Live Meeting</span></span>  <br/> |<span data-ttu-id="2462a-132">LMC</span><span class="sxs-lookup"><span data-stu-id="2462a-132">LMC</span></span>  <br/> |
|<span data-ttu-id="2462a-133">Windows Messenger</span><span class="sxs-lookup"><span data-stu-id="2462a-133">Windows Messenger</span></span>  <br/> |<span data-ttu-id="2462a-134">WM</span><span class="sxs-lookup"><span data-stu-id="2462a-134">WM</span></span>  <br/> |
|<span data-ttu-id="2462a-135">Client für Real-Time Communications</span><span class="sxs-lookup"><span data-stu-id="2462a-135">Real-time Communications Client</span></span>  <br/> |<span data-ttu-id="2462a-136">RTC</span><span class="sxs-lookup"><span data-stu-id="2462a-136">RTC</span></span>  <br/> |
|<span data-ttu-id="2462a-137">Lync 2010 für iPad</span><span class="sxs-lookup"><span data-stu-id="2462a-137">Lync 2010 for iPad</span></span>  <br/> |<span data-ttu-id="2462a-138">iPadLync</span><span class="sxs-lookup"><span data-stu-id="2462a-138">iPadLync</span></span>  <br/> |
|<span data-ttu-id="2462a-139">Lync 2010 für iPhone</span><span class="sxs-lookup"><span data-stu-id="2462a-139">Lync 2010 for iPhone</span></span>  <br/> |<span data-ttu-id="2462a-140">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="2462a-140">iPhoneLync</span></span>  <br/> |
|<span data-ttu-id="2462a-141">Lync 2010 für Windows Phone</span><span class="sxs-lookup"><span data-stu-id="2462a-141">Lync 2010 for Windows Phone</span></span>  <br/> |<span data-ttu-id="2462a-142">WPLync</span><span class="sxs-lookup"><span data-stu-id="2462a-142">WPLync</span></span>  <br/> |
|<span data-ttu-id="2462a-143">Lync 2010 für Nokia</span><span class="sxs-lookup"><span data-stu-id="2462a-143">Lync 2010 for Nokia</span></span>  <br/> |<span data-ttu-id="2462a-144">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="2462a-144">NokiaLync</span></span>  <br/> |
|<span data-ttu-id="2462a-145">Lync 2010 für Android</span><span class="sxs-lookup"><span data-stu-id="2462a-145">Lync 2010 for Android</span></span>  <br/> |<span data-ttu-id="2462a-146">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="2462a-146">AndroidLync</span></span>  <br/> |
|<span data-ttu-id="2462a-147">Mobilitätsdienst</span><span class="sxs-lookup"><span data-stu-id="2462a-147">Mobility service</span></span>  <br/> |<span data-ttu-id="2462a-148">McxService</span><span class="sxs-lookup"><span data-stu-id="2462a-148">McxService</span></span>  <br/> |
   
- <span data-ttu-id="2462a-149">**Versionsnummer** Sie können die Versionsnummern für die folgenden Felder angeben oder Platzhalter verwenden, um die clientversionsnummer anzugeben.</span><span class="sxs-lookup"><span data-stu-id="2462a-149">**Version number** You can specify the version numbers for the following fields, or use wildcards to indicate the client version number.</span></span>
    
  - <span data-ttu-id="2462a-150">**Hauptversion** Gibt die Nummer, die der Hauptversion des Clients entspricht.</span><span class="sxs-lookup"><span data-stu-id="2462a-150">**Major version** Specifies the number that corresponds to the major release of the client.</span></span>
    
  - <span data-ttu-id="2462a-151">**Nebenversion** Gibt die Nummer, die der Nebenversion des Clients entspricht.</span><span class="sxs-lookup"><span data-stu-id="2462a-151">**Minor version** Specifies the number that corresponds to the minor release of the client.</span></span>
    
  - <span data-ttu-id="2462a-152">**Erstellen** Gibt die Buildnummer an, die der Haupt- und Nebenversion des Clients entspricht.</span><span class="sxs-lookup"><span data-stu-id="2462a-152">**Build** Specifies the build number that corresponds to the major and minor release of the client.</span></span>
    
  - <span data-ttu-id="2462a-153">**Update** Gibt die Nummer, die der aktualisierten Version des Clients entspricht.</span><span class="sxs-lookup"><span data-stu-id="2462a-153">**Update** Specifies the number that corresponds to the updated release of the client.</span></span>
    
- <span data-ttu-id="2462a-154">**Vergleichsvorgang** Sie können den Vergleichsvorgang für die Clientversion angeben, die Sie in den vorherigen Schritten angegeben.</span><span class="sxs-lookup"><span data-stu-id="2462a-154">**Comparison operation** You can specify the matching operation for the client version you specified in the preceding steps.</span></span> <span data-ttu-id="2462a-155">Die folgenden Vorgänge sind verfügbar:</span><span class="sxs-lookup"><span data-stu-id="2462a-155">The following operations are available:</span></span>
    
  - <span data-ttu-id="2462a-156">**Identisch mit**</span><span class="sxs-lookup"><span data-stu-id="2462a-156">**Same as**</span></span>
    
  - <span data-ttu-id="2462a-157">**Ist nicht**</span><span class="sxs-lookup"><span data-stu-id="2462a-157">**Is not**</span></span>
    
  - <span data-ttu-id="2462a-158">**Neuer als**</span><span class="sxs-lookup"><span data-stu-id="2462a-158">**Newer than**</span></span>
    
  - <span data-ttu-id="2462a-159">**Neuer als oder identisch mit**</span><span class="sxs-lookup"><span data-stu-id="2462a-159">**Newer than or same as**</span></span>
    
  - <span data-ttu-id="2462a-160">**Älter als**</span><span class="sxs-lookup"><span data-stu-id="2462a-160">**Older than**</span></span>
    
  - <span data-ttu-id="2462a-161">**Älter als oder identisch mit**</span><span class="sxs-lookup"><span data-stu-id="2462a-161">**Older than or same as**</span></span>
    
- <span data-ttu-id="2462a-162">**Aktion** Sie können angeben, dass die Aktion ausführen, wenn die Kriterien in den vorherigen Schritten erfüllt sind.</span><span class="sxs-lookup"><span data-stu-id="2462a-162">**Action** You can specify the action to perform when the criteria in the preceding steps are met.</span></span> <span data-ttu-id="2462a-163">Die folgenden Aktionen sind verfügbar:</span><span class="sxs-lookup"><span data-stu-id="2462a-163">The following actions are available:</span></span>
    
  - <span data-ttu-id="2462a-164">**Zulassen** Ermöglicht dem Client anmelden.</span><span class="sxs-lookup"><span data-stu-id="2462a-164">**Allow** Allows the client to log on.</span></span>
    
  - <span data-ttu-id="2462a-165">**Zulassen und Upgrade** Ermöglicht dem Client anmelden und Updates von Windows Server Update Service oder Microsoft Update zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="2462a-165">**Allow and Upgrade** Allows the client to log on and receive updates from Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="2462a-166">Diese Aktion ist nur verfügbar, wenn der Benutzer-Agent **OC** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="2462a-166">This action is available only when user agent **OC** is selected.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2462a-167">Wählen diese Aktion bewirkt, dass eine Benachrichtigung der Benutzer das nächste Mal Skype für Unternehmen anmelden angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="2462a-167">Selecting this action causes a notification to appear the next time users sign in to Skype for Business.</span></span> <span data-ttu-id="2462a-168">Die Benachrichtigung weist darauf hin, dass ein Update verfügbar ist, selbst wenn etwaige Updates noch nicht in Windows Server Update Service oder Microsoft Update veröffentlicht wurden.</span><span class="sxs-lookup"><span data-stu-id="2462a-168">The notification states that an update is available, even if updates have not yet been released to Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="2462a-169">Um Unklarheiten zu vermeiden, sollten Sie diese Aktion erst dann auswählen, wenn Updates verfügbar gemacht wurden.</span><span class="sxs-lookup"><span data-stu-id="2462a-169">To avoid confusion, you should choose this action only after updates become available.</span></span> 
  
  - <span data-ttu-id="2462a-170">**Mit URL zulassen** Erlaubt die Anmeldung des Clients und zeigt eine Meldung an, wo Sie ein anderes Clientversion herunterladen.</span><span class="sxs-lookup"><span data-stu-id="2462a-170">**Allow with URL** Allows the client to log on and displays a message about where to download another client version.</span></span> <span data-ttu-id="2462a-171">Sie geben die URL im Feld **URL** an.</span><span class="sxs-lookup"><span data-stu-id="2462a-171">You specify the URL in the **URL** field.</span></span>
    
  - <span data-ttu-id="2462a-172">**Blockieren** Verhindert die Anmeldung des Clients.</span><span class="sxs-lookup"><span data-stu-id="2462a-172">**Block** Prevents the client from logging on.</span></span>
    
  - <span data-ttu-id="2462a-173">**Blockieren und Upgrade** Verhindert die Clientanmeldung auf und ermöglicht den Client die Updates von Windows Server Update Service oder Microsoft Update zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="2462a-173">**Block and Upgrade** Prevents the client from logging on and allows the client to receive updates from Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="2462a-174">Diese Aktion ist nur verfügbar, wenn der Benutzer-Agent **OC** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="2462a-174">This action is available only when user agent **OC** is selected.</span></span>
    
  - <span data-ttu-id="2462a-p110">**Mit URL blockieren**   Verhindert die Anmeldung des Clients und zeigt eine Meldung an, wo eine andere Clientversion heruntergeladen werden kann. Sie geben die URL im Feld **URL** an.</span><span class="sxs-lookup"><span data-stu-id="2462a-p110">**Block with URL** prevents the client from logging on and displays a message about where to download another client version. You specify the URL in the **URL** field.</span></span>
    
<span data-ttu-id="2462a-177">Ausführliche Informationen zur Interoperabilität zwischen Clients und Clientversionen finden Sie unter [Client Interoperability](http://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="2462a-177">For details about interoperability among clients and client versions, see [Client Interoperability](http://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="2462a-178">Ausführliche Informationen zur Verwendung von clientversionskonfigurationen finden Sie unter [Ändern der Standardaktion für Clients nicht explizit unterstützt oder eingeschränkt](http://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="2462a-178">For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](http://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>

