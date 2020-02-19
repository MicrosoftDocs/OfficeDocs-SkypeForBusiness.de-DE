---
title: 'Lync Server 2013: anonymen Benutzer Zugriff aktivieren oder deaktivieren'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable anonymous user access
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c873953b16004f514871c0cf4b4708ad41c0117
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137744"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-anonymous-user-access-in-lync-server-2013"></a><span data-ttu-id="c0492-102">Aktivieren oder Deaktivieren des Zugriffs anonymer Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c0492-102">Enable or disable anonymous user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0492-103">_**Letztes Änderungsstand des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="c0492-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="c0492-104">Anonyme Benutzer sind Benutzer, die nicht über ein Benutzerkonto in der Active Directory-Domänendienste Ihrer Organisation oder in einer unterstützten Verbunddomäne verfügen, aber zur Remote Teilnahme an einer lokalen Konferenz eingeladen werden können.</span><span class="sxs-lookup"><span data-stu-id="c0492-104">Anonymous users are users who do not have a user account in your organization's Active Directory Domain Services or in a supported federated domain, but can be invited to participate remotely in an on-premises conference.</span></span> <span data-ttu-id="c0492-105">Durch das Zulassen der anonymen Teilnahme an Besprechungen aktivieren Sie anonyme Benutzer (also Benutzer, deren Identität nur über den Besprechungs-oder Konferenzschlüssel überprüft wird), um an Besprechungen teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="c0492-105">By allowing anonymous participation in meetings you enable anonymous users (that is, users whose identity is verified through the meeting or conference key only) to join meetings.</span></span> <span data-ttu-id="c0492-106">Das Zulassen der anonymen Teilnahme erfordert die Aktivierung für Ihre Organisation.</span><span class="sxs-lookup"><span data-stu-id="c0492-106">Allowing anonymous participation requires enabling it for your organization.</span></span>

<span data-ttu-id="c0492-107">Wenn Sie den Zugriff durch anonyme Benutzer später vorübergehend oder dauerhaft verhindern möchten, können Sie ihn für Ihre Organisation deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="c0492-107">If you later want to temporarily or permanently prevent access by anonymous users, you can disable it for your organization.</span></span> <span data-ttu-id="c0492-108">Verwenden Sie das Verfahren in diesem Abschnitt, um den anonymen Benutzer Zugriff für Ihre Organisation zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="c0492-108">Use the procedure in this section to enable or disable anonymous user access for your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c0492-109">Indem Sie den anonymen Benutzer Zugriff für Ihre Organisation aktivieren, geben Sie nur an, dass Ihre Server mit dem Zugriffs-Edgedienst den Zugriff durch anonyme Benutzer unterstützen.</span><span class="sxs-lookup"><span data-stu-id="c0492-109">By enabling anonymous user access for your organization you are only specifying that your servers running the Access Edge service support access by anonymous users.</span></span> <span data-ttu-id="c0492-110">Anonyme Benutzer können nur dann an Besprechungen in Ihrer Organisation teilnehmen, wenn Sie mindestens eine konferenzrichtlinie konfiguriert haben und diese auf einen oder mehrere Benutzer oder Benutzergruppen anwenden.</span><span class="sxs-lookup"><span data-stu-id="c0492-110">Anonymous users cannot participate in any meetings in your organization until you also configure at least one conferencing policy and apply it to one or more users or user groups.</span></span> <span data-ttu-id="c0492-111">Die einzigen Benutzer, die anonyme Benutzer zu Besprechungen einladen können, sind die Benutzer, denen eine konferenzrichtlinie zugewiesen ist, die für die Unterstützung anonymer Benutzer konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="c0492-111">The only users that can invite anonymous users to meetings are those users that are assigned a conferencing policy that is configured to support anonymous users.</span></span> <span data-ttu-id="c0492-112">Ausführliche Informationen zum Konfigurieren von Konferenzrichtlinien zur Unterstützung der Einladung anonymer Benutzer finden Sie unter <A href="lync-server-2013-conferencing-policies.md">Conferencing Policies in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c0492-112">For details about configuring conferencing policies to support inviting anonymous users, see <A href="lync-server-2013-conferencing-policies.md">Conferencing policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a><span data-ttu-id="c0492-113">So aktivieren oder deaktivieren Sie den anonymen Benutzer Zugriff für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="c0492-113">To enable or disable anonymous user access for your organization</span></span>

1.  <span data-ttu-id="c0492-114">Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="c0492-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c0492-115">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="c0492-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c0492-116">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c0492-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c0492-117">Klicken Sie in der linken Navigationsleiste auf **Zugriff durch externe Benutzer** und dann auf **Konfiguration für Zugriffsedge**.</span><span class="sxs-lookup"><span data-stu-id="c0492-117">In the left navigation bar, click **External User Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="c0492-118">Klicken Sie auf der Seite **Konfiguration für Zugriffsedge** auf **Global**, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="c0492-118">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="c0492-119">Führen Sie im Abschnitt **Konfiguration für Zugriffsedge bearbeiten** eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="c0492-119">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="c0492-120">Aktivieren Sie das Kontrollkästchen **Kommunikation mit anonymen Benutzern aktivieren** , um den anonymen Benutzer Zugriff für Ihre Organisation zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="c0492-120">To enable anonymous user access for your organization, select the **Enable communications with anonymous users** check box.</span></span>
    
      - <span data-ttu-id="c0492-121">Deaktivieren Sie das Kontrollkästchen **Kommunikation mit anonymen Benutzern aktivieren** , um den anonymen Benutzer Zugriff für Ihre Organisation zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="c0492-121">To disable anonymous user access for your organization, clear the **Enable communications with anonymous users** check box.</span></span>

6.  <span data-ttu-id="c0492-122">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="c0492-122">Click **Commit**.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c0492-123">Aktivieren oder Deaktivieren des Zugriffs durch anonyme Benutzer mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="c0492-123">Enabling or Disabling Anonymous User Access by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="c0492-124">Sie können den anonymen Benutzer Zugriff mit Windows PowerShell und dem Cmdlet " **csaccessedgeconfiguration nicht angeben** " verwalten.</span><span class="sxs-lookup"><span data-stu-id="c0492-124">You can manage anonymous user access by using Windows PowerShell and the **Set-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="c0492-125">Sie können dieses Cmdlet entweder über die lync Server 2013 Management-Shell oder über eine Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="c0492-125">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="c0492-126">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="c0492-126">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-anonymous-user-access"></a><span data-ttu-id="c0492-127">So aktivieren Sie den anonymen Benutzer Zugriff</span><span class="sxs-lookup"><span data-stu-id="c0492-127">To enable anonymous user access</span></span>

  - <span data-ttu-id="c0492-128">Zum Aktivieren des Zugriffs durch anonyme Benutzer legen Sie den Wert der **AllowAnonymousUsers** -Eigenschaft auf true ($true) fest:</span><span class="sxs-lookup"><span data-stu-id="c0492-128">To enable anonymous user access, set the value of the **AllowAnonymousUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

</div>

<div>

## <a name="to-disable-anonymous-user-access"></a><span data-ttu-id="c0492-129">So deaktivieren Sie den anonymen Benutzer Zugriff</span><span class="sxs-lookup"><span data-stu-id="c0492-129">To disable anonymous user access</span></span>

  - <span data-ttu-id="c0492-130">Wenn Sie den anonymen Benutzer Zugriff deaktivieren möchten, legen Sie den Wert der **AllowAnonymousUsers** -Eigenschaft auf false ($false) fest:</span><span class="sxs-lookup"><span data-stu-id="c0492-130">To disable anonymous user access, set the value of the **AllowAnonymousUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c0492-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c0492-131">See Also</span></span>


[<span data-ttu-id="c0492-132">Referenz für konferenzrichtlinieneinstellungen für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c0492-132">Conferencing policy settings reference for Lync Server 2013</span></span>](lync-server-2013-conferencing-policy-settings-reference.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

