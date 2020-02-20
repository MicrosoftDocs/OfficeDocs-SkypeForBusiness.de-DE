---
title: 'Lync Server 2013: Erstellen oder Ändern einer Zugriffsnummer für Einwahlkonferenzen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a dial-in conferencing access number
ms:assetid: 06f55c28-57f8-4d4e-8313-9740846796d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398126(v=OCS.15)
ms:contentKeyID: 48183304
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb2793a37fcac58afdf3e996094bcb8d2ff8f5a2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154397"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-dial-in-conferencing-access-number-in-lync-server-2013"></a><span data-ttu-id="f269b-102">Erstellen oder Ändern einer Zugriffsnummer für Einwahlkonferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f269b-102">Create or modify a dial-in conferencing access number in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f269b-103">_**Letztes Änderungsstand des Themas:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="f269b-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="f269b-104">Führen Sie die folgenden Schritte aus, wenn Sie eine Zugriffsnummer für Einwahlkonferenzen erstellen oder ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="f269b-104">Follow these steps if you want to create or modify a dial-in conferencing access number.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f269b-105">Bevor Sie eine neue Zugriffsnummer für die Einwahl erstellen, müssen Sie in den Wähleinstellungen, die der neuen Zugriffsnummer für die Einwahl zugeordnet sind, eine Region für Einwahlkonferenzen festlegen.</span><span class="sxs-lookup"><span data-stu-id="f269b-105">Before you create a new dial-in access number, you must set a dial-in conferencing region in the dial plan that is associated with the new dial-in access number.</span></span> <span data-ttu-id="f269b-106">In mehreren Wählplänen kann dieselbe Region verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f269b-106">Multiple dial plans can use the same region.</span></span>



</div>

<div>

## <a name="to-create-or-modify-a-dial-in-access-number"></a><span data-ttu-id="f269b-107">So erstellen oder ändern Sie eine Zugriffsnummer für die Einwahl</span><span class="sxs-lookup"><span data-stu-id="f269b-107">To create or modify a dial-in access number</span></span>

1.  <span data-ttu-id="f269b-108">Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="f269b-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f269b-109">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f269b-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f269b-110">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f269b-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f269b-111">Klicken Sie in der linken Navigationsleiste auf **Konferenz** und dann auf **Zugriffsnummer für Einwahl**.</span><span class="sxs-lookup"><span data-stu-id="f269b-111">In the left navigation bar, click **Conferencing** and then click **Dial-in Access Number**.</span></span>

4.  <span data-ttu-id="f269b-112">Führen Sie auf der Seite **Zugriffsnummer für Einwahl** einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="f269b-112">On the **Dial-in Access Number** page, do one of the following:</span></span>
    
      - <span data-ttu-id="f269b-113">Klicken Sie auf **neu** , um eine **neue Zugriffsnummer für Einwahl**zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f269b-113">Click **New** to open **New Dial-in Access Number**.</span></span>
    
      - <span data-ttu-id="f269b-114">Klicken Sie auf eine der Einwahlnummern in der Liste, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details einblenden**.</span><span class="sxs-lookup"><span data-stu-id="f269b-114">Click one of the dial-in access numbers in the list, click **Edit**, and then click **Show details**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="f269b-115">Wenn Sie das Suchfeld verwenden, um nach dem Inhalt einer Spalte in der Liste der Zugriffsnummern für Einwahlen zu suchen, ergeben sich möglicherweise nicht die erwarteten Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="f269b-115">Using the search field to search for the contents of a column in the list of dial-in access numbers may not yield the results you expect.</span></span> <span data-ttu-id="f269b-116">Sortieren Sie stattdessen die Liste nach der gewünschten Spalte, um die Zugriffsnummer für die Einwahl zu identifizieren, die Sie anzeigen oder ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="f269b-116">Instead, sort the list by the column of interest to identify the dial-in access number you want to view or change.</span></span>

        
        </div>

5.  <span data-ttu-id="f269b-117">Geben Sie unter **Anzeige Nummer**die Telefonnummer ein, die von Telefonbenutzern mit öffentlichem Telefonnetz (PSTN) gewählt wird, um an einer Konferenz teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="f269b-117">In **Display number**, type the phone number that public switched telephone network (PSTN) phone users dial to join a conference.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f269b-118">Diese Nummer wird in Besprechungseinladungen und auf der Webseite mit den Einstellungen für Einwahlkonferenzen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f269b-118">This number is displayed in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>

    
    </div>

6.  <span data-ttu-id="f269b-119">Geben Sie unter **Anzeigename**eine Beschreibung für die Zugriffsnummer für die Einwahl ein.</span><span class="sxs-lookup"><span data-stu-id="f269b-119">In **Display name**, type a description for the dial-in access number.</span></span> <span data-ttu-id="f269b-120">Dies ist der Name, der der Zugriffsnummer für die Einwahl in lync-Suchergebnissen zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="f269b-120">This is the name that is associated with the dial-in access number in Lync search results.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f269b-121">Dieser Name wird im Client angezeigt, wenn ein Benutzer die Zugriffsnummer anruft.</span><span class="sxs-lookup"><span data-stu-id="f269b-121">This name is displayed in the client when a user calls the access number.</span></span>

    
    </div>

7.  <span data-ttu-id="f269b-122">Geben Sie im Feld **Anschluss-URI**die E. 164-Nummer der Zugriffsnummer für die Einwahl im Tel-URI-Format ein, einschließlich des +-Symbols vor der Nummer und ohne Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="f269b-122">In **Line URI**, type the E.164 number of the dial-in access number in TEL URI format, including the + symbol before the number and excluding spaces.</span></span> <span data-ttu-id="f269b-123">Beispielsweise Tel: + 14255550200.</span><span class="sxs-lookup"><span data-stu-id="f269b-123">For example, tel:+14255550200.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f269b-124">Derselbe Leitungs-URI kann nicht von einer anderen Zugriffsnummer für Einwahlkonferenzen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f269b-124">The same Line URI cannot be reused by another dial-in conferencing access number.</span></span>

    
    </div>

8.  <span data-ttu-id="f269b-125">Führen Sie unter **SIP-URI**die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="f269b-125">In **SIP URI**, do the following:</span></span>
    
      - <span data-ttu-id="f269b-126">Geben Sie in das Textfeld einen eindeutigen SIP-URI für diese Zugriffsnummer für Einwahlkonferenzen ein.</span><span class="sxs-lookup"><span data-stu-id="f269b-126">In the text box, type a unique SIP URI for this dial-in conferencing access number.</span></span> <span data-ttu-id="f269b-127">Dieser SIP-URI wird an verschiedenen Orten angezeigt, einschließlich, aber nicht ausschließlich, Anrufbenachrichtigungen und vorherige Versionen von Communicator-Clients.</span><span class="sxs-lookup"><span data-stu-id="f269b-127">This SIP URI is displayed in various locations including, but not limited to, call notification messages and previous versions of Communicator clients.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="f269b-128">Derselbe SIP-URI kann nicht von einer anderen Zugriffsnummer für Einwahlkonferenzen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f269b-128">The same SIP URI cannot be reused by another dial-in conferencing access number.</span></span> <span data-ttu-id="f269b-129">Der SIP-URI kann nicht geändert werden, nachdem die Zugriffsnummer erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="f269b-129">The SIP URI cannot be modified after the access number is created.</span></span> <span data-ttu-id="f269b-130">Die einzige Möglichkeit zum Ändern des SIP-URI besteht darin, die Zugriffsnummer zu löschen und neu zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f269b-130">The only way to change the SIP URI is to delete and recreate the access number.</span></span>

        
        </div>
    
      - <span data-ttu-id="f269b-131">Klicken Sie im Dropdown-Listenfeld auf die Domäne der Konferenzzentrale, die diese Zugriffsnummer für die Einwahl unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f269b-131">In the drop-down list box, click the domain of the Conferencing Attendant application that supports this dial-in access number.</span></span>

9.  <span data-ttu-id="f269b-132">Klicken Sie unter **Pool**auf den Pool, der die Instanz der Konferenzzentrale ausführt, die diese Zugriffsnummer für die Einwahl unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f269b-132">In **Pool**, click the pool that is running the instance of Conferencing Attendant that supports this dial-in access number.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f269b-133">Wenn der Pool nach dem Erstellen der Zugriffsnummer geändert werden muss, müssen Sie das Cmdlet " <STRONG>CsApplicationEndpoint</STRONG> " verwenden oder die Zugriffsnummer löschen und neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f269b-133">If you need to change the pool after you create the access number, you must use the <STRONG>Move-CsApplicationEndpoint</STRONG> cmdlet or delete and recreate the access number.</span></span>

    
    </div>

10. <span data-ttu-id="f269b-134">Klicken Sie in der **primären Sprache**auf die Sprache, in der Eingabeaufforderungen für diese Zugriffsnummer für die Einwahl wiedergegeben werden.</span><span class="sxs-lookup"><span data-stu-id="f269b-134">In **Primary language**, click the language in which prompts are played for this dial-in access number.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f269b-135">Die primäre Sprache ist die Sprache, die die Konferenzzentrale verwendet, um den Anruf entgegenzunehmen.</span><span class="sxs-lookup"><span data-stu-id="f269b-135">The primary language is the language that the Conferencing Attendant uses to answer the call.</span></span> <span data-ttu-id="f269b-136">Unterstützte Sprachen werden neben jeder Access-Telefonnummer auf der Webseite mit den Einstellungen für Einwahlkonferenzen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f269b-136">Supported languages are displayed alongside each access phone number on the Dial-in Conferencing Settings webpage.</span></span>

    
    </div>

11. <span data-ttu-id="f269b-137">Optional Klicken Sie in **sekundären Sprachen (maximal vier)** auf **Hinzufügen**, wählen Sie eine oder mehrere zusätzliche Sprachen aus, die für Anrufer für diese Zugriffsnummer für die Einwahl unterstützt werden sollen, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f269b-137">(Optional) In **Secondary languages (maximum of four)**, click **Add**, select one or more additional languages that you want to support for callers to this dial-in access number, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f269b-138">Sie können für jede Zugriffsnummer für die Einwahl bis zu vier sekundäre Sprachen auswählen.</span><span class="sxs-lookup"><span data-stu-id="f269b-138">You can choose up to four secondary languages for each dial-in access number.</span></span> <span data-ttu-id="f269b-139">Benutzer können eine sekundäre Sprache auswählen, bevor Sie die Konferenz-ID eingeben, wenn Sie sich in eine Konferenz einwählen.</span><span class="sxs-lookup"><span data-stu-id="f269b-139">Users can select a secondary language before entering the conference ID when they dial in to a conference.</span></span>

    
    </div>

12. <span data-ttu-id="f269b-140">Klicken Sie zum Hinzufügen einer Region für die Zugriffsnummer für die Einwahl unter **zugeordnete Regionen**auf **Hinzufügen**, klicken Sie auf eine oder mehrere Regionen, die den Wählplänen für diese Zugriffsnummer für die Einwahl zugeordnet sind, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f269b-140">To add a region for the dial-in access number, under **Associated regions**, click **Add**, click one or more regions that are associated with the dial plans for this dial-in access number, and then click **OK**.</span></span>

13. <span data-ttu-id="f269b-141">Wenn Sie eine Region aus der Zugriffsnummer für die Einwahl löschen möchten, klicken Sie unter **zugeordnete Regionen**auf die Region, die Sie löschen möchten, und klicken Sie dann auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="f269b-141">To delete a region from the dial-in access number, under **Associated regions**, click the region you want to delete, and then click **Remove**.</span></span>

14. <span data-ttu-id="f269b-142">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="f269b-142">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

