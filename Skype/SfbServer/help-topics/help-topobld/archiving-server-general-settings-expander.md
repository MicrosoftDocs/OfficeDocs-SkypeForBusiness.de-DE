---
title: Allgemeine Einstellungen des Archivierungsservers – Erweiterung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.ArchivingGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b820af7-8d00-42e2-979c-dbae17159a08
description: 'Im Topologie-Generator können Sie die Eigenschaften für einen einzelnen Server, auf dem die Archivierung ausgeführt wird, entweder mit der rechten Maustaste auf den Server, auf dem die Archivierung ausgeführt wird, in der Konsolenstruktur bearbeiten und in der Symbolleiste auf Aktion klicken, oder indem Sie im Bereich "Aktionen" auf eine Aufgabe klicken und dann auf Eigenschaften bearbeiten und eine der folgenden Optionen ändern:'
ms.openlocfilehash: d160b9e7294719ff2251e95e5cc2ab72dd3a6ffd
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216896"
---
# <a name="archiving-server-general-settings-expander"></a>Allgemeine Einstellungen des Archivierungsservers – Erweiterung
 
Im Topologie-Generator können Sie die Eigenschaften für einen einzelnen Server, auf dem die Archivierung ausgeführt wird, entweder mit der rechten Maustaste auf den Server, auf dem die Archivierung ausgeführt wird, in der Konsolenstruktur bearbeiten und in der Symbolleiste auf **Aktion** klicken, oder indem Sie im Bereich "Aktionen" auf eine Aufgabe klicken und dann auf **Eigenschaften bearbeiten** und eine der folgenden Optionen ändern:
  
- **FQDN**: Zum Ändern des vollqualifizierten Domänennamens des Servers, der als Server bereitgestellt werden soll, auf dem die Archivierung ausgeführt wird.
    
- **SQL-Speicher**: Zum Ändern der Instanz von SQL Server, die für die SQL Server-Archivierungsdatenbank verwendet werden soll. Wenn Sie die SQL Server-Datenbank eines Servers ändern, auf dem die Archivierung ausgeführt wird, müssen Sie den entsprechenden Server neu starten, damit die Änderungen wirksam werden.
    
- **Dateifreigabe**: Zum Ändern des Ordners, der für den Archivierungsdateispeicher verwendet werden soll. Wenn Sie die Dateifreigabe eines Servers ändern, auf dem die Archivierung ausgeführt wird, müssen Sie den entsprechenden Server neu starten, damit die Änderungen wirksam werden. Darüber hinaus müssen Sie vorherige Konferenzdateien in den Ordner des neuen Dateispeichers verschieben, um den Verlust von archivierten Konferenzdateien zu verhindern.
    
> [!NOTE]
> Wählen Sie die Option **Eigenschaften bearbeiten** für den Knoten des Front-End-Pools oder den Survivable Branch Appliance-Knoten aus, der momentan dem Server zugeordnet ist, auf dem die Archivierung ausgeführt wird, um die dem entsprechenden Server zugeordneten Pools zu ändern.
  
> [!NOTE]
> Der Knoten Archivierung enthält einen Server, der die Archivierung ausführt, wenn Sie der Topologie im Topologie-Generator zuvor einen Server mit der Archivierung hinzugefügt haben. Sie können die Eigenschaften für jeden Server, auf dem die Archivierung läuft, in der Liste bearbeiten. Instant Messaging-oder Webkonferenzen (Messaging) können jedoch erst archiviert werden, wenn Sie den Dienst für den Server eingerichtet haben, auf dem die Archivierung läuft. 
  

