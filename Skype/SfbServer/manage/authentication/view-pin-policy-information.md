---
title: Anzeigen von PIN-Richtlinieninformationen in Skype für Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
description: 'Zusammenfassung: Hier eines Benutzers PIN-Richtlinie für Skype für Business Server.'
ms.openlocfilehash: 37bb66dfb3d899057d1679c2438fd7e695349629
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919675"
---
# <a name="view-pin-policy-information-in-skype-for-business-server"></a><span data-ttu-id="4c28d-103">Anzeigen von PIN-Richtlinieninformationen in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="4c28d-103">View PIN policy information in Skype for Business Server</span></span>
 
<span data-ttu-id="4c28d-104">**Zusammenfassung:** Anzeigen von Informationen eines Benutzers PIN-Richtlinie für Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="4c28d-104">**Summary:** View a user's PIN policy information for Skype for Business Server.</span></span>
  
<span data-ttu-id="4c28d-105">Sie können die Registerkarte **PIN-Richtlinie** , um Ansicht personal Identification Number (PIN) Authentifizierung von Benutzern, die Skype für Unternehmen mit IP-Telefone verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="4c28d-105">You can use the **PIN Policy** tab to view personal identification number (PIN) authentication of users who are connecting to Skype for Business with IP Phones.</span></span> <span data-ttu-id="4c28d-106">Stellen Sie zur Verwendung der PIN-Authentifizierung sicher, dass in den Webdiensteinstellungen die Option **PIN-Authentifizierung aktivieren** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="4c28d-106">To use PIN authentication, make sure that **Enable PIN Authentication** is selected in Web Service settings.</span></span>
  
<span data-ttu-id="4c28d-107">Führen Sie die folgenden Schritte aus, um eine PIN-Richtlinie auf Benutzer- oder Standortebene zu ändern.</span><span class="sxs-lookup"><span data-stu-id="4c28d-107">Follow these steps to modify a user-level or a site-level PIN policy.</span></span> 
  
### <a name="to-view-information-about-a-pin-policy-in-skype-for-business-server-control-panel"></a><span data-ttu-id="4c28d-108">Zum Anzeigen von Informationen über eine PIN-Richtlinie in Skype Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="4c28d-108">To view information about a PIN policy in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="4c28d-109">Von einem Benutzerkonto, das Mitglied der Gruppe RTCUniversalServerAdmins (oder gleichwertige Benutzerrechte verfügt), oder der CsServerAdministrator oder CsAdministrator-Rolle, melden Sie sich an einem beliebigen Computer, die im Netzwerk ist in der Bereitstellung von Skype für Business Server zugeordnet ist .</span><span class="sxs-lookup"><span data-stu-id="4c28d-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="4c28d-110">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="4c28d-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="4c28d-111">Klicken Sie in der linken Navigationsleiste auf **Sicherheit** und dann auf **PIN-Richtlinie**.</span><span class="sxs-lookup"><span data-stu-id="4c28d-111">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="4c28d-112">Klicken Sie auf der Seite **PIN-Richtlinie** auf eine Richtlinie, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="4c28d-112">On the **PIN Policy** page, click a policy, click **Edit**, and then click **Show details**.</span></span>
    
## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="4c28d-113">Anzeigen von PIN-Richtlinien mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="4c28d-113">Viewing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="4c28d-114">Sie können auch PIN-Richtlinien mithilfe von Windows PowerShell und das Cmdlet Get-CsPinPolicy anzeigen.</span><span class="sxs-lookup"><span data-stu-id="4c28d-114">You can also view PIN policies by using Windows PowerShell and the Get-CsPinPolicy cmdlet.</span></span> <span data-ttu-id="4c28d-115">Dieses Cmdlet kann von der Skype für Business Server-Verwaltungsshell oder von einer remote Windows PowerShell-Sitzung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="4c28d-115">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="4c28d-116">Weitere Informationen zur Verwendung von remote Windows PowerShell zum Skype für Business Server herstellen finden Sie im Blog-Artikel ["Quick Start: Verwalten von Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="4c28d-116">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="4c28d-117">Der Vorgang ist in Skype für Business Server identisch.</span><span class="sxs-lookup"><span data-stu-id="4c28d-117">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-view-pin-policies"></a><span data-ttu-id="4c28d-118">So zeigen Sie PIN-Richtlinien an</span><span class="sxs-lookup"><span data-stu-id="4c28d-118">To view PIN policies</span></span>

<span data-ttu-id="4c28d-119">Anzeigen von Informationen zu allen PIN-Richtlinien, geben Sie den folgenden Befehl in der Skype für Business Server-Verwaltungsshell, und drücken Sie die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="4c28d-119">To view information about all your PIN policies, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
  ```
  Get-CsPinPolicy
  ```

<span data-ttu-id="4c28d-120">Es werden etwa folgende Informationen zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="4c28d-120">That will return information similar to this:</span></span>

<pre>
Identity             : Global
Description          :
MinPasswordLength    : 5
PINHistoryCount      : 0
AllowCommonPatterns  : False
PINLifetime          : 0
MaximumLogonAttempts :
</pre>

<span data-ttu-id="4c28d-121">Weitere Informationen finden Sie im Hilfethema für das Cmdlet [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="4c28d-121">For more information, see the help topic for the [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4c28d-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4c28d-122">See also</span></span>

[<span data-ttu-id="4c28d-123">Erstellen Sie eine neue PIN-Richtlinie in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="4c28d-123">Create a new PIN policy in Skype for Business Server</span></span>](create-a-new-pin-policy.md)
