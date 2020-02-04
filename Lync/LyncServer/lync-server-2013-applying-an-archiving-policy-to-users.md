---
title: 'Lync Server 2013: Anwenden einer Archivierungsrichtlinie auf Benutzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Applying an Archiving policy to users
ms:assetid: 624a7d3e-389d-403a-97e5-f7bb17023ef3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521004(v=OCS.15)
ms:contentKeyID: 48184290
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d1cf0db76b888b9774a16f7a6353ccf1b399eb3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737585"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="applying-an-archiving-policy-to-users-in-lync-server-2013"></a><span data-ttu-id="7f6c7-102">Anwenden einer Archivierungsrichtlinie auf Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f6c7-102">Applying an Archiving policy to users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7f6c7-103">_**Letztes Änderungsdatum des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="7f6c7-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="7f6c7-104">Wenn ein Benutzer für lync Server 2013 aktiviert wurde und Sie eine oder mehrere Benutzerrichtlinien für die Archivierung für Benutzer erstellt haben, die sich auf lync Server 2013 befinden, können Sie die Archivierungsunterstützung für bestimmte Benutzer implementieren, indem Sie die entsprechenden Richtlinien auf diese Benutzer oder Benutzergruppen anwenden.</span><span class="sxs-lookup"><span data-stu-id="7f6c7-104">If a user has been enabled for Lync Server 2013 and you have created one or more user policies for archiving for users homed on Lync Server 2013, you can implement archiving support for specific users by applying the appropriate policies to those users or user groups.</span></span> <span data-ttu-id="7f6c7-105">Wenn Sie beispielsweise eine Richtlinie erstellen, um die Archivierung interner Kommunikation zu unterstützen, können Sie diese auf mindestens einen Benutzer oder eine Benutzergruppe anwenden, um die Archivierung der lync Server 2013-Kommunikation des Benutzers zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="7f6c7-105">For example, if you create a policy to support archiving of internal communications, you can apply it to at least one user or user group to support archiving of the user’s Lync Server 2013 communications.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7f6c7-106">Wenn Sie die Microsoft Exchange-Integration für Ihre Bereitstellung aktiviert haben, Steuern Exchange-in-situ-Speicherrichtlinien, ob die Archivierung für die Benutzer aktiviert ist, die sich in Exchange 2013 befinden, und dass ihre Postfächer in-situ-Speicher abgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="7f6c7-106">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="7f6c7-107">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Einrichten von Richtlinien für die Archivierung in lync Server 2013 bei Verwendung der Exchange Server-Integration</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="7f6c7-107">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="7f6c7-108">Sie sollten alle geeigneten Optionen in den Archivierungs Konfigurationen angeben, bevor Sie die Archivierung aktivieren.</span><span class="sxs-lookup"><span data-stu-id="7f6c7-108">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="7f6c7-109">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Verwalten von Archivierungs Konfigurationsoptionen in lync Server 2013 für Ihre Organisation, Websites und Pools</A> in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="7f6c7-109">For details, see <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</A> in the Operations documentation.</span></span>



</div>

<span data-ttu-id="7f6c7-110">Verwenden Sie das in diesem Thema beschriebene Verfahren, um eine zuvor erstellte Archivierungs Benutzerrichtlinie auf ein oder mehrere Benutzerkonten oder Benutzergruppen anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="7f6c7-110">Use the procedure in this topic to apply a previously created Archiving user policy to one or more user accounts or user groups.</span></span>

<div>

## <a name="to-apply-an-archiving-user-policy-to-a-user-account"></a><span data-ttu-id="7f6c7-111">So wenden Sie eine Archivierungs Benutzerrichtlinie auf ein Benutzerkonto an</span><span class="sxs-lookup"><span data-stu-id="7f6c7-111">To apply an archiving user policy to a user account</span></span>

1.  <span data-ttu-id="7f6c7-112">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsArchivingAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="7f6c7-112">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7f6c7-113">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="7f6c7-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7f6c7-114">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="7f6c7-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7f6c7-115">Klicken Sie in der linken Navigationsleiste auf **Benutzer** und suchen Sie anschließend nach dem Benutzerkonto, das Sie konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="7f6c7-115">In the left navigation bar, click **Users**, and then search for the user account that you want to configure.</span></span>

4.  <span data-ttu-id="7f6c7-116">Klicken Sie in der Tabelle mit den Suchergebnissen auf das Benutzerkonto, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="7f6c7-116">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="7f6c7-117">Wählen Sie in **lync Server-Benutzer bearbeiten** unter **Archivierungsrichtlinie**die Archivierungs Benutzerrichtlinie aus, die Sie anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="7f6c7-117">In **Edit Lync Server User** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7f6c7-118">Die <STRONG> &lt;automatischen&gt; </STRONG> Einstellungen gelten für die standardmäßigen Server Installationseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="7f6c7-118">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server installation settings.</span></span> <span data-ttu-id="7f6c7-119">Diese Einstellungen werden vom Server automatisch übernommen.</span><span class="sxs-lookup"><span data-stu-id="7f6c7-119">These settings are applied automatically by the server.</span></span>

    
    </div>

6.  <span data-ttu-id="7f6c7-120">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="7f6c7-120">Click **Commit**.</span></span>

</div>

<div>

## <a name="assigning-a-per-user-archiving-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="7f6c7-121">Zuweisen einer pro-Benutzer-Archivierungsrichtlinie mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="7f6c7-121">Assigning a Per-User Archiving Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="7f6c7-122">Archivierungsrichtlinien für einzelne Benutzer können mithilfe von Windows PowerShell und dem Cmdlet **Grant-CsArchivingPolicy** zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="7f6c7-122">Per-user archiving policies can be assigned by using Windows PowerShell and the **Grant-CsArchivingPolicy** cmdlet.</span></span> <span data-ttu-id="7f6c7-123">Sie können dieses Cmdlet entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="7f6c7-123">You can run this cmdlet from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="7f6c7-124">Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="7f6c7-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-assign-a-per-user-archiving-policy-to-a-single-user"></a><span data-ttu-id="7f6c7-125">So weisen Sie einem einzelnen Benutzer eine Archivierungsrichtlinie pro Benutzer zu</span><span class="sxs-lookup"><span data-stu-id="7f6c7-125">To assign a per-user archiving policy to a single user</span></span>

  - <span data-ttu-id="7f6c7-126">Mithilfe des folgenden Befehls wird die benutzerbezogene Archivierungsrichtlinie „RedmondArchivingPolicy“ dem Benutzer Jonas Baar zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="7f6c7-126">The following command assigns the per-user archiving policy RedmondArchivingPolicy to the user Ken Myer.</span></span>
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-archiving-policy-to-multiple-users"></a><span data-ttu-id="7f6c7-127">So weisen Sie eine Archivierungsrichtlinie für einzelne Benutzer mehreren Benutzern zu</span><span class="sxs-lookup"><span data-stu-id="7f6c7-127">To assign a per-user archiving policy to multiple users</span></span>

  - <span data-ttu-id="7f6c7-128">Dieser Befehl weist allen Benutzern, die Konten im Registrierungspool ATL-CS-001.litwareinc.com haben, die Archivierungsrichtlinien für einzelne Benutzer zu RedmondArchivingPolicy.</span><span class="sxs-lookup"><span data-stu-id="7f6c7-128">This command assigns the per-user archiving policy RedmondArchivingPolicy to all users who have accounts homed on the Registrar pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="7f6c7-129">Details zu dem in diesem Befehl verwendeten Filter Parameter finden Sie in der Dokumentation zum Cmdlet " [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) ".</span><span class="sxs-lookup"><span data-stu-id="7f6c7-129">For details about the Filter parameter used in this command, see the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet documentation.</span></span>
    
        Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-archiving-policy"></a><span data-ttu-id="7f6c7-130">So weisen Sie eine Archivierungsrichtlinie für einzelne Benutzer zu</span><span class="sxs-lookup"><span data-stu-id="7f6c7-130">To assign a per-user archiving policy</span></span>

  - <span data-ttu-id="7f6c7-131">Mit dem folgenden Befehl wird die Zuweisung einer pro-Benutzer-Archivierungsrichtlinie, die Ken Myers zuvor zugewiesen wurde, aufheben.</span><span class="sxs-lookup"><span data-stu-id="7f6c7-131">The following command unassigns any per-user archiving policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="7f6c7-132">Anschließend wird Ken Myer automatisch mithilfe der globalen Richtlinie oder, soweit vorhanden, mit seiner lokalen Standortrichtlinie verwaltet.</span><span class="sxs-lookup"><span data-stu-id="7f6c7-132">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="7f6c7-133">Eine Standortrichtlinie hat Vorrang vor der globalen Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="7f6c7-133">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null

</div>

<span data-ttu-id="7f6c7-134">Ausführliche Informationen finden Sie in der Dokumentation zu [Grant-CsArchivingPolicy-](https://docs.microsoft.com/powershell/module/skype/Grant-CsArchivingPolicy) Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="7f6c7-134">For details, see the [Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsArchivingPolicy) cmdlet documentation.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7f6c7-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7f6c7-135">See Also</span></span>


[<span data-ttu-id="7f6c7-136">Verwalten der Archivierung interner und externer Kommunikation in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f6c7-136">Managing the Archiving of internal and external communications in Lync Server 2013</span></span>](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
[<span data-ttu-id="7f6c7-137">Zuweisen von Richtlinien für einzelne Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f6c7-137">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

