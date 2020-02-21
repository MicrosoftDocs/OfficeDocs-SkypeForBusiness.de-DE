---
title: 'Lync Server 2013: Delegieren der administrativen Steuerung von lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delegating administrative control of Lync Server 2013
ms:assetid: 0f378eff-8ef4-4c60-9fd2-67d7ee259ef8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520951(v=OCS.15)
ms:contentKeyID: 48183418
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e93985818c62b195227323f4c0f6d5030db1f16f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190882"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delegating-administrative-control-of-lync-server-2013"></a><span data-ttu-id="dc5bf-102">Delegieren der administrativen Steuerung von lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dc5bf-102">Delegating administrative control of Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc5bf-103">_**Letztes Änderungsstand des Themas:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="dc5bf-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="dc5bf-104">In lync Server 2013 werden administrative Aufgaben an Benutzer mithilfe der neuen Funktion für die rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC) delegiert.</span><span class="sxs-lookup"><span data-stu-id="dc5bf-104">In Lync Server 2013, administrative tasks are delegated to users by using the new role-based access control (RBAC) feature.</span></span> <span data-ttu-id="dc5bf-105">Bei der Installation von lync Server werden eine Reihe von RBAC-Rollen für Sie erstellt.</span><span class="sxs-lookup"><span data-stu-id="dc5bf-105">When you install Lync Server, a number of RBAC roles are created for you.</span></span> <span data-ttu-id="dc5bf-106">Diese Rollen entsprechen universellen Sicherheitsgruppen in Active Directory-Domänendienste.</span><span class="sxs-lookup"><span data-stu-id="dc5bf-106">These roles correspond to universal security groups in Active Directory Domain Services.</span></span> <span data-ttu-id="dc5bf-107">Beispielsweise entspricht die RBAC-Rolle "cshelpdesk" der "cshelpdesk"-Gruppe, die im Container Users in Active Directory-Domänendienste gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="dc5bf-107">For example, the RBAC role CsHelpDesk corresponds to the CsHelpDesk group found in the Users container in Active Directory Domain Services.</span></span> <span data-ttu-id="dc5bf-108">Darüber hinaus ist jede RBAC-Rolle einer Gruppe von lync Server Windows PowerShell-Cmdlets zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="dc5bf-108">In addition, each RBAC role is associated with a set of Lync Server Windows PowerShell cmdlets.</span></span> <span data-ttu-id="dc5bf-109">Diese Cmdlets stellen die Aufgaben dar, die von Benutzern ausgeführt werden können, denen die gegebene RBAC-Rolle zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="dc5bf-109">These cmdlets represent the tasks that can be carried out by users who have been assigned the given RBAC role.</span></span> <span data-ttu-id="dc5bf-110">Beispielsweise wurde der "cshelpdesk"-Rolle die Cmdlets Lock-CsClientPin und UnlockCsClientPin zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="dc5bf-110">For example, the CsHelpDesk role has been assigned the Lock-CsClientPin and UnlockCsClientPin cmdlets.</span></span> <span data-ttu-id="dc5bf-111">Das bedeutet, dass Benutzer, denen die "cshelpdesk"-Rolle zugewiesen wurde, Benutzer-PIN-Nummern Sperren und entsperren können.</span><span class="sxs-lookup"><span data-stu-id="dc5bf-111">That means users who have been assigned the CsHelpDesk role can lock and unlock user PIN numbers.</span></span> <span data-ttu-id="dc5bf-112">Der "cshelpdesk"-Rolle wurde jedoch das Cmdlet New-CsVoicePolicy nicht zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="dc5bf-112">However, the CsHelpDesk role has not been assigned the New-CsVoicePolicy cmdlet.</span></span> <span data-ttu-id="dc5bf-113">Das bedeutet, dass Benutzer, denen die "cshelpdesk"-Rolle zugewiesen wurde, keine neuen VoIP-Richtlinien erstellen können.</span><span class="sxs-lookup"><span data-stu-id="dc5bf-113">That means that users who have been assigned the CsHelpDesk role cannot create new voice policies.</span></span>

<div>

## <a name="viewing-information-about-rbac-roles"></a><span data-ttu-id="dc5bf-114">Anzeigen von Informationen zu RBAC-Rollen</span><span class="sxs-lookup"><span data-stu-id="dc5bf-114">Viewing Information about RBAC Roles</span></span>

<span data-ttu-id="dc5bf-115">Sie können grundlegende Informationen zu ihren RBAC-Rollen abrufen, indem Sie den folgenden Befehl in der lync Server-Verwaltungsshell ausführen:</span><span class="sxs-lookup"><span data-stu-id="dc5bf-115">You can retrieve basic information about your RBAC roles by running the following command from within the Lync Server Management Shell:</span></span>

    Get-CsAdminRole

<span data-ttu-id="dc5bf-116">Beachten Sie, dass die Identität der RBAC-Rolle (beispielsweise CsVoiceAdministrator) eine direkte Zuordnung zu einer Sicherheitsgruppe hat, die im Container "Benutzer" in Active Directory-Domänendienste gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="dc5bf-116">Keep in mind that the Identity of the RBAC role (for example, CsVoiceAdministrator) has a direct mapping to a security group found in the Users container in Active Directory Domain Services.</span></span>

<span data-ttu-id="dc5bf-117">Um eine Liste der Cmdlets anzuzeigen, die einer Rolle zugewiesen wurden, verwenden Sie einen Befehl wie den folgenden:</span><span class="sxs-lookup"><span data-stu-id="dc5bf-117">To view a list of the cmdlets that have been assigned to a role, use a command similar to this:</span></span>

    Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets

</div>

<div>

## <a name="assigning-an-rbac-role-to-a-user"></a><span data-ttu-id="dc5bf-118">Zuweisen einer RBAC-Rolle zu einem Benutzer</span><span class="sxs-lookup"><span data-stu-id="dc5bf-118">Assigning an RBAC Role to a User</span></span>

<span data-ttu-id="dc5bf-119">Um einem Benutzer eine RBAC-Rolle zuzuweisen, müssen Sie diesen Benutzer der entsprechenden Active Directory Sicherheitsgruppe hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="dc5bf-119">To assign an RBAC role to a user, you must add that user to the appropriate Active Directory security group.</span></span> <span data-ttu-id="dc5bf-120">Um beispielsweise die CsLocationAdministrator-Rolle einem Benutzer zuzuweisen, müssen Sie diesen Benutzer der Gruppe CsLocationAdministrator hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="dc5bf-120">For example, to assign the CsLocationAdministrator role to a user, you must add that user to the CsLocationAdministrator group.</span></span> <span data-ttu-id="dc5bf-121">Dies kann durch Ausführen des folgenden Verfahrens geschehen:</span><span class="sxs-lookup"><span data-stu-id="dc5bf-121">That can be done by carrying out the following procedure:</span></span>

<span data-ttu-id="dc5bf-122">**So weisen Sie einen Benutzer einer Sicherheitsgruppe zu**</span><span class="sxs-lookup"><span data-stu-id="dc5bf-122">**To assign a user to a security group**</span></span>

1.  <span data-ttu-id="dc5bf-123">Melden Sie sich mit einem Konto, das über die Berechtigung zum Ändern der Mitgliedschaft einer Active Directory Gruppe verfügt, an einem Computer an, auf dem Active Directory Benutzer und Computer installiert wurden.</span><span class="sxs-lookup"><span data-stu-id="dc5bf-123">Using an account that has permission to modify the membership of an Active Directory group, log on to a computer where Active Directory Users and Computers has been installed.</span></span>

2.  <span data-ttu-id="dc5bf-124">Klicken Sie im **Startmenü**auf **Alle Programme**, dann auf **Verwaltung**, und klicken Sie dann auf **Benutzer und Computer Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="dc5bf-124">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>

3.  <span data-ttu-id="dc5bf-125">Erweitern Sie in Active Directory Benutzer und Computer den Namen Ihrer Domäne, und klicken Sie auf den Container **Benutzer** .</span><span class="sxs-lookup"><span data-stu-id="dc5bf-125">In Active Directory Users and Computers, expand the name of your domain and click the **Users** container.</span></span>

4.  <span data-ttu-id="dc5bf-126">Klicken Sie mit der rechten Maustaste auf die Sicherheitsgruppe **CsLocationAdministrator**, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="dc5bf-126">Right-click the security group **CsLocationAdministrator**, and then click **Properties**.</span></span>

5.  <span data-ttu-id="dc5bf-127">Klicken Sie im Dialogfeld **Eigenschaften** auf der Registerkarte **Mitglieder** auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="dc5bf-127">In the **Properties** dialog box, on the **Members** tab, click **Add**.</span></span>

6.  <span data-ttu-id="dc5bf-128">Geben Sie im Dialogfeld **Benutzer, Computer, Kontakte oder Gruppen auswählen** in das Feld **Geben Sie die zu verwendenden Objektnamen ein** den Benutzernamen oder den Anzeigenamen des Benutzers ein, der der Gruppe hinzugefügt werden soll (beispielsweise **Ken Myers**), und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="dc5bf-128">In the **Select Users, Computers, Contacts, or Groups** dialog box, type the user name or display name of the user to be added to the group (for example, **Ken Myer**) in the **Enter the object names to select** box and then click **OK**.</span></span>

7.  <span data-ttu-id="dc5bf-129">Klicken Sie im Dialogfeld **Eigenschaften** auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="dc5bf-129">In the **Properties** dialog box, click **OK**.</span></span>

<span data-ttu-id="dc5bf-130">Um sicherzustellen, dass die RBAC-Rolle zugewiesen wurde, verwenden Sie das Cmdlet [Get-CsAdminRoleAssignment](https://docs.microsoft.com/powershell/module/skype/Get-CsAdminRoleAssignment) , und übergeben Sie das Cmdlet sAMAccountName (Active Directory Anmeldename) des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="dc5bf-130">To verify that the RBAC role has been assigned, use the [Get-CsAdminRoleAssignment](https://docs.microsoft.com/powershell/module/skype/Get-CsAdminRoleAssignment) cmdlet, passing the cmdlet the SamAccountName (Active Directory logon name) of the user.</span></span> <span data-ttu-id="dc5bf-131">Führen Sie diesen Befehl beispielsweise in der lync Server-Verwaltungsshell aus:</span><span class="sxs-lookup"><span data-stu-id="dc5bf-131">For example, run this command from within the Lync Server Management Shell:</span></span>

    Get-CsAdminRoleAssignment  -Identity "kenmyer"

</div>

</div>

<span> </span>

</div>

</div>

</div>

