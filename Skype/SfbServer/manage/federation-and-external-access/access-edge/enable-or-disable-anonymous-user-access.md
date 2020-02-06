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
ms.openlocfilehash: 40b365f25abccc05a5eb5156e1c7d79106a7537c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818406"
---
# <a name="enable-or-disable-anonymous-user-access-in-skype-for-business-server"></a><span data-ttu-id="04021-102">Aktivieren oder Deaktivieren des anonymen Benutzerzugriffs in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="04021-102">Enable or disable anonymous user access in Skype for Business Server</span></span>

<span data-ttu-id="04021-103">Anonyme Benutzer sind Benutzer, die nicht über ein Benutzerkonto in den Active Directory-Domänendiensten Ihrer Organisation oder in einer unterstützten Föderationsdomäne verfügen, aber zur Remote Teilnahme an einer lokalen Konferenz eingeladen werden können.</span><span class="sxs-lookup"><span data-stu-id="04021-103">Anonymous users are users who do not have a user account in your organization's Active Directory Domain Services or in a supported federated domain, but can be invited to participate remotely in an on-premises conference.</span></span> <span data-ttu-id="04021-104">Durch das zulassen anonymer Teilnahme an Besprechungen können Sie anonyme Benutzer (also Benutzer, deren Identität nur über den Besprechungs-oder Konferenzschlüssel überprüft wird) aktivieren, um an Besprechungen teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="04021-104">By allowing anonymous participation in meetings you enable anonymous users (that is, users whose identity is verified through the meeting or conference key only) to join meetings.</span></span> <span data-ttu-id="04021-105">Das Zulassen einer anonymen Teilnahme erfordert die Aktivierung für Ihre Organisation.</span><span class="sxs-lookup"><span data-stu-id="04021-105">Allowing anonymous participation requires enabling it for your organization.</span></span>

<span data-ttu-id="04021-106">Wenn Sie den Zugriff von anonymen Benutzern später vorübergehend oder dauerhaft verhindern möchten, können Sie ihn für Ihre Organisation deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="04021-106">If you later want to temporarily or permanently prevent access by anonymous users, you can disable it for your organization.</span></span> <span data-ttu-id="04021-107">Verwenden Sie das Verfahren in diesem Abschnitt, um den anonymen Benutzer Zugriff für Ihre Organisation zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="04021-107">Use the procedure in this section to enable or disable anonymous user access for your organization.</span></span>

> [!NOTE]  
> <span data-ttu-id="04021-108">Indem Sie den anonymen Benutzer Zugriff für Ihre Organisation aktivieren, geben Sie nur an, dass die Server, auf denen der Access Edge-Dienst ausgeführt wird, den Zugriff durch anonyme Benutzer unterstützen.</span><span class="sxs-lookup"><span data-stu-id="04021-108">By enabling anonymous user access for your organization you are only specifying that your servers running the Access Edge service support access by anonymous users.</span></span> <span data-ttu-id="04021-109">Anonyme Benutzer können erst dann an Besprechungen in Ihrer Organisation teilnehmen, wenn Sie mindestens eine konferenzrichtlinie konfiguriert und auf einen oder mehrere Benutzer oder Benutzergruppen anwenden.</span><span class="sxs-lookup"><span data-stu-id="04021-109">Anonymous users cannot participate in any meetings in your organization until you also configure at least one conferencing policy and apply it to one or more users or user groups.</span></span> <span data-ttu-id="04021-110">Die einzigen Benutzer, die anonyme Benutzer zu Besprechungen einladen können, sind diejenigen Benutzer, denen eine konferenzrichtlinie zugewiesen ist, die für die Unterstützung anonymer Benutzer konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="04021-110">The only users that can invite anonymous users to meetings are those users that are assigned a conferencing policy that is configured to support anonymous users.</span></span> <span data-ttu-id="04021-111">Details zum Konfigurieren von Konferenzrichtlinien zur Unterstützung der Einladung anonymer Benutzer finden Sie unter [Verwalten von Konferenzrichtlinien](../../conferencing/conferencing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="04021-111">For details about configuring conferencing policies to support inviting anonymous users, see [Manage conferencing policies](../../conferencing/conferencing-policies.md).</span></span>

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a><span data-ttu-id="04021-112">So aktivieren oder deaktivieren Sie den anonymen Benutzer Zugriff für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="04021-112">To enable or disable anonymous user access for your organization</span></span>

1.  <span data-ttu-id="04021-113">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="04021-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="04021-114">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="04021-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="04021-115">Klicken Sie in der linken Navigationsleiste auf **externer Benutzer Zugriff**, und klicken Sie dann auf **Access-Edge-Konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="04021-115">In the left navigation bar, click **External User Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="04021-116">Klicken Sie auf der Seite **Access Edge Configuration** auf **Global**, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="04021-116">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="04021-117">Führen Sie in " **Access-Edge-Konfiguration bearbeiten**" eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="04021-117">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="04021-118">Aktivieren Sie das Kontrollkästchen **Kommunikation mit anonymen Benutzern aktivieren** , um den anonymen Benutzer Zugriff für Ihre Organisation zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="04021-118">To enable anonymous user access for your organization, select the **Enable communications with anonymous users** check box.</span></span>
    
      - <span data-ttu-id="04021-119">Wenn Sie den anonymen Benutzer Zugriff für Ihre Organisation deaktivieren möchten, deaktivieren Sie das Kontrollkästchen **Kommunikation mit anonymen Benutzern aktivieren** .</span><span class="sxs-lookup"><span data-stu-id="04021-119">To disable anonymous user access for your organization, clear the **Enable communications with anonymous users** check box.</span></span>

6.  <span data-ttu-id="04021-120">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="04021-120">Click **Commit**.</span></span>


## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="04021-121">Aktivieren oder Deaktivieren des Zugriffs auf anonyme Benutzer mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="04021-121">Enabling or disabling anonymous user access by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="04021-122">Sie können den anonymen Benutzer Zugriff mithilfe von Windows PowerShell und dem Cmdlet " **Satz-csaccessedgeconfiguration nicht angeben** " verwalten.</span><span class="sxs-lookup"><span data-stu-id="04021-122">You can manage anonymous user access by using Windows PowerShell and the **Set-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="04021-123">Sie können dieses Cmdlet entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="04021-123">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-anonymous-user-access"></a><span data-ttu-id="04021-124">So aktivieren Sie den anonymen Benutzer Zugriff</span><span class="sxs-lookup"><span data-stu-id="04021-124">To enable anonymous user access</span></span>

  - <span data-ttu-id="04021-125">Um den anonymen Benutzer Zugriff zu aktivieren, setzen Sie den Wert der **AllowAnonymousUsers** -Eigenschaft auf true ($true):</span><span class="sxs-lookup"><span data-stu-id="04021-125">To enable anonymous user access, set the value of the **AllowAnonymousUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

## <a name="to-disable-anonymous-user-access"></a><span data-ttu-id="04021-126">So deaktivieren Sie den anonymen Benutzer Zugriff</span><span class="sxs-lookup"><span data-stu-id="04021-126">To disable anonymous user access</span></span>

  - <span data-ttu-id="04021-127">Um den anonymen Benutzer Zugriff zu deaktivieren, setzen Sie den Wert der **AllowAnonymousUsers** -Eigenschaft auf false ($false):</span><span class="sxs-lookup"><span data-stu-id="04021-127">To disable anonymous user access, set the value of the **AllowAnonymousUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False


## <a name="see-also"></a><span data-ttu-id="04021-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="04021-128">See Also</span></span>

[<span data-ttu-id="04021-129">Set-CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="04021-129">Set-CsClientPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientPolicy?view=skype-ps)  
  
