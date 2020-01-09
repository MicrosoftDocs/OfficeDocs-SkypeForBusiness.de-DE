---
title: Anzeigen von PIN-Richtlinieninformationen in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
description: 'Zusammenfassung: Anzeigen der PIN-Richtlinieninformationen eines Benutzers für Skype for Business Server.'
ms.openlocfilehash: c61c55f97abc661558089c1d26ee4f5537fcf36b
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991950"
---
# <a name="view-pin-policy-information-in-skype-for-business-server"></a><span data-ttu-id="5b125-103">Anzeigen von PIN-Richtlinieninformationen in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5b125-103">View PIN policy information in Skype for Business Server</span></span>
 
<span data-ttu-id="5b125-104">**Zusammenfassung:** Zeigen Sie die PIN-Richtlinieninformationen eines Benutzers für Skype for Business Server an.</span><span class="sxs-lookup"><span data-stu-id="5b125-104">**Summary:** View a user's PIN policy information for Skype for Business Server.</span></span>
  
<span data-ttu-id="5b125-105">Auf der Registerkarte **PIN-Richtlinie** können Sie die PIN-Authentifizierung (Personal Identification Number) von Benutzern anzeigen, die eine Verbindung mit Skype for Business mit IP-Telefonen herstellen.</span><span class="sxs-lookup"><span data-stu-id="5b125-105">You can use the **PIN Policy** tab to view personal identification number (PIN) authentication of users who are connecting to Skype for Business with IP Phones.</span></span> <span data-ttu-id="5b125-106">Stellen Sie zur Verwendung der PIN-Authentifizierung sicher, dass in den Webdiensteinstellungen die Option **PIN-Authentifizierung aktivieren** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="5b125-106">To use PIN authentication, make sure that **Enable PIN Authentication** is selected in Web Service settings.</span></span>
  
<span data-ttu-id="5b125-107">Führen Sie die folgenden Schritte aus, um eine PIN-Richtlinie auf Benutzer- oder Standortebene zu ändern.</span><span class="sxs-lookup"><span data-stu-id="5b125-107">Follow these steps to modify a user-level or a site-level PIN policy.</span></span> 
  
### <a name="to-view-information-about-a-pin-policy-in-skype-for-business-server-control-panel"></a><span data-ttu-id="5b125-108">So zeigen Sie Informationen zu einer PIN-Richtlinie in der Skype for Business Server-Systemsteuerung an</span><span class="sxs-lookup"><span data-stu-id="5b125-108">To view information about a PIN policy in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="5b125-109">Melden Sie sich bei einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder über entsprechende Benutzerrechte verfügt) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, bei jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie Skype for Business Server bereitgestellt haben. .</span><span class="sxs-lookup"><span data-stu-id="5b125-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="5b125-110">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="5b125-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="5b125-111">Klicken Sie in der linken Navigationsleiste auf **Sicherheit** und dann auf **PIN-Richtlinie**.</span><span class="sxs-lookup"><span data-stu-id="5b125-111">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="5b125-112">Klicken Sie auf der Seite **PIN-Richtlinie** auf eine Richtlinie, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="5b125-112">On the **PIN Policy** page, click a policy, click **Edit**, and then click **Show details**.</span></span>
    
## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="5b125-113">Anzeigen von PIN-Richtlinien mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="5b125-113">Viewing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="5b125-114">Sie können auch PIN-Richtlinien mithilfe von Windows PowerShell und dem Cmdlet Get-CsPinPolicy anzeigen.</span><span class="sxs-lookup"><span data-stu-id="5b125-114">You can also view PIN policies by using Windows PowerShell and the Get-CsPinPolicy cmdlet.</span></span> <span data-ttu-id="5b125-115">Dieses Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="5b125-115">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="5b125-116">Details zur Verwendung der Remote-Windows PowerShell zum Herstellen einer Verbindung mit Skype for Business Server finden Sie im Blog-Artikel ["schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="5b125-116">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="5b125-117">Der Vorgang ist in Skype for Business Server identisch.</span><span class="sxs-lookup"><span data-stu-id="5b125-117">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-view-pin-policies"></a><span data-ttu-id="5b125-118">So zeigen Sie PIN-Richtlinien an</span><span class="sxs-lookup"><span data-stu-id="5b125-118">To view PIN policies</span></span>

<span data-ttu-id="5b125-119">Wenn Sie Informationen zu allen Ihren PIN-Richtlinien anzeigen möchten, geben Sie in der Skype for Business Server-Verwaltungsshell den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="5b125-119">To view information about all your PIN policies, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
  ```PowerShell
  Get-CsPinPolicy
  ```

<span data-ttu-id="5b125-120">Es werden etwa folgende Informationen zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="5b125-120">That will return information similar to this:</span></span>

<pre>
Identity             : Global
Description          :
MinPasswordLength    : 5
PINHistoryCount      : 0
AllowCommonPatterns  : False
PINLifetime          : 0
MaximumLogonAttempts :
</pre>

<span data-ttu-id="5b125-121">Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="5b125-121">For more information, see the help topic for the [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5b125-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5b125-122">See also</span></span>

[<span data-ttu-id="5b125-123">Erstellen einer neuen PIN-Richtlinie in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5b125-123">Create a new PIN policy in Skype for Business Server</span></span>](create-a-new-pin-policy.md)
