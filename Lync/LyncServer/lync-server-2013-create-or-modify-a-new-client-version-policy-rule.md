---
title: 'Lync Server 2013: Erstellen oder Ändern einer neuen clientversionsrichtlinien Regel'
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
ms.openlocfilehash: 732113537b79ad2ac767f64b861f296be508899c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512722"
---
# <a name="create-or-modify-a-new-client-version-policy-rule-in-lync-server-2013"></a><span data-ttu-id="28f28-102">Erstellen oder Ändern einer neuen clientversionsrichtlinien Regel in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="28f28-102">Create or modify a new client version policy rule in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="28f28-103">_**Letztes Änderungsstand des Themas:** 2013-01-21_</span><span class="sxs-lookup"><span data-stu-id="28f28-103">_**Topic Last Modified:** 2013-01-21_</span></span>

<span data-ttu-id="28f28-104">Regeln für Client Versionsrichtlinien definieren die Aktionen, die ausgeführt werden sollten, wenn Benutzer versuchen, sich mit bestimmten Clients und Clientversionen anzumelden.</span><span class="sxs-lookup"><span data-stu-id="28f28-104">Client version policy rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span> <span data-ttu-id="28f28-105">Sie können in lync Server 2013 Systemsteuerung einzelne Regeln für eine clientversionsrichtlinie erstellen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="28f28-105">You can create or modify individual rules for a client version policy from Lync Server 2013 Control Panel.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="28f28-106">Regeln werden in der Reihenfolge ihrer Rangfolge aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="28f28-106">Rules are listed in order of precedence.</span></span> <span data-ttu-id="28f28-107">Wenn Sie beispielsweise über eine Regel verfügen, mit der Clients, auf denen Version 1,5 ausgeführt wird, eine Verbindung herstellen können, gefolgt von einer Regel, die verhindert, dass Clients eine ältere Version als 2,0 ausgeführt haben, hat die erste Regel Vorrang, und Clients, auf denen Version 1,5 ausgeführt wird, können eine Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="28f28-107">For example, if you have a rule that allows clients running version 1.5 to connect, followed by a rule that blocks clients running a version earlier than 2.0, the first rule takes precedence, and clients running version 1.5 are allowed to connect.</span></span>



</div>

<div>

## <a name="to-create-or-modify-client-version-policy-rules-with-lync-server-control-panel"></a><span data-ttu-id="28f28-108">So erstellen oder ändern Sie clientversionsrichtlinien Regeln mit lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="28f28-108">To create or modify client version policy rules with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="28f28-109">[Erstellen oder ändern Sie eine neue clientversionsrichtlinie in lync Server 2013](lync-server-2013-create-or-modify-a-new-client-version-policy.md) mit lync Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="28f28-109">[Create or modify a new client version policy in Lync Server 2013](lync-server-2013-create-or-modify-a-new-client-version-policy.md) with Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="28f28-110">Führen Sie auf der Seite **Client Versionsrichtlinie bearbeiten** eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="28f28-110">On the **Edit Client Version Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="28f28-111">Klicken Sie auf **Neu**, um eine neue Clientversionsrichtlinie zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="28f28-111">Click **New** to create a new client version rule.</span></span>
    
      - <span data-ttu-id="28f28-112">Klicken Sie auf einen der definierten Clienttypen in der Liste, und klicken Sie dann auf **Details einblenden**.</span><span class="sxs-lookup"><span data-stu-id="28f28-112">Click one of the defined client types in the list, and then click **Show details**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="28f28-113">Sie können den Clienttyp mithilfe von Platzhalterzeichen angeben.</span><span class="sxs-lookup"><span data-stu-id="28f28-113">You can use wildcards to indicate the client type.</span></span>

    
    </div>

3.  <span data-ttu-id="28f28-114">Wählen Sie unter **Benutzer-Agent** einen Clienttyp aus.</span><span class="sxs-lookup"><span data-stu-id="28f28-114">In **User agent**, select a client type.</span></span>

4.  <span data-ttu-id="28f28-115">Führen Sie unter **Versionsnummer** die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="28f28-115">Under **Version number**, do the following:</span></span>
    
      - <span data-ttu-id="28f28-116">Geben Sie in **Hauptversion** die Nummer ein, die der Hauptversion des Clients entspricht.</span><span class="sxs-lookup"><span data-stu-id="28f28-116">In **Major version**, type the number that corresponds to the major release of the client.</span></span>
    
      - <span data-ttu-id="28f28-117">Geben Sie in **Nebenversion** die Nummer ein, die der Nebenversion des Clients entspricht.</span><span class="sxs-lookup"><span data-stu-id="28f28-117">In **Minor version**, type the number that corresponds to the minor release of the client.</span></span>
    
      - <span data-ttu-id="28f28-118">Geben Sie in **Build** die Nummer ein, die der Haupt- und Nebenversion des Clients entspricht.</span><span class="sxs-lookup"><span data-stu-id="28f28-118">In **Build**, type the number that corresponds to the major and minor release of the client.</span></span>
    
      - <span data-ttu-id="28f28-119">Geben Sie in **Update** die Nummer ein, die der aktualisierten Version des Clients entspricht.</span><span class="sxs-lookup"><span data-stu-id="28f28-119">In **Update**, type the number that corresponds to the updated release of the client.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="28f28-120">Sie können die Clientversionsnummer mithilfe von Platzhalterzeichen angeben.</span><span class="sxs-lookup"><span data-stu-id="28f28-120">You can use wildcards to indicate the client version number.</span></span>

    
    </div>

5.  <span data-ttu-id="28f28-121">Klicken Sie unter **Vergleichsvorgang** auf eine der folgenden Optionen, um den Vergleichsvorgang für die in den vorherigen Schritten angegebene Clientversion festzulegen:</span><span class="sxs-lookup"><span data-stu-id="28f28-121">To specify the matching operation for the client version you specified in the preceding steps, in **Comparison operation**, click one of the following:</span></span>
    
      - <span data-ttu-id="28f28-122">**Gleich**</span><span class="sxs-lookup"><span data-stu-id="28f28-122">**Same as**</span></span>
    
      - <span data-ttu-id="28f28-123">**Ungleich**</span><span class="sxs-lookup"><span data-stu-id="28f28-123">**Is not**</span></span>
    
      - <span data-ttu-id="28f28-124">**Neuer als**</span><span class="sxs-lookup"><span data-stu-id="28f28-124">**Newer than**</span></span>
    
      - <span data-ttu-id="28f28-125">**Neuer als oder gleich**</span><span class="sxs-lookup"><span data-stu-id="28f28-125">**Newer than or same as**</span></span>
    
      - <span data-ttu-id="28f28-126">**Älter als**</span><span class="sxs-lookup"><span data-stu-id="28f28-126">**Older than**</span></span>
    
      - <span data-ttu-id="28f28-127">**Älter als oder gleich**</span><span class="sxs-lookup"><span data-stu-id="28f28-127">**Older than or same as**</span></span>

6.  <span data-ttu-id="28f28-128">Klicken Sie unter **Aktion** auf eine der folgenden Optionen, um die Aktion anzugeben, die bei Übereinstimmung mit dem angegebenen Kriterium ausgeführt werden soll:</span><span class="sxs-lookup"><span data-stu-id="28f28-128">To specify the action to perform when the criteria in the preceding steps are met, click one of the following in **Action**:</span></span>
    
      - <span data-ttu-id="28f28-129">Klicken Sie auf **Zulassen**, um die Anmeldung des Clients zu erlauben.</span><span class="sxs-lookup"><span data-stu-id="28f28-129">To allow the client to log on, click **Allow**.</span></span>
    
      - <span data-ttu-id="28f28-p103">Klicken Sie auf **Zulassen und aktualisieren**, um dem Client die Anmeldung zu erlauben und Updates über Windows Server Update Service oder Microsoft Update abzurufen. Diese Aktion ist nur verfügbar, wenn der Benutzer-Agent **OC** ausgewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="28f28-p103">To allow the client to log on and receive updates from Windows Server Update Service or Microsoft Update, click **Allow and Upgrade**. This action is available only when user agent **OC** is selected.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="28f28-132">Durch Auswahl dieser Aktion wird eine Benachrichtigung angezeigt, wenn sich Benutzer das nächste Mal bei lync 2013 anmelden.</span><span class="sxs-lookup"><span data-stu-id="28f28-132">Selecting this action causes a notification to appear the next time users sign in to Lync 2013.</span></span> <span data-ttu-id="28f28-133">Die Benachrichtigung weist darauf hin, dass ein Update verfügbar ist, selbst wenn etwaige Updates noch nicht in Windows Server Update Service oder Microsoft Update veröffentlicht wurden.</span><span class="sxs-lookup"><span data-stu-id="28f28-133">The notification states that an update is available, even if updates have not yet been released to Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="28f28-134">Um Unklarheiten zu vermeiden, sollten Sie diese Aktion erst dann auswählen, wenn Updates verfügbar gemacht wurden.</span><span class="sxs-lookup"><span data-stu-id="28f28-134">To avoid confusion, you should choose this action only after updates become available.</span></span>

        
        </div>
    
      - <span data-ttu-id="28f28-p105">Klicken Sie auf **Mit URL zulassen**, um die Anmeldung des Clients zu erlauben und den Benutzer in einer Meldung darauf hinzuweisen, wo eine andere Clientversion heruntergeladen werden kann. Sie geben die URL später in diesem Verfahren an.</span><span class="sxs-lookup"><span data-stu-id="28f28-p105">To allow the client to log on and display a message about where to download another client version, click **Allow with URL**. You specify the URL later in this procedure.</span></span>
    
      - <span data-ttu-id="28f28-137">Um die Anmeldung des Clients zu verhindern, klicken Sie auf **Blockieren**.</span><span class="sxs-lookup"><span data-stu-id="28f28-137">To prevent the client from logging on, click **Block**.</span></span>
    
      - <span data-ttu-id="28f28-p106">Klicken Sie auf **Blockieren und aktualisieren**, um dem Client die Anmeldung zu verweigern und Updates über Windows Server Update Service oder Microsoft Update abzurufen. Diese Aktion ist nur verfügbar, wenn der Benutzer-Agent **OC** ausgewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="28f28-p106">To prevent the client from logging on and allow the client to receive updates from Windows Server Update Service or Microsoft Update, click **Block and Upgrade**. This action is available only when user agent **OC** is selected.</span></span>
    
      - <span data-ttu-id="28f28-p107">Klicken Sie auf **Mit URL blockieren**, um die Anmeldung des Clients zu verweigern und den Benutzer in einer Meldung darauf hinzuweisen, wo eine andere Clientversion heruntergeladen werden kann. Sie geben die URL später in diesem Verfahren an.</span><span class="sxs-lookup"><span data-stu-id="28f28-p107">To prevent the client from logging on and display a message about where to download another client version, click **Block with URL**. You specify the URL later in this procedure.</span></span>

7.  <span data-ttu-id="28f28-142">(Optional) Wenn Sie im vorherigen Schritt auf **Mit URL zulassen** oder **Mit URL blockieren** geklickt haben, geben Sie unter **URL** die URL für den Clientdownload ein.</span><span class="sxs-lookup"><span data-stu-id="28f28-142">(Optional) If you clicked **Allow with URL** or **Block with URL** in the previous step, type the client download URL to include in the message in **URL**.</span></span>

8.  <span data-ttu-id="28f28-143">Klicken Sie auf **OK** und dann auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="28f28-143">Click **OK**, and then click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

