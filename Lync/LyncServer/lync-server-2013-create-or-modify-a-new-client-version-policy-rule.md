---
title: 'Lync Server 2013: Erstellen oder Ändern einer neuen Richtlinienregel für Clientversionen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a new client version policy rule
ms:assetid: 6f879d99-8401-41e0-a562-195c890d63ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898478(v=OCS.15)
ms:contentKeyID: 50873758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 442341c51ef6477f72fb9e88cdea5fe7fc527aa8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722445"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-new-client-version-policy-rule-in-lync-server-2013"></a><span data-ttu-id="a41f3-102">Erstellen oder Ändern einer neuen Richtlinienregel für Clientversionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a41f3-102">Create or modify a new client version policy rule in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a41f3-103">_**Letztes Änderungsdatum des Themas:** 2013-01-21_</span><span class="sxs-lookup"><span data-stu-id="a41f3-103">_**Topic Last Modified:** 2013-01-21_</span></span>

<span data-ttu-id="a41f3-104">Client Versionsrichtlinien Regeln definieren die Aktionen, die ausgeführt werden sollen, wenn Benutzer versuchen, sich mit bestimmten Clients und Clientversionen anzumelden.</span><span class="sxs-lookup"><span data-stu-id="a41f3-104">Client version policy rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span> <span data-ttu-id="a41f3-105">Sie können in der lync Server 2013-Systemsteuerung einzelne Regeln für eine clientversionsrichtlinie erstellen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="a41f3-105">You can create or modify individual rules for a client version policy from Lync Server 2013 Control Panel.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a41f3-106">Regeln werden in der Reihenfolge der Rangfolge aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="a41f3-106">Rules are listed in order of precedence.</span></span> <span data-ttu-id="a41f3-107">Wenn Sie beispielsweise über eine Regel verfügen, mit der Clients, auf denen Version 1,5 ausgeführt wird, eine Verbindung herstellen können, gefolgt von einer Regel, die Clients mit einer älteren Version als 2,0 blockiert, hat die erste Regel Vorrang, und Clients, auf denen Version 1,5 ausgeführt wird, können eine Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="a41f3-107">For example, if you have a rule that allows clients running version 1.5 to connect, followed by a rule that blocks clients running a version earlier than 2.0, the first rule takes precedence, and clients running version 1.5 are allowed to connect.</span></span>



</div>

<div>

## <a name="to-create-or-modify-client-version-policy-rules-with-lync-server-control-panel"></a><span data-ttu-id="a41f3-108">So erstellen oder ändern Sie clientversionsrichtlinien Regeln mit der lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="a41f3-108">To create or modify client version policy rules with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="a41f3-109">[Erstellen oder Ändern einer neuen clientversionsrichtlinie in lync Server 2013](lync-server-2013-create-or-modify-a-new-client-version-policy.md) mit der lync Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="a41f3-109">[Create or modify a new client version policy in Lync Server 2013](lync-server-2013-create-or-modify-a-new-client-version-policy.md) with Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="a41f3-110">Führen Sie auf der Seite **Client-Versionsrichtlinie bearbeiten** eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="a41f3-110">On the **Edit Client Version Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="a41f3-111">Klicken Sie auf **neu** , um eine neue clientversionsregel zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a41f3-111">Click **New** to create a new client version rule.</span></span>
    
      - <span data-ttu-id="a41f3-112">Klicken Sie in der Liste auf einen der definierten Clienttypen, und klicken Sie dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="a41f3-112">Click one of the defined client types in the list, and then click **Show details**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a41f3-113">Sie können Platzhalter zum Angeben des Clienttyps verwenden.</span><span class="sxs-lookup"><span data-stu-id="a41f3-113">You can use wildcards to indicate the client type.</span></span>

    
    </div>

3.  <span data-ttu-id="a41f3-114">Wählen Sie im **Benutzer-Agent**einen Clienttyp aus.</span><span class="sxs-lookup"><span data-stu-id="a41f3-114">In **User agent**, select a client type.</span></span>

4.  <span data-ttu-id="a41f3-115">Führen Sie unter **Versionsnummer**die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="a41f3-115">Under **Version number**, do the following:</span></span>
    
      - <span data-ttu-id="a41f3-116">Geben Sie in der **Hauptversion**die Nummer ein, die der Hauptversion des Clients entspricht.</span><span class="sxs-lookup"><span data-stu-id="a41f3-116">In **Major version**, type the number that corresponds to the major release of the client.</span></span>
    
      - <span data-ttu-id="a41f3-117">Geben Sie in der **Nebenversion**die Zahl ein, die der Nebenversion des Clients entspricht.</span><span class="sxs-lookup"><span data-stu-id="a41f3-117">In **Minor version**, type the number that corresponds to the minor release of the client.</span></span>
    
      - <span data-ttu-id="a41f3-118">Geben Sie in **Build**die Zahl ein, die der Haupt-und Nebenversion des Clients entspricht.</span><span class="sxs-lookup"><span data-stu-id="a41f3-118">In **Build**, type the number that corresponds to the major and minor release of the client.</span></span>
    
      - <span data-ttu-id="a41f3-119">Geben Sie in **Update**die Nummer ein, die der aktualisierten Version des Clients entspricht.</span><span class="sxs-lookup"><span data-stu-id="a41f3-119">In **Update**, type the number that corresponds to the updated release of the client.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a41f3-120">Sie können Platzhalter verwenden, um die Versionsnummer des Clients anzugeben.</span><span class="sxs-lookup"><span data-stu-id="a41f3-120">You can use wildcards to indicate the client version number.</span></span>

    
    </div>

5.  <span data-ttu-id="a41f3-121">Wenn Sie den übereinstimmenden Vorgang für die Client Version angeben möchten, die Sie in den vorherigen Schritten angegeben haben, klicken Sie im **Vergleichsvorgang**auf eine der folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="a41f3-121">To specify the matching operation for the client version you specified in the preceding steps, in **Comparison operation**, click one of the following:</span></span>
    
      - <span data-ttu-id="a41f3-122">**Identisch mit**</span><span class="sxs-lookup"><span data-stu-id="a41f3-122">**Same as**</span></span>
    
      - <span data-ttu-id="a41f3-123">**Ist nicht**</span><span class="sxs-lookup"><span data-stu-id="a41f3-123">**Is not**</span></span>
    
      - <span data-ttu-id="a41f3-124">**Neuer als**</span><span class="sxs-lookup"><span data-stu-id="a41f3-124">**Newer than**</span></span>
    
      - <span data-ttu-id="a41f3-125">**Neuer als oder identisch mit**</span><span class="sxs-lookup"><span data-stu-id="a41f3-125">**Newer than or same as**</span></span>
    
      - <span data-ttu-id="a41f3-126">**Älter als**</span><span class="sxs-lookup"><span data-stu-id="a41f3-126">**Older than**</span></span>
    
      - <span data-ttu-id="a41f3-127">**Älter als oder identisch mit**</span><span class="sxs-lookup"><span data-stu-id="a41f3-127">**Older than or same as**</span></span>

6.  <span data-ttu-id="a41f3-128">Wenn Sie die Aktion angeben möchten, die ausgeführt werden soll, wenn die Kriterien in den vorherigen Schritten erfüllt sind, klicken Sie in **Aktion**auf eine der folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="a41f3-128">To specify the action to perform when the criteria in the preceding steps are met, click one of the following in **Action**:</span></span>
    
      - <span data-ttu-id="a41f3-129">Klicken Sie auf **zulassen**, damit sich der Client anmelden kann.</span><span class="sxs-lookup"><span data-stu-id="a41f3-129">To allow the client to log on, click **Allow**.</span></span>
    
      - <span data-ttu-id="a41f3-130">Wenn Sie zulassen möchten, dass der Client sich beim Windows Server Update-Dienst oder Microsoft Update anmeldet und Updates erhält, klicken Sie auf **zulassen und aktualisieren**.</span><span class="sxs-lookup"><span data-stu-id="a41f3-130">To allow the client to log on and receive updates from Windows Server Update Service or Microsoft Update, click **Allow and Upgrade**.</span></span> <span data-ttu-id="a41f3-131">Diese Aktion ist nur verfügbar, wenn der Benutzer-Agent **OC** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="a41f3-131">This action is available only when user agent **OC** is selected.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a41f3-132">Wenn Sie diese Aktion auswählen, wird eine Benachrichtigung angezeigt, wenn sich die Benutzer das nächste Mal bei lync 2013 anmelden.</span><span class="sxs-lookup"><span data-stu-id="a41f3-132">Selecting this action causes a notification to appear the next time users sign in to Lync 2013.</span></span> <span data-ttu-id="a41f3-133">Die Benachrichtigung weist darauf hin, dass ein Update verfügbar ist, selbst wenn etwaige Updates noch nicht in Windows Server Update Service oder Microsoft Update veröffentlicht wurden.</span><span class="sxs-lookup"><span data-stu-id="a41f3-133">The notification states that an update is available, even if updates have not yet been released to Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="a41f3-134">Um Unklarheiten zu vermeiden, sollten Sie diese Aktion erst dann auswählen, wenn Updates verfügbar gemacht wurden.</span><span class="sxs-lookup"><span data-stu-id="a41f3-134">To avoid confusion, you should choose this action only after updates become available.</span></span>

        
        </div>
    
      - <span data-ttu-id="a41f3-135">Klicken Sie auf **Allow with URL**, damit der Client sich anmelden und eine Meldung darüber anzeigen kann, wo eine andere Client Version heruntergeladen werden kann.</span><span class="sxs-lookup"><span data-stu-id="a41f3-135">To allow the client to log on and display a message about where to download another client version, click **Allow with URL**.</span></span> <span data-ttu-id="a41f3-136">Sie geben die URL später in diesem Verfahren an.</span><span class="sxs-lookup"><span data-stu-id="a41f3-136">You specify the URL later in this procedure.</span></span>
    
      - <span data-ttu-id="a41f3-137">Klicken Sie auf **blockieren**, um zu verhindern, dass der Client sich anmeldet.</span><span class="sxs-lookup"><span data-stu-id="a41f3-137">To prevent the client from logging on, click **Block**.</span></span>
    
      - <span data-ttu-id="a41f3-138">Klicken Sie auf **blockieren und aktualisieren**, um zu verhindern, dass der Client sich anmeldet und dem Client das Empfangen von Updates vom Windows Server Update-Dienst oder Microsoft Update ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="a41f3-138">To prevent the client from logging on and allow the client to receive updates from Windows Server Update Service or Microsoft Update, click **Block and Upgrade**.</span></span> <span data-ttu-id="a41f3-139">Diese Aktion ist nur verfügbar, wenn der Benutzer-Agent **OC** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="a41f3-139">This action is available only when user agent **OC** is selected.</span></span>
    
      - <span data-ttu-id="a41f3-140">Wenn Sie verhindern möchten, dass der Client sich anmeldet und eine Meldung darüber anzeigt, wo eine andere Client Version heruntergeladen werden soll, klicken Sie auf **mit URL blockieren**.</span><span class="sxs-lookup"><span data-stu-id="a41f3-140">To prevent the client from logging on and display a message about where to download another client version, click **Block with URL**.</span></span> <span data-ttu-id="a41f3-141">Sie geben die URL später in diesem Verfahren an.</span><span class="sxs-lookup"><span data-stu-id="a41f3-141">You specify the URL later in this procedure.</span></span>

7.  <span data-ttu-id="a41f3-142">Optional Wenn Sie im vorherigen Schritt auf **Allow with URL** oder **Block with URL** geklickt haben, geben Sie die Client Download-URL ein, die in die Nachricht in **URL**aufgenommen werden soll.</span><span class="sxs-lookup"><span data-stu-id="a41f3-142">(Optional) If you clicked **Allow with URL** or **Block with URL** in the previous step, type the client download URL to include in the message in **URL**.</span></span>

8.  <span data-ttu-id="a41f3-143">Klicken Sie auf **OK**und dann auf **Commit**.</span><span class="sxs-lookup"><span data-stu-id="a41f3-143">Click **OK**, and then click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

