---
title: 'Lync Server 2013: Zurücksetzen der globalen Richtlinie für den externen Benutzerzugriff'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reset the global policy for external user access
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 971239018f3a8e1bcc92c036f50ed36616256ac7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723755"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reset-the-global-policy-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="f1f0e-102">Zurücksetzen der globalen Richtlinie für den externen Benutzerzugriff in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1f0e-102">Reset the global policy for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1f0e-103">_**Letztes Änderungsdatum des Themas:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="f1f0e-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="f1f0e-104">Es ist nicht möglich, eine globale Richtlinie vollständig zu löschen.</span><span class="sxs-lookup"><span data-stu-id="f1f0e-104">You cannot completely delete a global policy.</span></span> <span data-ttu-id="f1f0e-105">Wenn Sie die Option " **Löschen** " in der globalen Richtlinie verwenden, wird die globale Richtlinie nur auf die Standardeinstellungen zurückgesetzt, die keine Unterstützung für externe Benutzerzugriffsoptionen beinhalten.</span><span class="sxs-lookup"><span data-stu-id="f1f0e-105">Using the **Delete** option on the global policy only resets the global policy to the default settings, which do not include support for any external user access options.</span></span>

<div>

## <a name="to-reset-the-global-policy-to-the-default-settings"></a><span data-ttu-id="f1f0e-106">So setzen Sie die globale Richtlinie auf die Standardeinstellungen zurück</span><span class="sxs-lookup"><span data-stu-id="f1f0e-106">To reset the global policy to the default settings</span></span>

1.  <span data-ttu-id="f1f0e-107">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="f1f0e-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f1f0e-108">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f1f0e-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f1f0e-109">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f1f0e-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f1f0e-110">Klicken Sie in der linken Navigationsleiste auf **externer Benutzer Zugriff**, und klicken Sie auf **Richtlinie für den externen Zugriff**.</span><span class="sxs-lookup"><span data-stu-id="f1f0e-110">In the left navigation bar, click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="f1f0e-111">Klicken Sie auf der Registerkarte **Richtlinie für den externen Zugriff** auf die globale Richtlinie, klicken Sie auf **Bearbeiten**und dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="f1f0e-111">On the **External Access Policy** tab, click the global policy, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="f1f0e-112">Wenn Sie aufgefordert werden, den Löschvorgang zu bestätigen, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f1f0e-112">When prompted to confirm the deletion, click **OK**.</span></span> <span data-ttu-id="f1f0e-113">Oben auf der Seite wird eine Meldung angezeigt, in der Sie darüber informiert werden, dass die globale Richtlinie zurückgesetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="f1f0e-113">A message appears at the top of the page informing you that the global policy has been reset.</span></span>

</div>

<div>

## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f1f0e-114">Zurücksetzen der globalen Richtlinie für den externen Zugriff mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="f1f0e-114">Resetting the Global External Access Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="f1f0e-115">Die globale Richtlinie für den externen Zugriff kann mithilfe von Windows PowerShell und dem Cmdlet Remove-CsExternalAccessPolicy zurückgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="f1f0e-115">The global external access policy can be reset by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="f1f0e-116">Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Windows PowerShell-Remotesitzung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f1f0e-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="f1f0e-117">Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="f1f0e-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-reset-the-global-external-access-policy"></a><span data-ttu-id="f1f0e-118">So setzen Sie die globale Richtlinie für den externen Zugriff zurück</span><span class="sxs-lookup"><span data-stu-id="f1f0e-118">To reset the global external access policy</span></span>

  - <span data-ttu-id="f1f0e-119">Mit diesem Befehl wird die globale Richtlinie für den externen Zugriff zurückgesetzt:</span><span class="sxs-lookup"><span data-stu-id="f1f0e-119">This command resets the global external access policy:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "global"

</div>

<span data-ttu-id="f1f0e-120">Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) .</span><span class="sxs-lookup"><span data-stu-id="f1f0e-120">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

