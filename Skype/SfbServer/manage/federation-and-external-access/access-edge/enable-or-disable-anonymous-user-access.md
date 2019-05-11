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
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: 6bc424dc0b26f794d45c5a601b468bbb78c92ef6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919451"
---
# <a name="enable-or-disable-anonymous-user-access-in-skype-for-business-server"></a><span data-ttu-id="aceac-102">Aktivieren Sie oder deaktivieren Sie den anonymen Benutzerzugriff in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="aceac-102">Enable or disable anonymous user access in Skype for Business Server</span></span>

<span data-ttu-id="aceac-103">Anonyme Benutzer sind Benutzer, die ein Benutzerkonto in Ihrer Organisation Active Directory Domain Services oder in einer unterstützten verbunddomäne nicht haben, aber zur Remote Teilnahme an einer lokalen Konferenz eingeladen werden können.</span><span class="sxs-lookup"><span data-stu-id="aceac-103">Anonymous users are users who do not have a user account in your organization's Active Directory Domain Services or in a supported federated domain, but can be invited to participate remotely in an on-premises conference.</span></span> <span data-ttu-id="aceac-104">Durch anonyme Teilnahme an Besprechungen zulassen aktivieren Sie anonyme Benutzern (d. h., Benutzer, deren Identität wird über die Besprechung oder Konferenz-Taste nur überprüft) an Besprechungen teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="aceac-104">By allowing anonymous participation in meetings you enable anonymous users (that is, users whose identity is verified through the meeting or conference key only) to join meetings.</span></span> <span data-ttu-id="aceac-105">Zulassen der anonymen Teilnahme erfordert es für Ihre Organisation zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="aceac-105">Allowing anonymous participation requires enabling it for your organization.</span></span>

<span data-ttu-id="aceac-106">Wenn Sie später vorübergehend oder endgültig Zugriff durch anonyme Benutzer zu verhindern möchten, können Sie es für Ihre Organisation deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="aceac-106">If you later want to temporarily or permanently prevent access by anonymous users, you can disable it for your organization.</span></span> <span data-ttu-id="aceac-107">Verwenden Sie das Verfahren in diesem Abschnitt zum Aktivieren oder Deaktivieren des anonymen Zugriffs für Ihre Organisation.</span><span class="sxs-lookup"><span data-stu-id="aceac-107">Use the procedure in this section to enable or disable anonymous user access for your organization.</span></span>

> [!NOTE]  
> <span data-ttu-id="aceac-108">Durch Aktivieren des anonymen Zugriffs für Ihre Organisation werden Sie nur angeben, dass Servern mit Zugriffs-edgediensts Zugriff durch anonyme Benutzer zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="aceac-108">By enabling anonymous user access for your organization you are only specifying that your servers running the Access Edge service support access by anonymous users.</span></span> <span data-ttu-id="aceac-109">Anonyme Benutzer können nicht an alle Konferenzen in Ihrer Organisation teilnehmen, bis Sie auch mindestens eine konferenzrichtlinie konfigurieren und einen oder mehrere Benutzer oder Benutzergruppen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="aceac-109">Anonymous users cannot participate in any meetings in your organization until you also configure at least one conferencing policy and apply it to one or more users or user groups.</span></span> <span data-ttu-id="aceac-110">Nur Benutzer, die anonyme Benutzer zu Besprechungen einladen können sind Benutzer, die eine konferenzrichtlinie zugeordnet sind, die Unterstützung für anonyme Benutzer konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="aceac-110">The only users that can invite anonymous users to meetings are those users that are assigned a conferencing policy that is configured to support anonymous users.</span></span> <span data-ttu-id="aceac-111">Ausführliche Informationen zum Konfigurieren von konferenzrichtlinien zur Unterstützung der anonyme Benutzer einladen finden Sie unter [Manage Conferencing Policies](../../conferencing/conferencing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="aceac-111">For details about configuring conferencing policies to support inviting anonymous users, see [Manage conferencing policies](../../conferencing/conferencing-policies.md).</span></span>

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a><span data-ttu-id="aceac-112">So aktivieren oder Deaktivieren des anonymen Zugriffs für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="aceac-112">To enable or disable anonymous user access for your organization</span></span>

1.  <span data-ttu-id="aceac-113">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="aceac-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="aceac-114">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="aceac-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="aceac-115">Klicken Sie in der linken Navigationsleiste auf **Zugriff durch externe Benutzer**und klicken Sie dann auf **Konfiguration für Zugriffsedge**.</span><span class="sxs-lookup"><span data-stu-id="aceac-115">In the left navigation bar, click **External User Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="aceac-116">Klicken Sie auf der Seite **Konfiguration für Zugriffsedge** auf **Global**, klicken Sie auf **Bearbeiten**und klicken Sie dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="aceac-116">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="aceac-117">Führen Sie in der **Konfiguration für Zugriffsedge bearbeiten**eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="aceac-117">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="aceac-118">Um Anonymer Benutzerzugriff für Ihre Organisation zu aktivieren, aktivieren Sie das Kontrollkästchen **Kommunikation mit anonymen Benutzern aktivieren** .</span><span class="sxs-lookup"><span data-stu-id="aceac-118">To enable anonymous user access for your organization, select the **Enable communications with anonymous users** check box.</span></span>
    
      - <span data-ttu-id="aceac-119">Deaktivieren Sie das Kontrollkästchen **Kommunikation mit anonymen Benutzern aktivieren** , um Anonymer Benutzerzugriff für Ihre Organisation zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="aceac-119">To disable anonymous user access for your organization, clear the **Enable communications with anonymous users** check box.</span></span>

6.  <span data-ttu-id="aceac-120">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="aceac-120">Click **Commit**.</span></span>


## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="aceac-121">Aktivieren oder Deaktivieren der Zugriff anonymer Benutzer mithilfe von Windows PowerShell-cmdlets</span><span class="sxs-lookup"><span data-stu-id="aceac-121">Enabling or disabling anonymous user access by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="aceac-122">Sie können mithilfe von Windows PowerShell und das **Set-CsAccessEdgeConfiguration** -Cmdlet Zugriff anonymer Benutzer verwalten.</span><span class="sxs-lookup"><span data-stu-id="aceac-122">You can manage anonymous user access by using Windows PowerShell and the **Set-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="aceac-123">Sie können dieses Cmdlet entweder von der Skype für Business Server-Verwaltungsshell oder aus einer Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="aceac-123">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-anonymous-user-access"></a><span data-ttu-id="aceac-124">So aktivieren Sie den anonymen Benutzerzugriff</span><span class="sxs-lookup"><span data-stu-id="aceac-124">To enable anonymous user access</span></span>

  - <span data-ttu-id="aceac-125">Zum Aktivieren des Benutzerzugriffs für anonyme legen Sie den Wert der **AllowAnonymousUsers** -Eigenschaft auf "true" ($True):</span><span class="sxs-lookup"><span data-stu-id="aceac-125">To enable anonymous user access, set the value of the **AllowAnonymousUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

## <a name="to-disable-anonymous-user-access"></a><span data-ttu-id="aceac-126">So deaktivieren Sie den anonymen Benutzerzugriff</span><span class="sxs-lookup"><span data-stu-id="aceac-126">To disable anonymous user access</span></span>

  - <span data-ttu-id="aceac-127">Um Zugriff anonymer Benutzer deaktivieren möchten, legen Sie den Wert der **AllowAnonymousUsers** -Eigenschaft auf "false" ($False):</span><span class="sxs-lookup"><span data-stu-id="aceac-127">To disable anonymous user access, set the value of the **AllowAnonymousUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False


## <a name="see-also"></a><span data-ttu-id="aceac-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aceac-128">See Also</span></span>

[<span data-ttu-id="aceac-129">Set-CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="aceac-129">Set-CsClientPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientPolicy?view=skype-ps)  
  
