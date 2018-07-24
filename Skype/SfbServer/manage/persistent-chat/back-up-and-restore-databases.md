---
title: Sichern und Wiederherstellen von Datenbanken für beständigen Chat in Skype for Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4f2b689b-7f15-48dc-a069-da7bc8527def
description: 'Zusammenfassung: Informationen Sie zum Sichern und Wiederherstellen von Datenbanken in Skype Persistent Chat Server for Business Server 2015.'
ms.openlocfilehash: 9287037a0cf89f9451a31356b442bcba93f5010f
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20992806"
---
# <a name="back-up-and-restore-persistent-chat-databases-in-skype-for-business-server-2015"></a>Sichern und Wiederherstellen von Datenbanken für beständigen Chat in Skype for Business Server 2015
 
**Zusammenfassung:** Informationen Sie zum Sichern und Wiederherstellen von Datenbanken in Skype Persistent Chat Server for Business Server 2015.
  
Persistent Chat-Server erfordert SQL Server-Datenbanksoftware Chatroom Daten, beispielsweise Verlauf und Inhalte, Konfiguration, benutzerbereitstellung und anderen relevanten Metadaten gespeichert. Darüber hinaus wird, wenn Ihre Organisation verfügt Vorschriften, die erfordern Persistent Chat-Aktivität archiviert werden sollen, und der optionale kompatibilitätsdienst aktiviert ist, SQL Server-Datenbanksoftware verwendet zum Speichern von Compliance-Daten, einschließlich chatinhalte und Ereignisse, wie z. B. Teilnehmen an, und lassen Chatrooms. Inhalt des Chatrooms wird in der Datenbank für beständigen Chat (Mgc) gespeichert. Die Konformitätsdaten werden in der Konformitätsdatenbank (mgccomp) gespeichert. Es handelt sich hierbei um unternehmenswichtige Daten, die regelmäßig gesichert werden sollten. 
  
> [!NOTE]
> Beständiger Chat wird steht in Skype für Business Server 2015 jedoch nicht mehr unterstützt in Skype Business Server 2019. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter [Weg von Skype für Unternehmen, die Microsoft-Teams](/microsoftteams/journey-skypeforbusiness-teams). Wenn Sie Persistent Chat verwenden müssen, sind Ihrer Auswahl an Benutzer, die diese Funktionalität Teams migrieren oder weiterhin Skype für Business Server 2015 verwenden. 

## <a name="back-up-the-databases"></a>Sichern von Datenbanken

Es gibt zwei Methoden zum Sichern der Daten für beständigen Chat. 
  
- Die SQL Server-Sicherung
    
- Das **Export-CsPersistentChatData** -Cmdlet, das Daten für beständigen Chat als Datei exportiert
    
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

Wie Sie Ihre Daten beständigen Chat wiederherstellen, hängt von der-Methode, mit der Sie eine Sicherungskopie erstellen. Wenn Sie SQL Server-Sicherungsverfahren verwendet haben, müssen Sie SQL Server-Wiederherstellungsverfahren verwenden. Wenn Sie das Cmdlet " **Export-CsPersistentChatData** " verwendet, um Daten für beständigen Chat zu sichern, müssen Sie das Cmdlet **Import-CsPersistentChatData** verwenden, um die Daten wiederherzustellen:
  
```
Import-CsPersistentChatData -FileName <String> <COMMON PARAMETERS>
```

oder
  
```
Import-CsPersistentChatData -ByteInput <Byte > <COMMON PARAMETERS>
```