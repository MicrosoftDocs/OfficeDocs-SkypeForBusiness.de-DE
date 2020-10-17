---
title: Erstellen eines neuen URL-Filters zur Behandlung von Hyperlinks in Chat Unterhaltungen
description: Erstellen Sie einen neuen URL-Filter, um Hyperlinks in Chat Unterhaltungen zu behandeln.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a new URL filter to handle hyperlinks in IM conversations
ms:assetid: d0ee01e5-f039-4a34-ac9d-659fe4e9e879
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182590(v=OCS.15)
ms:contentKeyID: 48185426
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e583b3e8cbd04279ab7f54b4138a349fa0d1e85
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554661"
---
# <a name="create-a-new-url-filter-in-lync-server-2013-to-handle-hyperlinks-in-im-conversations"></a><span data-ttu-id="adbd2-103">Erstellen eines neuen URL-Filters in lync Server 2013 zur Behandlung von Hyperlinks in Chat Unterhaltungen</span><span class="sxs-lookup"><span data-stu-id="adbd2-103">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="adbd2-104">_**Letztes Änderungsstand des Themas:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="adbd2-104">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="adbd2-105">Zusätzlich zum Ändern des globalen URL-Filters können Sie benutzerdefinierte URL-Filter für einzelne Websites in ihrer lync Server 2013-Bereitstellung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="adbd2-105">In addition to modifying the global URL filter, you can configure custom URL filters for individual sites within your Lync Server 2013 deployment.</span></span> <span data-ttu-id="adbd2-106">Ausführliche Informationen zur URL-Filterung finden Sie unter [Configuring File Transfer and URL Filtering for Instant Messaging (Sofortnachrichten) in lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span><span class="sxs-lookup"><span data-stu-id="adbd2-106">For details about URL filtering, see [Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span></span>

<div>

## <a name="to-create-a-new-url-filter"></a><span data-ttu-id="adbd2-107">So erstellen Sie einen neuen URL-Filter</span><span class="sxs-lookup"><span data-stu-id="adbd2-107">To create a new URL filter</span></span>

1.  <span data-ttu-id="adbd2-108">Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="adbd2-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="adbd2-109">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="adbd2-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="adbd2-110">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="adbd2-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="adbd2-111">Klicken Sie in der linken Navigationsleiste auf **Chat und Anwesenheit** und dann auf **URL-Filter**.</span><span class="sxs-lookup"><span data-stu-id="adbd2-111">In the left navigation bar, click **IM and Presence**, and then click **URL Filter**.</span></span>

4.  <span data-ttu-id="adbd2-112">Klicken Sie auf der Seite **URL-Filter** auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="adbd2-112">On the **URL Filter** page, click **New**.</span></span>

5.  <span data-ttu-id="adbd2-113">Klicken Sie im Dialogfeld **Standort auswählen** auf den Standort, für den Sie den URL-Filter erstellen möchten, und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="adbd2-113">In **Select a Site**, click the site for which you want to create the URL filter, and then click **OK**.</span></span>

6.  <span data-ttu-id="adbd2-114">Aktivieren Sie im Dialogfeld **Neuer URL-Filter** das Kontrollkästchen **URL-Filter aktivieren**, um die URL-Filterung für den Standort zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="adbd2-114">In the **New URL Filter** dialog box, select the **Enable URL Filter** check box to enable URL filtering for the site.</span></span>

7.  <span data-ttu-id="adbd2-115">Wenn Sie alle aktiven URLs blockieren möchten, die eine Datei mit einer der unter **Dateityperweiterungen, die blockiert werden sollen** aufgeführten Erweiterungen enthalten, aktivieren Sie im Abschnitt **Dateifilter bearbeiten** das Kontrollkästchen **URLs mit Dateierweiterung blockieren**.</span><span class="sxs-lookup"><span data-stu-id="adbd2-115">To block any active URL that contains a file with an extension listed under **File type extensions to block** in **Edit File Filter**, select the **Block URLs with file extension** check box.</span></span>

8.  <span data-ttu-id="adbd2-116">Klicken Sie im Dropdown-Listenfeld **Linkpräfix** auf die gewünschte Option zur Verarbeitung von URLs in Sofortnachrichtenunterhaltungen.</span><span class="sxs-lookup"><span data-stu-id="adbd2-116">In the **Hyperlink prefix** drop-down list box, click the option that corresponds to how you want to handle URLs in instant message conversations.</span></span>
    
    <span data-ttu-id="adbd2-117">Über die Option **Nachricht zulassen** wird dem Benutzer beim Senden eines zulässigen Links eine Warnmeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="adbd2-117">The **Allow message** box enables a warning message to be sent to the user when sending hyperlinks that are allowed to be sent.</span></span>

9.  <span data-ttu-id="adbd2-118">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="adbd2-118">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="adbd2-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="adbd2-119">See Also</span></span>


[<span data-ttu-id="adbd2-120">Konfigurieren der Dateiübertragung und der URL-Filterung für Chatnachrichten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="adbd2-120">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[<span data-ttu-id="adbd2-121">Erstellen eines neuen dateiübertragungsfilters in lync Server 2013 für einen bestimmten Standort</span><span class="sxs-lookup"><span data-stu-id="adbd2-121">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[<span data-ttu-id="adbd2-122">Ändern des standardmäßigen dateiübertragungsfilters in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="adbd2-122">Modify the default file transfer filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-file-transfer-filter.md)  


[<span data-ttu-id="adbd2-123">Ändern des standardmäßigen URL-Filters in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="adbd2-123">Modify the default URL filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

