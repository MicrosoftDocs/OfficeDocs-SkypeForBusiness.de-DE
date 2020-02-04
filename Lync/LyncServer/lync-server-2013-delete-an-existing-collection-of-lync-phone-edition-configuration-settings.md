---
title: Löschen einer vorhandenen Sammlung von lync Phone Edition-Konfigurationseinstellungen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of Lync Phone Edition configuration settings
ms:assetid: 1bfc427d-4dcd-4199-b25f-8d5cfec2164f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687984(v=OCS.15)
ms:contentKeyID: 49733574
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbf7d49a14ce45550777c6c122cd799f6a511f76
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737405"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="4378d-102">Löschen einer vorhandenen Sammlung von lync Phone Edition-Konfigurationseinstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4378d-102">Delete an existing collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4378d-103">_**Letztes Änderungsdatum des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="4378d-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="4378d-104">Wenn Sie eine Sammlung von Einstellungen für Geräte, auf denen lync Phone Edition ausgeführt wird, nicht mehr verwenden möchten, löschen Sie Sie.</span><span class="sxs-lookup"><span data-stu-id="4378d-104">If you no longer want to use a collection of settings for devices running Lync Phone Edition, delete it.</span></span> <span data-ttu-id="4378d-105">Wenn Sie eine Sammlung für eine Website löschen, gelten die globalen Einstellungen für die Telefone auf dieser Website.</span><span class="sxs-lookup"><span data-stu-id="4378d-105">If you delete a collection for a site, the global settings will apply to the phones in that site.</span></span> <span data-ttu-id="4378d-106">Sie können die globale Sammlung nicht löschen.</span><span class="sxs-lookup"><span data-stu-id="4378d-106">You cannot delete the global collection.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="4378d-107">Anstatt eine Sammlung zu löschen, möchten Sie möglicherweise nur einige Einstellungen ändern.</span><span class="sxs-lookup"><span data-stu-id="4378d-107">Instead of deleting a collection, you might just want to change some of the settings.</span></span> <span data-ttu-id="4378d-108">Ausführliche Informationen hierzu finden Sie unter <A href="lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md">erstellen oder Ändern einer Sammlung von lync Phone Edition-Konfigurationseinstellungen in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="4378d-108">For details about how to do so, see <A href="lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md">Create or modify a collection of Lync Phone Edition configuration settings in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-delete-a-collection-of-lync-phone-edition-configuration-settings"></a><span data-ttu-id="4378d-109">So löschen Sie eine Sammlung von lync Phone Edition-Konfigurationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="4378d-109">To delete a collection of Lync Phone Edition configuration settings</span></span>

1.  <span data-ttu-id="4378d-110">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="4378d-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4378d-111">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="4378d-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4378d-112">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4378d-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4378d-113">Klicken Sie in der linken Navigationsleiste auf **Clients**, und klicken Sie dann auf die Navigationsschaltfläche **Gerätekonfiguration** .</span><span class="sxs-lookup"><span data-stu-id="4378d-113">In the left navigation bar, click **Clients**, and then click the **Device Configuration** navigation button.</span></span>

4.  <span data-ttu-id="4378d-114">Klicken Sie auf der Seite **Device Configuration** auf die Sammlung, die Sie löschen möchten, klicken Sie auf das Menü **Bearbeiten** , und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="4378d-114">On the **Device Configuration** page, click the collection you want to delete, click the **Edit** menu, and then click **Delete**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="4378d-115">Wenn Sie die globale Sammlung löschen, werden die Einstellungen einfach auf die Standardeinstellungen zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="4378d-115">If you delete the global collection, the settings just revert to the default settings.</span></span> <span data-ttu-id="4378d-116">Die Sammlung verschwindet nicht.</span><span class="sxs-lookup"><span data-stu-id="4378d-116">The collection does not go away.</span></span>

    
    </div>

5.  <span data-ttu-id="4378d-117">Klicken Sie im Bestätigungsfeld auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="4378d-117">In the confirmation box, click **OK**.</span></span>

</div>

<div>

## <a name="removing-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="4378d-118">Entfernen der lync Phone Edition-Konfigurationseinstellungen mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="4378d-118">Removing Lync Phone Edition Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="4378d-119">Sie können die lync Phone Edition-Konfigurationseinstellungen mithilfe von Windows PowerShell und dem Cmdlet **Remove-CsUCConfiguration** löschen.</span><span class="sxs-lookup"><span data-stu-id="4378d-119">You can delete Lync Phone Edition configuration settings by using Windows PowerShell and the **Remove-CsUCConfiguration** cmdlet.</span></span> <span data-ttu-id="4378d-120">Sie können dieses Cmdlet entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="4378d-120">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="4378d-121">Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="4378d-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-lync-phone-edition-configuration-settings"></a><span data-ttu-id="4378d-122">So entfernen Sie eine bestimmte Sammlung von lync Phone Edition-Konfigurationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="4378d-122">To remove a specified collection of Lync Phone Edition configuration settings</span></span>

  - <span data-ttu-id="4378d-123">Mit diesem Befehl werden die auf die Redmond-Website angewendeten UC-Telefon Konfigurationseinstellungen gelöscht:</span><span class="sxs-lookup"><span data-stu-id="4378d-123">This command deletes the UC phone configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsUCPhoneConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-of-the-lync-phone-edition-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="4378d-124">So entfernen Sie alle auf den Website Bereich angewendeten lync Phone Edition-Konfigurationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="4378d-124">To remove all of the Lync Phone Edition configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="4378d-125">Mit diesem Befehl werden alle auf den Dienstbereich angewendeten UC-Telefon Konfigurationseinstellungen entfernt:</span><span class="sxs-lookup"><span data-stu-id="4378d-125">This command removes all the UC phone configuration settings applied to the service scope:</span></span>
    
        Get-CsUCPhoneConfiguration -Filter "site:*" | Remove-CsUCPhoneConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-lync-phone-edition-configuration-settings-where-phone-locking-is-disabled"></a><span data-ttu-id="4378d-126">So entfernen Sie alle lync Phone Edition-Konfigurationseinstellungen, bei denen die Telefon Sperrung deaktiviert ist</span><span class="sxs-lookup"><span data-stu-id="4378d-126">To remove all of the Lync Phone Edition configuration settings where phone locking is disabled</span></span>

  - <span data-ttu-id="4378d-127">Dieser Befehl löscht eine beliebige Sammlung von UC-Telefon Konfigurationseinstellungen, bei denen die Telefon Sperrung deaktiviert wurde:</span><span class="sxs-lookup"><span data-stu-id="4378d-127">This command deletes any collection of UC phone configuration settings where phone locking has been disabled:</span></span>
    
        Get-CsUCPhoneConfiguration | Where-Object {$_.EnforcePhoneLock -eq $False} | Remove-CsUCPhoneConfiguration

</div>

<span data-ttu-id="4378d-128">Ausführliche Informationen finden Sie unter [Remove-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398249(v=OCS.15)).</span><span class="sxs-lookup"><span data-stu-id="4378d-128">For details, see [Remove-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398249(v=OCS.15)).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

