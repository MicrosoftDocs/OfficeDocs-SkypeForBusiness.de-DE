---
title: Konfigurieren von Archivierungs Ausschlüssen für externe Benutzer in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 394ac291-05cd-4fa1-acb3-714af538b47f
description: 'Zusammenfassung: Lesen Sie dieses Thema, um zu erfahren, wie Sie eine Archivierungs Verzichterklärung für Skype for Business Server konfigurieren.'
ms.openlocfilehash: 5901429918d4cf346cbbf9f1fdad6ff4736817ea
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234358"
---
# <a name="configure-archiving-disclaimers-for-external-users-in-skype-for-business-server"></a><span data-ttu-id="3b0b6-103">Konfigurieren von Archivierungs Ausschlüssen für externe Benutzer in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="3b0b6-103">Configure archiving disclaimers for external users in Skype for Business Server</span></span>
 
<span data-ttu-id="3b0b6-104">**Zusammenfassung:** In diesem Thema erfahren Sie, wie Sie einen Haftungsausschluss für die Archivierung von Skype for Business Server konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="3b0b6-104">**Summary:** Read this topic to learn how to configure an archiving disclaimer for Skype for Business Server.</span></span>
  
<span data-ttu-id="3b0b6-105">Wenn Ihre Organisation mit externen Partnern kommuniziert, müssen Sie die Partner darüber informieren, dass diese Kommunikationen archiviert werden.</span><span class="sxs-lookup"><span data-stu-id="3b0b6-105">If your organization communicates with external partners, you need to let them know that you are archiving communications with them.</span></span> <span data-ttu-id="3b0b6-106">Wenn Sie einen Edgeserver bereitstellen und den Verbund für Ihre Organisation aktivieren, werden Sie gefragt, ob Sie einen Archivierungs Ausschluss automatisch an externe Partner senden möchten.</span><span class="sxs-lookup"><span data-stu-id="3b0b6-106">When you deploy an Edge Server and enable federation for your organization, you are asked whether you want to automatically send an archiving disclaimer to external partners.</span></span> 
  
<span data-ttu-id="3b0b6-107">Wenn Sie diese Konfiguration ändern müssen, können Sie die Skype for Business Server-Systemsteuerung oder das Windows PowerShell-Cmdlet " **Satz-csaccessedgeconfiguration nicht angeben** " verwenden.</span><span class="sxs-lookup"><span data-stu-id="3b0b6-107">If you need to change this configuration, you can use the Skype for Business Server Control Panel or the Windows PowerShell **Set-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="3b0b6-108">Cmdlets können entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="3b0b6-108">Cmdlets can be run either from the Skype for Business Server management shell or from a remote session of Windows PowerShell.</span></span>
  
<span data-ttu-id="3b0b6-109">Damit externe Benutzer mit Benutzern in Ihrer Skype for Business Server-Bereitstellung zusammenarbeiten können, müssen Sie auch mindestens eine Richtlinie für den externen Zugriff konfigurieren, um den Zugriff durch externe Benutzer zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="3b0b6-109">To enable external users to collaborate with users in your Skype for Business Server deployment, you must also configure at least one external access policy to support external user access.</span></span> <span data-ttu-id="3b0b6-110">Ausführliche Informationen finden Sie unter Verwalten von XMPP-Verbundpartnern für Ihre Organisation.</span><span class="sxs-lookup"><span data-stu-id="3b0b6-110">For details, see Manage XMPP Federated Partners for Your Organization.</span></span> <span data-ttu-id="3b0b6-111">Ausführliche Informationen zur Steuerung des Zugriffs für bestimmte Partnerdomänen finden Sie unter „Control Access by Individual Federated Domains“.</span><span class="sxs-lookup"><span data-stu-id="3b0b6-111">For details about controlling access for specific federated domains, see Control Access by Individual Federated Domains.</span></span>
  
## <a name="enable-or-disable-archiving-disclaimer-using-the-control-panel"></a><span data-ttu-id="3b0b6-112">Aktivieren oder Deaktivieren des Archivierungshaftungsausschlusses mithilfe der Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="3b0b6-112">Enable or disable archiving disclaimer using the Control Panel</span></span>

1. <span data-ttu-id="3b0b6-113">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="3b0b6-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="3b0b6-114">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="3b0b6-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="3b0b6-115">Klicken Sie in der linken Navigationsleiste auf **Partnerverbund und externer Zugriff** und dann auf **Zugriffs-Edgekonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="3b0b6-115">In the left navigation bar, click **Federation and External Access**, and then click **Access Edge Configuration**.</span></span>
    
4. <span data-ttu-id="3b0b6-116">Klicken Sie auf der Registerkarte **Zugriffs-Edgekonfiguration** auf **Global**, klicken Sie auf **Bearbeiten** und dann auf **Details einblenden**.</span><span class="sxs-lookup"><span data-stu-id="3b0b6-116">On the **Access Edge Configuration** tab, click **Global**, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="3b0b6-117">Aktivieren oder deaktivieren Sie im Abschnitt **Zugriffs-Edgekonfiguration bearbeiten** unter **Partnerverbund und Verbindung mit öffentlichen Chatdiensten aktivieren** das Kontrollkästchen **Archivierungshaftungsausschluss an Verbundpartner senden**, um das automatische Versenden eines Archivierungshaftungsausschlusses zu aktivieren bzw. zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="3b0b6-117">In **Edit Access Edge Configuration**, under **Enable federation and public IM connectivity**, select or clear the **Send archiving disclaimer to federated partners** check box to enable or disable automatically sending the archiving disclaimer.</span></span>
    
6. <span data-ttu-id="3b0b6-118">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="3b0b6-118">Click **Commit**.</span></span>
    
## <a name="enable-or-disable-archiving-disclaimer-using-windows-powershell"></a><span data-ttu-id="3b0b6-119">Aktivieren oder Deaktivieren des Archivierungshaftungsausschlusses mithilfe von Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3b0b6-119">Enable or disable archiving disclaimer using Windows PowerShell</span></span>

<span data-ttu-id="3b0b6-120">Zum Aktivieren des Archivierungshaftungsausschlusses legen Sie den Wert der Eigenschaft **EnableArchivingDisclaimer** auf „True“ ($True) fest:</span><span class="sxs-lookup"><span data-stu-id="3b0b6-120">To enable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to True ($True):</span></span>
  
```
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True
```

<span data-ttu-id="3b0b6-121">Zum Deaktivieren des Archivierungshaftungsausschlusses legen Sie den Wert der Eigenschaft **EnableArchivingDisclaimer** auf „False“ ($False) fest:</span><span class="sxs-lookup"><span data-stu-id="3b0b6-121">To disable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to False ($False):</span></span>
  
```
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False
```


