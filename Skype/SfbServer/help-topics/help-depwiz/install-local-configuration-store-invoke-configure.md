---
title: Aufrufen von lokalen Konfigurationsspeicher installieren (Konfiguration)
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
ms.openlocfilehash: 74269ee40116b91097c77702942f42de9f7d882a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="install-local-configuration-store-invoke-configure"></a>Aufrufen von lokalen Konfigurationsspeicher installieren (Konfiguration)
 
Zum Starten der Installation der Datenbank, die die lokale schreibgeschützte Kopie des zentralen Verwaltungsspeichers enthalten soll, wählen Sie zwischen Abrufen der Konfigurations des definierten veröffentlichte mithilfe des Topologie-Generator von der Central bereits installiert und konfiguriert Verwaltungsspeicher, oder lesen die definierte Konfiguration von einem anderen Medium. Wählen Sie für einen Computer, auf dem internen Netzwerk Ihrer Organisation ist in **Konfiguration automatisch aus dem zentralen Verwaltungsspeicher abrufen**.
  
Wenn Sie ein Replikat des zentralen Verwaltungsspeichers auf einem Edge-Server installieren, wählen Sie die exportierte Kopie des Dokuments Konfiguration von Wechselmedium, wie einem USB-Laufwerk, USB-Laufwerk, CD-ROM- oder anderen Medien lesen. 
  
> [!IMPORTANT]
> Wenn Sie den lokalen Konfigurationsspeicher auf einem Edge-Server installieren, müssen die Konfigurationsinformationen werden in einem Format, das aus dem zentralen exportiert wurde speichern durch Ausführen des Windows PowerShell-Cmdlets:`Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`
  
Nachdem Sie die entsprechende Option ausgewählt haben, klicken Sie auf **Weiter**.
  

