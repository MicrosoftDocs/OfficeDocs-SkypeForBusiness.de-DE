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
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Eine globale Richtlinie kann nicht vollständig gelöscht werden. Mit der Option **Löschen** auf die globale Richtlinie setzt nur die globale Richtlinie auf die Standardeinstellungen, die keine Unterstützung für externe Benutzer Zugriffsoptionen enthalten.
ms.openlocfilehash: c2f938219a35de97088c26f81d9d59e46e799ebb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33923174"
---
# <a name="reset-the-global-policy-for-external-user-access-in-skype-for-business-server"></a><span data-ttu-id="da773-104">Zurücksetzen der globalen Richtlinie für den Zugriff externer Benutzer in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="da773-104">Reset the global policy for external user access in Skype for Business Server</span></span> 

<span data-ttu-id="da773-105">Wenn Sie erstellt oder konfiguriert Richtlinien für den externen Benutzerzugriff, die Sie nicht mehr verwenden möchten, können Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="da773-105">If you have created or configured external user access policies that you no longer want to use, you can do the following:</span></span>

  - <span data-ttu-id="da773-106">Löschen Sie alle Standort- oder Benutzerrichtlinie, die Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="da773-106">Delete any site or user policy that you created.</span></span>

  - <span data-ttu-id="da773-107">Die globale Richtlinie auf die Standardeinstellungen zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="da773-107">Reset the global policy to the default settings.</span></span> <span data-ttu-id="da773-108">Die Standardeinstellungen für die globale Richtlinie verweigern keinen Zugriff externer Benutzer.</span><span class="sxs-lookup"><span data-stu-id="da773-108">The default global policy settings deny any external user access.</span></span> <span data-ttu-id="da773-109">Die globale Richtlinie kann nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="da773-109">The global policy cannot be deleted.</span></span>

<span data-ttu-id="da773-110">Eine globale Richtlinie kann nicht vollständig gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="da773-110">You cannot completely delete a global policy.</span></span> <span data-ttu-id="da773-111">Mit der Option **Löschen** auf die globale Richtlinie setzt nur die globale Richtlinie auf die Standardeinstellungen, die keine Unterstützung für externe Benutzer Zugriffsoptionen enthalten.</span><span class="sxs-lookup"><span data-stu-id="da773-111">Using the **Delete** option on the global policy only resets the global policy to the default settings, which do not include support for any external user access options.</span></span>

## <a name="to-reset-the-global-policy-to-the-default-settings"></a><span data-ttu-id="da773-112">So setzen Sie die globale Richtlinie auf die Standardeinstellungen zurück</span><span class="sxs-lookup"><span data-stu-id="da773-112">To reset the global policy to the default settings</span></span>

1.  <span data-ttu-id="da773-113">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="da773-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="da773-114">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="da773-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="da773-115">Klicken Sie in der linken Navigationsleiste klicken Sie auf **Zugriff durch externe Benutzer**, klicken Sie auf **Richtlinie für den externen Zugriff**.</span><span class="sxs-lookup"><span data-stu-id="da773-115">In the left navigation bar, click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="da773-116">Klicken Sie auf der Registerkarte **Richtlinie für den externen Zugriff** auf die globale Richtlinie, klicken Sie auf **Bearbeiten**und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="da773-116">On the **External Access Policy** tab, click the global policy, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="da773-117">Wenn Sie aufgefordert werden, den Löschvorgang zu bestätigen, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="da773-117">When prompted to confirm the deletion, click **OK**.</span></span> <span data-ttu-id="da773-118">Am oberen Rand der Seite, die Sie darüber informiert, dass die globale Richtlinie zurückgesetzt wurde, wird eine Meldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="da773-118">A message appears at the top of the page informing you that the global policy has been reset.</span></span>


## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="da773-119">Zurücksetzen der globalen externe Zugriffsrichtlinie mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="da773-119">Resetting the Global External Access Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="da773-120">Die globale externe Zugriffsrichtlinie kann mithilfe von Windows PowerShell und Remove-CsExternalAccessPolicy-Cmdlet zurückgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="da773-120">The global external access policy can be reset by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="da773-121">Dieses Cmdlet kann von der Skype für Business Server-Verwaltungsshell oder von einer Windows PowerShell-Remotesitzung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="da773-121">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> 

## <a name="to-reset-the-global-external-access-policy"></a><span data-ttu-id="da773-122">Zurücksetzen die globalen externe Zugriffsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="da773-122">To reset the global external access policy</span></span>

  - <span data-ttu-id="da773-123">Mit diesem Befehl werden die globalen externe Zugriffsrichtlinie zurückgesetzt:</span><span class="sxs-lookup"><span data-stu-id="da773-123">This command resets the global external access policy:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "global"

<span data-ttu-id="da773-124">Weitere Informationen finden Sie im Hilfethema zum [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) -Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="da773-124">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>


