---
title: Zurücksetzen der globalen Richtlinie für den externen Benutzerzugriff
ms.reviewer: ''
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
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
description: Es ist nicht möglich, eine globale Richtlinie vollständig zu löschen. Wenn Sie die Option " **Löschen** " in der globalen Richtlinie verwenden, wird die globale Richtlinie nur auf die Standardeinstellungen zurückgesetzt, die keine Unterstützung für externe Benutzerzugriffsoptionen beinhalten.
ms.openlocfilehash: e0e59c4de1b7a4bacbef30b4caa3d26c29b81e84
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818266"
---
# <a name="reset-the-global-policy-for-external-user-access-in-skype-for-business-server"></a><span data-ttu-id="ac80a-104">Zurücksetzen der globalen Richtlinie für den Zugriff durch externe Benutzer in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ac80a-104">Reset the global policy for external user access in Skype for Business Server</span></span> 

<span data-ttu-id="ac80a-105">Wenn Sie Richtlinien für den externen Benutzer Zugriff erstellt oder konfiguriert haben, die Sie nicht mehr verwenden möchten, können Sie die folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="ac80a-105">If you have created or configured external user access policies that you no longer want to use, you can do the following:</span></span>

  - <span data-ttu-id="ac80a-106">Löschen Sie alle von Ihnen erstellten Websites oder Benutzerrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="ac80a-106">Delete any site or user policy that you created.</span></span>

  - <span data-ttu-id="ac80a-107">Setzen Sie die globale Richtlinie auf die Standardeinstellungen zurück.</span><span class="sxs-lookup"><span data-stu-id="ac80a-107">Reset the global policy to the default settings.</span></span> <span data-ttu-id="ac80a-108">Die globalen Standardrichtlinieneinstellungen verweigern den Zugriff externer Benutzer.</span><span class="sxs-lookup"><span data-stu-id="ac80a-108">The default global policy settings deny any external user access.</span></span> <span data-ttu-id="ac80a-109">Die globale Richtlinie kann nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="ac80a-109">The global policy cannot be deleted.</span></span>

<span data-ttu-id="ac80a-110">Es ist nicht möglich, eine globale Richtlinie vollständig zu löschen.</span><span class="sxs-lookup"><span data-stu-id="ac80a-110">You cannot completely delete a global policy.</span></span> <span data-ttu-id="ac80a-111">Wenn Sie die Option " **Löschen** " in der globalen Richtlinie verwenden, wird die globale Richtlinie nur auf die Standardeinstellungen zurückgesetzt, die keine Unterstützung für externe Benutzerzugriffsoptionen beinhalten.</span><span class="sxs-lookup"><span data-stu-id="ac80a-111">Using the **Delete** option on the global policy only resets the global policy to the default settings, which do not include support for any external user access options.</span></span>

## <a name="to-reset-the-global-policy-to-the-default-settings"></a><span data-ttu-id="ac80a-112">So setzen Sie die globale Richtlinie auf die Standardeinstellungen zurück</span><span class="sxs-lookup"><span data-stu-id="ac80a-112">To reset the global policy to the default settings</span></span>

1.  <span data-ttu-id="ac80a-113">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="ac80a-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ac80a-114">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="ac80a-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="ac80a-115">Klicken Sie in der linken Navigationsleiste auf **externer Benutzer Zugriff**, und klicken Sie auf **Richtlinie für den externen Zugriff**.</span><span class="sxs-lookup"><span data-stu-id="ac80a-115">In the left navigation bar, click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="ac80a-116">Klicken Sie auf der Registerkarte **Richtlinie für den externen Zugriff** auf die globale Richtlinie, klicken Sie auf **Bearbeiten**und dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="ac80a-116">On the **External Access Policy** tab, click the global policy, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="ac80a-117">Wenn Sie aufgefordert werden, den Löschvorgang zu bestätigen, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ac80a-117">When prompted to confirm the deletion, click **OK**.</span></span> <span data-ttu-id="ac80a-118">Oben auf der Seite wird eine Meldung angezeigt, in der Sie darüber informiert werden, dass die globale Richtlinie zurückgesetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="ac80a-118">A message appears at the top of the page informing you that the global policy has been reset.</span></span>


## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="ac80a-119">Zurücksetzen der globalen Richtlinie für den externen Zugriff mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="ac80a-119">Resetting the Global External Access Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="ac80a-120">Die globale Richtlinie für den externen Zugriff kann mithilfe von Windows PowerShell und dem Cmdlet Remove-CsExternalAccessPolicy zurückgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="ac80a-120">The global external access policy can be reset by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="ac80a-121">Dieses Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder über eine Windows PowerShell-Remotesitzung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ac80a-121">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> 

## <a name="to-reset-the-global-external-access-policy"></a><span data-ttu-id="ac80a-122">So setzen Sie die globale Richtlinie für den externen Zugriff zurück</span><span class="sxs-lookup"><span data-stu-id="ac80a-122">To reset the global external access policy</span></span>

  - <span data-ttu-id="ac80a-123">Mit diesem Befehl wird die globale Richtlinie für den externen Zugriff zurückgesetzt:</span><span class="sxs-lookup"><span data-stu-id="ac80a-123">This command resets the global external access policy:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "global"

<span data-ttu-id="ac80a-124">Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) .</span><span class="sxs-lookup"><span data-stu-id="ac80a-124">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>


