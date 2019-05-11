---
title: Installieren des lokalen Konfigurationsspeichers – Aufruf (Konfiguration)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: e9a5744d9a73c1f7263a78f3852d5915f5703066
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33910981"
---
# <a name="install-local-configuration-store-invoke-configure"></a>Installieren des lokalen Konfigurationsspeichers – Aufruf (Konfiguration)
 
Zum Starten der Installation der Datenbank, die die lokale schreibgeschützte Kopie des zentralen Verwaltungsspeichers enthalten soll, wählen Sie zwischen Abrufen der Konfigurations des definierten veröffentlichte mithilfe des Topologie-Generator von der Central bereits installiert und konfiguriert Verwaltungsspeicher, oder lesen die definierte Konfiguration von einem anderen Medium. Wählen Sie für einen Computer, auf dem internen Netzwerk Ihrer Organisation ist in **Konfiguration automatisch aus dem zentralen Verwaltungsspeicher abrufen**.
  
Wenn Sie ein Replikat des zentralen Verwaltungsspeichers auf einem Edge-Server installieren, wählen Sie die exportierte Kopie des Dokuments Konfiguration von Wechselmedium, wie einem USB-Laufwerk, USB-Laufwerk, CD-ROM- oder anderen Medien lesen. 
  
> [!IMPORTANT]
> Wenn Sie den lokalen Konfigurationsspeicher auf einem Edge-Server installieren, müssen die Konfigurationsinformationen werden in einem Format, das aus dem zentralen exportiert wurde speichern durch Ausführen des Windows PowerShell-Cmdlets:`Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`
  
Nachdem Sie die entsprechende Option ausgewählt haben, klicken Sie auf **Weiter**.
  

