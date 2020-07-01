---
title: 'Lync Server 2013: Zuweisen einer VoIP-Richtlinie pro Benutzer'
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
ms.openlocfilehash: 1528ef6124193023a0e5938caac7b40c2c6187a2
ms.sourcegitcommit: 9b1c138b39fd87e239a7b1c5051f30c633e7d813
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "44943928"
---
# <a name="assign-a-per-user-voice-policy-in-lync-server-2013"></a><span data-ttu-id="600fd-102">Zuweisen einer VoIP-Richtlinie pro Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="600fd-102">Assign a per-user voice policy in Lync Server 2013</span></span>

 


<span data-ttu-id="600fd-103">VoIP-Richtlinien auf globaler und auf Standortebene werden automatisch allen lync Server 2013 Benutzerkonten zugewiesen, die für Enterprise-VoIP aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="600fd-103">Global and site-level voice policies are automatically assigned to all Lync Server 2013 user accounts that are enabled for Enterprise Voice.</span></span> <span data-ttu-id="600fd-104">Sie können VoIP-Richtlinien auch bestimmten Benutzern zuweisen, indem Sie entweder die lync Server 2013-Systemsteuerung oder die lync Server 2013-Verwaltungsshell verwenden.</span><span class="sxs-lookup"><span data-stu-id="600fd-104">You can also assign voice policies to specific users by using either the Lync Server 2013 Control Panel or the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="600fd-105">Verwenden Sie die Verfahren in diesem Thema, um lync Server Benutzern explizit benutzerspezifische Richtlinien zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="600fd-105">Use the procedures in this topic to explicitly assign per-user policies to Lync Server users.</span></span>

## <a name="to-assign-a-user-specific-voice-policy-using-the-lync-server-control-panel"></a><span data-ttu-id="600fd-106">So weisen Sie eine benutzerspezifische VoIP-Richtlinie mithilfe der lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="600fd-106">To assign a user-specific voice policy using the Lync Server Control Panel</span></span>

1.  <span data-ttu-id="600fd-107">Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="600fd-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="600fd-108">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="600fd-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="600fd-109">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="600fd-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="600fd-110">Klicken Sie auf der linken Navigationsleiste auf **Benutzer**, und suchen Sie anschließend nach dem Benutzerkonto, das Sie konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="600fd-110">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="600fd-111">Klicken Sie in der Tabelle mit den Suchergebnissen auf das Benutzerkonto, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="600fd-111">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="600fd-112">Wählen Sie in **Lync Server-Benutzer bearbeiten** unter **VoIP-Richtlinie** die Benutzerrichtlinie aus, die Sie anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="600fd-112">In **Edit Lync Server User** under **Voice policy**, select the user policy that you want to apply.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="600fd-113">Durch die <STRONG> &lt; automatischen &gt; </STRONG> Einstellungen werden die Standardeinstellungen für Server oder globale Richtlinien übernommen.</span><span class="sxs-lookup"><span data-stu-id="600fd-113">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server or global policy settings.</span></span>



## <a name="assign-per-user-voice-policies"></a><span data-ttu-id="600fd-114">Zuweisen von VoIP-Richtlinien pro Benutzer</span><span class="sxs-lookup"><span data-stu-id="600fd-114">Assign per-user voice policies</span></span>

<span data-ttu-id="600fd-115">Sie können benutzerspezifische VoIP-Richtlinien mithilfe von Windows PowerShell und dem Cmdlet **Grant-CsVoicePolicy** zuweisen.</span><span class="sxs-lookup"><span data-stu-id="600fd-115">You can assign per-user voice policies by using Windows PowerShell and the **Grant-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="600fd-116">Sie können dieses Cmdlet in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="600fd-116">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="600fd-117">Informationen zum Verwenden von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie in diesem lync Server Windows PowerShell Blogbeitrag: [schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="600fd-117">To learn about using remote Windows PowerShell to connect to Lync Server, read this Lync Server Windows PowerShell blog post: [Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span>

### <a name="assign-a-per-user-voice-policy-to-a-single-user"></a><span data-ttu-id="600fd-118">Zuweisen einer benutzerbasierten VoIP-Richtlinie zu einem einzelnen Benutzer</span><span class="sxs-lookup"><span data-stu-id="600fd-118">Assign a per-user voice policy to a single user</span></span>

  - <span data-ttu-id="600fd-119">Der folgende Befehl weist die benutzerbasierte VoIP-Richtlinie "RedmondVoicePolicy" dem Benutzer "Ken Myer" zu.</span><span class="sxs-lookup"><span data-stu-id="600fd-119">The following command assigns the per-user voice policy RedmondVoicePolicy to the user Ken Myer.</span></span>
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

## <a name="assign-a-per-user-voice-policy-to-multiple-users"></a><span data-ttu-id="600fd-120">Zuweisen einer VoIP-Richtlinie für einzelne Benutzer zu mehreren Benutzern</span><span class="sxs-lookup"><span data-stu-id="600fd-120">Assign a per-user voice policy to multiple users</span></span>

  - <span data-ttu-id="600fd-121">Der folgende Befehl weist die benutzerbasierte VoIP-Richtlinie "FinanceVoicePolicy" allen Benutzern zu, die Konten in der OU "Finance" in Active Directory haben.</span><span class="sxs-lookup"><span data-stu-id="600fd-121">This command assigns the per-user voice policy FinanceVoicePolicy to all the users who have accounts in the Finance OU in Active Directory.</span></span> <span data-ttu-id="600fd-122">Weitere Informationen zu dem in diesem Befehl verwendeten ou-Parameter finden Sie in der Dokumentation zum Cmdlet [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="600fd-122">For more information on the OU parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -OU "ou=Finance,ou=North America,dc=litwareinc,dc=com" | Grant-CsVoicePolicy -PolicyName "FinanceVoicePolicy"

## <a name="unassign-a-per-user-voice-policy"></a><span data-ttu-id="600fd-123">Aufheben der Zuweisung einer VoIP-Richtlinie pro Benutzer</span><span class="sxs-lookup"><span data-stu-id="600fd-123">Unassign a per-user voice policy</span></span>

  - <span data-ttu-id="600fd-124">The following command unassigns any per-user voice policy previously assigned to Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="600fd-124">The following command unassigns any per-user voice policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="600fd-125">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span><span class="sxs-lookup"><span data-stu-id="600fd-125">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="600fd-126">A site policy takes precedence over the global policy.</span><span class="sxs-lookup"><span data-stu-id="600fd-126">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="600fd-127">Weitere Informationen finden Sie im Hilfethema zum [Grant-CsVoicePolicy-](https://technet.microsoft.com/library/gg398828\(v=ocs.15\)) Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="600fd-127">For more information, see the help topic for the [Grant-CsVoicePolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="600fd-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="600fd-128">See Also</span></span>


[<span data-ttu-id="600fd-129">Deaktivieren eines Benutzers für Enterprise-VoIP in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="600fd-129">Disable a user for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-disable-a-user-for-enterprise-voice.md)  


[<span data-ttu-id="600fd-130">Lync Server 2013 Management-Shell</span><span class="sxs-lookup"><span data-stu-id="600fd-130">Lync Server 2013 Management Shell</span></span>](lync-server-2013-lync-server-management-shell.md)

