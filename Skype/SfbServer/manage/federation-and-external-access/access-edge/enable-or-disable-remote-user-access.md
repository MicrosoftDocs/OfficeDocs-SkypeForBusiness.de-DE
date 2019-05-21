---
title: Aktivieren oder Deaktivieren des Zugriffs durch Remotebenutzer
ms.reviewer: ''
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Wenn Sie den Remotebenutzerzugriff für Remotebenutzer aktivieren, werden die unterstützten Remotebenutzer über das Internet verbunden und müssen nicht über ein VPN eine Verbindung herstellen, um mit internen Benutzern über Skype for Business Server zusammenzuarbeiten.
ms.openlocfilehash: dde2bbb2d71d84bc9102683afc37208e3c4616bd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280236"
---
# <a name="enable-or-disable-remote-user-access-in-skype-for-business-server"></a><span data-ttu-id="e1e32-103">Aktivieren oder Deaktivieren des Remotebenutzerzugriffs in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e1e32-103">Enable or disable remote user access in Skype for Business Server</span></span>

<span data-ttu-id="e1e32-104">Bei Remote Benutzern handelt es sich um Benutzer in Ihrer Organisation, die eine persistente Active Directory-Identität innerhalb der Organisation aufweisen.</span><span class="sxs-lookup"><span data-stu-id="e1e32-104">Remote users are users in your organization who have a persistent Active Directory identity within the organization.</span></span> <span data-ttu-id="e1e32-105">Remote Benutzer können sich häufig über ein virtuelles privates Netzwerk (VPN) bei Skype for Business Server von außerhalb Ihres Netzwerks anmelden, wenn diese nicht mit dem Netzwerk Ihrer Organisation verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="e1e32-105">Remote users often sign in to Skype for Business Server from outside your network by using a virtual private network (VPN) when they are not connected to your organization’s network.</span></span> <span data-ttu-id="e1e32-106">Zu den Remotebenutzern gehören Mitarbeiter, die zu Hause oder unterwegs arbeiten, und andere Remotemitarbeiter, beispielsweise vertrauenswürdige Anbieter, denen Enterprise-Anmeldeinformationen gewährt wurden.</span><span class="sxs-lookup"><span data-stu-id="e1e32-106">Remote users include employees working at home or on the road and other remote workers, such as trusted vendors, who have been granted enterprise credentials.</span></span> <span data-ttu-id="e1e32-107">Wenn Sie den Remotebenutzerzugriff für Remotebenutzer aktivieren, werden die unterstützten Remotebenutzer über das Internet verbunden und müssen nicht über ein VPN eine Verbindung herstellen, um mit internen Benutzern über Skype for Business Server zusammenzuarbeiten.</span><span class="sxs-lookup"><span data-stu-id="e1e32-107">If you enable remote user access for remote users, supported remote users connect over the Internet and do not have to connect using a VPN in order to collaborate with internal users using Skype for Business Server.</span></span>

<span data-ttu-id="e1e32-108">Wenn Sie den Zugriff durch Remotebenutzer unterstützen möchten, müssen Sie den Zugriff durch Remotebenutzer aktivieren.</span><span class="sxs-lookup"><span data-stu-id="e1e32-108">To support remote user access, you must enable remote user access.</span></span> <span data-ttu-id="e1e32-109">Wenn Sie den Remotebenutzerzugriff aktivieren, aktivieren Sie ihn für die gesamte Organisation.</span><span class="sxs-lookup"><span data-stu-id="e1e32-109">When you enable remote user access, you enable it for your entire organization.</span></span> <span data-ttu-id="e1e32-110">Wenn Sie später den Remotebenutzerzugriff vorübergehend oder dauerhaft verhindern möchten, können Sie ihn für Ihre Organisation deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="e1e32-110">If you later want to temporarily or permanently prevent remote user access, you can disable it for your organization.</span></span> <span data-ttu-id="e1e32-111">Verwenden Sie das Verfahren in diesem Abschnitt, um den Remotebenutzerzugriff für Ihre Organisation zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="e1e32-111">Use the procedure in this section to enable or disable remote user access for your organization.</span></span>


> [!NOTE]  
> <span data-ttu-id="e1e32-112">Das Aktivieren des Remotebenutzerzugriffs gibt nur an, dass Ihre Server, auf denen der Access Edge-Dienst ausgeführt wird, die Kommunikation mit Remotebenutzern unterstützen, aber Remotebenutzer nicht an Instant Messaging (im) oder Konferenzen in Ihrer Organisation teilnehmen können, bis Sie auch die Konfiguration unter mindestens eine Richtlinie zum Verwalten der Verwendung von Remotebenutzerzugriff.</span><span class="sxs-lookup"><span data-stu-id="e1e32-112">Enabling remote user access only specifies that your servers running the Access Edge service support communications with remote users, but remote users cannot participate in instant messaging (IM) or conferences in your organization until you also configure at least one policy to manage the use of remote user access.</span></span> <span data-ttu-id="e1e32-113">Skype for Business Server-Richtlinieneinstellungen, die auf einer Richtlinienebene angewendet werden, können Einstellungen außer Kraft setzen, die auf einer anderen Richtlinienebene angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="e1e32-113">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="e1e32-114">Die Priorität der Skype for Business Server-Richtlinie lautet: Benutzerrichtlinien (der meiste Einfluss) überschreibt eine Website Richtlinie, und eine Website Richtlinie überschreibt eine globale Richtlinie (geringster Einfluss).</span><span class="sxs-lookup"><span data-stu-id="e1e32-114">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="e1e32-115">Mit anderen Worten: Je geringer der Abstand zwischen Richtlinieneinstellung und betroffenem Objekt, desto stärker der Einfluss auf das Objekt.</span><span class="sxs-lookup"><span data-stu-id="e1e32-115">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> <span data-ttu-id="e1e32-116">Details zum Konfigurieren von Richtlinien für die Verwendung von Remotebenutzerzugriff finden Sie unter [Konfigurieren von Richtlinien zum Steuern des Remotebenutzerzugriffs in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="e1e32-116">For details about configuring policies for the use of remote user access, see [Configure policies to control remote user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span></span>


## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a><span data-ttu-id="e1e32-117">So aktivieren oder deaktivieren Sie den Remotebenutzerzugriff für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="e1e32-117">To enable or disable remote user access for your organization</span></span>

1.  <span data-ttu-id="e1e32-118">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="e1e32-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e1e32-119">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="e1e32-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="e1e32-120">Klicken Sie in der linken Navigationsleiste auf **Partnerverbund und externer Zugriff** und dann auf **Zugriffs-Edgekonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="e1e32-120">In the left navigation bar, click **Federation and External Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="e1e32-121">Klicken Sie auf der Seite **Access Edge Configuration** auf **Global**, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="e1e32-121">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="e1e32-122">Führen Sie in " **Access-Edge-Konfiguration bearbeiten**" eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="e1e32-122">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="e1e32-123">Aktivieren Sie das Kontrollkästchen **Remotebenutzerzugriff aktivieren** , um den Remotebenutzerzugriff für Ihre Organisation zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="e1e32-123">To enable remote user access for your organization, select the **Enable remote user access** check box.</span></span>
    
      - <span data-ttu-id="e1e32-124">Deaktivieren Sie das Kontrollkästchen **Remotebenutzerzugriff aktivieren** , um den Remotebenutzerzugriff für Ihre Organisation zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="e1e32-124">To disable remote user access for your organization, clear the **Enable remote user access** check box.</span></span>

6.  <span data-ttu-id="e1e32-125">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="e1e32-125">Click **Commit**.</span></span>

<span data-ttu-id="e1e32-126">Damit Remotebenutzer sich bei ihren Servern mit Skype for Business Server anmelden können, müssen Sie auch mindestens eine Richtlinie für den externen Zugriff konfigurieren, um den Zugriff durch Remotebenutzer zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="e1e32-126">To enable remote users to sign in to your servers running Skype for Business Server, you must also configure at least one external access policy to support remote user access.</span></span> <span data-ttu-id="e1e32-127">Ausführliche Informationen finden Sie unter [Konfigurieren von Richtlinien zum Steuern des Remotebenutzerzugriffs in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="e1e32-127">For details, see [Configure policies to control remote user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span></span>


## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e1e32-128">Aktivieren oder Deaktivieren des Remotebenutzerzugriffs mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="e1e32-128">Enabling or disabling remote user access by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="e1e32-129">Der Remote Benutzer Zugriff kann mithilfe von Windows PowerShell und dem Cmdlet "csaccessedgeconfiguration nicht angeben" verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="e1e32-129">Remote user access can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="e1e32-130">Dieses Cmdlet kann entweder über die Skype for Business Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e1e32-130">This cmdlet can be run either from the Skype for Business Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-remote-user-access"></a><span data-ttu-id="e1e32-131">So aktivieren Sie den Remotebenutzerzugriff</span><span class="sxs-lookup"><span data-stu-id="e1e32-131">To enable remote user access</span></span>

  - <span data-ttu-id="e1e32-132">Um den Remotebenutzerzugriff zu aktivieren, legen Sie den Wert der **AllowOutsideUsers** -Eigenschaft auf true ($true) fest:</span><span class="sxs-lookup"><span data-stu-id="e1e32-132">To enable remote user access, set the value of the **AllowOutsideUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

## <a name="to-disable-remote-user-access"></a><span data-ttu-id="e1e32-133">So deaktivieren Sie den Remotebenutzerzugriff</span><span class="sxs-lookup"><span data-stu-id="e1e32-133">To disable remote user access</span></span>

  - <span data-ttu-id="e1e32-134">Um den Remotebenutzerzugriff zu deaktivieren, legen Sie den Wert der **AllowOutsideUsers** -Eigenschaft auf false ($false) fest:</span><span class="sxs-lookup"><span data-stu-id="e1e32-134">To disable remote user access, set the value of the **AllowOutsideUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False


