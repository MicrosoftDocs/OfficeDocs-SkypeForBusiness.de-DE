---
title: 'Lync Server 2013: Suchen nach lync Server-Benutzern'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Search for Lync Server users
ms:assetid: 3b9f6f55-d7a9-46ae-8e10-f221ba0d3bb5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429701(v=OCS.15)
ms:contentKeyID: 48183871
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7134afbc86134471e8d536b36fc8e28142a64db2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764923"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="search-for-lync-server-users-in-lync-server-2013"></a><span data-ttu-id="07494-102">Suchen nach lync Server-Benutzern in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="07494-102">Search for Lync Server users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="07494-103">_**Letztes Änderungsdatum des Themas:** 2014-05-14_</span><span class="sxs-lookup"><span data-stu-id="07494-103">_**Topic Last Modified:** 2014-05-14_</span></span>

<span data-ttu-id="07494-104">Sie können die Ergebnisse einer Suchabfrage verwenden, um Benutzer für lync Server 2013 zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="07494-104">You can use the results of a search query to configure users for Lync Server 2013.</span></span> <span data-ttu-id="07494-105">Sie können anhand des Anzeigenamens, des Vornamens, des Nachnamens, des SAM-Kontonamens (Security Accounts Manager), der SIP-Adresse oder des Anschluss-URI (Uniform Resource Identifier) nach Benutzern suchen.</span><span class="sxs-lookup"><span data-stu-id="07494-105">You can search for users by display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI).</span></span>

<span data-ttu-id="07494-106">Sie können mithilfe der lync Server-Systemsteuerung oder des Snap-Ins Active Directory-Benutzer und-Computer nach Benutzern suchen.</span><span class="sxs-lookup"><span data-stu-id="07494-106">You can search for users by using the Lync Server Control Panel or the Active Directory Users and Computers snap-in.</span></span> <span data-ttu-id="07494-107">Im folgenden Verfahren wird beschrieben, wie Sie mithilfe der lync Server-Systemsteuerung nach Benutzern suchen können.</span><span class="sxs-lookup"><span data-stu-id="07494-107">The following procedure describes how to use Lync Server Control Panel to search for users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="07494-108">In einer Umgebung mit einer zentralen Gesamtstrukturtopologie sind die Suchergebnisse möglicherweise nicht korrekt, wenn Sie nach einem Benutzer anhand der e-Mail-Adresse des Benutzers suchen.</span><span class="sxs-lookup"><span data-stu-id="07494-108">In an environment with a central forest topology, search results might not be accurate when you search for a user by the user’s email address.</span></span> <span data-ttu-id="07494-109">Stattdessen können Sie nach Benutzern suchen, indem Sie ein SIP-Adresspräfix angeben, beispielsweise SIP: Name, einen Suchfilter hinzufügen und eine SIP-Adresse auswählen, die eine teilweise e-Mail-Adresse enthält, oder das Cmdlet " <STRONG>Get-CSUser</STRONG> " verwenden.</span><span class="sxs-lookup"><span data-stu-id="07494-109">Instead, you can search for users by specifying a SIP address prefix, for example, sip:name, add a search filter and select a SIP address that contains a partial email address, or use the <STRONG>Get-CSUser</STRONG> cmdlet.</span></span>



</div>

<div>

## <a name="to-search-for-one-or-more-users"></a><span data-ttu-id="07494-110">So suchen Sie nach einem oder mehreren Benutzern</span><span class="sxs-lookup"><span data-stu-id="07494-110">To search for one or more users</span></span>

1.  <span data-ttu-id="07494-111">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="07494-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="07494-112">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="07494-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="07494-113">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="07494-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="07494-114">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="07494-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="07494-115">Geben Sie im Feld **Benutzer suchen** den gesamten oder den ersten Teil des Anzeigenamens, des Vornamens, des Nachnamens, des SAM-Kontonamens, der SIP-Adresse oder des Leitungs-URIs des Benutzerkontos ein, nach dem Sie suchen möchten, und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="07494-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, SAM account name, SIP address, or line URI of the user account that you want to search for, and then click **Find**.</span></span>

5.  <span data-ttu-id="07494-116">(Optional) Geben Sie zusätzliche Suchkriterien ein, um die Ergebnisse einzuschränken:</span><span class="sxs-lookup"><span data-stu-id="07494-116">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="07494-117">Klicken Sie in der oberen rechten Ecke des Bildschirms oberhalb der **Suchergebnisse**auf die Schaltfläche zum Erweitern des Pfeils, und klicken Sie dann auf **Filter hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="07494-117">Click the expand arrow button in the upper-right corner of the screen above **Search results**, and then click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="07494-118">Geben Sie die Benutzereigenschaft ein, indem Sie Sie eingeben oder in der Dropdownliste auf den Pfeil klicken, um eine Benutzereigenschaft auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="07494-118">Enter the user property by typing it or clicking the arrow in the drop-down list to select a user property.</span></span>
    
    3.  <span data-ttu-id="07494-119">Klicken Sie in der Liste **gleich** an auf **gleich** oder **ungleich**.</span><span class="sxs-lookup"><span data-stu-id="07494-119">In the **Equal to** list, click **Equal to** or **Not equal to**.</span></span>
    
    4.  <span data-ttu-id="07494-120">Geben Sie im Textfeld die Suchkriterien ein, die Sie zum Filtern der Suchergebnisse verwenden möchten, und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="07494-120">In the text box, type the search criteria you want to use to filter search results, and then click **Find**.</span></span>

6.  <span data-ttu-id="07494-121">Die Suchergebnisse werden unter **Suchergebnisse**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="07494-121">The search results appear under **Search Results**.</span></span> <span data-ttu-id="07494-122">Sie können einen oder alle Benutzer in der Liste auswählen und Konfigurationsaufgaben für die von Ihnen ausgewählten Benutzer durchführen.</span><span class="sxs-lookup"><span data-stu-id="07494-122">You can select any or all of the users in the list and perform configuration tasks on the users you select.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="07494-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="07494-123">See Also</span></span>


[<span data-ttu-id="07494-124">Anzeigen von Informationen zu Benutzerkonten, die für lync Server 2013 aktiviert sind</span><span class="sxs-lookup"><span data-stu-id="07494-124">Viewing information about user accounts enabled for Lync Server 2013</span></span>](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)  
[<span data-ttu-id="07494-125">Aktivieren und Deaktivieren von Benutzern für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="07494-125">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

