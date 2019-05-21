---
title: Allgemeine Einstellungen des Archivierungsservers – Erweiterung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.ArchivingGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b820af7-8d00-42e2-979c-dbae17159a08
description: 'Im Topologie-Generator können Sie die Eigenschaften für einen einzelnen Server, auf dem die Archivierung ausgeführt wird, bearbeiten, indem Sie entweder in der Konsolenstruktur mit der rechten Maustaste auf den jeweiligen Server und dann in der Symbolleiste auf Aktion klicken oder indem Sie im Bereich „Aktionen“ auf eine Aufgabe und anschließend auf Eigenschaften bearbeiten klicken und dann die folgenden Optionen ändern:'
ms.openlocfilehash: 224b149dd7ff3d0a1398bf7cb644ebb259d5b949
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34288775"
---
# <a name="archiving-server-general-settings-expander"></a>Allgemeine Einstellungen des Archivierungsservers – Erweiterung
 
Im Topologie-Generator können Sie die Eigenschaften für einen einzelnen Server, auf dem die Archivierung ausgeführt wird, bearbeiten, indem Sie entweder in der Konsolenstruktur mit der rechten Maustaste auf den jeweiligen Server und dann in der Symbolleiste auf **Aktion** klicken oder indem Sie im Bereich „Aktionen“ auf eine Aufgabe und anschließend auf **Eigenschaften bearbeiten** klicken und dann die folgenden Optionen ändern:
  
- **FQDN**: Zum Ändern des vollqualifizierten Domänennamens des Servers, der als Server bereitgestellt werden soll, auf dem die Archivierung ausgeführt wird.
    
- **SQL-Speicher**: Zum Ändern der Instanz von SQL Server, die für die SQL Server-Archivierungsdatenbank verwendet werden soll. Wenn Sie die SQL Server-Datenbank eines Servers ändern, auf dem die Archivierung ausgeführt wird, müssen Sie den entsprechenden Server neu starten, damit die Änderungen wirksam werden.
    
- **Dateifreigabe**: Zum Ändern des Ordners, der für den Archivierungsdateispeicher verwendet werden soll. Wenn Sie die Dateifreigabe eines Servers ändern, auf dem die Archivierung ausgeführt wird, müssen Sie den entsprechenden Server neu starten, damit die Änderungen wirksam werden. Darüber hinaus müssen Sie vorherige Konferenzdateien in den Ordner des neuen Dateispeichers verschieben, um den Verlust von archivierten Konferenzdateien zu verhindern.
    
> [!NOTE]
> Wählen Sie die Option **Eigenschaften bearbeiten** für den Knoten des Front-End-Pools oder der Survivable Branch-Anwendung aus, der momentan dem Server zugeordnet ist, auf dem die Archivierung ausgeführt wird, um die dem entsprechenden Server zugeordneten Pools zu ändern.
  
> [!NOTE]
> Der Knoten „Archivierung“ enthält einen Server, auf dem die Archivierung ausgeführt wird, wenn Sie der Topologie im Topologie-Generator vorher einen entsprechenden Server hinzugefügt haben. Sie können die Eigenschaften für jeden Server, auf dem die Archivierung ausgeführt wird, in der Liste bearbeiten. Chat- oder Webkonferenzdaten (Sprachnachrichten) können jedoch erst archiviert werden, wenn Sie auch den Dienst für den Server eingerichtet haben, auf dem die Archivierung ausgeführt wird. 
  

