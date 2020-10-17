---
title: Erstellen oder Ändern einer Sammlung von lync Phone Edition Konfigurationseinstellungen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of Lync Phone Edition configuration settings
ms:assetid: 6cf714af-8f57-4a71-89ad-0a776302b2ba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688086(v=OCS.15)
ms:contentKeyID: 49733683
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11e2d314497223b5a18aa864b0e5333e3762480d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506212"
---
# <a name="create-or-modify-a-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="74c70-102">Erstellen oder Ändern einer Sammlung von lync Phone Edition Konfigurationseinstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74c70-102">Create or modify a collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74c70-103">_**Letztes Änderungsstand des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="74c70-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="74c70-104">Wenn Sie lync Server installieren, erhalten Sie eine globale Sammlung von lync Phone Edition-Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="74c70-104">When you install Lync Server, you get a global collection of Lync Phone Edition settings.</span></span> <span data-ttu-id="74c70-105">Diese Einstellungen gelten für alle Geräte, auf denen lync Phone Edition in Ihrer Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="74c70-105">These settings apply to all devices running Lync Phone Edition in your deployment.</span></span> <span data-ttu-id="74c70-106">Sie können diese Einstellungen jederzeit ändern.</span><span class="sxs-lookup"><span data-stu-id="74c70-106">You can change these settings at any time.</span></span> <span data-ttu-id="74c70-107">Sie können auch eine neue Auflistung der Einstellungen einrichten, die für die Geräte an einem bestimmten Standort gelten.</span><span class="sxs-lookup"><span data-stu-id="74c70-107">You can also set up a new collection of settings that apply to the devices in a specific site.</span></span> <span data-ttu-id="74c70-108">Standorteinstellungen haben Vorrang vor globalen Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="74c70-108">Site settings take precedence over global settings.</span></span>

<span data-ttu-id="74c70-109">Zu den Konfigurationseinstellungen zählen der Auflistungsname, der Geltungsbereich (global oder standortweit), die SIP-Sicherheitseinstellung, der Protokolliergrad, die Stufe der VoIP-Dienstqualität (QoS), das Einstellen der Telefonsperre sowie Details zur Telefonsperre, d. h., a) wie lang die Persönliche Identifikationsnummer (PIN-Nummer) sein muss, und b) nach wie viel Zeit im Ruhezustand das Telefon automatisch gesperrt wird.</span><span class="sxs-lookup"><span data-stu-id="74c70-109">Configuration settings consist of the collection name, scope (global or site), SIP security setting, logging level, voice quality of service (QoS) level, phone-lock setting, and phone-lock details, that is, how long the a) unlock personal identification number (PIN) must be and b) phone stays idle before locking itself.</span></span>

<div>

## <a name="to-create-a-collection-of-lync-phone-edition-configuration-settings-or-edit-settings-for-an-existing-collection"></a><span data-ttu-id="74c70-110">So erstellen Sie eine Sammlung von lync Phone Edition Konfigurationseinstellungen oder Bearbeitungseinstellungen für eine vorhandene Sammlung</span><span class="sxs-lookup"><span data-stu-id="74c70-110">To create a collection of Lync Phone Edition configuration settings or edit settings for an existing collection</span></span>

1.  <span data-ttu-id="74c70-111">Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="74c70-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="74c70-112">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="74c70-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="74c70-113">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="74c70-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="74c70-114">Klicken Sie in der linken Navigationsleiste auf **Clients** und dann auf die Navigationsschaltfläche **Gerätekonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="74c70-114">In the left navigation bar, click **Clients**, and then click the **Device Configuration** navigation button.</span></span>

4.  <span data-ttu-id="74c70-115">Führen Sie auf der Seite **Gerätekonfiguration** einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="74c70-115">On the **Device Configuration** page, do one of the following:</span></span>
    
      - <span data-ttu-id="74c70-116">Um eine neue Sammlung von lync Phone Edition Konfigurationseinstellungen zu erstellen, klicken Sie auf **neu**, wählen Sie einen Standort aus, klicken Sie auf **OK**, überprüfen Sie die Standardeinstellungen, und nehmen Sie bei Bedarf Änderungen vor.</span><span class="sxs-lookup"><span data-stu-id="74c70-116">To create a new collection of Lync Phone Edition configuration settings, click **New**, select a site, click **OK**, review the default settings, and, if you want to, make any changes.</span></span>
    
      - <span data-ttu-id="74c70-117">Zum Bearbeiten von Einstellungen in einer vorhandenen Auflistung klicken Sie auf die Auflistung und dann auf das Menü **Bearbeiten**. Wählen Sie **Details anzeigen** und nehmen Sie Ihre Änderungen vor.</span><span class="sxs-lookup"><span data-stu-id="74c70-117">To edit any of the settings in an existing collection, click the collection, click the **Edit** menu, click **Show details**, and then make your changes.</span></span>
        
        <div>
        

        > [!TIP]
        > <span data-ttu-id="74c70-p103">Wenn Sie wieder die Standardeinstellungen für die globale Auflistung verwenden möchten, klicken Sie auf das Menü <STRONG>Bearbeiten</STRONG>, dann auf <STRONG>Löschen</STRONG> und schließlich auf <STRONG>OK</STRONG>. Hierdurch wird die globale Auflistung nicht gelöscht; die Einstellungen werden lediglich auf die Standardwerte zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="74c70-p103">To go back to using the default settings for the global collection, click the global collection, click the <STRONG>Edit</STRONG> menu, click <STRONG>Delete</STRONG>, and then click <STRONG>OK</STRONG>. This will not delete the global collection; it just resets the settings to the defaults.</span></span>

        
        </div>

5.  <span data-ttu-id="74c70-120">Klicken Sie auf **Commit**.</span><span class="sxs-lookup"><span data-stu-id="74c70-120">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-new-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="74c70-121">Erstellen neuer lync Phone Edition-Konfigurationseinstellungen mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="74c70-121">Creating New Lync Phone Edition Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="74c70-122">Sie können lync Phone Edition Konfigurationseinstellungen können (nur auf Standortebene) mithilfe von Windows PowerShell und dem **New-CsUCPhoneConfiguration-** Cmdlet erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="74c70-122">You can create Lync Phone Edition configuration settings can (at the site scope only) by using Windows PowerShell and the **New-CsUCPhoneConfiguration** cmdlet.</span></span> <span data-ttu-id="74c70-123">Sie können dieses Cmdlet in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="74c70-123">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="74c70-124">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="74c70-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-new-lync-phone-edition-configuration-settings-that-use-the-default-values"></a><span data-ttu-id="74c70-125">So erstellen Sie neue lync Phone Edition-Konfigurationseinstellungen, die die Standardwerte verwenden</span><span class="sxs-lookup"><span data-stu-id="74c70-125">To create new Lync Phone Edition configuration settings that use the default values</span></span>

  - <span data-ttu-id="74c70-126">Über diesen Befehl wird ein neuer Satz mit Konfigurationseinstellungen für das UC-Telefon für den Standort in Redmond erstellt:</span><span class="sxs-lookup"><span data-stu-id="74c70-126">This command creates a new set of UC phone configuration settings for the Redmond site:</span></span>
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond"
    
    <span data-ttu-id="74c70-127">Da im vorstehenden Befehl (abgesehen vom obligatorischen Identity-Parameter) keine Parameter angegeben wurden, verwendet die neue Auflistung mit Konfigurationseinstellungen für alle enthaltenen Eigenschaften die Standardwerte.</span><span class="sxs-lookup"><span data-stu-id="74c70-127">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span>

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-new-lync-phone-edition-configuration-settings"></a><span data-ttu-id="74c70-128">So ändern Sie einen einzelnen Eigenschaftswert beim Erstellen neuer lync Phone Edition-Konfigurationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="74c70-128">To change a single property value when creating new Lync Phone Edition configuration settings</span></span>

  - <span data-ttu-id="74c70-p105">Zum Erstellen von Einstellungen, die verschiedene Eigenschaftswerte verwenden, geben Sie einfach den entsprechenden Parameter und den Parameterwert an. Um beispielsweise eine Auflistung von Konfigurationseinstellungen für UC-Telefone zu erstellen, für die standardmäßig die Telefonsperre erforderlich ist, müssen Sie einen Befehl wie den folgenden verwenden:</span><span class="sxs-lookup"><span data-stu-id="74c70-p105">To create settings that use different property values, simply include the appropriate parameter and parameter value. For example, to create a collection of UC phone configuration settings that, by default, require phone locking, use a command like this:</span></span>
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-new-lync-phone-edition-configuration-settings"></a><span data-ttu-id="74c70-131">So ändern Sie beim Erstellen neuer lync Phone Edition-Konfigurationseinstellungen mehrere Eigenschaftswerte</span><span class="sxs-lookup"><span data-stu-id="74c70-131">To change multiple property values when creating new Lync Phone Edition configuration settings</span></span>

  - <span data-ttu-id="74c70-p106">Mehrere Eigenschaftswerte können durch die Angabe mehrerer Parameter geändert werden. Der folgende Befehl beispielsweise erzwingt die Telefonsperre und legt gleichzeitig als minimale PIN-Länge 8 Ziffern fest:</span><span class="sxs-lookup"><span data-stu-id="74c70-p106">Multiple property values can be modified by including multiple parameters. For example, this command enforces phone locking and also sets the minimum PIN length to 8 digits:</span></span>
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True -MinPhonePinLength 8

</div>

<span data-ttu-id="74c70-134">Ausführliche Informationen finden Sie unter [New-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398445(v=OCS.15)).</span><span class="sxs-lookup"><span data-stu-id="74c70-134">For details, see [New-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398445(v=OCS.15)).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="74c70-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="74c70-135">See Also</span></span>


[<span data-ttu-id="74c70-136">Löschen einer vorhandenen Sammlung von lync Phone Edition Konfigurationseinstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74c70-136">Delete an existing collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[<span data-ttu-id="74c70-137">Konfigurieren von Sicherheitseinstellungen für lync Phone Edition in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74c70-137">Configure security settings for Lync Phone Edition in Lync Server 2013</span></span>](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[<span data-ttu-id="74c70-138">Erzwingen der Telefonsperre in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74c70-138">Enforce phone locking in Lync Server 2013</span></span>](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

