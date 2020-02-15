---
title: Aktivieren oder Deaktivieren des Zugriffs durch anonyme Benutzer
ms.reviewer: ''
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ''
ms.openlocfilehash: cc0d779e2728fd2a82547b52bda57c05c7a983a3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006000"
---
# <a name="enable-or-disable-anonymous-user-access-in-skype-for-business-server"></a><span data-ttu-id="ce047-102">Aktivieren oder Deaktivieren des Zugriffs anonymer Benutzer in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ce047-102">Enable or disable anonymous user access in Skype for Business Server</span></span>

<span data-ttu-id="ce047-103">Anonyme Benutzer sind Benutzer, die nicht über ein Benutzerkonto in der Active Directory-Domänendienste Ihrer Organisation oder in einer unterstützten Verbunddomäne verfügen, aber zur Remote Teilnahme an einer lokalen Konferenz eingeladen werden können.</span><span class="sxs-lookup"><span data-stu-id="ce047-103">Anonymous users are users who do not have a user account in your organization's Active Directory Domain Services or in a supported federated domain, but can be invited to participate remotely in an on-premises conference.</span></span> <span data-ttu-id="ce047-104">Durch das Zulassen der anonymen Teilnahme an Besprechungen aktivieren Sie anonyme Benutzer (also Benutzer, deren Identität nur über den Besprechungs-oder Konferenzschlüssel überprüft wird), um an Besprechungen teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="ce047-104">By allowing anonymous participation in meetings you enable anonymous users (that is, users whose identity is verified through the meeting or conference key only) to join meetings.</span></span> <span data-ttu-id="ce047-105">Das Zulassen der anonymen Teilnahme erfordert die Aktivierung für Ihre Organisation.</span><span class="sxs-lookup"><span data-stu-id="ce047-105">Allowing anonymous participation requires enabling it for your organization.</span></span>

<span data-ttu-id="ce047-106">Wenn Sie den Zugriff durch anonyme Benutzer später vorübergehend oder dauerhaft verhindern möchten, können Sie ihn für Ihre Organisation deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="ce047-106">If you later want to temporarily or permanently prevent access by anonymous users, you can disable it for your organization.</span></span> <span data-ttu-id="ce047-107">Verwenden Sie das Verfahren in diesem Abschnitt, um den anonymen Benutzer Zugriff für Ihre Organisation zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="ce047-107">Use the procedure in this section to enable or disable anonymous user access for your organization.</span></span>

> [!NOTE]  
> <span data-ttu-id="ce047-108">Indem Sie den anonymen Benutzer Zugriff für Ihre Organisation aktivieren, geben Sie nur an, dass Ihre Server mit dem Zugriffs-Edgedienst den Zugriff durch anonyme Benutzer unterstützen.</span><span class="sxs-lookup"><span data-stu-id="ce047-108">By enabling anonymous user access for your organization you are only specifying that your servers running the Access Edge service support access by anonymous users.</span></span> <span data-ttu-id="ce047-109">Anonyme Benutzer können nur dann an Besprechungen in Ihrer Organisation teilnehmen, wenn Sie mindestens eine konferenzrichtlinie konfiguriert haben und diese auf einen oder mehrere Benutzer oder Benutzergruppen anwenden.</span><span class="sxs-lookup"><span data-stu-id="ce047-109">Anonymous users cannot participate in any meetings in your organization until you also configure at least one conferencing policy and apply it to one or more users or user groups.</span></span> <span data-ttu-id="ce047-110">Die einzigen Benutzer, die anonyme Benutzer zu Besprechungen einladen können, sind die Benutzer, denen eine konferenzrichtlinie zugewiesen ist, die für die Unterstützung anonymer Benutzer konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="ce047-110">The only users that can invite anonymous users to meetings are those users that are assigned a conferencing policy that is configured to support anonymous users.</span></span> <span data-ttu-id="ce047-111">Ausführliche Informationen zum Konfigurieren von Konferenzrichtlinien zur Unterstützung der Einladung anonymer Benutzer finden Sie unter [Manage Conferencing Policies](../../conferencing/conferencing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="ce047-111">For details about configuring conferencing policies to support inviting anonymous users, see [Manage conferencing policies](../../conferencing/conferencing-policies.md).</span></span>

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a><span data-ttu-id="ce047-112">So aktivieren oder deaktivieren Sie den anonymen Benutzer Zugriff für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="ce047-112">To enable or disable anonymous user access for your organization</span></span>

1.  <span data-ttu-id="ce047-113">Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="ce047-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ce047-114">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="ce047-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="ce047-115">Klicken Sie in der linken Navigationsleiste auf **Zugriff durch externe Benutzer** und dann auf **Konfiguration für Zugriffsedge**.</span><span class="sxs-lookup"><span data-stu-id="ce047-115">In the left navigation bar, click **External User Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="ce047-116">Klicken Sie auf der Seite **Konfiguration für Zugriffsedge** auf **Global**, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="ce047-116">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="ce047-117">Führen Sie im Abschnitt **Konfiguration für Zugriffsedge bearbeiten** eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="ce047-117">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="ce047-118">Aktivieren Sie das Kontrollkästchen **Kommunikation mit anonymen Benutzern aktivieren** , um den anonymen Benutzer Zugriff für Ihre Organisation zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="ce047-118">To enable anonymous user access for your organization, select the **Enable communications with anonymous users** check box.</span></span>
    
      - <span data-ttu-id="ce047-119">Deaktivieren Sie das Kontrollkästchen **Kommunikation mit anonymen Benutzern aktivieren** , um den anonymen Benutzer Zugriff für Ihre Organisation zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="ce047-119">To disable anonymous user access for your organization, clear the **Enable communications with anonymous users** check box.</span></span>

6.  <span data-ttu-id="ce047-120">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="ce047-120">Click **Commit**.</span></span>


## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="ce047-121">Aktivieren oder Deaktivieren des Zugriffs durch anonyme Benutzer mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="ce047-121">Enabling or disabling anonymous user access by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="ce047-122">Sie können den anonymen Benutzer Zugriff mit Windows PowerShell und dem Cmdlet " **csaccessedgeconfiguration nicht angeben** " verwalten.</span><span class="sxs-lookup"><span data-stu-id="ce047-122">You can manage anonymous user access by using Windows PowerShell and the **Set-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="ce047-123">Sie können dieses Cmdlet entweder über die Skype for Business Server Management-Shell oder über eine Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="ce047-123">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-anonymous-user-access"></a><span data-ttu-id="ce047-124">So aktivieren Sie den anonymen Benutzer Zugriff</span><span class="sxs-lookup"><span data-stu-id="ce047-124">To enable anonymous user access</span></span>

  - <span data-ttu-id="ce047-125">Zum Aktivieren des Zugriffs durch anonyme Benutzer legen Sie den Wert der **AllowAnonymousUsers** -Eigenschaft auf true ($true) fest:</span><span class="sxs-lookup"><span data-stu-id="ce047-125">To enable anonymous user access, set the value of the **AllowAnonymousUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

## <a name="to-disable-anonymous-user-access"></a><span data-ttu-id="ce047-126">So deaktivieren Sie den anonymen Benutzer Zugriff</span><span class="sxs-lookup"><span data-stu-id="ce047-126">To disable anonymous user access</span></span>

  - <span data-ttu-id="ce047-127">Wenn Sie den anonymen Benutzer Zugriff deaktivieren möchten, legen Sie den Wert der **AllowAnonymousUsers** -Eigenschaft auf false ($false) fest:</span><span class="sxs-lookup"><span data-stu-id="ce047-127">To disable anonymous user access, set the value of the **AllowAnonymousUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False


## <a name="see-also"></a><span data-ttu-id="ce047-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ce047-128">See Also</span></span>

[<span data-ttu-id="ce047-129">Gruppe-CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="ce047-129">Set-CsClientPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy?view=skype-ps)  
  
