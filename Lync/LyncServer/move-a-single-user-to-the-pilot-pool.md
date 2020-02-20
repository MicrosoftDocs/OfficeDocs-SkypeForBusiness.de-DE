---
title: Verlagern eines einzelnen Benutzers in den Pilot Pool
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Move a single user to the pilot pool
ms:assetid: e9de81a8-40dd-4446-81e7-a2b810eaea50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205401(v=OCS.15)
ms:contentKeyID: 48185905
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 187b0b3055710f89b8c16d8167c1b6692d5eaac2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148684"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-a-single-user-to-the-pilot-pool"></a><span data-ttu-id="73fea-102">Verlagern eines einzelnen Benutzers in den Pilot Pool</span><span class="sxs-lookup"><span data-stu-id="73fea-102">Move a single user to the pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="73fea-103">_**Letztes Änderungsstand des Themas:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="73fea-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="73fea-104">Sie können einen Benutzer aus dem lync Server 2010 Pool mithilfe lync Server 2013 Systemsteuerung oder lync Server 2013 Verwaltungsshell in den lync Server 2013 Pilot Pool migrieren.</span><span class="sxs-lookup"><span data-stu-id="73fea-104">You can move a user from your Lync Server 2010 pool to your Lync Server 2013 pilot pool using Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="73fea-105">Im Beispiel unten in der Spalte registrierungsstellenpool ist **pool01.contoso.net** der lync Server 2010 Pool, und alle sechs dieser Benutzer sind mit diesem Pool verbunden.</span><span class="sxs-lookup"><span data-stu-id="73fea-105">In the example below, in the Registrar pool column, **pool01.contoso.net** is the Lync Server 2010 pool, and all six of these users are connected to this pool.</span></span> <span data-ttu-id="73fea-106">Verwenden Sie die folgenden Verfahren, um einen Benutzer mithilfe lync Server 2013 Systemsteuerung und lync Server-Verwaltungsshell in ihren lync Server 2013 Pool zu versetzen.</span><span class="sxs-lookup"><span data-stu-id="73fea-106">Use the following procedures to move a user to your Lync Server 2013 pool using Lync Server 2013 Control Panel and Lync Server Management Shell.</span></span>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="73fea-107">So können Sie einen Benutzer mithilfe der lync Server 2013-Systemsteuerung migrieren</span><span class="sxs-lookup"><span data-stu-id="73fea-107">To move a user by using the Lync Server 2013 Control Panel</span></span>

<span data-ttu-id="73fea-108">**Liste der Benutzer in der lync Server 2013-Systemsteuerung**</span><span class="sxs-lookup"><span data-stu-id="73fea-108">**List of users in the Lync Server 2013 Control Panel**</span></span>

<span data-ttu-id="73fea-109">![Lync Server-Systemsteuerung, Dialogfeld "Benutzer Verschiebe"](images/JJ721870.a2bce284-0392-4db3-9bb2-9f12699738e7(OCS.15).jpg "Lync Server-Systemsteuerung, Dialogfeld "Benutzer Verschiebe"")</span><span class="sxs-lookup"><span data-stu-id="73fea-109">![Lync Server Control Panel, Move User dialog](images/JJ721870.a2bce284-0392-4db3-9bb2-9f12699738e7(OCS.15).jpg "Lync Server Control Panel, Move User dialog")</span></span>

1.  <span data-ttu-id="73fea-110">Melden Sie sich über ein Konto, das Mitglied der Gruppe "RTCUniversalServerAdmins" oder der Administratorrolle "CsAdministrator" oder "CsUserAdministrator" ist, am Front-End-Server an.</span><span class="sxs-lookup"><span data-stu-id="73fea-110">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>

2.  <span data-ttu-id="73fea-111">Öffnen Sie die **Lync Server-Systemsteuerung**.</span><span class="sxs-lookup"><span data-stu-id="73fea-111">Open **Lync Server Control Panel**.</span></span>

3.  <span data-ttu-id="73fea-112">Klicken Sie auf **Benutzer**, dann auf die Suche und auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="73fea-112">Click **Users**, click Search, and then click **Find**.</span></span>

4.  <span data-ttu-id="73fea-113">Wählen Sie einen Benutzer aus, den Sie in den lync Server 2013 Pool umlegen möchten.</span><span class="sxs-lookup"><span data-stu-id="73fea-113">Select a user that you want to move to the Lync Server 2013 pool.</span></span> <span data-ttu-id="73fea-114">In diesem Beispiel verschieben wir Sara Davis.</span><span class="sxs-lookup"><span data-stu-id="73fea-114">In this example, we will move user Sara Davis.</span></span>

5.  <span data-ttu-id="73fea-115">Wählen Sie im Menü **Aktion** die Option **Ausgewählte Benutzer in Pool verschieben**.</span><span class="sxs-lookup"><span data-stu-id="73fea-115">On the **Action** menu, select **Move selected users to pool**.</span></span>

6.  <span data-ttu-id="73fea-116">Wählen Sie in der Dropdownliste den lync Server 2013 Pool aus.</span><span class="sxs-lookup"><span data-stu-id="73fea-116">From the drop-down list, select the Lync Server 2013 pool.</span></span>

7.  <span data-ttu-id="73fea-117">Klicken Sie auf **Aktion**, und klicken Sie anschließend auf **Ausgewählte Benutzer in Pool verschieben**.</span><span class="sxs-lookup"><span data-stu-id="73fea-117">Click **Action** and then click **Move selected users to pool**.</span></span> <span data-ttu-id="73fea-118">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="73fea-118">Click **OK**.</span></span>
    
    <span data-ttu-id="73fea-119">![Dialogfeld zum Migrieren von Benutzern, Ziel registrierungsstellenpool](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Dialogfeld zum Migrieren von Benutzern, Ziel registrierungsstellenpool")</span><span class="sxs-lookup"><span data-stu-id="73fea-119">![Move Users, destination registrar pool dialog box](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Move Users, destination registrar pool dialog box")</span></span>  

8.  <span data-ttu-id="73fea-120">Stellen Sie sicher, dass die Spalte **Registrierungspool** für den Benutzer jetzt den lync Server 2013 Pool enthält, der angibt, dass der Benutzer erfolgreich verschoben wurde.</span><span class="sxs-lookup"><span data-stu-id="73fea-120">Verify that the **Registrar pool** column for the user now contains the Lync Server 2013 pool, which indicates that the user has been successfully moved.</span></span>

</div>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="73fea-121">So migrieren Sie einen Benutzer mithilfe der lync Server 2013-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="73fea-121">To move a user by using the Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="73fea-122">Öffnen Sie die Lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="73fea-122">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="73fea-123">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="73fea-123">At the command line, type the following:</span></span>
    
        Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"

3.  <span data-ttu-id="73fea-124">Geben Sie anschließend an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="73fea-124">Next, at the command line, type the following:</span></span>
    
        Get-CsUser -Identity "David Pelton"

4.  <span data-ttu-id="73fea-125">Die **RegistrarPool** -Identität verweist nun auf den lync Server 2013-Pool.</span><span class="sxs-lookup"><span data-stu-id="73fea-125">The **RegistrarPool** identity now points to the Lync Server 2013 pool.</span></span> <span data-ttu-id="73fea-126">Das Vorhandensein dieser Identität zeigt, dass der Benutzer erfolgreich verschoben wurde.</span><span class="sxs-lookup"><span data-stu-id="73fea-126">The presence of this identity confirms that the user has been successfully moved.</span></span>
    
    <span data-ttu-id="73fea-127">![Ausgabe von Get-CsUser-Cmdlet mit Identitäts Filter](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Ausgabe von Get-CsUser-Cmdlet mit Identitäts Filter")</span><span class="sxs-lookup"><span data-stu-id="73fea-127">![Output from Get-CsUser cmdlet with Identity filter](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Output from Get-CsUser cmdlet with Identity filter")</span></span>  
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="73fea-128">Ausführliche Informationen zum Cmdlet <STRONG>Get-CsUser</STRONG> erhalten Sie, indem Sie Folgendes ausführen: <STRONG>Get-Help Get-CsUser –Detailed</STRONG></span><span class="sxs-lookup"><span data-stu-id="73fea-128">For details about the <STRONG>Get-CsUser</STRONG> cmdlet, run: <STRONG>Get-Help Get-CsUser –Detailed</STRONG></span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

