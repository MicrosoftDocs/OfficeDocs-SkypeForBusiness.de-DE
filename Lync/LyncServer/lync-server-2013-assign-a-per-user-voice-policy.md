---
title: 'Lync Server 2013: Zuweisen einer VoIP-Richtlinie für einzelne Benutzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user voice policy
ms:assetid: 9ee47ee7-1030-43b8-a4dc-bf685ea24659
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688155(v=OCS.15)
ms:contentKeyID: 49733758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c3818ae60cd9ae3e8537bf17bee01508e32dfa26
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723405"
---
# <a name="assign-a-per-user-voice-policy-in-lync-server-2013"></a><span data-ttu-id="3f4d0-102">Zuweisen einer VoIP-Richtlinie für einzelne Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3f4d0-102">Assign a per-user voice policy in Lync Server 2013</span></span>

 


<span data-ttu-id="3f4d0-103">VoIP-Richtlinien auf globaler und Websiteebene werden automatisch allen lync Server 2013-Benutzerkonten zugewiesen, die für Enterprise-VoIP aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="3f4d0-103">Global and site-level voice policies are automatically assigned to all Lync Server 2013 user accounts that are enabled for Enterprise Voice.</span></span> <span data-ttu-id="3f4d0-104">Sie können bestimmten Benutzern auch Sprachrichtlinien zuweisen, indem Sie entweder die lync Server 2013-Systemsteuerung oder die lync Server 2013-Verwaltungsshell verwenden.</span><span class="sxs-lookup"><span data-stu-id="3f4d0-104">You can also assign voice policies to specific users by using either the Lync Server 2013 Control Panel or the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="3f4d0-105">Verwenden Sie die in diesem Thema beschriebenen Verfahren, um lync Server-Benutzern explizit Richtlinien für einzelne Benutzer zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="3f4d0-105">Use the procedures in this topic to explicitly assign per-user policies to Lync Server users.</span></span>

## <a name="to-assign-a-user-specific-voice-policy-using-the-lync-server-control-panel"></a><span data-ttu-id="3f4d0-106">So weisen Sie mithilfe der lync Server-Systemsteuerung eine benutzerspezifische VoIP-Richtlinie zu</span><span class="sxs-lookup"><span data-stu-id="3f4d0-106">To assign a user-specific voice policy using the Lync Server Control Panel</span></span>

1.  <span data-ttu-id="3f4d0-107">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="3f4d0-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3f4d0-108">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="3f4d0-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3f4d0-109">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3f4d0-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3f4d0-110">Klicken Sie in der linken Navigationsleiste auf **Benutzer** und suchen Sie anschließend nach dem Benutzerkonto, das Sie konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="3f4d0-110">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="3f4d0-111">Klicken Sie in der Tabelle mit den Suchergebnissen auf das Benutzerkonto, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="3f4d0-111">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="3f4d0-112">Wählen Sie in **lync Server-Benutzer bearbeiten** unter **VoIP-Richtlinie**die Benutzerrichtlinie aus, die Sie anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="3f4d0-112">In **Edit Lync Server User** under **Voice policy**, select the user policy that you want to apply.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="3f4d0-113">Die <STRONG> &lt;automatischen&gt; </STRONG> Einstellungen gelten für den Standardserver oder die globalen Richtlinieneinstellungen.</span><span class="sxs-lookup"><span data-stu-id="3f4d0-113">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server or global policy settings.</span></span>



## <a name="assigning-a-per-user-voice-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="3f4d0-114">Zuweisen einer pro-Benutzer-VoIP-Richtlinie mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="3f4d0-114">Assigning a Per-User Voice Policy by using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="3f4d0-115">Sie können VoIP-Richtlinien für einzelne Benutzer mithilfe von Windows PowerShell und dem Cmdlet **Grant-CsVoicePolicy** zuweisen.</span><span class="sxs-lookup"><span data-stu-id="3f4d0-115">You can assign per-user voice policies by using Windows PowerShell and the **Grant-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="3f4d0-116">Sie können dieses Cmdlet in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="3f4d0-116">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="3f4d0-117">Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="3f4d0-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-voice-policy-to-a-single-user"></a><span data-ttu-id="3f4d0-118">So weisen Sie einem einzelnen Benutzer eine VoIP-Richtlinie pro Benutzer zu</span><span class="sxs-lookup"><span data-stu-id="3f4d0-118">To assign a per-user voice policy to a single user</span></span>

  - <span data-ttu-id="3f4d0-119">Mit dem folgenden Befehl wird dem Benutzer Ken Myers die Richtlinie für die benutzerspezifische VoIP-RedmondVoicePolicy zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="3f4d0-119">The following command assigns the per-user voice policy RedmondVoicePolicy to the user Ken Myer.</span></span>
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

## <a name="to-assign-a-per-user-voice-policy-to-multiple-users"></a><span data-ttu-id="3f4d0-120">So weisen Sie mehreren Benutzern eine VoIP-Richtlinie pro Benutzer zu</span><span class="sxs-lookup"><span data-stu-id="3f4d0-120">To assign a per-user voice policy to multiple users</span></span>

  - <span data-ttu-id="3f4d0-121">Dieser Befehl weist allen Benutzern, die über Konten in der Organisationseinheit Finanzen in Active Directory verfügen, die VoIP-Richtlinien für einzelne Benutzer zu FinanceVoicePolicy.</span><span class="sxs-lookup"><span data-stu-id="3f4d0-121">This command assigns the per-user voice policy FinanceVoicePolicy to all the users who have accounts in the Finance OU in Active Directory.</span></span> <span data-ttu-id="3f4d0-122">Weitere Informationen zu dem in diesem Befehl verwendeten ou-Parameter finden Sie in der Dokumentation für das Cmdlet [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="3f4d0-122">For more information on the OU parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -OU "ou=Finance,ou=North America,dc=litwareinc,dc=com" | Grant-CsVoicePolicy -PolicyName "FinanceVoicePolicy"

## <a name="to-unassign-a-per-user-voice-policy"></a><span data-ttu-id="3f4d0-123">So heben Sie die Zuweisung einer VoIP-Richtlinie für einzelne Benutzer auf</span><span class="sxs-lookup"><span data-stu-id="3f4d0-123">To unassign a per-user voice policy</span></span>

  - <span data-ttu-id="3f4d0-124">Mit dem folgenden Befehl wird die Zuweisung einer einzelnen Benutzer-VoIP-Richtlinie, die Ken Myers zuvor zugewiesen wurde, aufheben.</span><span class="sxs-lookup"><span data-stu-id="3f4d0-124">The following command unassigns any per-user voice policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="3f4d0-125">Anschließend wird Ken Myer automatisch mithilfe der globalen Richtlinie oder, soweit vorhanden, mit seiner lokalen Standortrichtlinie verwaltet.</span><span class="sxs-lookup"><span data-stu-id="3f4d0-125">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="3f4d0-126">Eine Standortrichtlinie hat Vorrang vor der globalen Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="3f4d0-126">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="3f4d0-127">Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Grant-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398828\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="3f4d0-127">For more information, see the help topic for the [Grant-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398828\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="3f4d0-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3f4d0-128">See Also</span></span>


[<span data-ttu-id="3f4d0-129">Deaktivieren eines Benutzers für Enterprise-VoIP in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3f4d0-129">Disable a user for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-disable-a-user-for-enterprise-voice.md)  


[<span data-ttu-id="3f4d0-130">Verwaltungsshell für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3f4d0-130">Lync Server 2013 Management Shell</span></span>](lync-server-2013-lync-server-management-shell.md)

