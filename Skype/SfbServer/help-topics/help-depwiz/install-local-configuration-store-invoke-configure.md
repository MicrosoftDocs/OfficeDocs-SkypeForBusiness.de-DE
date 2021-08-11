---
title: Installieren des lokalen Konfigurationsspeichers – Aufruf (Konfiguration)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployReplicaConfig
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 92dccbca-7a5b-4064-9f2e-964b8e62433c
description: Um mit der Installation der Datenbank zu beginnen, die die lokale schreibgeschützte Kopie des zentralen Verwaltungsspeichers enthält, wählen Sie zwischen dem Abrufen der definierten Konfiguration, die mithilfe des Topologie-Generators veröffentlicht wurde, aus dem bereits installierten und konfigurierten zentralen Verwaltungsspeicher oder dem Lesen der definierten Konfiguration von anderen Medien. Wählen Sie für einen Computer, der sich im internen Netzwerk Ihrer Organisation befindet, die Option "Konfiguration automatisch aus der zentralen Verwaltung Store abrufen" aus.
ms.openlocfilehash: 6035603e638a8d1459310c8b73002b5c9e922fc76e166cbd880ad9614f161563
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54285115"
---
# <a name="install-local-configuration-store-invoke-configure"></a>Installieren des lokalen Konfigurationsspeichers – Aufruf (Konfiguration)
 
Um mit der Installation der Datenbank zu beginnen, die die lokale schreibgeschützte Kopie des zentralen Verwaltungsspeichers enthält, wählen Sie zwischen dem Abrufen der definierten Konfiguration, die mithilfe des Topologie-Generators veröffentlicht wurde, aus dem bereits installierten und konfigurierten zentralen Verwaltungsspeicher oder dem Lesen der definierten Konfiguration von anderen Medien. Wählen Sie für einen Computer, der sich im internen Netzwerk Ihrer Organisation befindet, die Option **"Konfiguration automatisch aus der zentralen Verwaltung Store abrufen" aus.**
  
Wenn Sie ein Replikat des zentralen Verwaltungsspeichers auf einem Edgeserver speichern, sollten Sie sich für das Lesen der exportierten Kopie des Konfigurationsdokuments von tragbaren Medien entscheiden, z. B. einem USB-Stick, einem USB-Festplattenlaufwerk, einer CD-ROM oder anderen Medien. 
  
> [!IMPORTANT]
> Wenn Sie den lokalen Konfigurationsspeicher auf einem Edgeserver installieren, müssen die Konfigurationsinformationen in einem Format vorliegen, das aus dem zentralen Verwaltungsspeicher exportiert wurde, indem Sie das Cmdlet Windows PowerShell ausführen:`Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`
  
Klicken Sie nach dem Auswählen der gewünschten Optionen auf **Weiter**.
  

