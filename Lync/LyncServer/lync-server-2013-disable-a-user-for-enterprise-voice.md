---
title: 'Lync Server 2013: Deaktivieren eines Benutzers für Enterprise-VoIP'
description: 'Lync Server 2013: Deaktivieren Sie einen Benutzer für Enterprise-VoIP.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disable a user for Enterprise Voice
ms:assetid: 462002d8-21df-4d77-bf7f-4d059d6a4bb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688043(v=OCS.15)
ms:contentKeyID: 49733635
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d99916444e2b1c984e251f6e6289d88e31a538a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568211"
---
# <a name="disable-a-user-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="d71eb-103">Deaktivieren eines Benutzers für Enterprise-VoIP in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d71eb-103">Disable a user for Enterprise Voice in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d71eb-104">_**Letztes Änderungsstand des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="d71eb-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="d71eb-105">Verwenden Sie das folgende Verfahren, um Enterprise-VoIP für ein Benutzerkonto zu deaktivieren, das für lync Server 2013 aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="d71eb-105">Use the following procedure to disable Enterprise Voice for a user account that is enabled for Lync Server 2013.</span></span>

<div>

## <a name="to-disable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="d71eb-106">So deaktivieren Sie ein Benutzerkonto für Enterprise-VoIP</span><span class="sxs-lookup"><span data-stu-id="d71eb-106">To disable a user account for Enterprise Voice</span></span>

1.  <span data-ttu-id="d71eb-107">Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="d71eb-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d71eb-108">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="d71eb-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d71eb-109">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d71eb-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d71eb-110">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="d71eb-110">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="d71eb-111">Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, das aktiviert werden soll, und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="d71eb-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="d71eb-112">Klicken Sie in der Tabelle auf das Benutzerkonto, das Sie für Enterprise-VoIP aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="d71eb-112">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>

6.  <span data-ttu-id="d71eb-113">Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="d71eb-113">On the **Edit** menu, click **Show details**.</span></span>

7.  <span data-ttu-id="d71eb-114">Klicken Sie auf der Seite **Lync Server-Benutzer bearbeiten** unter **Telefonie** auf eine beliebige Option außer **Enterprise-VoIP**.</span><span class="sxs-lookup"><span data-stu-id="d71eb-114">On the **Edit Lync Server User** page, under **Telephony**, click any option except **Enterprise Voice**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d71eb-115">Klicken Sie unter <STRONG>Telefonie</STRONG>auf <STRONG>Audio/Video deaktiviert</STRONG>, um zu verhindern, dass ein Benutzer über lync Audio-oder Videoanrufe tätigen kann.</span><span class="sxs-lookup"><span data-stu-id="d71eb-115">To restrict a user from making audio or video calls by using Lync, under <STRONG>Telephony</STRONG>, click <STRONG>Audio/video disabled</STRONG>.</span></span>

    
    </div>

8.  <span data-ttu-id="d71eb-116">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="d71eb-116">Click **Commit**.</span></span>

<span data-ttu-id="d71eb-117">Der Benutzer kann nun das Enterprise-VoIP-Feature nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="d71eb-117">The user is now unable to use the Enterprise Voice feature.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d71eb-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d71eb-118">See Also</span></span>


[<span data-ttu-id="d71eb-119">Aktivieren von Benutzern für Enterprise-VoIP in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d71eb-119">Enable users for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-enable-users-for-enterprise-voice.md)  


[<span data-ttu-id="d71eb-120">Verwalten von Enterprise-VoIP für Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d71eb-120">Managing Enterprise Voice for users in Lync Server 2013</span></span>](lync-server-2013-managing-enterprise-voice-for-users.md)  
[<span data-ttu-id="d71eb-121">Lync Server 2013 Management-Shell</span><span class="sxs-lookup"><span data-stu-id="d71eb-121">Lync Server 2013 Management Shell</span></span>](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

