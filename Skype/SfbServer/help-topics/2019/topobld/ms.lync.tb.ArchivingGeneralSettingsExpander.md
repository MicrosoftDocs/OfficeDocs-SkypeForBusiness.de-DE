---
title: Allgemeine Einstellungen des Archivierungsservers – Erweiterung
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.ArchivingGeneralSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 0b820af7-8d00-42e2-979c-dbae17159a08
ROBOTS: NOINDEX, NOFOLLOW
description: 'Im Topologie-Generator können Sie die Eigenschaften für einen einzelnen Server bearbeiten, auf dem die Archivierung ausgeführt wird, indem Sie entweder mit der rechten Maustaste auf den Server klicken, auf dem die Archivierung in der Konsolenstruktur ausgeführt wird, und auf der Symbolleiste auf Aktion klicken, oder indem Sie im Bereich "Aktionen" auf eine Aufgabe klicken und dann auf "Eigenschaften bearbeiten" klicken und eine der folgenden Optionen ändern:'
ms.openlocfilehash: 331aa14ff8adee17c201c4e1bf71dbe411d97ac8
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60836817"
---
# <a name="archiving-server-general-settings-expander"></a>Allgemeine Einstellungen des Archivierungsservers – Erweiterung
 
Im Topologie-Generator können Sie die Eigenschaften für einen einzelnen Server bearbeiten, auf dem die Archivierung ausgeführt wird, indem Sie entweder mit der rechten Maustaste auf den Server klicken, auf dem die Archivierung in der Konsolenstruktur ausgeführt wird, und auf der Symbolleiste auf **Aktion** klicken, oder indem Sie im Bereich "Aktionen" auf eine Aufgabe klicken und dann auf **"Eigenschaften bearbeiten"** klicken und eine der folgenden Optionen ändern:
  
- **FQDN**: Zum Ändern des vollqualifizierten Domänennamens des Servers, der als Server bereitgestellt werden soll, auf dem die Archivierung ausgeführt wird.
    
- **SQL-Speicher**: Zum Ändern der Instanz von SQL Server, die für die SQL Server-Archivierungsdatenbank verwendet werden soll. Wenn Sie die SQL Server-Datenbank eines Servers ändern, auf dem die Archivierung ausgeführt wird, müssen Sie den entsprechenden Server neu starten, damit die Änderungen wirksam werden.
    
- **Dateifreigabe**: Zum Ändern des Ordners, der für den Archivierungsdateispeicher verwendet werden soll. Wenn Sie die Dateifreigabe eines Servers ändern, auf dem die Archivierung ausgeführt wird, müssen Sie den entsprechenden Server neu starten, damit die Änderungen wirksam werden. Darüber hinaus müssen Sie vorherige Konferenzdateien in den Ordner des neuen Dateispeichers verschieben, um den Verlust von archivierten Konferenzdateien zu verhindern.
    
> [!NOTE]
> Wählen Sie die Option **Eigenschaften bearbeiten** für den Knoten des Front-End-Pools oder den Survivable Branch Appliance-Knoten aus, der momentan dem Server zugeordnet ist, auf dem die Archivierung ausgeführt wird, um die dem entsprechenden Server zugeordneten Pools zu ändern.
  
> [!NOTE]
> Der Archivierungsknoten enthält einen Server, auf dem die Archivierung ausgeführt wird, wenn Sie der Topologie im Topologie-Generator zuvor einen Server mit Archivierung hinzugefügt haben. Sie können Eigenschaften für jeden Server bearbeiten, auf dem die Archivierung in der Liste ausgeführt wird. Chatnachrichten oder Webkonferenzen (Messaging) können jedoch erst archiviert werden, wenn Sie auch den Dienst für den Server eingerichtet haben, auf dem die Archivierung ausgeführt wird. 
  

