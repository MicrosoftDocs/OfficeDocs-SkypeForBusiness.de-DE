---
title: Verlagern eines einzelnen Benutzers in den Pilot Pool
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Move a single user to the pilot pool
ms:assetid: 80d5b365-f153-4c61-a148-f9e18ce6e027
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688109(v=OCS.15)
ms:contentKeyID: 49733708
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 051e5b0c550b76dc61aa7935ea8867cc282ddd24
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034661"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-a-single-user-to-the-pilot-pool"></a><span data-ttu-id="ae13c-102">Verlagern eines einzelnen Benutzers in den Pilot Pool</span><span class="sxs-lookup"><span data-stu-id="ae13c-102">Move a single user to the pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ae13c-103">_**Letztes Änderungsstand des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="ae13c-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="ae13c-104">Sie können einen Benutzer aus dem Office Communications Server 2007 R2 Pool mithilfe lync Server 2013 Systemsteuerung oder lync Server 2013 Verwaltungsshell in den lync Server 2013 Pilot Pool migrieren.</span><span class="sxs-lookup"><span data-stu-id="ae13c-104">You can move a user from your Office Communications Server 2007 R2 pool to your Lync Server 2013 pilot pool using Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="ae13c-105">Im Beispiel unten in der Spalte registrierungsstellenpool ist \*\* \<Office Communications Server\> \*\* der Office Communications Server 2007 R2-Pool, und alle sechs dieser Benutzer sind mit diesem Pool verbunden.</span><span class="sxs-lookup"><span data-stu-id="ae13c-105">In the example below, in the Registrar pool column, **\<Office Communications Server\>** is the Office Communications Server 2007 R2 pool, and all six of these users are connected to this pool.</span></span> <span data-ttu-id="ae13c-106">Verwenden Sie die folgenden Verfahren, um einen Benutzer mithilfe lync Server 2013 Systemsteuerung und lync Server-Verwaltungsshell in ihren lync Server 2013 Pool zu versetzen.</span><span class="sxs-lookup"><span data-stu-id="ae13c-106">Use the following procedures to move a user to your Lync Server 2013 pool using Lync Server 2013 Control Panel and Lync Server Management Shell.</span></span>

<span data-ttu-id="ae13c-107">![Suchen nach OCS-Benutzern in lync Server-Systemsteuerung](images/JJ688109.d2008fd6-868b-4f26-84cf-57bb69e073d3(OCS.15).jpg "Suchen nach OCS-Benutzern in lync Server-Systemsteuerung")</span><span class="sxs-lookup"><span data-stu-id="ae13c-107">![Search for OCS users in Lync Server Control Panel](images/JJ688109.d2008fd6-868b-4f26-84cf-57bb69e073d3(OCS.15).jpg "Search for OCS users in Lync Server Control Panel")</span></span>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="ae13c-108">So können Sie einen Benutzer mithilfe der lync Server 2013-Systemsteuerung migrieren</span><span class="sxs-lookup"><span data-stu-id="ae13c-108">To move a user by using the Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="ae13c-109">Melden Sie sich über ein Konto, das Mitglied der Gruppe "RTCUniversalServerAdmins" oder der Administratorrolle "CsAdministrator" oder "CsUserAdministrator" ist, am Front-End-Server an.</span><span class="sxs-lookup"><span data-stu-id="ae13c-109">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>

2.  <span data-ttu-id="ae13c-110">Öffnen Sie die Lync Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="ae13c-110">Open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="ae13c-111">Klicken Sie auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="ae13c-111">Click **Users**.</span></span>

4.  <span data-ttu-id="ae13c-112">Klicken Sie auf der Registerkarte **Benutzersuche** auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="ae13c-112">From the **User Search** tab, click the **Search** button.</span></span>

5.  <span data-ttu-id="ae13c-113">Klicken Sie anschließend auf **Filter hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ae13c-113">Next, click **Add Filter**.</span></span>

6.  <span data-ttu-id="ae13c-114">Erstellen Sie einen Filter, wobei der Wert für den Office Communications Server-Benutzer\*\*\*\* dem Wert **True** entspricht.</span><span class="sxs-lookup"><span data-stu-id="ae13c-114">Create a filter where **Office Communications Server user** is equal to **True**.</span></span>

7.  <span data-ttu-id="ae13c-115">Klicken Sie auf **Suchen** , um nach Legacy Office Communications Server 2007 R2 Benutzern zu suchen.</span><span class="sxs-lookup"><span data-stu-id="ae13c-115">Click **Find** to search for legacy Office Communications Server 2007 R2 users.</span></span>
    
    <span data-ttu-id="ae13c-116">![Suchen nach OCS-Benutzern in lync Server-Systemsteuerung](images/JJ688109.09528349-7915-41e1-91b4-6ab5c12b1b38(OCS.15).jpg "Suchen nach OCS-Benutzern in lync Server-Systemsteuerung")</span><span class="sxs-lookup"><span data-stu-id="ae13c-116">![Search for OCS users in Lync Server Control Panel](images/JJ688109.09528349-7915-41e1-91b4-6ab5c12b1b38(OCS.15).jpg "Search for OCS users in Lync Server Control Panel")</span></span>  

8.  <span data-ttu-id="ae13c-117">Wählen Sie einen Benutzer aus, den Sie in den lync Server 2013 Pool umlegen möchten.</span><span class="sxs-lookup"><span data-stu-id="ae13c-117">Select a user that you want to move to the Lync Server 2013 pool.</span></span> <span data-ttu-id="ae13c-118">In diesem Beispiel verschieben wir Sara Davis.</span><span class="sxs-lookup"><span data-stu-id="ae13c-118">In this example, we will move user Sara Davis.</span></span>

9.  <span data-ttu-id="ae13c-119">Wählen Sie im Menü **Aktion** die Option **Ausgewählte Benutzer in Pool verschieben**.</span><span class="sxs-lookup"><span data-stu-id="ae13c-119">On the **Action** menu, select **Move selected users to pool**.</span></span>

10. <span data-ttu-id="ae13c-120">Wählen Sie in der Dropdownliste den lync Server 2013 Pool aus.</span><span class="sxs-lookup"><span data-stu-id="ae13c-120">From the drop-down list, select the Lync Server 2013 pool.</span></span>

11. <span data-ttu-id="ae13c-121">Klicken Sie auf **Aktion**, und klicken Sie anschließend auf **Ausgewählte Benutzer in Pool verschieben**.</span><span class="sxs-lookup"><span data-stu-id="ae13c-121">Click **Action** and then click **Move selected users to pool**.</span></span> <span data-ttu-id="ae13c-122">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ae13c-122">Click **OK**.</span></span>
    
    <span data-ttu-id="ae13c-123">![Festlegen des Ziel Pools im Dialogfeld "Benutzer migrieren"](images/JJ688109.d7dc0759-87c5-4c23-938f-361576621504(OCS.15).jpg "Festlegen des Ziel Pools im Dialogfeld "Benutzer migrieren"")</span><span class="sxs-lookup"><span data-stu-id="ae13c-123">![Setting the Destination pool in Move Users dialog](images/JJ688109.d7dc0759-87c5-4c23-938f-361576621504(OCS.15).jpg "Setting the Destination pool in Move Users dialog")</span></span>  

12. <span data-ttu-id="ae13c-124">Stellen Sie sicher, dass die Spalte **Registrierungspool** für den Benutzer jetzt den lync Server 2013 Pool enthält, der angibt, dass der Benutzer erfolgreich verschoben wurde.</span><span class="sxs-lookup"><span data-stu-id="ae13c-124">Verify that the **Registrar pool** column for the user now contains the Lync Server 2013 pool, which indicates that the user has been successfully moved</span></span>

</div>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="ae13c-125">So migrieren Sie einen Benutzer mithilfe der lync Server 2013-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="ae13c-125">To move a user by using the Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="ae13c-126">Öffnen Sie die Lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="ae13c-126">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="ae13c-127">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="ae13c-127">At the command line, type the following:</span></span>
    
        Move-CsLegacyUser -Identity "David Pelton" -Target "pool02.contoso.net"

3.  <span data-ttu-id="ae13c-128">Geben Sie anschließend an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="ae13c-128">Next, at the command line, type the following:</span></span>
    
        Get-CsUser -Identity "David Pelton"

4.  <span data-ttu-id="ae13c-129">Die **RegistrarPool** -Identität verweist nun auf den lync Server 2013-Pool.</span><span class="sxs-lookup"><span data-stu-id="ae13c-129">The **RegistrarPool** identity now points to the Lync Server 2013 pool.</span></span> <span data-ttu-id="ae13c-130">Das Vorhandensein dieser Identität zeigt, dass der Benutzer erfolgreich verschoben wurde.</span><span class="sxs-lookup"><span data-stu-id="ae13c-130">The presence of this identity confirms that the user has been successfully moved.</span></span>
    
    <span data-ttu-id="ae13c-131">![Ausgabe von Get-CsUser-Cmdlet mit Identitäts Filter](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Ausgabe von Get-CsUser-Cmdlet mit Identitäts Filter")</span><span class="sxs-lookup"><span data-stu-id="ae13c-131">![Output from Get-CsUser cmdlet with Identity filter](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Output from Get-CsUser cmdlet with Identity filter")</span></span>  
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ae13c-132">Ausführliche Informationen zum Cmdlet <STRONG>Get-CsUser</STRONG> erhalten Sie, indem Sie Folgendes ausführen: <STRONG>Get-Help Get-CsUser –Detailed</STRONG></span><span class="sxs-lookup"><span data-stu-id="ae13c-132">For details about the <STRONG>Get-CsUser</STRONG> cmdlet, run: <STRONG>Get-Help Get-CsUser –Detailed</STRONG></span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

