---
title: Clientversionsregel
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientCVPolicyRuleEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 6e7e94c2-1475-4334-b8da-716b24a4c255
ROBOTS: NOINDEX, NOFOLLOW
description: Eine Clientversionsrichtlinie besteht aus einer Gruppe von Clientversionsregeln. Mit diesen Regeln werden die Aktionen definiert, die ausgeführt werden sollen, wenn Benutzer sich mit bestimmten Clients und Clientversionen anmelden möchten.
ms.openlocfilehash: a4d8cb38f30e8c332a9cec0ea90e27c012187d47
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794594"
---
# <a name="client-version-rule"></a><span data-ttu-id="6fb5b-104">Clientversionsregel</span><span class="sxs-lookup"><span data-stu-id="6fb5b-104">Client Version Rule</span></span>

<span data-ttu-id="6fb5b-p102">Eine Clientversionsrichtlinie besteht aus einer Gruppe von Clientversionsregeln. Mit diesen Regeln werden die Aktionen definiert, die ausgeführt werden sollen, wenn Benutzer sich mit bestimmten Clients und Clientversionen anmelden möchten.</span><span class="sxs-lookup"><span data-stu-id="6fb5b-p102">A client version policy is made up of a set of client version rules. These rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="6fb5b-107">Mögliche Aufgaben</span><span class="sxs-lookup"><span data-stu-id="6fb5b-107">Tasks you can perform</span></span>

<span data-ttu-id="6fb5b-108">Auf der Seite **Neue Clientversionskonfiguration erstellen** oder **Clientversionskonfiguration bearbeiten** können Sie die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="6fb5b-108">You can perform the following tasks on the **New Client Version Configuration** or **Edit Client Version Configuration** page:</span></span>

- <span data-ttu-id="6fb5b-109">Hinzufügen neuer Regeln zu einer Clientversionsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="6fb5b-109">Add new rules to a client version policy.</span></span>

- <span data-ttu-id="6fb5b-110">Ändern der Regeln, aus denen eine vorhandene Clientversionsrichtlinie besteht</span><span class="sxs-lookup"><span data-stu-id="6fb5b-110">Modify the rules that make up an existing client version policy</span></span>

## <a name="ui-reference"></a><span data-ttu-id="6fb5b-111">Referenz zur Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="6fb5b-111">UI Reference</span></span>

<span data-ttu-id="6fb5b-112">In den folgenden Listen werden die Menüs, Befehle, Felder und Eigenschaften der Seite beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6fb5b-112">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="6fb5b-113">**Benutzer-Agent** Sie können einen Clienttyp aus der Liste auswählen.</span><span class="sxs-lookup"><span data-stu-id="6fb5b-113">**User agent** You can select a client type from the list.</span></span> <span data-ttu-id="6fb5b-114">In der folgenden Tabelle sind die Codes der Benutzer-Agents definiert.</span><span class="sxs-lookup"><span data-stu-id="6fb5b-114">The following table defines user agent codes.</span></span> <span data-ttu-id="6fb5b-115">Diese Liste enthält Legacyclient Typen, die teilweise nicht mehr unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="6fb5b-115">This list includes legacy client types, some of which are no longer supported.</span></span>

|<span data-ttu-id="6fb5b-116">**Clientname**</span><span class="sxs-lookup"><span data-stu-id="6fb5b-116">**Client Name**</span></span>|<span data-ttu-id="6fb5b-117">**Benutzer-Agent**</span><span class="sxs-lookup"><span data-stu-id="6fb5b-117">**User Agent**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6fb5b-118">Lync 2013, lync 2010, Office Communicator</span><span class="sxs-lookup"><span data-stu-id="6fb5b-118">Lync 2013, Lync 2010, Office Communicator</span></span>  <br/> |<span data-ttu-id="6fb5b-119">OC</span><span class="sxs-lookup"><span data-stu-id="6fb5b-119">OC</span></span>  <br/> |
|<span data-ttu-id="6fb5b-120">Lync Web App, Communicator Web Access</span><span class="sxs-lookup"><span data-stu-id="6fb5b-120">Lync Web App, Communicator Web Access</span></span>  <br/> |<span data-ttu-id="6fb5b-121">CWA</span><span class="sxs-lookup"><span data-stu-id="6fb5b-121">CWA</span></span>  <br/> |
|<span data-ttu-id="6fb5b-122">Lync Phone Edition, Office Communicator Phone</span><span class="sxs-lookup"><span data-stu-id="6fb5b-122">Lync Phone Edition, Office Communicator Phone</span></span>  <br/> |<span data-ttu-id="6fb5b-123">OCPhone</span><span class="sxs-lookup"><span data-stu-id="6fb5b-123">OCPhone</span></span>  <br/> |
|<span data-ttu-id="6fb5b-124">Communicator Phone Edition-Plattform</span><span class="sxs-lookup"><span data-stu-id="6fb5b-124">Communicator Phone Edition Platform</span></span>  <br/> |<span data-ttu-id="6fb5b-125">CPE</span><span class="sxs-lookup"><span data-stu-id="6fb5b-125">CPE</span></span>  <br/> |
|<span data-ttu-id="6fb5b-126">Unified Communications-Plattform</span><span class="sxs-lookup"><span data-stu-id="6fb5b-126">Unified Communications Platform</span></span>  <br/> |<span data-ttu-id="6fb5b-127">UCCP</span><span class="sxs-lookup"><span data-stu-id="6fb5b-127">UCCP</span></span>  <br/> |
|<span data-ttu-id="6fb5b-128">Lync 2010-Teilnehmer</span><span class="sxs-lookup"><span data-stu-id="6fb5b-128">Lync 2010 Attendee</span></span>  <br/> |<span data-ttu-id="6fb5b-129">AOC</span><span class="sxs-lookup"><span data-stu-id="6fb5b-129">AOC</span></span>  <br/> |
|<span data-ttu-id="6fb5b-130">Live Meeting-Add-In</span><span class="sxs-lookup"><span data-stu-id="6fb5b-130">Live Meeting Add-In</span></span>  <br/> |<span data-ttu-id="6fb5b-131">LiveMeetingAddins</span><span class="sxs-lookup"><span data-stu-id="6fb5b-131">LiveMeetingAddins</span></span>  <br/> |
|<span data-ttu-id="6fb5b-132">Office Live Meeting</span><span class="sxs-lookup"><span data-stu-id="6fb5b-132">Office Live Meeting</span></span>  <br/> |<span data-ttu-id="6fb5b-133">LMC</span><span class="sxs-lookup"><span data-stu-id="6fb5b-133">LMC</span></span>  <br/> |
|<span data-ttu-id="6fb5b-134">Windows Messenger</span><span class="sxs-lookup"><span data-stu-id="6fb5b-134">Windows Messenger</span></span>  <br/> |<span data-ttu-id="6fb5b-135">WM</span><span class="sxs-lookup"><span data-stu-id="6fb5b-135">WM</span></span>  <br/> |
|<span data-ttu-id="6fb5b-136">Client für Real-Time Communications</span><span class="sxs-lookup"><span data-stu-id="6fb5b-136">Real-time Communications Client</span></span>  <br/> |<span data-ttu-id="6fb5b-137">RTC</span><span class="sxs-lookup"><span data-stu-id="6fb5b-137">RTC</span></span>  <br/> |
|<span data-ttu-id="6fb5b-138">Lync 2010 für iPad</span><span class="sxs-lookup"><span data-stu-id="6fb5b-138">Lync 2010 for iPad</span></span>  <br/> |<span data-ttu-id="6fb5b-139">iPadLync</span><span class="sxs-lookup"><span data-stu-id="6fb5b-139">iPadLync</span></span>  <br/> |
|<span data-ttu-id="6fb5b-140">Lync 2010 für iPhone</span><span class="sxs-lookup"><span data-stu-id="6fb5b-140">Lync 2010 for iPhone</span></span>  <br/> |<span data-ttu-id="6fb5b-141">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="6fb5b-141">iPhoneLync</span></span>  <br/> |
|<span data-ttu-id="6fb5b-142">Lync 2010 für Windows Phone</span><span class="sxs-lookup"><span data-stu-id="6fb5b-142">Lync 2010 for Windows Phone</span></span>  <br/> |<span data-ttu-id="6fb5b-143">WPLync</span><span class="sxs-lookup"><span data-stu-id="6fb5b-143">WPLync</span></span>  <br/> |
|<span data-ttu-id="6fb5b-144">Lync 2010 für Nokia</span><span class="sxs-lookup"><span data-stu-id="6fb5b-144">Lync 2010 for Nokia</span></span>  <br/> |<span data-ttu-id="6fb5b-145">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="6fb5b-145">NokiaLync</span></span>  <br/> |
|<span data-ttu-id="6fb5b-146">Lync 2010 für Android</span><span class="sxs-lookup"><span data-stu-id="6fb5b-146">Lync 2010 for Android</span></span>  <br/> |<span data-ttu-id="6fb5b-147">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="6fb5b-147">AndroidLync</span></span>  <br/> |
|<span data-ttu-id="6fb5b-148">Mobilitätsdienst</span><span class="sxs-lookup"><span data-stu-id="6fb5b-148">Mobility service</span></span>  <br/> |<span data-ttu-id="6fb5b-149">McxService</span><span class="sxs-lookup"><span data-stu-id="6fb5b-149">McxService</span></span>  <br/> |

- <span data-ttu-id="6fb5b-150">**Versionsnummer** Sie können die Versionsnummern für die folgenden Felder angeben oder Platzhalter verwenden, um die Versionsnummer des Clients anzugeben.</span><span class="sxs-lookup"><span data-stu-id="6fb5b-150">**Version number** You can specify the version numbers for the following fields, or use wildcards to indicate the client version number.</span></span>

  - <span data-ttu-id="6fb5b-151">**Hauptversion** Gibt die Nummer an, die der Hauptversion des Clients entspricht.</span><span class="sxs-lookup"><span data-stu-id="6fb5b-151">**Major version** Specifies the number that corresponds to the major release of the client.</span></span>

  - <span data-ttu-id="6fb5b-152">**Nebenversion** Gibt die Nummer an, die der Nebenversion des Clients entspricht.</span><span class="sxs-lookup"><span data-stu-id="6fb5b-152">**Minor version** Specifies the number that corresponds to the minor release of the client.</span></span>

  - <span data-ttu-id="6fb5b-153">**Erstellen** Gibt die Buildnummer an, die der Haupt-und Nebenversion des Clients entspricht.</span><span class="sxs-lookup"><span data-stu-id="6fb5b-153">**Build** Specifies the build number that corresponds to the major and minor release of the client.</span></span>

  - <span data-ttu-id="6fb5b-154">**Update** Gibt die Nummer an, die der aktualisierten Version des Clients entspricht.</span><span class="sxs-lookup"><span data-stu-id="6fb5b-154">**Update** Specifies the number that corresponds to the updated release of the client.</span></span>

- <span data-ttu-id="6fb5b-155">**Vergleichsvorgang** Sie können den übereinstimmenden Vorgang für die Client Version angeben, die Sie in den vorherigen Schritten angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="6fb5b-155">**Comparison operation** You can specify the matching operation for the client version you specified in the preceding steps.</span></span> <span data-ttu-id="6fb5b-156">Die folgenden Vorgänge sind verfügbar:</span><span class="sxs-lookup"><span data-stu-id="6fb5b-156">The following operations are available:</span></span>

  - <span data-ttu-id="6fb5b-157">**Identisch mit**</span><span class="sxs-lookup"><span data-stu-id="6fb5b-157">**Same as**</span></span>

  - <span data-ttu-id="6fb5b-158">**Ist nicht**</span><span class="sxs-lookup"><span data-stu-id="6fb5b-158">**Is not**</span></span>

  - <span data-ttu-id="6fb5b-159">**Neuer als**</span><span class="sxs-lookup"><span data-stu-id="6fb5b-159">**Newer than**</span></span>

  - <span data-ttu-id="6fb5b-160">**Neuer als oder identisch mit**</span><span class="sxs-lookup"><span data-stu-id="6fb5b-160">**Newer than or same as**</span></span>

  - <span data-ttu-id="6fb5b-161">**Älter als**</span><span class="sxs-lookup"><span data-stu-id="6fb5b-161">**Older than**</span></span>

  - <span data-ttu-id="6fb5b-162">**Älter als oder identisch mit**</span><span class="sxs-lookup"><span data-stu-id="6fb5b-162">**Older than or same as**</span></span>

- <span data-ttu-id="6fb5b-163">**Aktion** Sie können die Aktion angeben, die ausgeführt werden soll, wenn die Kriterien in den vorherigen Schritten erfüllt sind.</span><span class="sxs-lookup"><span data-stu-id="6fb5b-163">**Action** You can specify the action to perform when the criteria in the preceding steps are met.</span></span> <span data-ttu-id="6fb5b-164">Die folgenden Aktionen sind verfügbar:</span><span class="sxs-lookup"><span data-stu-id="6fb5b-164">The following actions are available:</span></span>

  - <span data-ttu-id="6fb5b-165">**Zulassen** Ermöglicht es dem Client, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="6fb5b-165">**Allow** Allows the client to log on.</span></span>

  - <span data-ttu-id="6fb5b-166">**Zulassen und aktualisieren** Ermöglicht es dem Client, sich anzumelden und Updates vom Windows Server Update-Dienst oder Microsoft Update zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="6fb5b-166">**Allow and Upgrade** Allows the client to log on and receive updates from Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="6fb5b-167">Diese Aktion ist nur verfügbar, wenn der Benutzer-Agent **OC** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="6fb5b-167">This action is available only when user agent **OC** is selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6fb5b-168">Wenn Sie diese Aktion auswählen, wird eine Benachrichtigung angezeigt, wenn sich die Benutzer das nächste Mal bei Skype for Business anmelden.</span><span class="sxs-lookup"><span data-stu-id="6fb5b-168">Selecting this action causes a notification to appear the next time users sign in to Skype for Business.</span></span> <span data-ttu-id="6fb5b-169">Die Benachrichtigung weist darauf hin, dass ein Update verfügbar ist, selbst wenn etwaige Updates noch nicht in Windows Server Update Service oder Microsoft Update veröffentlicht wurden.</span><span class="sxs-lookup"><span data-stu-id="6fb5b-169">The notification states that an update is available, even if updates have not yet been released to Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="6fb5b-170">Um Unklarheiten zu vermeiden, sollten Sie diese Aktion erst dann auswählen, wenn Updates verfügbar gemacht wurden.</span><span class="sxs-lookup"><span data-stu-id="6fb5b-170">To avoid confusion, you should choose this action only after updates become available.</span></span>

  - <span data-ttu-id="6fb5b-171">**Mit URL zulassen** Ermöglicht es dem Client, sich anzumelden und eine Meldung darüber anzuzeigen, wo eine andere Client Version heruntergeladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="6fb5b-171">**Allow with URL** Allows the client to log on and displays a message about where to download another client version.</span></span> <span data-ttu-id="6fb5b-172">Sie geben die URL im Feld **URL** an.</span><span class="sxs-lookup"><span data-stu-id="6fb5b-172">You specify the URL in the **URL** field.</span></span>

  - <span data-ttu-id="6fb5b-173">**Blockieren** Verhindert, dass der Client sich anmeldet.</span><span class="sxs-lookup"><span data-stu-id="6fb5b-173">**Block** Prevents the client from logging on.</span></span>

  - <span data-ttu-id="6fb5b-174">**Blockieren und aktualisieren** Verhindert, dass der Client sich anmeldet und dem Client ermöglicht, Updates vom Windows Server Update-Dienst oder Microsoft Update zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="6fb5b-174">**Block and Upgrade** Prevents the client from logging on and allows the client to receive updates from Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="6fb5b-175">Diese Aktion ist nur verfügbar, wenn der Benutzer-Agent **OC** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="6fb5b-175">This action is available only when user agent **OC** is selected.</span></span>

  - <span data-ttu-id="6fb5b-p110">**Mit URL blockieren**   Verhindert die Anmeldung des Clients und zeigt eine Meldung an, wo eine andere Clientversion heruntergeladen werden kann. Sie geben die URL im Feld **URL** an.</span><span class="sxs-lookup"><span data-stu-id="6fb5b-p110">**Block with URL** prevents the client from logging on and displays a message about where to download another client version. You specify the URL in the **URL** field.</span></span>

<span data-ttu-id="6fb5b-178">Details zur Interoperabilität zwischen Clients und Clientversionen finden Sie unter [Client Interoperabilität](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="6fb5b-178">For details about interoperability among clients and client versions, see [Client Interoperability](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="6fb5b-179">Ausführliche Informationen zur Verwendung von Clientversionskonfigurationen finden Sie in der Betriebsdokumentation unter [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx).</span><span class="sxs-lookup"><span data-stu-id="6fb5b-179">For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>

