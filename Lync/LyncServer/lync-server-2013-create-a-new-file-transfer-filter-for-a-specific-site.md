---
title: 'Lync Server 2013: Erstellen eines neuen dateiübertragungsfilters für einen bestimmten Standort'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a new file transfer filter for a specific site
ms:assetid: d0006487-5217-491c-b730-e6c551cd9825
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182589(v=OCS.15)
ms:contentKeyID: 48185577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10e33523c18f323c34ed129616f0e6012a4ebf11
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501932"
---
# <a name="create-a-new-file-transfer-filter-in-lync-server-2013-for-a-specific-site"></a><span data-ttu-id="7bc8d-102">Erstellen eines neuen dateiübertragungsfilters in lync Server 2013 für einen bestimmten Standort</span><span class="sxs-lookup"><span data-stu-id="7bc8d-102">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7bc8d-103">_**Letztes Änderungsstand des Themas:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="7bc8d-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="7bc8d-104">Zusätzlich zum Ändern des globalen dateiübertragungsfilters können Sie benutzerdefinierte Dateiübertragungsfilter für bestimmte Websites in ihrer lync Server 2013-Bereitstellung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="7bc8d-104">In addition to modifying the global file transfer filter, you can configure custom file transfer filters for specific sites within your Lync Server 2013 deployment.</span></span> <span data-ttu-id="7bc8d-105">Ausführliche Informationen zur Dateiübertragungsfilterung finden Sie unter [Configuring File Transfer and URL Filtering for Instant Messaging (Sofortnachrichten) in lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span><span class="sxs-lookup"><span data-stu-id="7bc8d-105">For details about file transfer filtering, see [Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span></span>

<div>

## <a name="to-create-a-file-transfer-filter-for-a-specific-site"></a><span data-ttu-id="7bc8d-106">So erstellen Sie einen Dateiübertragungsfilter für einen spezifischen Standort</span><span class="sxs-lookup"><span data-stu-id="7bc8d-106">To create a file transfer filter for a specific site</span></span>

1.  <span data-ttu-id="7bc8d-107">Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="7bc8d-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7bc8d-108">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="7bc8d-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7bc8d-109">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="7bc8d-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7bc8d-110">Klicken Sie in der linken Navigationsleiste auf **Chat und Anwesenheit** und dann auf **Dateifilter**.</span><span class="sxs-lookup"><span data-stu-id="7bc8d-110">In the left navigation bar, click **IM and Presence** and then click **File Filter**.</span></span>

4.  <span data-ttu-id="7bc8d-111">Klicken Sie auf der Seite **Dateifilter** auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="7bc8d-111">On the **File Filter** page, click **New**.</span></span>

5.  <span data-ttu-id="7bc8d-112">Klicken Sie im Dialogfeld **Standort auswählen** auf den Standort, für den Sie den Dateiübertragungsfilter erstellen möchten, und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="7bc8d-112">In the **Select a Site** dialog box, click the site for which you want to create the file transfer filter, and then click **OK**.</span></span>

6.  <span data-ttu-id="7bc8d-113">Aktivieren Sie im Abschnitt **Neuer Dateifilter** das Kontrollkästchen **Dateifilter aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="7bc8d-113">In **New File Filter**, click the **Enable file filter** check box.</span></span>

7.  <span data-ttu-id="7bc8d-114">Klicken Sie im Dropdown-Listenfeld **Dateiübertragung** auf **Alles blockieren** oder **Bestimmte Dateitypen blockieren**.</span><span class="sxs-lookup"><span data-stu-id="7bc8d-114">In **File transfer** drop-down list box, click **Block All** or **Block specific file types**.</span></span>

8.  <span data-ttu-id="7bc8d-115">Wenn Sie auf **Alles blockieren** geklickt haben, fahren Sie mit Schritt 10 fort.</span><span class="sxs-lookup"><span data-stu-id="7bc8d-115">If you clicked **Block All**, skip to step 10.</span></span>

9.  <span data-ttu-id="7bc8d-116">Führen Sie eine der folgenden Aktionen aus, wenn Sie auf die Option **Bestimmte Dateitypen blockieren** geklickt haben:</span><span class="sxs-lookup"><span data-stu-id="7bc8d-116">If you clicked **Block specific file types**, do the following:</span></span>
    
    1.  <span data-ttu-id="7bc8d-117">Klicken Sie auf **Auswählen**, um die standardmäßige Liste der Erweiterungen für Dateitypen zu ändern, die blockiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="7bc8d-117">Click **Select** to modify the default list of file type extensions that you want to block.</span></span>
    
    2.  <span data-ttu-id="7bc8d-118">Wählen Sie im Dialogfeld **Dateityp auswählen** die Dateitypen aus, die Sie blockieren oder zulassen möchten, indem Sie die zugehörigen Erweiterungen aus den Kategorien unter **Dateityperweiterungen** entfernen oder sie hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="7bc8d-118">In the **Select File Type** dialog box, select the file types that you want to block or allow by adding or removing their extensions from the categories under **File type extensions**.</span></span>
    
    3.  <span data-ttu-id="7bc8d-119">Wenn die Erweiterung des gewünschten Dateityps nicht aufgeführt wird, geben Sie die Erweiterung in das Textfeld unter **Dateityperweiterungen der Liste hinzufügen** ein, und klicken Sie anschließend auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="7bc8d-119">If you do not see the extension for a file type that you want to block, type the extension in the text box under **Add file type extensions to the list**, and then click **Add**.</span></span>
    
    4.  <span data-ttu-id="7bc8d-120">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="7bc8d-120">Click **OK**.</span></span>

10. <span data-ttu-id="7bc8d-121">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="7bc8d-121">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7bc8d-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7bc8d-122">See Also</span></span>


[<span data-ttu-id="7bc8d-123">Konfigurieren der Dateiübertragung und der URL-Filterung für Chatnachrichten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7bc8d-123">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[<span data-ttu-id="7bc8d-124">Erstellen eines neuen URL-Filters in lync Server 2013 zur Behandlung von Hyperlinks in Chat Unterhaltungen</span><span class="sxs-lookup"><span data-stu-id="7bc8d-124">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  
[<span data-ttu-id="7bc8d-125">Ändern des standardmäßigen dateiübertragungsfilters in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7bc8d-125">Modify the default file transfer filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-file-transfer-filter.md)  


[<span data-ttu-id="7bc8d-126">Ändern des standardmäßigen URL-Filters in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7bc8d-126">Modify the default URL filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

