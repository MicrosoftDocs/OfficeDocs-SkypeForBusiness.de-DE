---
title: 'Lync Server 2013: Entfernen eines Benutzerkontos von lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove a user account from Lync Server
ms:assetid: 2f512aba-e358-45ae-af58-74312ee9c514
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688008(v=OCS.15)
ms:contentKeyID: 49733596
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97ee26fd15eb9df9174fd33cf9a45a6fe49411af
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746825"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-a-user-account-from-lync-server-2013"></a><span data-ttu-id="57431-102">Entfernen eines Benutzerkontos aus lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="57431-102">Remove a user account from Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="57431-103">_**Letztes Änderungsdatum des Themas:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="57431-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="57431-104">Sie können das folgende Verfahren verwenden, um ein zuvor hinzugefügtes Benutzerkonto in lync Server 2013 zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="57431-104">You can use the following procedure to remove a previously added user account in Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="57431-105">Wenn Sie einen Benutzer entfernen, gehen alle Einstellungen verloren, die Sie für das Benutzerkonto konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="57431-105">Removing a user will cause you to lose any settings you configured for the user account.</span></span> <span data-ttu-id="57431-106">Wenn Sie stattdessen ein Benutzerkonto vorübergehend deaktivieren möchten, lesen Sie das Thema <A href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">deaktivieren oder erneutes Aktivieren des Benutzerkontos für lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="57431-106">If you would like to temporarily disable a user account instead, see the topic <A href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Disable or re-enable user account for Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-remove-a-user-account-by-using-lync-server-management-shell"></a><span data-ttu-id="57431-107">So entfernen Sie ein Benutzerkonto mithilfe der lync Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="57431-107">To remove a user account by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="57431-108">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="57431-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="57431-109">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="57431-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="57431-110">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="57431-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="57431-111">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="57431-111">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="57431-112">Geben Sie im Feld **Benutzer suchen** den gesamten oder den ersten Teil des Anzeigenamens, des Vornamens, des Nachnamens, des SAM-Kontos (Security Accounts Manager), der SIP-Adresse oder des Uniform Resource Identifier (URI) des Benutzerkontos ein, das Sie deaktivieren oder erneut aktivieren möchten, und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="57431-112">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="57431-113">Klicken Sie in der Tabelle auf das Benutzerkonto, das Sie entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="57431-113">In the table, click the user account that you want to remove.</span></span>

6.  <span data-ttu-id="57431-114">Klicken Sie im Menü **Aktion** auf **aus lync Server entfernen**, und es wird ein Dialogfeld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="57431-114">On the **Action** menu, select **Remove from Lync Server**, and a dialog box appears.</span></span>

7.  <span data-ttu-id="57431-115">Wählen Sie im Dialogfeld **OK** aus, um den Benutzer zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="57431-115">From the dialog box, select **OK** to remove the user.</span></span>

</div>

<div>

## <a name="removing-user-accounts-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="57431-116">Entfernen von Benutzerkonten mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="57431-116">Removing User Accounts by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="57431-117">Sie können Benutzerkonten mithilfe des Cmdlets Disable-CsUser entfernen.</span><span class="sxs-lookup"><span data-stu-id="57431-117">You can remove user accounts by using the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="57431-118">Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Windows PowerShell-Remotesitzung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="57431-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="57431-119">Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="57431-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-user-account"></a><span data-ttu-id="57431-120">So entfernen Sie ein Benutzerkonto</span><span class="sxs-lookup"><span data-stu-id="57431-120">To remove a user account</span></span>

  - <span data-ttu-id="57431-121">Wenn Sie ein Benutzerkonto entfernen möchten, verwenden Sie das Cmdlet Disable-CsUser.</span><span class="sxs-lookup"><span data-stu-id="57431-121">To remove a user account, use the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="57431-122">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="57431-122">For example:</span></span>
    
        Disable-CsUser -Identity "Ken Myer"
    
    <span data-ttu-id="57431-123">Nachdem dieser Befehl ausgeführt wurde, gibt es keine Möglichkeit, das Konto und seine vorherigen Einstellungen wieder zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="57431-123">After this command has run there is no way to re-enable the account and its previous settings.</span></span> <span data-ttu-id="57431-124">Stattdessen müssen Sie das Cmdlet Enable-CsUser verwenden, um ein nagelneues Konto für Ken Myers zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="57431-124">Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.</span></span>

</div>

<span data-ttu-id="57431-125">Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/Disable-CsUser) .</span><span class="sxs-lookup"><span data-stu-id="57431-125">For more information, see the help topic for the [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/Disable-CsUser) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="57431-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="57431-126">See Also</span></span>


[<span data-ttu-id="57431-127">Deaktivieren oder erneutes Aktivieren des Benutzerkontos für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="57431-127">Disable or re-enable user account for Lync Server 2013</span></span>](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  


[<span data-ttu-id="57431-128">Aktivieren und Deaktivieren von Benutzern für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="57431-128">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

