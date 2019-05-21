---
title: Aktivieren oder Deaktivieren des Versands eines Archivierungshaftungsausschlusses an Verbundpartner
ms.reviewer: ''
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48185391
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: c2f64a617cae938ffe64ec8db313402785413c49
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280215"
---
# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-skype-for-business-server"></a><span data-ttu-id="a6341-102">Aktivieren oder Deaktivieren des Sendens einer Archivierungs Klausel an verbundene Partner in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a6341-102">Enable or disable sending an Archiving disclaimer to federated partners in Skype for Business Server</span></span>

<span data-ttu-id="a6341-103">Zu dem Zeitpunkt, zu dem Sie Ihre Edgeserver und den aktivierten Verbund für Ihre Organisation bereitgestellt haben, sollten Sie angegeben haben, ob die Archivierungs Verzicht automatisch an Verbundpartner gesendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a6341-103">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to automatically send the archiving disclaimer to federated partners.</span></span> <span data-ttu-id="a6341-104">Wenn Sie die externe Kommunikation archivieren, sollten Sie das Senden eines Archivierungs Verzichts aktivieren.</span><span class="sxs-lookup"><span data-stu-id="a6341-104">If you archive external communications, you should enable the sending of an archiving disclaimer.</span></span> <span data-ttu-id="a6341-105">Verwenden Sie das in diesem Thema beschriebene Verfahren, um diese Konfiguration zu ändern.</span><span class="sxs-lookup"><span data-stu-id="a6341-105">Use the procedure in this topic to change that configuration.</span></span>

> [!NOTE]
> <span data-ttu-id="a6341-106">Im folgenden Verfahren wird davon ausgegangen, dass Sie die Föderation für Ihre Organisation bereits aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="a6341-106">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="a6341-107">Details zum Aktivieren von Föderationen finden Sie unter [Aktivieren oder Deaktivieren des Remotebenutzerzugriffs](enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="a6341-107">For details about enabling federation, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>


## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a><span data-ttu-id="a6341-108">So aktivieren oder deaktivieren Sie das Senden einer Archivierungs Klausel an verbundene Partner</span><span class="sxs-lookup"><span data-stu-id="a6341-108">To enable or disable sending of an archiving disclaimer to federated partners</span></span>

1.  <span data-ttu-id="a6341-109">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="a6341-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a6341-110">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="a6341-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="a6341-111">Klicken Sie in der linken Navigationsleiste auf **externer Benutzer Zugriff**, und klicken Sie auf **Access-Edge-Konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="a6341-111">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="a6341-112">Klicken Sie auf der Registerkarte **Zugriffs-Edgekonfiguration** auf **Global**, klicken Sie auf **Bearbeiten** und dann auf **Details einblenden**.</span><span class="sxs-lookup"><span data-stu-id="a6341-112">On the **Access Edge Configuration** tab, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="a6341-113">Aktivieren oder deaktivieren Sie in " **Access-Edge-Konfiguration bearbeiten**" unter **Kommunikation mit Verbundbenutzern aktivieren**das Kontrollkästchen **Archivierungs Ausschluss an verbundene Partner senden** , um das automatische Senden der Archivierung zu aktivieren oder zu deaktivieren. Haftungsausschluss.</span><span class="sxs-lookup"><span data-stu-id="a6341-113">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Send archiving disclaimer to federated partners** check box to enable or disable automatically sending the archiving disclaimer.</span></span>

6.  <span data-ttu-id="a6341-114">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="a6341-114">Click **Commit**.</span></span>

<span data-ttu-id="a6341-115">Damit Föderationsbenutzer mit Benutzern in Ihrer Skype for Business Server-Bereitstellung zusammenarbeiten können, müssen Sie auch mindestens eine Richtlinie für den externen Zugriff konfiguriert haben, um den Verbundbenutzer Zugriff zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="a6341-115">To enable federated users to collaborate with users in your Skype for Business Server deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="a6341-116">Details zum Steuern des Zugriffs für bestimmte Verbunddomänen finden Sie unter [Konfigurieren der Unterstützung für zulässige externe Domänen](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="a6341-116">For details about controlling access for specific federated domains, see [Configure support for allowed external domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span></span>


## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a6341-117">Aktivieren oder Deaktivieren des Archivierungs Verzichts mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="a6341-117">Enabling or disabling the archiving disclaimer by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="a6341-118">Die Verwendung des Haftungsausschlusses für die Archivierung kann mithilfe von Windows PowerShell und dem Cmdlet "Satz-csaccessedgeconfiguration nicht angeben" verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="a6341-118">The use of the archiving disclaimer can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="a6341-119">Dieses Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a6341-119">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-the-archiving-disclaimer"></a><span data-ttu-id="a6341-120">So aktivieren Sie den Archivierungs Ausschluss</span><span class="sxs-lookup"><span data-stu-id="a6341-120">To enable the archiving disclaimer</span></span>

  - <span data-ttu-id="a6341-121">Zum Aktivieren des Archivierungshaftungsausschlusses legen Sie den Wert der Eigenschaft **EnableArchivingDisclaimer** auf „True“ ($True) fest:</span><span class="sxs-lookup"><span data-stu-id="a6341-121">To enable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

## <a name="to-disable-the-archiving-disclaimer"></a><span data-ttu-id="a6341-122">So deaktivieren Sie den Haftungsausschluss für Archivierung</span><span class="sxs-lookup"><span data-stu-id="a6341-122">To disable the archiving disclaimer</span></span>

  - <span data-ttu-id="a6341-123">Zum Deaktivieren des Archivierungshaftungsausschlusses legen Sie den Wert der Eigenschaft **EnableArchivingDisclaimer** auf „False“ ($False) fest:</span><span class="sxs-lookup"><span data-stu-id="a6341-123">To disable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False


