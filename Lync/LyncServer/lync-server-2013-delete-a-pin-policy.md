---
title: 'Lync Server 2013: Löschen einer PIN-Richtlinie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a PIN policy
ms:assetid: 7c378927-2e41-418e-9721-327021bd2e45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521020(v=OCS.15)
ms:contentKeyID: 48184609
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc11f1383ec652c512fe5542d9a6780ce028c516
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740995"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-pin-policy-in-lync-server-2013"></a><span data-ttu-id="4e48c-102">Löschen einer PIN-Richtlinie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e48c-102">Delete a PIN policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e48c-103">_**Letztes Änderungsdatum des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="4e48c-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="4e48c-104">Führen Sie die folgenden Schritte aus, um eine PIN-Richtlinie (persönliche Identifikationsnummer) zu löschen.</span><span class="sxs-lookup"><span data-stu-id="4e48c-104">Follow these steps to delete a personal identification number (PIN) policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4e48c-105">Die globale PIN-Richtlinie kann nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="4e48c-105">You cannot delete the global PIN policy.</span></span>



</div>

<div>

## <a name="to-delete-a-pin-policy-in-lync-server-2013-control-panel"></a><span data-ttu-id="4e48c-106">So löschen Sie eine PIN-Richtlinie in der lync Server 2013-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="4e48c-106">To delete a PIN policy in Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="4e48c-107">Melden Sie sich bei einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder über entsprechende Benutzerrechte verfügt) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, bei jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie lync Server 2013 bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="4e48c-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="4e48c-108">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="4e48c-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4e48c-109">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4e48c-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4e48c-110">Klicken Sie in der linken Navigationsleiste auf **Sicherheit** und dann auf **PIN-Richtlinie**.</span><span class="sxs-lookup"><span data-stu-id="4e48c-110">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>

4.  <span data-ttu-id="4e48c-111">Geben Sie auf der Seite **PIN-Richtlinie** im Suchfeld den vollständigen oder teilweisen Namen der Richtlinie ein, die Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="4e48c-111">On the **PIN Policy** page, and in the search field, type all or part of the name of the policy you want to delete.</span></span>

5.  <span data-ttu-id="4e48c-112">Klicken Sie in der Richtlinienliste auf die gewünschte Richtlinie, klicken Sie auf **Bearbeiten** und dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="4e48c-112">In the list of policies, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="4e48c-113">Klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="4e48c-113">Click **OK**.</span></span>

</div>

<div>

## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="4e48c-114">Entfernen von PIN-Richtlinien mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="4e48c-114">Removing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="4e48c-115">Sie können PIN-Richtlinien mithilfe von Windows PowerShell und dem Cmdlet Remove-CsPinPolicy löschen.</span><span class="sxs-lookup"><span data-stu-id="4e48c-115">You can delete PIN policies by using Windows PowerShell and the Remove-CsPinPolicy cmdlet.</span></span> <span data-ttu-id="4e48c-116">Sie können dieses Cmdlet entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="4e48c-116">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="4e48c-117">Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="4e48c-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specific-pin-policy"></a><span data-ttu-id="4e48c-118">So entfernen Sie eine bestimmte PIN-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="4e48c-118">To remove a specific PIN policy</span></span>

  - <span data-ttu-id="4e48c-119">Mit diesem Befehl wird die PIN-Richtlinie mit dem Identitätswert „RedmondUsersPinPolicy“ entfernt.</span><span class="sxs-lookup"><span data-stu-id="4e48c-119">This command removes the PIN policy with the Identity RedmondPinPolicy:</span></span>
    
        Remove-CsPinPolicy -Identity "RedmondPinPolicy"

</div>

<div>

## <a name="to-remove-all-the-pin-policies-applied-to-the-site-scope"></a><span data-ttu-id="4e48c-120">So entfernen Sie alle PIN-Richtlinien, die auf den Standortbereich angewendet wurden</span><span class="sxs-lookup"><span data-stu-id="4e48c-120">To remove all the PIN policies applied to the site scope</span></span>

  - <span data-ttu-id="4e48c-121">Mit diesem Befehl werden alle PIN-Richtlinien entfernt, die für den Standortbereich konfiguriert sind:</span><span class="sxs-lookup"><span data-stu-id="4e48c-121">This command removes all the PIN policies configured at the site scope:</span></span>
    
        Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy

</div>

<div>

## <a name="to-remove-all-the-pin-policies-that-allow-the-use-of-common-patterns"></a><span data-ttu-id="4e48c-122">So entfernen Sie alle PIN-Richtlinien, die die Verwendung gängiger Muster zulassen</span><span class="sxs-lookup"><span data-stu-id="4e48c-122">To remove all the PIN policies that allow the use of common patterns</span></span>

  - <span data-ttu-id="4e48c-123">Mit diesem Befehl werden alle PIN-Richtlinien entfernt, die die Verwendung gängiger Muster zulassen: G</span><span class="sxs-lookup"><span data-stu-id="4e48c-123">And this one removes all the PIN policies that allow the use of common patterns:G</span></span>
    
        et-CsPinPolicy | Where-Object {$_.AllowCommonPatterns -eq $True} | Remove-CsPinPolicy

</div>

<span data-ttu-id="4e48c-124">Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsPinPolicy) .</span><span class="sxs-lookup"><span data-stu-id="4e48c-124">For more information, see the help topic for the [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsPinPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

