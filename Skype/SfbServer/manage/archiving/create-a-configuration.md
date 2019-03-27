---
title: Erstellen einer Archivierungskonfiguration in Skype für Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dc574afa-0b7d-404f-99b3-c812430b7c70
description: 'Zusammenfassung: Informationen Sie zum Erstellen einer Archivierungskonfiguration für Skype für Business Server.'
ms.openlocfilehash: 2a45a627ab8bbeedd18d1cbda636606ebc641745
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881284"
---
# <a name="create-an-archiving-configuration-in-skype-for-business-server"></a><span data-ttu-id="81958-103">Erstellen einer Archivierungskonfiguration in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="81958-103">Create an archiving configuration in Skype for Business Server</span></span>

<span data-ttu-id="81958-104">**Zusammenfassung:** Informationen Sie zum Erstellen einer Archivierungskonfiguration für Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="81958-104">**Summary:** Learn how to create an archiving configuration for Skype for Business Server.</span></span>
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a><span data-ttu-id="81958-105">Konfigurieren von Archivierungsoptionen mithilfe der Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="81958-105">Configure archiving options by using the Control Panel</span></span>

<span data-ttu-id="81958-106">So konfigurieren Sie Archivierungsoptionen für einen bestimmten Standort oder einen bestimmten Pool:</span><span class="sxs-lookup"><span data-stu-id="81958-106">To configure archiving options for a specific site or pool:</span></span> 
  
1. <span data-ttu-id="81958-107">Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsArchivingAdministrator“ oder „CsAdministrator“ zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="81958-107">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="81958-108">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="81958-108">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="81958-109">Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="81958-109">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="81958-110">Klicken Sie auf der Seite **Archivierungskonfiguration** auf **Neu** und führen Sie eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="81958-110">On the **Archiving Configuration** page, click **New**, and then do one of the following:</span></span> 
    
   - <span data-ttu-id="81958-111">Um eine Standortarchivierungskonfiguration zu erstellen, klicken Sie auf **Standortkonfiguration** und wählen Sie anschließend in **Standort auswählen** den Standort aus, der für die Archivierung konfiguriert werden soll.</span><span class="sxs-lookup"><span data-stu-id="81958-111">To create a site archiving configuration, click **Site Configuration**, and then in **Select a site**, select the site to be configured for archiving.</span></span>
    
   - <span data-ttu-id="81958-112">Um eine Poolarchivierungskonfiguration zu erstellen, klicken Sie auf **Poolkonfiguration** und wählen Sie anschließend in **Pool auswählen** den Pool aus, der für die Archivierung konfiguriert werden soll.</span><span class="sxs-lookup"><span data-stu-id="81958-112">To create a pool archiving configuration, click **Pool Configuration**, and then in **Select a pool**, select the pool to be configured for archiving.</span></span>
    
5. <span data-ttu-id="81958-113">Führen Sie unter **Neue Archivierungseinstellung** im Dropdown-Listenfeld **Archivierungseinstellung** eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="81958-113">In **New Archiving Setting**, in the **Archiving setting** drop-down list box, do one of the following:</span></span>
    
   - <span data-ttu-id="81958-114">Klicken Sie auf **Chatsitzungen archivieren**, um die Archivierung ausschließlich für Chatsitzungen zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="81958-114">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
   - <span data-ttu-id="81958-115">Klicken Sie auf **Chat- und Webkonferenzsitzungen archivieren**, um sowohl Chatsitzungen als auch Konferenzen zu archivieren.</span><span class="sxs-lookup"><span data-stu-id="81958-115">To enable archiving for both IM sessions and web conferences, click **Archive IM and web conferencing sessions**.</span></span>
    
   - <span data-ttu-id="81958-116">Klicken Sie auf **Archivierung deaktivieren**, um die Archivierung für diese Konfiguration zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="81958-116">To disable archiving for this configuration, click **Disable archiving**.</span></span>
    
6. <span data-ttu-id="81958-117">Führen Sie außerdem in **Neue Archivierungseinstellung** die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="81958-117">Also in **New Archiving Setting**, do the following:</span></span>
    
   - <span data-ttu-id="81958-118">Aktivieren Sie das Kontrollkästchen **Bei Archivierungsfehler Chat- oder Webkonferenzsitzungen blockieren**, um Aktivitäten zu blockieren, wenn die Archivierung nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="81958-118">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="81958-119">Klicken Sie auf das Kontrollkästchen **Microsoft Exchange-Integration** , um die Verwendung von Microsoft Exchange Server zum Speichern von archivierten Daten.</span><span class="sxs-lookup"><span data-stu-id="81958-119">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="81958-120">Zum Aktivieren des Löschvorgangs für Daten aktivieren Sie das Kontrollkästchen **Bereinigungsfunktion für alle Archivierungsdaten aktivieren** und führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="81958-120">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
     - <span data-ttu-id="81958-121">Klicken Sie auf **Löschen von exportierten und gespeicherten Archivierungsdaten nach einer Höchstdauer von (Tage)** und geben Sie eine Anzahl von Tagen an, um die archivierten Inhalte nach einer bestimmten Anzahl von Tagen zu löschen.</span><span class="sxs-lookup"><span data-stu-id="81958-121">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
     - <span data-ttu-id="81958-122">Klicken Sie auf **Nur exportierte Archivierungsdaten löschen**, um nur die exportierten Daten zu löschen.</span><span class="sxs-lookup"><span data-stu-id="81958-122">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
7. <span data-ttu-id="81958-123">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="81958-123">Click **Commit**.</span></span>
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a><span data-ttu-id="81958-124">Konfigurieren von Archivierungsoptionen mit Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="81958-124">Configure archiving options by using Windows PowerShell</span></span>

<span data-ttu-id="81958-125">Mithilfe des Cmdlets **New-CsArchivingConfiguration** können Sie ebenfalls Archivierungsoptionen für einen bestimmten Standort oder einen bestimmten Pool konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="81958-125">You can also configure archiving options for a specific site or pool by using the **New-CsArchivingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="81958-126">Mit dem folgenden Befehl wird eine neue Auflistung von Archivierungskonfigurationseinstellungen für den Standort „Redmond“ erstellt:</span><span class="sxs-lookup"><span data-stu-id="81958-126">The following command creates a new collection of archiving configuration settings for the Redmond site:</span></span>
  
```
New-CsArchivingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="81958-127">Da im vorherigen Befehl keine weiteren Parameter außer dem obligatorischen Identity-Parameter angegeben wurden, werden in der neuen Auflistung von Konfigurationseinstellungen für alle Eigenschaften die Standardwerte verwendet.</span><span class="sxs-lookup"><span data-stu-id="81958-127">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span> 
  
<span data-ttu-id="81958-p101">Zum Erstellen von Einstellungen, die verschiedene Eigenschaftswerte verwenden, geben Sie einfach den entsprechenden Parameter und den Parameterwert an. Im folgenden Beispiel wird eine Auflistung von Konfigurationseinstellungen erstellt, die standardmäßig nur die Archivierung von Chatsitzungen zulassen:</span><span class="sxs-lookup"><span data-stu-id="81958-p101">To create settings that use different property values, simply include the appropriate parameter and parameter value. The following example creates a collection of archiving configuration settings that, by default, allow archiving of instant messaging sessions only:</span></span>
  
```
New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly"
```

<span data-ttu-id="81958-p102">Mehrere Eigenschaftswerte können geändert werden, indem Sie mehrere Parameter angeben. Beispielsweise werden mit dem folgenden Befehl die neuen Einstellungen so konfiguriert, dass Chatsitzungen archiviert werden und Chats blockiert werden, falls der Archivierungsdienst nicht verfügbar ist:</span><span class="sxs-lookup"><span data-stu-id="81958-p102">Multiple property values can be modified by including multiple parameters. For example, this command configures the new settings to archive instant messaging sessions and to block instant messaging of the archiving service is not available:</span></span>
  
```
New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly" -BlockOnArchiveFailure $True
```

<span data-ttu-id="81958-132">Weitere Informationen finden Sie im Hilfethema für das [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csarchivingconfiguration?view=skype-ps) -Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="81958-132">For more information, see the help topic for the [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csarchivingconfiguration?view=skype-ps) cmdlet.</span></span>
