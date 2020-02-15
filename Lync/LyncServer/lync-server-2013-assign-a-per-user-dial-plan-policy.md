---
title: 'Lync Server 2013: Zuweisen einer Richtlinie für den Wählplan auf Benutzerbasis'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user dial plan policy
ms:assetid: 9fea861f-7770-4cae-9b1f-2a960595bfc9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688156(v=OCS.15)
ms:contentKeyID: 49733760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ea17e772bd98501b0d50674a2b82a9abb0e0b38
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043707"
---
# <a name="assign-a-per-user-dial-plan-policy-in-lync-server-2013"></a><span data-ttu-id="806fe-102">Zuweisen einer benutzerbezogenen Wähl Plan Richtlinie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="806fe-102">Assign a per-user dial plan policy in Lync Server 2013</span></span>

 


<span data-ttu-id="806fe-p101">Für den Abschluss der Benutzerkontokonfiguration für Benutzer von Enterprise-VoIP oder Benutzer von Einwahlkonferenzen müssen dem Benutzer Wähleinstellungen zugewiesen werden. Für die Benutzerkonten werden automatisch die globalen Wähleinstellungen verwendet oder, sofern vorhanden und Sie keine benutzerbezogenen Wähleinstellungen explizit zuweisen, die Wähleinstellungen auf Standortebene verwendet. Wenn Sie die globalen Wähleinstellungen oder den Standortwählplan für alle Benutzer verwenden möchten, die für Enterprise VoIP aktiviert sind, können Sie diesen Abschnitt überspringen.</span><span class="sxs-lookup"><span data-stu-id="806fe-p101">To complete user account configuration for either users of Enterprise Voice or users of dial-in conferencing, the user must be assigned a dial plan. User accounts will automatically use the global dial plan or, if one exists, the site-level dial plan when you do not explicitly assign an existing per-user dial plan. If you want to use the global or site dial plan for all users that are enabled for Enterprise Voice, you can skip this section.</span></span>

## <a name="to-assign-a-dial-plan-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="806fe-106">So weisen Sie einen Wählplan mithilfe der lync Server 2013-Systemsteuerung zu</span><span class="sxs-lookup"><span data-stu-id="806fe-106">To assign a dial plan by using the Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="806fe-107">Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="806fe-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="806fe-108">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="806fe-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="806fe-109">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="806fe-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="806fe-110">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="806fe-110">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="806fe-111">Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, das aktiviert werden soll, und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="806fe-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="806fe-112">Klicken Sie in der Tabelle auf das Benutzerkonto, dem Sie Einwähleinstellungen zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="806fe-112">In the table, click the user account that you want to assign a dial plan.</span></span>

6.  <span data-ttu-id="806fe-113">Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="806fe-113">On the **Edit** menu, click **Show details**.</span></span>

7.  <span data-ttu-id="806fe-114">Klicken Sie auf der Seite **Lync Server-Benutzer bearbeiten** unter **Telefonie** auf **Enterprise-VoIP**.</span><span class="sxs-lookup"><span data-stu-id="806fe-114">On the **Edit Lync Server User** page, under **Telephony**, click **Enterprise Voice**.</span></span>

8.  <span data-ttu-id="806fe-115">Klicken Sie auf **Wählplanrichtlinie**, und wählen Sie dann die gewünschten Einwähleinstellungen aus.</span><span class="sxs-lookup"><span data-stu-id="806fe-115">Click **Dial plan policy**, and then choose the desired dial plan.</span></span>

9.  <span data-ttu-id="806fe-116">Klicken Sie auf **Commit**.</span><span class="sxs-lookup"><span data-stu-id="806fe-116">Click **Commit**.</span></span>

<span data-ttu-id="806fe-117">Ausführliche Informationen zum Konfigurieren von Wählplänen finden Sie unter [Konfigurieren von Wählplänen in lync Server 2013](lync-server-2013-configuring-dial-plans.md) Thema.</span><span class="sxs-lookup"><span data-stu-id="806fe-117">For details about configuring dial plans, see the [Configuring dial plans in Lync Server 2013](lync-server-2013-configuring-dial-plans.md) topic.</span></span>

## <a name="assign-a-per-user-dial-plan-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="806fe-118">Zuweisen eines benutzerbezogenen Wählplans mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="806fe-118">Assign a Per-User Dial Plan by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="806fe-119">Sie können benutzerspezifische Wählpläne mit Windows PowerShell und dem Cmdlet **Grant-CsdialPlan** zuweisen.</span><span class="sxs-lookup"><span data-stu-id="806fe-119">You can assign per-user dial plans with Windows PowerShell and the **Grant-CsdialPlan** cmdlet.</span></span> <span data-ttu-id="806fe-120">Sie können dieses Cmdlet entweder über die lync Server 2013 Management-Shell oder über eine Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="806fe-120">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="806fe-121">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="806fe-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a><span data-ttu-id="806fe-122">So weisen Sie einem einzelnen Benutzer einen Wählplan pro Benutzer zu</span><span class="sxs-lookup"><span data-stu-id="806fe-122">To assign a per-user dial plan to a single user</span></span>

  - <span data-ttu-id="806fe-123">Mithilfe des folgenden Befehls werden dem Benutzer Ken Myer die benutzerbezogenen Einwähleinstellungen RedmondDialPlan zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="806fe-123">The following command assigns the per-user dial plan RedmondDialPlan to the user Ken Myer.</span></span>
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"

## <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a><span data-ttu-id="806fe-124">So weisen Sie mehreren Benutzern einen Wählplan pro Benutzer zu</span><span class="sxs-lookup"><span data-stu-id="806fe-124">To assign a per-user dial plan to multiple users</span></span>

  - <span data-ttu-id="806fe-125">Mithilfe dieses Befehls werden die benutzerbezogenen Einwähleinstellungen RedmondDialPlan allen Benutzern zugewiesen, die in Redmond arbeiten.</span><span class="sxs-lookup"><span data-stu-id="806fe-125">This command assigns the per-user dial plan RedmondDialPlan to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="806fe-126">Weitere Informationen zum LdapFilter-Parameter, der in diesem Befehl verwendet wird, finden Sie in der Dokumentation zum Cmdlet [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="806fe-126">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"

## <a name="to-unassign-a-per-user-dial-plan"></a><span data-ttu-id="806fe-127">So heben Sie die Zuweisung von benutzerbezogenen Wähleinstellungen auf</span><span class="sxs-lookup"><span data-stu-id="806fe-127">To unassign a per-user dial plan</span></span>

  - <span data-ttu-id="806fe-p105">Mithilfe des folgenden Befehls wird die Zuweisung der benutzerbezogenen Einwähleinstellungen aufgehoben, die Ken Myer zuvor zugewiesen wurde. Nachdem die Zuweisung der benutzerbezogenen Einwähleinstellungen aufgehoben wurde, wird Ken Myer automatisch mithilfe der globalen Einwähleinstellungen, seines lokalen Standortwählplans (sofern vorhanden) oder mithilfe der Wähleinstellungen auf Dienstebene für seine Registrierung oder sein PSTN-Gateway verwaltet. Wähleinstellungen auf Dienstebene haben Vorrang vor jeglichen Standortwählplänen, und ein Standortwählplan hat Vorrang vor den globalen Einwähleinstellungen.</span><span class="sxs-lookup"><span data-stu-id="806fe-p105">The following command unassigns any per-user dial plan previously assigned to Ken Myer. After the per-user dial plan is unassigned, Ken Myer will automatically be managed by using the global dial plan, his local site dial plan (if one exists), or the service-scope dial plan assigned to his Registrar or PSTN gateway. A service scope dial plan takes precedence over any site dial plan, and a site dial plan takes precedence over the global dial plan.</span></span>
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="806fe-131">Weitere Informationen finden Sie im Hilfethema zum [Grant-CsDialPlan-](https://technet.microsoft.com/library/gg398547\(v=ocs.15\)) Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="806fe-131">For more information, see the help topic for the [Grant-CsDialPlan](https://technet.microsoft.com/library/gg398547\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="806fe-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="806fe-132">See Also</span></span>


[<span data-ttu-id="806fe-133">Konfigurieren von Wählplänen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="806fe-133">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)  
[<span data-ttu-id="806fe-134">Für lync Server 2013 aktivierte Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="806fe-134">User accounts enabled for Lync Server 2013</span></span>](lync-server-2013-user-accounts-enabled-for-lync-server.md)

