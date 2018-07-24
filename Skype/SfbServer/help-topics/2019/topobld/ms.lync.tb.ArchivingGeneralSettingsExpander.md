---
title: Allgemeine Einstellungen des Archivierungsservers – Erweiterung
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.ArchivingGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b820af7-8d00-42e2-979c-dbae17159a08
ROBOTS: NOINDEX, NOFOLLOW
description: 'Im Topologie-Generator können Sie die Eigenschaften für einen einzelnen Server, auf dem die Archivierung ausgeführt wird, bearbeiten, indem Sie entweder in der Konsolenstruktur mit der rechten Maustaste auf den jeweiligen Server und dann in der Symbolleiste auf Aktion klicken oder indem Sie im Bereich „Aktionen“ auf eine Aufgabe und anschließend auf Eigenschaften bearbeiten klicken und dann die folgenden Optionen ändern:'
ms.openlocfilehash: 6419b7b4fff2c533a0dc91ab0819b0a58044447d
ms.sourcegitcommit: 1f7299f535ec6b34f92301b4abc14d8922492eeb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "21060112"
---
# <a name="archiving-server-general-settings-expander"></a><span data-ttu-id="d3e00-103">Allgemeine Einstellungen des Archivierungsservers – Erweiterung</span><span class="sxs-lookup"><span data-stu-id="d3e00-103">Archiving Server General Settings Expander</span></span>
 
<span data-ttu-id="d3e00-104">Im Topologie-Generator können Sie die Eigenschaften für einen einzelnen Server, auf dem die Archivierung ausgeführt wird, bearbeiten, indem Sie entweder in der Konsolenstruktur mit der rechten Maustaste auf den jeweiligen Server und dann in der Symbolleiste auf **Aktion** klicken oder indem Sie im Bereich „Aktionen“ auf eine Aufgabe und anschließend auf **Eigenschaften bearbeiten** klicken und dann die folgenden Optionen ändern:</span><span class="sxs-lookup"><span data-stu-id="d3e00-104">In Topology Builder, you can edit the properties for an individual server running Archiving either by right-clicking the server running Archiving in the console tree and clicking **Action** in the toolbar, or by clicking a task in the Actions pane, and then clicking **Edit Properties** and changing any of the following options:</span></span>
  
- <span data-ttu-id="d3e00-105">**FQDN**: Zum Ändern des vollqualifizierten Domänennamens des Servers, der als Server bereitgestellt werden soll, auf dem die Archivierung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d3e00-105">**FQDN**, to change the fully qualified domain name (FQDN) of the server that you want to deploy as an Server running Archiving.</span></span>
    
- <span data-ttu-id="d3e00-p101">**SQL-Speicher**: Zum Ändern der Instanz von SQL Server, die für die SQL Server-Archivierungsdatenbank verwendet werden soll. Wenn Sie die SQL Server-Datenbank eines Servers ändern, auf dem die Archivierung ausgeführt wird, müssen Sie den entsprechenden Server neu starten, damit die Änderungen wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="d3e00-p101">**SQL store**, to change the instance of SQL Server to be used for the archiving SQL Server database. If you change the SQL Server database of a server running Archiving, you must restart the server running Archiving to make sure that the change takes effect.</span></span>
    
- <span data-ttu-id="d3e00-p102">**Dateifreigabe**: Zum Ändern des Ordners, der für den Archivierungsdateispeicher verwendet werden soll. Wenn Sie die Dateifreigabe eines Servers ändern, auf dem die Archivierung ausgeführt wird, müssen Sie den entsprechenden Server neu starten, damit die Änderungen wirksam werden. Darüber hinaus müssen Sie vorherige Konferenzdateien in den Ordner des neuen Dateispeichers verschieben, um den Verlust von archivierten Konferenzdateien zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="d3e00-p102">**File share**, to change the folder to be used for the archiving file store. If you change the file share of a Server running Archiving, you must restart the Server running Archiving to make sure that the change takes effect. Additionally, you must move previous conference files to the new file store folder to avoid loss of archived conference files.</span></span>
    
> [!NOTE]
> <span data-ttu-id="d3e00-111">Wählen Sie die Option **Eigenschaften bearbeiten** für den Knoten des Front-End-Pools oder der Survivable Branch-Anwendung aus, der momentan dem Server zugeordnet ist, auf dem die Archivierung ausgeführt wird, um die dem entsprechenden Server zugeordneten Pools zu ändern.</span><span class="sxs-lookup"><span data-stu-id="d3e00-111">To change the pools associated with a server running Archiving, select the **Edit Properties** option for the individual Front End pool node or Survivable Branch Appliance node that is currently associated with the server running Archiving.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d3e00-p103">Der Knoten „Archivierung“ enthält einen Server, auf dem die Archivierung ausgeführt wird, wenn Sie der Topologie im Topologie-Generator vorher einen entsprechenden Server hinzugefügt haben. Sie können die Eigenschaften für jeden Server, auf dem die Archivierung ausgeführt wird, in der Liste bearbeiten. Chat- oder Webkonferenzdaten (Sprachnachrichten) können jedoch erst archiviert werden, wenn Sie auch den Dienst für den Server eingerichtet haben, auf dem die Archivierung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d3e00-p103">The Archiving node contains a server running Archiving if you have previously added a server running Archiving to the topology in Topology Builder. You can edit properties for any server running Archiving in the list. However, instant messaging or web conferencing (messaging) cannot be archived until you also set up the service for the server running Archiving.</span></span> 
  

