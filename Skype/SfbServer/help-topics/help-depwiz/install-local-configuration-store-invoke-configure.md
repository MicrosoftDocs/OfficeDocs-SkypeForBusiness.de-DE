---
title: Installieren des lokalen Konfigurationsspeichers – Aufruf (Konfiguration)
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployReplicaConfig
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 92dccbca-7a5b-4064-9f2e-964b8e62433c
description: Zum Starten der Installation der Datenbank, die die lokale schreibgeschützte Kopie des zentralen Verwaltungsspeichers enthalten soll, wählen Sie zwischen Abrufen der Konfigurations des definierten veröffentlichte mithilfe des Topologie-Generator von der Central bereits installiert und konfiguriert Verwaltungsspeicher, oder lesen die definierte Konfiguration von einem anderen Medium. Wählen Sie für einen Computer, auf dem internen Netzwerk Ihrer Organisation ist automatisch aus dem zentralen Verwaltungsspeicher Konfiguration abrufen.
ms.openlocfilehash: d8577e6eb18d57669657afb93ed07da37ffa31cd
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30894649"
---
# <a name="install-local-configuration-store-invoke-configure"></a><span data-ttu-id="5e6b2-104">Installieren des lokalen Konfigurationsspeichers – Aufruf (Konfiguration)</span><span class="sxs-lookup"><span data-stu-id="5e6b2-104">Install Local Configuration Store Invoke (Configure)</span></span>
 
<span data-ttu-id="5e6b2-105">Zum Starten der Installation der Datenbank, die die lokale schreibgeschützte Kopie des zentralen Verwaltungsspeichers enthalten soll, wählen Sie zwischen Abrufen der Konfigurations des definierten veröffentlichte mithilfe des Topologie-Generator von der Central bereits installiert und konfiguriert Verwaltungsspeicher, oder lesen die definierte Konfiguration von einem anderen Medium.</span><span class="sxs-lookup"><span data-stu-id="5e6b2-105">To begin the installation of the database that will hold the local read-only copy of the Central Management store, you select between retrieving the defined configuration published by using Topology Builder from the already installed and configured Central Management store, or reading the defined configuration from other media.</span></span> <span data-ttu-id="5e6b2-106">Wählen Sie für einen Computer, auf dem internen Netzwerk Ihrer Organisation ist in **Konfiguration automatisch aus dem zentralen Verwaltungsspeicher abrufen**.</span><span class="sxs-lookup"><span data-stu-id="5e6b2-106">For a machine that is on your organization's internal network, select **Retrieve configuration automatically from the Central Management Store**.</span></span>
  
<span data-ttu-id="5e6b2-107">Wenn Sie ein Replikat des zentralen Verwaltungsspeichers auf einem Edge-Server installieren, wählen Sie die exportierte Kopie des Dokuments Konfiguration von Wechselmedium, wie einem USB-Laufwerk, USB-Laufwerk, CD-ROM- oder anderen Medien lesen.</span><span class="sxs-lookup"><span data-stu-id="5e6b2-107">If you are installing a replica of the Central Management store on an Edge Server, you select to read the exported copy of the configuration document from portable media, such as a USB flash drive, USB hard disk drive, CD-ROM, or other media.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="5e6b2-108">Wenn Sie den lokalen Konfigurationsspeicher auf einem Edge-Server installieren, müssen die Konfigurationsinformationen werden in einem Format, das aus dem zentralen exportiert wurde speichern durch Ausführen des Windows PowerShell-Cmdlets:`Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`</span><span class="sxs-lookup"><span data-stu-id="5e6b2-108">If you are installing the Local Configuration store on an Edge Server, the configuration information must be in a format that was exported from the Central Management store by running the Windows PowerShell cmdlet:  `Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`</span></span>
  
<span data-ttu-id="5e6b2-109">Nachdem Sie die entsprechende Option ausgewählt haben, klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="5e6b2-109">After you have selected the appropriate option, click **Next**.</span></span>
  

