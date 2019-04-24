---
title: Aktivieren oder Deaktivieren des Zugriffs durch Remotebenutzer
ms.reviewer: ''
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Wenn Sie den Zugriff durch Remotebenutzer für Remotebenutzer aktivieren, unterstützte Remotebenutzer über das Internet herstellen und müssen keine Verbindung herstellen über ein VPN, um die Zusammenarbeit mit internen Benutzern Skype für Business Server verwenden.
ms.openlocfilehash: aea136e6c8758fd646a20b8bc7a64a393d45a3e7
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199927"
---
# <a name="enable-or-disable-remote-user-access-in-skype-for-business-server"></a><span data-ttu-id="4bb8e-103">Aktivieren Sie oder deaktivieren Sie des Zugriffs durch Remotebenutzer in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="4bb8e-103">Enable or disable remote user access in Skype for Business Server</span></span>

<span data-ttu-id="4bb8e-104">Remote-Benutzer sind Benutzer in Ihrer Organisation, die über eine beständige Active Directory-Identität innerhalb der Organisation verfügen.</span><span class="sxs-lookup"><span data-stu-id="4bb8e-104">Remote users are users in your organization who have a persistent Active Directory identity within the organization.</span></span> <span data-ttu-id="4bb8e-105">Remotebenutzer anmelden häufig zu Skype für Business Server von außerhalb des Netzwerks mithilfe von ein virtuelles privates Netzwerk (VPN), wenn sie nicht mit dem Netzwerk Ihrer Organisation verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="4bb8e-105">Remote users often sign in to Skype for Business Server from outside your network by using a virtual private network (VPN) when they are not connected to your organization’s network.</span></span> <span data-ttu-id="4bb8e-106">Remotebenutzer sind Mitarbeiter, die zu Hause arbeiten oder unterwegs sind und andere Remotemitarbeiter wie vertrauenswürdigen Anbieter, die erteilt worden Anmeldeinformationen für das Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="4bb8e-106">Remote users include employees working at home or on the road and other remote workers, such as trusted vendors, who have been granted enterprise credentials.</span></span> <span data-ttu-id="4bb8e-107">Wenn Sie den Zugriff durch Remotebenutzer für Remotebenutzer aktivieren, unterstützte Remotebenutzer über das Internet herstellen und müssen keine Verbindung herstellen über ein VPN, um die Zusammenarbeit mit internen Benutzern Skype für Business Server verwenden.</span><span class="sxs-lookup"><span data-stu-id="4bb8e-107">If you enable remote user access for remote users, supported remote users connect over the Internet and do not have to connect using a VPN in order to collaborate with internal users using Skype for Business Server.</span></span>

<span data-ttu-id="4bb8e-108">Zur Unterstützung des Zugriffs durch Remotebenutzer, müssen Sie den Zugriff durch Remotebenutzer aktivieren.</span><span class="sxs-lookup"><span data-stu-id="4bb8e-108">To support remote user access, you must enable remote user access.</span></span> <span data-ttu-id="4bb8e-109">Wenn Sie den Zugriff durch Remotebenutzer aktivieren, können Sie es für die gesamte Organisation.</span><span class="sxs-lookup"><span data-stu-id="4bb8e-109">When you enable remote user access, you enable it for your entire organization.</span></span> <span data-ttu-id="4bb8e-110">Wenn Sie später vorübergehend oder endgültig Zugriff durch Remotebenutzer verhindern möchten, können Sie es für Ihre Organisation deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="4bb8e-110">If you later want to temporarily or permanently prevent remote user access, you can disable it for your organization.</span></span> <span data-ttu-id="4bb8e-111">Verwenden Sie das Verfahren in diesem Abschnitt zum Aktivieren oder Deaktivieren der Zugriff durch Remotebenutzer für Ihre Organisation.</span><span class="sxs-lookup"><span data-stu-id="4bb8e-111">Use the procedure in this section to enable or disable remote user access for your organization.</span></span>


> [!NOTE]  
> <span data-ttu-id="4bb8e-112">Aktivieren des Zugriffs durch Remotebenutzer angegeben nur Servern mit Zugriffs-edgediensts unterstützen die Kommunikation mit Remotebenutzern, dass remote-Benutzer können nicht teilnehmen instant messaging (IM) oder Konferenzen in Ihrer Organisation, bis Sie auch auf Konfigurieren mindestens eine Richtlinie auf die Verwendung der des Zugriffs durch Remotebenutzer verwalten.</span><span class="sxs-lookup"><span data-stu-id="4bb8e-112">Enabling remote user access only specifies that your servers running the Access Edge service support communications with remote users, but remote users cannot participate in instant messaging (IM) or conferences in your organization until you also configure at least one policy to manage the use of remote user access.</span></span> <span data-ttu-id="4bb8e-113">Skype für Business Server aufgeführt, die auf einer Richtlinienebene angewendet werden kann Einstellungen außer Kraft setzen, die auf einer anderen Richtlinienebene angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="4bb8e-113">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="4bb8e-114">Skype für Business Server RichtlinienPrioritäten ist: Benutzerrichtlinie (die meisten beeinflussen) überschreibt eine Standortrichtlinie, und klicken Sie dann eine Standortrichtlinie überschreibt eine globale Richtlinie (mindestens beeinflussen).</span><span class="sxs-lookup"><span data-stu-id="4bb8e-114">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="4bb8e-115">Mit anderen Worten: Je geringer der Abstand zwischen Richtlinieneinstellung und betroffenem Objekt, desto stärker der Einfluss auf das Objekt.</span><span class="sxs-lookup"><span data-stu-id="4bb8e-115">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> <span data-ttu-id="4bb8e-116">Ausführliche Informationen zum Konfigurieren von Richtlinien für die Verwendung des Zugriffs durch Remotebenutzer finden Sie unter [Konfigurieren von Richtlinien zur Steuerung des Zugriffs durch Remotebenutzer in Skype für Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="4bb8e-116">For details about configuring policies for the use of remote user access, see [Configure policies to control remote user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span></span>


## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a><span data-ttu-id="4bb8e-117">So aktivieren oder Deaktivieren der Zugriff durch Remotebenutzer für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="4bb8e-117">To enable or disable remote user access for your organization</span></span>

1.  <span data-ttu-id="4bb8e-118">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="4bb8e-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4bb8e-119">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="4bb8e-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="4bb8e-120">Klicken Sie in der linken Navigationsleiste auf **Partnerverbund und externer Zugriff** und dann auf **Zugriffs-Edgekonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="4bb8e-120">In the left navigation bar, click **Federation and External Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="4bb8e-121">Klicken Sie auf der Seite **Konfiguration für Zugriffsedge** auf **Global**, klicken Sie auf **Bearbeiten**und klicken Sie dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="4bb8e-121">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="4bb8e-122">Führen Sie in der **Konfiguration für Zugriffsedge bearbeiten**eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="4bb8e-122">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="4bb8e-123">Um den Zugriff durch Remotebenutzer für Ihre Organisation zu aktivieren, aktivieren Sie das Kontrollkästchen **Zugriff durch Remotebenutzer aktivieren** .</span><span class="sxs-lookup"><span data-stu-id="4bb8e-123">To enable remote user access for your organization, select the **Enable remote user access** check box.</span></span>
    
      - <span data-ttu-id="4bb8e-124">Deaktivieren Sie das Kontrollkästchen **Zugriff durch Remotebenutzer aktivieren** , um den Zugriff durch Remotebenutzer für Ihre Organisation zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="4bb8e-124">To disable remote user access for your organization, clear the **Enable remote user access** check box.</span></span>

6.  <span data-ttu-id="4bb8e-125">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="4bb8e-125">Click **Commit**.</span></span>

<span data-ttu-id="4bb8e-126">Um Remotebenutzern zur Anmeldung bei Servern mit Skype für Business Server zu aktivieren, müssen Sie auch mindestens eine externe Zugriffsrichtlinie, um die Unterstützung des Zugriffs durch Remotebenutzer konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="4bb8e-126">To enable remote users to sign in to your servers running Skype for Business Server, you must also configure at least one external access policy to support remote user access.</span></span> <span data-ttu-id="4bb8e-127">Weitere Informationen hierzu finden Sie unter [Konfigurieren von Richtlinien zur Steuerung des Zugriffs durch Remotebenutzer in Skype für Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="4bb8e-127">For details, see [Configure policies to control remote user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span></span>


## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="4bb8e-128">Aktivieren oder Deaktivieren des Zugriffs durch Remotebenutzer mithilfe von Windows PowerShell-cmdlets</span><span class="sxs-lookup"><span data-stu-id="4bb8e-128">Enabling or disabling remote user access by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="4bb8e-129">Zugriff durch Remotebenutzer kann mithilfe von Windows PowerShell und das Set-CsAccessEdgeConfiguration-Cmdlet verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="4bb8e-129">Remote user access can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="4bb8e-130">Dieses Cmdlet kann von der Skype für Business Server 2013-Verwaltungsshell oder von einer remote Windows PowerShell-Sitzung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="4bb8e-130">This cmdlet can be run either from the Skype for Business Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-remote-user-access"></a><span data-ttu-id="4bb8e-131">Zum Aktivieren des Zugriffs durch Remotebenutzer</span><span class="sxs-lookup"><span data-stu-id="4bb8e-131">To enable remote user access</span></span>

  - <span data-ttu-id="4bb8e-132">Um den Zugriff durch Remotebenutzer aktivieren, legen Sie den Wert der **AllowOutsideUsers** -Eigenschaft auf "true" ($True):</span><span class="sxs-lookup"><span data-stu-id="4bb8e-132">To enable remote user access, set the value of the **AllowOutsideUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

## <a name="to-disable-remote-user-access"></a><span data-ttu-id="4bb8e-133">Deaktivieren des Zugriffs durch Remotebenutzer</span><span class="sxs-lookup"><span data-stu-id="4bb8e-133">To disable remote user access</span></span>

  - <span data-ttu-id="4bb8e-134">Zum Deaktivieren des Zugriffs durch Remotebenutzer legen Sie den Wert der **AllowOutsideUsers** -Eigenschaft auf "false" ($False) fest:</span><span class="sxs-lookup"><span data-stu-id="4bb8e-134">To disable remote user access, set the value of the **AllowOutsideUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False


