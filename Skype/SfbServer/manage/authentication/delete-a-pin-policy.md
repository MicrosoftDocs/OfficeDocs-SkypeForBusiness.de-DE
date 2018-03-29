---
title: Löschen einer PIN-Richtlinie in Skype for Business Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7c378927-2e41-418e-9721-327021bd2e45
description: 'Zusammenfassung: Löschen eines Benutzers einwahlkonferenzen PIN für Skype für Business Server 2015.'
ms.openlocfilehash: b64a4509105214358549f320cf8885d6386986f7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="delete-a-pin-policy-in-skype-for-business-server-2015"></a><span data-ttu-id="f0004-103">Löschen einer PIN-Richtlinie in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="f0004-103">Delete a PIN policy in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="f0004-104">**Zusammenfassung:** Löschen eines Benutzers einwahlkonferenzen PIN für Skype für Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="f0004-104">**Summary:** Delete a user's dial-in conferencing PIN for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="f0004-105">Führen Sie die folgenden Schritte aus, um eine PIN-Richtlinie (persönliche Identifikationsnummer) zu löschen.</span><span class="sxs-lookup"><span data-stu-id="f0004-105">Follow these steps to delete a personal identification number (PIN) policy.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f0004-106">Die globale PIN-Richtlinie kann nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="f0004-106">You cannot delete the global PIN policy.</span></span> 
  
### <a name="to-delete-a-pin-policy-in-skype-for-business-server-control-panel"></a><span data-ttu-id="f0004-107">So löschen Sie eine PIN-Richtlinie in Skype Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="f0004-107">To delete a PIN policy in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="f0004-108">Von einem Benutzerkonto, das Mitglied der Gruppe RTCUniversalServerAdmins (oder gleichwertige Benutzerrechte verfügt), oder der CsServerAdministrator oder CsAdministrator-Rolle, melden Sie sich an einem beliebigen Computer, die im Netzwerk ist in der Bereitstellung von Skype für Business Server zugeordnet ist 2015.</span><span class="sxs-lookup"><span data-stu-id="f0004-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2015.</span></span>
    
2. <span data-ttu-id="f0004-109">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f0004-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="f0004-110">Klicken Sie in der linken Navigationsleiste auf **Sicherheit** und dann auf **PIN-Richtlinie**.</span><span class="sxs-lookup"><span data-stu-id="f0004-110">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="f0004-111">Geben Sie auf der Seite **PIN-Richtlinie** im Suchfeld den vollständigen oder teilweisen Namen der Richtlinie ein, die Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="f0004-111">On the **PIN Policy** page, and in the search field, type all or part of the name of the policy you want to delete.</span></span>
    
5. <span data-ttu-id="f0004-112">Klicken Sie in der Richtlinienliste auf die gewünschte Richtlinie, klicken Sie auf **Bearbeiten** und dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="f0004-112">In the list of policies, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="f0004-113">Klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f0004-113">Click **OK**.</span></span>
    
## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f0004-114">Entfernen der PIN-Richtlinien mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="f0004-114">Removing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="f0004-115">Sie können die PIN-Richtlinien löschen, mithilfe von Windows PowerShell und das Cmdlet Remove-CsPinPolicy.</span><span class="sxs-lookup"><span data-stu-id="f0004-115">You can delete PIN policies by using Windows PowerShell and the Remove-CsPinPolicy cmdlet.</span></span> <span data-ttu-id="f0004-116">Sie können dieses Cmdlet entweder von der Skype für Business Server-Verwaltungsshell oder aus einer Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="f0004-116">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="f0004-117">Weitere Informationen zur Verwendung von remote Windows PowerShell zum Skype für Business Server herstellen finden Sie im Blog-Artikel ["Quick Start: Verwalten von Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="f0004-117">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="f0004-118">Der Vorgang ist in Skype für Business Server identisch.</span><span class="sxs-lookup"><span data-stu-id="f0004-118">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specific-pin-policy"></a><span data-ttu-id="f0004-119">So entfernen Sie eine bestimmte PIN-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="f0004-119">To remove a specific PIN policy</span></span>

- <span data-ttu-id="f0004-120">Mit diesem Befehl wird die PIN-Richtlinie mit dem Identitätswert „RedmondUsersPinPolicy“ entfernt.</span><span class="sxs-lookup"><span data-stu-id="f0004-120">This command removes the PIN policy with the Identity RedmondPinPolicy:</span></span>
    
  ```
  Remove-CsPinPolicy -Identity "RedmondPinPolicy"
  ```

### <a name="to-remove-all-the-pin-policies-applied-to-the-site-scope"></a><span data-ttu-id="f0004-121">So entfernen Sie alle PIN-Richtlinien, die auf den Standortbereich angewendet wurden</span><span class="sxs-lookup"><span data-stu-id="f0004-121">To remove all the PIN policies applied to the site scope</span></span>

- <span data-ttu-id="f0004-122">Mit diesem Befehl werden alle PIN-Richtlinien entfernt, die für den Standortbereich konfiguriert sind:</span><span class="sxs-lookup"><span data-stu-id="f0004-122">This command removes all the PIN policies configured at the site scope:</span></span>
    
  ```
  Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
  ```

### <a name="to-remove-all-the-pin-policies-that-allow-the-use-of-common-patterns"></a><span data-ttu-id="f0004-123">So entfernen Sie alle PIN-Richtlinien, die die Verwendung gängiger Muster zulassen</span><span class="sxs-lookup"><span data-stu-id="f0004-123">To remove all the PIN policies that allow the use of common patterns</span></span>

- <span data-ttu-id="f0004-124">Mit diesem Befehl werden alle PIN-Richtlinien entfernt, die die Verwendung gängiger Muster zulassen: G</span><span class="sxs-lookup"><span data-stu-id="f0004-124">And this one removes all the PIN policies that allow the use of common patterns:G</span></span>
    
  ```
  et-CsPinPolicy | Where-Object {$_.AllowCommonPatterns -eq $True} | Remove-CsPinPolicy
  ```

<span data-ttu-id="f0004-125">Weitere Informationen finden Sie im Hilfethema zum [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps) -Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f0004-125">For more information, see the help topic for the [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps) cmdlet.</span></span>
  

