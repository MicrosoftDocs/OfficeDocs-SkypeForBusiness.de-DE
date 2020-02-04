---
title: Installieren des lokalen Konfigurationsspeichers – Aufruf (Konfiguration)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployReplicaConfig
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 92dccbca-7a5b-4064-9f2e-964b8e62433c
ROBOTS: NOINDEX, NOFOLLOW
description: Wenn Sie mit der Installation der Datenbank beginnen möchten, die die lokale schreibgeschützte Kopie des zentralen Verwaltungsspeichers enthält, wählen Sie zwischen dem Abrufen der definierten Konfiguration, die mithilfe des Topologie-Generators aus dem bereits installierten und konfigurierten zentralen Verwaltungsspeicher oder Lesen der definierten Konfiguration von anderen Medien. Wählen Sie für einen Computer, der sich im internen Netzwerk Ihrer Organisation befindet, die Option Konfiguration automatisch aus dem zentralen Verwaltungsspeicher abrufen aus.
ms.openlocfilehash: a689d8cd7926cca109b808f8a186396dd48caaf8
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41705300"
---
# <a name="install-local-configuration-store-invoke-configure"></a><span data-ttu-id="39429-104">Installieren des lokalen Konfigurationsspeichers – Aufruf (Konfiguration)</span><span class="sxs-lookup"><span data-stu-id="39429-104">Install Local Configuration Store Invoke (Configure)</span></span>
 
<span data-ttu-id="39429-105">Wenn Sie mit der Installation der Datenbank beginnen möchten, die die lokale schreibgeschützte Kopie des zentralen Verwaltungsspeichers enthält, wählen Sie zwischen dem Abrufen der definierten Konfiguration, die mithilfe des Topologie-Generators aus dem bereits installierten und konfigurierten zentralen Verwaltungsspeicher oder Lesen der definierten Konfiguration von anderen Medien.</span><span class="sxs-lookup"><span data-stu-id="39429-105">To begin the installation of the database that will hold the local read-only copy of the Central Management store, you select between retrieving the defined configuration published by using Topology Builder from the already installed and configured Central Management store, or reading the defined configuration from other media.</span></span> <span data-ttu-id="39429-106">Wählen Sie für einen Computer, der sich im internen Netzwerk Ihrer Organisation befindet, **die Option Konfiguration automatisch aus dem zentralen Verwaltungsspeicher abrufen aus**.</span><span class="sxs-lookup"><span data-stu-id="39429-106">For a machine that is on your organization's internal network, select **Retrieve configuration automatically from the Central Management Store**.</span></span>
  
<span data-ttu-id="39429-107">Wenn Sie ein Replikat des zentralen Verwaltungsspeichers auf einem Edgeserver installieren, wählen Sie aus, um die exportierte Kopie des Konfigurationsdokuments von tragbaren Medien wie einem USB-Flashlaufwerk, einem USB-Festplattenlaufwerk, einer CD-ROM oder einem anderen Medium zu lesen.</span><span class="sxs-lookup"><span data-stu-id="39429-107">If you are installing a replica of the Central Management store on an Edge Server, you select to read the exported copy of the configuration document from portable media, such as a USB flash drive, USB hard disk drive, CD-ROM, or other media.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="39429-108">Wenn Sie den lokalen Konfigurationsspeicher auf einem Edgeserver installieren, müssen die Konfigurationsinformationen in einem Format vorliegen, das aus dem zentralen Verwaltungsspeicher exportiert wurde, indem Sie das Windows PowerShell-Cmdlet ausführen:`Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`</span><span class="sxs-lookup"><span data-stu-id="39429-108">If you are installing the Local Configuration store on an Edge Server, the configuration information must be in a format that was exported from the Central Management store by running the Windows PowerShell cmdlet:  `Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`</span></span>
  
<span data-ttu-id="39429-109">Nachdem Sie die entsprechende Option ausgewählt haben, klicken Sie auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="39429-109">After you have selected the appropriate option, click **Next**.</span></span>
  

