---
title: Sichern und Wiederherstellen von Datenbanken für beständigen Chat in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4f2b689b-7f15-48dc-a069-da7bc8527def
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie persistente Chat Server-Datenbanken in Skype for Business Server 2015 sichern und wiederherstellen.'
ms.openlocfilehash: 07d904620bbc5925ec6457924af6ee1e48d98d55
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279361"
---
# <a name="back-up-and-restore-persistent-chat-databases-in-skype-for-business-server-2015"></a>Sichern und Wiederherstellen von Datenbanken für beständigen Chat in Skype for Business Server 2015
 
**Zusammenfassung:** Erfahren Sie, wie Sie persistente Chat Server-Datenbanken in Skype for Business Server 2015 sichern und wiederherstellen.
  
Der Server für beständigen Chat erfordert, dass die SQL Server-Datenbanksoftware chatroomdaten wie Verlauf und Inhalt, Konfiguration, Benutzerbereitstellung und andere relevante Metadaten speichert. Wenn Ihre Organisation zudem über Regelungen verfügt, die das Archivieren beständiger Chat Aktivitäten erfordern, und der optionale Kompatibilitätsdienst aktiviert ist, wird die SQL Server-Datenbanksoftware zum Speichern von Kompatibilitätsdaten verwendet, einschließlich Chat Inhalten und Ereignissen wie betreten und verlassen von Räumen. Chatroom-Inhalte werden in der persistent Chat-Datenbank (MGC) gespeichert. Die Konformitätsdaten werden in der Konformitätsdatenbank (mgccomp) gespeichert. Es handelt sich hierbei um unternehmenswichtige Daten, die regelmäßig gesichert werden sollten. 
  
> [!NOTE]
> Der beständige Chat ist in Skype for Business Server 2015 verfügbar, wird aber in Skype for Business Server 2019 nicht mehr unterstützt. In Teams steht dieselbe Funktionalität zur Verfügung. Weitere Informationen finden Sie unter [Reise von Skype for Business zu Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams). Wenn Sie den beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktion für Teams benötigen, oder die Verwendung von Skype for Business Server 2015 fortsetzen. 

## <a name="back-up-the-databases"></a>Sichern von Datenbanken

Es gibt zwei Möglichkeiten, persistente Chat-Daten zu sichern. 
  
- Die SQL Server-Sicherung
    
- Das Cmdlet " **Export-CsPersistentChatData** ", das persistente Chat-Daten als Datei exportiert
    
Die mithilfe der SQL Server-Sicherung erstellten Daten belegen sehr viel mehr – ca. 20 mal mehr – Speicherplatz als die Daten, die mit dem Cmdlet **Export-CsPersistentChatData** exportiert werden. Die SQL Server-Sicherung ist aber vermutlich das Verfahren, mit dem Sie vertraut sind.
  
Wenn Sie SQL Server-Sicherungsverfahren einsetzen möchten, lesen Sie in Ihrer SQL-Dokumentation nach. 
  
Wenn Sie das Cmdlet **Export-CsPersistentChatData** verwenden möchten, können Sie den Befehl wie folgt festlegen:
  
```
Export-CsPersistentChatData [-FileName <String>] <COMMON PARAMETERS>
```

oder
  
```
Export-CsPersistentChatData [-AsBytes <SwitchParameter>] <COMMON PARAMETERS>
```

Der folgende Befehl exportiert beispielsweise Daten zum beständigen Chat aus der Datenbank für beständigen Chat auf dem Server „atl-sql-001.contoso.com“. Die exportierten Daten werden in der Datei „C:\Logs\PersistentChatData.zip“ gespeichert. Da der Parameter „Level“ nicht angegeben wurde, führt der Befehl einen vollständigen Export der Informationen zum beständigen Chat aus.
  
```
Export-CsPersistentChatData -DBInstance "atl-sql-001.contoso.com\rtc" -FileName "C:\Logs\PersistentChatData.zip"
```

## <a name="restore-the-databases"></a>Wiederherstellen von Datenbanken

Wie Sie Ihre beständigen Chat-Daten wiederherstellen, hängt von der Methode ab, die Sie zum Sichern verwendet haben. Wenn Sie SQL Server-Sicherungsverfahren verwendet haben, müssen Sie SQL Server-Wiederherstellungsverfahren verwenden. Wenn Sie das Cmdlet **Export-CsPersistentChatData** zum Sichern beständiger Chat-Daten verwendet haben, müssen Sie die Daten mithilfe des Cmdlets **Import-CsPersistentChatData** wiederherstellen:
  
```
Import-CsPersistentChatData -FileName <String> <COMMON PARAMETERS>
```

oder
  
```
Import-CsPersistentChatData -ByteInput <Byte > <COMMON PARAMETERS>
```
