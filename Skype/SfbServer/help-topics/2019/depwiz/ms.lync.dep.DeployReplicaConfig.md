---
title: Installieren des lokalen Konfigurationsspeichers – Aufruf (Konfiguration)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployReplicaConfig
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 92dccbca-7a5b-4064-9f2e-964b8e62433c
ROBOTS: NOINDEX, NOFOLLOW
description: Um mit der Installation der Datenbank zu beginnen, die die lokale schreibgeschützte Kopie des zentralen Verwaltungsspeichers enthält, können Sie zwischen dem Abrufen der definierten Konfiguration, die mithilfe des Topologie-Generators veröffentlicht wurde, aus dem bereits installierten und konfigurierten zentralen Verwaltungsspeicher oder dem Lesen der definierten Konfiguration von anderen Medien auswählen. Wählen Sie für einen Computer, der sich im internen Netzwerk Ihrer Organisation befindet, die Option "Konfiguration automatisch abrufen" aus dem zentralen Verwaltungsspeicher aus.
ms.openlocfilehash: f8f9aeaccb510de4efec0020a8993d56851d0544
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801545"
---
# <a name="install-local-configuration-store-invoke-configure"></a>Installieren des lokalen Konfigurationsspeichers – Aufruf (Konfiguration)
 
Um mit der Installation der Datenbank zu beginnen, die die lokale schreibgeschützte Kopie des zentralen Verwaltungsspeichers enthält, können Sie zwischen dem Abrufen der definierten Konfiguration, die mithilfe des Topologie-Generators veröffentlicht wurde, aus dem bereits installierten und konfigurierten zentralen Verwaltungsspeicher oder dem Lesen der definierten Konfiguration von anderen Medien auswählen. Wählen Sie für einen Computer, der sich im internen Netzwerk Ihrer Organisation befindet, die Option "Konfiguration automatisch abrufen" aus **dem zentralen Verwaltungsspeicher aus.**
  
Wenn Sie ein Replikat des zentralen Verwaltungsspeichers auf einem Edgeserver speichern, sollten Sie sich für das Lesen der exportierten Kopie des Konfigurationsdokuments von tragbaren Medien entscheiden, z. B. einem USB-Stick, einem USB-Festplattenlaufwerk, einer CD-ROM oder anderen Medien. 
  
> [!IMPORTANT]
> Wenn Sie den lokalen Konfigurationsspeicher auf einem Edgeserver installieren, müssen die Konfigurationsinformationen in einem Format vorliegen, das durch Ausführen des cmdlets Windows PowerShell wurde:  `Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`
  
Klicken Sie nach dem Auswählen der gewünschten Optionen auf **Weiter**.
  

