---
title: Erstellen eines neuen URL-Filters zur Behandlung von Links in Chat Unterhaltungen
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
ms.openlocfilehash: a7f6cd39034dbc3114f5b89fb15d252b71149762
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740385"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-new-url-filter-in-lync-server-2013-to-handle-hyperlinks-in-im-conversations"></a><span data-ttu-id="efd3f-102">Erstellen eines neuen URL-Filters in lync Server 2013 zur Behandlung von Hyperlinks in Chat Unterhaltungen</span><span class="sxs-lookup"><span data-stu-id="efd3f-102">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="efd3f-103">_**Letztes Änderungsdatum des Themas:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="efd3f-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="efd3f-104">Zusätzlich zum Ändern des globalen URL-Filters können Sie benutzerdefinierte URL-Filter für einzelne Websites in ihrer lync Server 2013-Bereitstellung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="efd3f-104">In addition to modifying the global URL filter, you can configure custom URL filters for individual sites within your Lync Server 2013 deployment.</span></span> <span data-ttu-id="efd3f-105">Details zur URL-Filterung finden Sie unter [Konfigurieren der Dateiübertragung und der URL-Filterung für Chatnachrichten in lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span><span class="sxs-lookup"><span data-stu-id="efd3f-105">For details about URL filtering, see [Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span></span>

<div>

## <a name="to-create-a-new-url-filter"></a><span data-ttu-id="efd3f-106">So erstellen Sie einen neuen URL-Filter</span><span class="sxs-lookup"><span data-stu-id="efd3f-106">To create a new URL filter</span></span>

1.  <span data-ttu-id="efd3f-107">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="efd3f-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="efd3f-108">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="efd3f-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="efd3f-109">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="efd3f-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="efd3f-110">Klicken Sie in der linken Navigationsleiste auf **Chat und Anwesenheit**, und klicken Sie dann auf **URL-Filter**.</span><span class="sxs-lookup"><span data-stu-id="efd3f-110">In the left navigation bar, click **IM and Presence**, and then click **URL Filter**.</span></span>

4.  <span data-ttu-id="efd3f-111">Klicken Sie auf der Seite **URL-Filter** auf **neu**.</span><span class="sxs-lookup"><span data-stu-id="efd3f-111">On the **URL Filter** page, click **New**.</span></span>

5.  <span data-ttu-id="efd3f-112">Klicken Sie unter **Website auswählen**auf die Website, für die Sie den URL-Filter erstellen möchten, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="efd3f-112">In **Select a Site**, click the site for which you want to create the URL filter, and then click **OK**.</span></span>

6.  <span data-ttu-id="efd3f-113">Aktivieren Sie im Dialogfeld **neuer URL-Filter** das Kontrollkästchen **URL-Filter aktivieren** , um die URL-Filterung für die Website zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="efd3f-113">In the **New URL Filter** dialog box, select the **Enable URL Filter** check box to enable URL filtering for the site.</span></span>

7.  <span data-ttu-id="efd3f-114">Aktivieren Sie das Kontrollkästchen **URLs mit Dateierweiterung blockieren** , um alle aktiven URLs zu blockieren, die eine Datei mit einer Erweiterung enthalten, die unter **Dateityperweiterungen zum Blockieren** in **Datei Filter bearbeiten**aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="efd3f-114">To block any active URL that contains a file with an extension listed under **File type extensions to block** in **Edit File Filter**, select the **Block URLs with file extension** check box.</span></span>

8.  <span data-ttu-id="efd3f-115">Klicken Sie im Dropdown-Listenfeld **Link-Präfix** auf die Option, die dem entspricht, wie URLs in Chat Unterhaltungen behandelt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="efd3f-115">In the **Hyperlink prefix** drop-down list box, click the option that corresponds to how you want to handle URLs in instant message conversations.</span></span>
    
    <span data-ttu-id="efd3f-116">Im Dialogfeld " **zulassen** " können Sie beim Senden von Links, die gesendet werden dürfen, eine Warnmeldung an den Benutzer senden.</span><span class="sxs-lookup"><span data-stu-id="efd3f-116">The **Allow message** box enables a warning message to be sent to the user when sending hyperlinks that are allowed to be sent.</span></span>

9.  <span data-ttu-id="efd3f-117">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="efd3f-117">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="efd3f-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="efd3f-118">See Also</span></span>


[<span data-ttu-id="efd3f-119">Konfigurieren der Dateiübertragung und der URL-Filterung für Chatnachrichten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="efd3f-119">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[<span data-ttu-id="efd3f-120">Erstellen eines neuen dateiübertragungsfilters in lync Server 2013 für eine bestimmte Website</span><span class="sxs-lookup"><span data-stu-id="efd3f-120">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[<span data-ttu-id="efd3f-121">Ändern des standardmäßigen dateiübertragungsfilters in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="efd3f-121">Modify the default file transfer filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-file-transfer-filter.md)  


[<span data-ttu-id="efd3f-122">Ändern des Standard-URL-Filters in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="efd3f-122">Modify the default URL filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

