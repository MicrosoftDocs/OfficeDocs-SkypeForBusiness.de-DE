---
title: 'Lync Server 2013: Löschen einer vorhandenen Netzwerk Website'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting an existing network site
ms:assetid: 2762149b-3572-4513-b838-beda7fa9e81e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688001(v=OCS.15)
ms:contentKeyID: 49733589
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c8e3828bccb84fcddb4404dd7228173c63ab8a5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763063"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-an-existing-network-site-in-lync-server-2013"></a><span data-ttu-id="aad73-102">Löschen einer vorhandenen Netzwerk Website in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aad73-102">Deleting an existing network site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aad73-103">_**Letztes Änderungsdatum des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="aad73-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="aad73-104">Netzwerk Websites sind die Büros oder Standorte, die in den einzelnen Regionen einer Anrufannahme Steuerung oder erweiterten 9-1-1-Bereitstellung konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="aad73-104">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="aad73-105">Sie können die lync Server 2013-Systemsteuerung verwenden, um Websites zu konfigurieren und Sie mit Regionen zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="aad73-105">You can use the Lync Server 2013 Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="aad73-106">Beispielsweise kann eine netzwerkregion für Nordamerika mit Netzwerken wie Chicago, Redmond und Vancouver verknüpft sein.</span><span class="sxs-lookup"><span data-stu-id="aad73-106">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="aad73-107">Eine CAC-Netzwerk Website muss für jede Website innerhalb einer Organisation erstellt werden, selbst wenn diese Website keine Bandbreiteneinschränkungen aufweist.</span><span class="sxs-lookup"><span data-stu-id="aad73-107">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="aad73-108">In der lync Server-Systemsteuerung können Sie Netzwerk Websites erstellen, ändern und löschen.</span><span class="sxs-lookup"><span data-stu-id="aad73-108">From the Lync Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="aad73-109">Gehen Sie wie folgt vor, um eine vorhandene Netzwerk Website zu löschen.</span><span class="sxs-lookup"><span data-stu-id="aad73-109">Use the following procedure to delete an existing network site.</span></span> <span data-ttu-id="aad73-110">Details zum Erstellen oder Ändern von Netzwerk Websites finden Sie unter [erstellen oder Ändern von Netzwerk Websites in lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md)</span><span class="sxs-lookup"><span data-stu-id="aad73-110">For details about creating or modifying network sites, see [Creating or modifying network sites in Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md)</span></span>

<div>

## <a name="to-delete-a-network-site"></a><span data-ttu-id="aad73-111">So löschen Sie eine Netzwerk Website</span><span class="sxs-lookup"><span data-stu-id="aad73-111">To delete a network site</span></span>

1.  <span data-ttu-id="aad73-112">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="aad73-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="aad73-113">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="aad73-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="aad73-114">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="aad73-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="aad73-115">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** , und klicken Sie dann auf **Website**.</span><span class="sxs-lookup"><span data-stu-id="aad73-115">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="aad73-116">Klicken Sie auf der Seite **Website** auf die Website, die Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="aad73-116">On the **Site** page, click the site that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="aad73-117">Sie können mehr als eine Website gleichzeitig löschen.</span><span class="sxs-lookup"><span data-stu-id="aad73-117">You can delete more than one site at a time.</span></span> <span data-ttu-id="aad73-118">Drücken Sie dazu STRG, und wählen Sie mehrere Websites aus, während Sie die STRG-Taste gedrückt halten.</span><span class="sxs-lookup"><span data-stu-id="aad73-118">To do this, press CTRL and select multiple sites while holding down the CTRL key.</span></span> <span data-ttu-id="aad73-119">Wenn Sie alle Websites auswählen möchten, klicken Sie im Menü <STRONG>Bearbeiten</STRONG> auf <STRONG>Alle auswählen</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="aad73-119">Or, to select all sites, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="aad73-120">Klicken Sie im Menü **Bearbeiten** auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="aad73-120">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="aad73-121">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="aad73-121">Click **OK**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="aad73-122">Sie können eine Netzwerk Website nicht entfernen, wenn Sie einem Netzwerk-Subnetz zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="aad73-122">You cannot remove a network site if it is associated with a network subnet.</span></span> <span data-ttu-id="aad73-123">Wenn Sie versuchen, eine Website zu entfernen, die einem Subnetz zugeordnet ist, wird eine Fehlermeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="aad73-123">If you attempt to remove a site associated with a subnet you will receive an error message.</span></span> <span data-ttu-id="aad73-124">Wenn Sie feststellen möchten, ob eine Website mit Subnetzen verknüpft ist, klicken Sie auf die Website, und klicken Sie dann im Menü <STRONG>Bearbeiten</STRONG> auf <STRONG>Details anzeigen</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="aad73-124">To see if a site is associated with any subnets, click the site and then click <STRONG>Show details</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

