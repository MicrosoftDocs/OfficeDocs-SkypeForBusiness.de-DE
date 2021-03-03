---
title: Sichern und Wiederherstellen von Datenbanken für beständigen Chat in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4f2b689b-7f15-48dc-a069-da7bc8527def
description: 'Zusammenfassung: Informationen zum Sichern und Wiederherstellen von Datenbanken für den Server für beständigen Chat in Skype for Business Server 2015.'
ms.openlocfilehash: 2c99f5e955756020f68b51ea214858c23fee0a48
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826375"
---
# <a name="back-up-and-restore-persistent-chat-databases-in-skype-for-business-server-2015"></a>Sichern und Wiederherstellen von Datenbanken für beständigen Chat in Skype for Business Server 2015
 
**Zusammenfassung:** Erfahren Sie, wie Sie Datenbanken für den Server für beständigen Chat in Skype for Business Server 2015 sichern und wiederherstellen.
  
Der Server für beständigen Chat erfordert SQL Server Datenbanksoftware zum Speichern von Chatroomdaten, z. B. Verlauf und Inhalt, Konfiguration, Benutzerbereitstellung und andere relevante Metadaten. Darüber hinaus wird die SQL Server-Datenbanksoftware zum Speichern von Kompatibilitätsdaten verwendet, einschließlich Chatinhalten und -ereignissen, z. B. zum Beitreten und Verlassen von Chatrooms, wenn in Ihrer Organisation Vorschriften gelten, die das Archivieren von Aktivitäten für beständigen Chat erfordern und der optionale Kompatibilitätsdienst aktiviert ist. Chatroominhalte werden in der Datenbank für beständigen Chat (mgc) gespeichert. Kompatibilitätsdaten werden in der Kompatibilitätsdatenbank (mgccomp) gespeichert. Dies sind geschäftskritische Daten, die regelmäßig gesichert werden sollten. 
  
> [!NOTE]
> Beständiger Chat ist in Skype for Business Server 2015 verfügbar, wird jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter ["Erste Schritte mit Ihrem Microsoft Teams-Upgrade".](/microsoftteams/upgrade-start-here) Wenn Sie beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktionalität benötigen, zu Teams migrieren oder Weiterhin Skype for Business Server 2015 verwenden. 

## <a name="back-up-the-databases"></a>Sichern der Datenbanken

Es gibt zwei Möglichkeiten zum Sichern von Daten für den beständigen Chat. 
  
- SQL Server Sicherung
    
- Das **Cmdlet "Export-CsPersistentChatData",** das Daten des beständigen Chats als Datei exportiert
    
Daten, die mithilfe der SQL Server-Sicherung erstellt werden, benötigen deutlich mehr Speicherplatz – möglicherweise 20-mal mehr – als die Daten, die mit dem **Cmdlet "Export-CsPersistentChatData"** erstellt wurden, aber die SQL Server-Sicherung ist wahrscheinlich ein Verfahren, mit dem Sie vertraut sind.
  
Wenn Sie die SQL Server verwenden möchten, finden Sie in SQL Dokumentation weitere Informationen. 
  
Wenn Sie das Cmdlet **"Export-CsPersistentChatData"** verwenden möchten, können Sie den Befehl wie folgt angeben:
  
```PowerShell
Export-CsPersistentChatData [-FileName <String>] <COMMON PARAMETERS>
```

oder
  
```PowerShell
Export-CsPersistentChatData [-AsBytes <SwitchParameter>] <COMMON PARAMETERS>
```

Der folgende Befehl exportiert beispielsweise Daten des beständigen Chats aus der Datenbank für beständigen Chat, die sich auf dem Server atl-sql-001.contoso.com; Die exportierten Daten werden in der Datei gespeichert, die C:\Logs\PersistentChatData.zip. Da der Parameter "Level" nicht angegeben wurde, wird mit dem Befehl ein vollständiger Export der Informationen für den beständigen Chat ausgeführt:
  
```PowerShell
Export-CsPersistentChatData -DBInstance "atl-sql-001.contoso.com\rtc" -FileName "C:\Logs\PersistentChatData.zip"
```

## <a name="restore-the-databases"></a>Wiederherstellen der Datenbanken

Wie Sie Ihre Daten für den beständigen Chat wiederherstellen, hängt von der Methode ab, die Sie zum Sichern verwendet haben. Wenn Sie SQL Server sicherungsprozeduren verwendet haben, müssen Sie die SQL Server verwenden. Wenn Sie das **Cmdlet "Export-CsPersistentChatData"** zum Sichern von Daten für den beständigen Chat verwendet haben, müssen Sie zum Wiederherstellen der Daten das Cmdlet **"Import-CsPersistentChatData"** verwenden:
  
```PowerShell
Import-CsPersistentChatData -FileName <String> <COMMON PARAMETERS>
```

oder
  
```PowerShell
Import-CsPersistentChatData -ByteInput <Byte > <COMMON PARAMETERS>
```
