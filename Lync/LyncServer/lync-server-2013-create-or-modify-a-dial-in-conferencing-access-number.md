---
title: 'Lync Server 2013: Erstellen oder Ändern einer Einwahlnummer für Einwahlkonferenzen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a dial-in conferencing access number
ms:assetid: 06f55c28-57f8-4d4e-8313-9740846796d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398126(v=OCS.15)
ms:contentKeyID: 48183304
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8372c8117f2e33594ae59b3eff15c6d7eee96ba6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832803"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-dial-in-conferencing-access-number-in-lync-server-2013"></a><span data-ttu-id="974fd-102">Erstellen oder Ändern einer Einwahlnummer für Einwahlkonferenzen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="974fd-102">Create or modify a dial-in conferencing access number in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="974fd-103">_**Letztes Änderungsdatum des Themas:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="974fd-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="974fd-104">Führen Sie die folgenden Schritte aus, wenn Sie eine Access-Nummer für Einwahlkonferenzen erstellen oder ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="974fd-104">Follow these steps if you want to create or modify a dial-in conferencing access number.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="974fd-105">Bevor Sie eine neue Einwahl Zugriffsnummer erstellen, müssen Sie in dem Wählplan, der der neuen Einwahl Zugriffsnummer zugeordnet ist, einen Bereich für Einwahlkonferenzen einrichten.</span><span class="sxs-lookup"><span data-stu-id="974fd-105">Before you create a new dial-in access number, you must set a dial-in conferencing region in the dial plan that is associated with the new dial-in access number.</span></span> <span data-ttu-id="974fd-106">Mehrere Wählpläne können denselben Bereich verwenden.</span><span class="sxs-lookup"><span data-stu-id="974fd-106">Multiple dial plans can use the same region.</span></span>



</div>

<div>

## <a name="to-create-or-modify-a-dial-in-access-number"></a><span data-ttu-id="974fd-107">So erstellen oder ändern Sie eine Einwahl Zugriffsnummer</span><span class="sxs-lookup"><span data-stu-id="974fd-107">To create or modify a dial-in access number</span></span>

1.  <span data-ttu-id="974fd-108">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="974fd-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="974fd-109">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="974fd-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="974fd-110">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="974fd-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="974fd-111">Klicken Sie in der linken Navigationsleiste auf **Konferenz** und dann auf **Einwahlnummer**.</span><span class="sxs-lookup"><span data-stu-id="974fd-111">In the left navigation bar, click **Conferencing** and then click **Dial-in Access Number**.</span></span>

4.  <span data-ttu-id="974fd-112">Führen Sie auf der Seite **Einwahlnummer** einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="974fd-112">On the **Dial-in Access Number** page, do one of the following:</span></span>
    
      - <span data-ttu-id="974fd-113">Klicken Sie auf **Neu**, um **Neue Einwahlnummer** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="974fd-113">Click **New** to open **New Dial-in Access Number**.</span></span>
    
      - <span data-ttu-id="974fd-114">Klicken Sie auf eine der Einwahlnummern in der Liste, klicken Sie auf **Bearbeiten** und anschließend auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="974fd-114">Click one of the dial-in access numbers in the list, click **Edit**, and then click **Show details**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="974fd-p103">Die Suche nach den Inhalten einer Spalte in der Liste der Zugriffsnummern für die Einwahl über das Suchfeld führt möglicherweise nicht zu den erwarteten Ergebnissen. Sortieren Sie die Liste stattdessen nach der gewünschten Spalte, um nach der Zugriffsnummer für die Einwahl zu suchen, die Sie anzeigen oder ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="974fd-p103">Using the search field to search for the contents of a column in the list of dial-in access numbers may not yield the results you expect. Instead, sort the list by the column of interest to identify the dial-in access number you want to view or change.</span></span>

        
        </div>

5.  <span data-ttu-id="974fd-117">Geben Sie im Feld **Anzeigenummer** die Telefonnummer ein, die PSTN-Telefonbenutzer (Public Switched Telephone Network, Telefonfestnetz) wählen, um an einer Konferenz teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="974fd-117">In **Display number**, type the phone number that public switched telephone network (PSTN) phone users dial to join a conference.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="974fd-118">Diese Nummer wird in Besprechungseinladungen und auf der Webseite mit den Einstellungen für die Einwahlkonferenz angezeigt.</span><span class="sxs-lookup"><span data-stu-id="974fd-118">This number is displayed in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>

    
    </div>

6.  <span data-ttu-id="974fd-119">Geben Sie in **Anzeigename** eine Beschreibung für die Zugriffsnummer für die Einwahl ein.</span><span class="sxs-lookup"><span data-stu-id="974fd-119">In **Display name**, type a description for the dial-in access number.</span></span> <span data-ttu-id="974fd-120">Dies ist der Name, der der Einwahl Zugriffsnummer in den lync-Suchergebnissen zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="974fd-120">This is the name that is associated with the dial-in access number in Lync search results.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="974fd-121">Der Name wird im Client angezeigt, wenn ein Benutzer die Einwahlnummer wählt.</span><span class="sxs-lookup"><span data-stu-id="974fd-121">This name is displayed in the client when a user calls the access number.</span></span>

    
    </div>

7.  <span data-ttu-id="974fd-p105">Geben Sie im Feld **Anschluss-URI** die E.164-Nummer der Zugriffsnummer für die Einwahl im TEL-URI-Format ein, einschließlich des +-Symbols vor der Nummer und ohne Leerzeichen. Beispiel: tel:+14255550200.</span><span class="sxs-lookup"><span data-stu-id="974fd-p105">In **Line URI**, type the E.164 number of the dial-in access number in TEL URI format, including the + symbol before the number and excluding spaces. For example, tel:+14255550200.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="974fd-124">Dieser Anschluss-URI kann nicht für eine andere Einwahlnummer für Einwahlkonferenzen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="974fd-124">The same Line URI cannot be reused by another dial-in conferencing access number.</span></span>

    
    </div>

8.  <span data-ttu-id="974fd-125">Führen Sie unter **SIP-URI** die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="974fd-125">In **SIP URI**, do the following:</span></span>
    
      - <span data-ttu-id="974fd-126">Geben Sie in das Textfeld einen eindeutigen SIP-URI für diese Zugriffsnummer für Einwahlkonferenzen ein.</span><span class="sxs-lookup"><span data-stu-id="974fd-126">In the text box, type a unique SIP URI for this dial-in conferencing access number.</span></span> <span data-ttu-id="974fd-127">Dieser SIP-URI wird an verschiedenen Speicherorten angezeigt, einschließlich, aber nicht ausschließlich, von Benachrichtigungsnachrichten und früheren Versionen von Communicator-Clients.</span><span class="sxs-lookup"><span data-stu-id="974fd-127">This SIP URI is displayed in various locations including, but not limited to, call notification messages and previous versions of Communicator clients.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="974fd-p107">Dieser SIP-URI kann nicht für eine andere Zugriffsnummer für Einwahlkonferenzen verwendet werden. Der SIP-URI kann nach der Erstellung der Zugriffsnummer nicht geändert werden. Die einzige Möglichkeit zum Ändern des SIP-URI besteht darin, die Zugriffsnummer zu löschen und neu zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="974fd-p107">The same SIP URI cannot be reused by another dial-in conferencing access number. The SIP URI cannot be modified after the access number is created. The only way to change the SIP URI is to delete and recreate the access number.</span></span>

        
        </div>
    
      - <span data-ttu-id="974fd-131">Klicken Sie im Dropdown-Listenfeld auf die Domäne der Conferencing Attendant-Anwendung, die diese Einwahl Zugriffsnummer unterstützt.</span><span class="sxs-lookup"><span data-stu-id="974fd-131">In the drop-down list box, click the domain of the Conferencing Attendant application that supports this dial-in access number.</span></span>

9.  <span data-ttu-id="974fd-132">Klicken Sie unter **Pool** auf den Pool, der die Instanz der Konferenzzentrale ausführt, die diese Einwahlnummer unterstützt.</span><span class="sxs-lookup"><span data-stu-id="974fd-132">In **Pool**, click the pool that is running the instance of Conferencing Attendant that supports this dial-in access number.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="974fd-133">Wenn der Pool nach dem Erstellen der Zugriffsnummer geändert werden muss, müssen Sie das Cmdlet <STRONG>Move-CsApplicationEndpoint</STRONG> verwenden oder die Zugriffsnummer löschen und neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="974fd-133">If you need to change the pool after you create the access number, you must use the <STRONG>Move-CsApplicationEndpoint</STRONG> cmdlet or delete and recreate the access number.</span></span>

    
    </div>

10. <span data-ttu-id="974fd-134">Klicken Sie unter **Primäre Sprache** auf die Sprache, in der Ansagen für diese Einwahlnummer wiedergegeben werden.</span><span class="sxs-lookup"><span data-stu-id="974fd-134">In **Primary language**, click the language in which prompts are played for this dial-in access number.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="974fd-p108">Bei der primären Sprache handelt es sich um die Sprache, die die Konferenzzentrale zum Beantworten des Anrufs verwendet. Die unterstützten Sprachen werden auf der Webseite mit den Einstellungen für die Einwahlkonferenz neben den verschiedenen Zugriffsnummern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="974fd-p108">The primary language is the language that the Conferencing Attendant uses to answer the call. Supported languages are displayed alongside each access phone number on the Dial-in Conferencing Settings webpage.</span></span>

    
    </div>

11. <span data-ttu-id="974fd-137">(Optional) Klicken Sie unter **Sekundäre Sprachen (maximal vier)** auf **Hinzufügen**, wählen Sie eine oder mehrere zusätzliche Sprachen aus, die für Anrufer dieser Zugriffsnummer für die Einwahl unterstützt werden sollen, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="974fd-137">(Optional) In **Secondary languages (maximum of four)**, click **Add**, select one or more additional languages that you want to support for callers to this dial-in access number, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="974fd-p109">Sie können für jede Zugriffsnummer für die Einwahl bis zu vier sekundäre Sprachen auswählen. Benutzer können beim Einwählen in eine Konferenz eine sekundäre Sprache auswählen, bevor sie die Konferenz-ID eingeben.</span><span class="sxs-lookup"><span data-stu-id="974fd-p109">You can choose up to four secondary languages for each dial-in access number. Users can select a secondary language before entering the conference ID when they dial in to a conference.</span></span>

    
    </div>

12. <span data-ttu-id="974fd-140">Wenn Sie einen Bereich für die Einwahl Zugriffsnummer hinzufügen möchten, klicken Sie unter **zugeordnete Regionen**auf **Hinzufügen**, klicken Sie auf eine oder mehrere Regionen, die den Wählplänen für diese Einwahl Zugriffsnummer zugeordnet sind, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="974fd-140">To add a region for the dial-in access number, under **Associated regions**, click **Add**, click one or more regions that are associated with the dial plans for this dial-in access number, and then click **OK**.</span></span>

13. <span data-ttu-id="974fd-141">Zum Löschen einer Region aus der Einwahlnummer klicken Sie unter **Zugeordnete Regionen** auf die zu löschende Region und anschließend auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="974fd-141">To delete a region from the dial-in access number, under **Associated regions**, click the region you want to delete, and then click **Remove**.</span></span>

14. <span data-ttu-id="974fd-142">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="974fd-142">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

