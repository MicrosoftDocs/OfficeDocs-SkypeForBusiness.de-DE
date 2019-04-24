---
title: Aktivieren oder Deaktivieren des Versands eines Archivierungshaftungsausschlusses an Verbundpartner
ms.reviewer: ''
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48185391
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: 859b4e295a90fd44ce69efe4af7daa63ddc8812c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32197863"
---
# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-skype-for-business-server"></a><span data-ttu-id="ba239-102">Aktivieren Sie oder deaktivieren Sie das Senden einer Archiving Disclaimer an Verbundpartner in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="ba239-102">Enable or disable sending an Archiving disclaimer to federated partners in Skype for Business Server</span></span>

<span data-ttu-id="ba239-103">Der Zeitpunkt Edgeserver bereitgestellt und aktiviert den Verbund für Ihr Unternehmen, Sie sollten angegeben haben, ob automatisch des Archivierungshaftungsausschlusses an Verbundpartner senden.</span><span class="sxs-lookup"><span data-stu-id="ba239-103">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to automatically send the archiving disclaimer to federated partners.</span></span> <span data-ttu-id="ba239-104">Wenn Sie externe Kommunikation archivieren, sollten Sie das Senden eines Archivierungshaftungsausschlusses aktivieren.</span><span class="sxs-lookup"><span data-stu-id="ba239-104">If you archive external communications, you should enable the sending of an archiving disclaimer.</span></span> <span data-ttu-id="ba239-105">Verwenden Sie das Verfahren in diesem Thema, um die Konfiguration zu ändern.</span><span class="sxs-lookup"><span data-stu-id="ba239-105">Use the procedure in this topic to change that configuration.</span></span>

> [!NOTE]
> <span data-ttu-id="ba239-106">Das folgende Verfahren wird davon ausgegangen, dass Sie den Verbund für Ihre Organisation bereits aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="ba239-106">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="ba239-107">Ausführliche Informationen zur Aktivierung des Verbunds finden Sie unter [Aktivieren oder Deaktivieren des Zugriffs durch Remotebenutzer](enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="ba239-107">For details about enabling federation, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>


## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a><span data-ttu-id="ba239-108">So aktivieren oder deaktivieren Sie das Senden eines Archivierungshaftungsausschlusses an Verbundpartner</span><span class="sxs-lookup"><span data-stu-id="ba239-108">To enable or disable sending of an archiving disclaimer to federated partners</span></span>

1.  <span data-ttu-id="ba239-109">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="ba239-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ba239-110">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="ba239-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="ba239-111">Klicken Sie in der linken Navigationsleiste auf **Zugriff durch externe Benutzer**, und dann auf **Konfiguration für Zugriffsedge**.</span><span class="sxs-lookup"><span data-stu-id="ba239-111">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="ba239-112">Klicken Sie auf der Registerkarte **Zugriffs-Edgekonfiguration** auf **Global**, klicken Sie auf **Bearbeiten** und dann auf **Details einblenden**.</span><span class="sxs-lookup"><span data-stu-id="ba239-112">On the **Access Edge Configuration** tab, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="ba239-113">**Konfiguration für Zugriffsedge bearbeiten**, unter der **Kommunikation mit Partnerbenutzern aktivieren**aktivieren Sie oder deaktivieren Sie das Kontrollkästchen **Archivierungshaftungsausschluss an Verbundpartner senden** zum Aktivieren oder deaktivieren automatisch Senden der Archivierung Haftungsausschluss.</span><span class="sxs-lookup"><span data-stu-id="ba239-113">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Send archiving disclaimer to federated partners** check box to enable or disable automatically sending the archiving disclaimer.</span></span>

6.  <span data-ttu-id="ba239-114">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="ba239-114">Click **Commit**.</span></span>

<span data-ttu-id="ba239-115">Um Verbundbenutzer Zusammenarbeit mit Benutzern in Ihrer Skype für Business Server-Bereitstellung zu aktivieren, müssen Sie auch mindestens eine externe Zugriffsrichtlinie zur Unterstützung der partnerbenutzerzugriff konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="ba239-115">To enable federated users to collaborate with users in your Skype for Business Server deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="ba239-116">Ausführliche Informationen zum Steuern des Zugriffs für spezifische Partnerdomänen an finden Sie unter [Konfigurieren der Unterstützung für zulässige externe Domänen](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="ba239-116">For details about controlling access for specific federated domains, see [Configure support for allowed external domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span></span>


## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="ba239-117">Aktivieren oder Deaktivieren des Archivierungshaftungsausschlusses mithilfe von Windows PowerShell-cmdlets</span><span class="sxs-lookup"><span data-stu-id="ba239-117">Enabling or disabling the archiving disclaimer by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="ba239-118">Die Verwendung von des Archivierungshaftungsausschlusses kann mithilfe von Windows PowerShell und das Set-CsAccessEdgeConfiguration-Cmdlet verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="ba239-118">The use of the archiving disclaimer can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="ba239-119">Dieses Cmdlet kann von der Skype für Business Server-Verwaltungsshell oder von einer remote Windows PowerShell-Sitzung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ba239-119">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-the-archiving-disclaimer"></a><span data-ttu-id="ba239-120">Zum Aktivieren des Archivierungshaftungsausschlusses</span><span class="sxs-lookup"><span data-stu-id="ba239-120">To enable the archiving disclaimer</span></span>

  - <span data-ttu-id="ba239-121">Zum Aktivieren des Archivierungshaftungsausschlusses legen Sie den Wert der Eigenschaft **EnableArchivingDisclaimer** auf „True“ ($True) fest:</span><span class="sxs-lookup"><span data-stu-id="ba239-121">To enable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

## <a name="to-disable-the-archiving-disclaimer"></a><span data-ttu-id="ba239-122">Zum Deaktivieren des Archivierungshaftungsausschlusses</span><span class="sxs-lookup"><span data-stu-id="ba239-122">To disable the archiving disclaimer</span></span>

  - <span data-ttu-id="ba239-123">Zum Deaktivieren des Archivierungshaftungsausschlusses legen Sie den Wert der Eigenschaft **EnableArchivingDisclaimer** auf „False“ ($False) fest:</span><span class="sxs-lookup"><span data-stu-id="ba239-123">To disable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False


