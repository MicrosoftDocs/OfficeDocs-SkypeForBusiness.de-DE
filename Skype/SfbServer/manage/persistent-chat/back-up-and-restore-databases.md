---
title: Sichern und Wiederherstellen von Datenbanken für beständigen Chat in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 4f2b689b-7f15-48dc-a069-da7bc8527def
description: 'Zusammenfassung: Erfahren Sie, wie Sie Datenbanken für den Server für beständigen Chat in Skype for Business Server 2015 sichern und wiederherstellen.'
ms.openlocfilehash: 3c294a33a82a9279e05e1d69e48b531f8b85e3c0
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60841167"
---
# <a name="back-up-and-restore-persistent-chat-databases-in-skype-for-business-server-2015"></a>Sichern und Wiederherstellen von Datenbanken für beständigen Chat in Skype for Business Server 2015
 
**Zusammenfassung:** Erfahren Sie, wie Sie Datenbanken für den Server für beständigen Chat in Skype for Business Server 2015 sichern und wiederherstellen.
  
Für den Server für beständigen Chat ist SQL Server Datenbanksoftware erforderlich, um Chatroomdaten wie Verlauf und Inhalt, Konfiguration, Benutzerbereitstellung und andere relevante Metadaten zu speichern. Wenn Ihre Organisation darüber hinaus Vorschriften hat, die die Archivierung von Aktivitäten für beständigen Chat erfordern und der optionale Compliancedienst aktiviert ist, wird SQL Server Datenbanksoftware zum Speichern von Compliancedaten verwendet, einschließlich Chatinhalten und -ereignissen, z. B. Dem Beitreten und Verlassen von Chatrooms. Chatroominhalte werden in der Datenbank für beständigen Chat (mgc) gespeichert. Compliancedaten werden in der Compliance-Datenbank (mgccomp) gespeichert. Hierbei handelt es sich um unternehmenskritische Daten, die regelmäßig gesichert werden sollten. 
  
> [!NOTE]
> Beständiger Chat ist in Skype for Business Server 2015 verfügbar, wird jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter [Erste Schritte mit Ihrem Microsoft Teams Upgrade.](/microsoftteams/upgrade-start-here) Wenn Sie den beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktionalität zum Teams benötigen, oder Skype for Business Server 2015 weiterhin verwenden. 

## <a name="back-up-the-databases"></a>Sichern der Datenbanken

Es gibt zwei Möglichkeiten zum Sichern von Daten für beständigen Chat. 
  
- SQL Server Sicherung
    
- Das Cmdlet **"Export-CsPersistentChatData",** das Daten für beständigen Chat als Datei exportiert
    
Daten, die mithilfe SQL Server Sicherung erstellt werden, erfordern wesentlich mehr Speicherplatz – möglicherweise 20 Mal mehr – als die mit dem Cmdlet **"Export-CsPersistentChatData"** erstellten Daten, aber SQL Server Sicherung ist wahrscheinlich ein Verfahren, mit dem Sie vertraut sind.
  
Wenn Sie SQL Server Sicherungsprozeduren verwenden möchten, finden Sie in ihrer SQL Dokumentation weitere Informationen. 
  
Wenn Sie das Cmdlet **"Export-CsPersistentChatData"** verwenden möchten, können Sie den Befehl wie folgt angeben:
  
```PowerShell
Export-CsPersistentChatData [-FileName <String>] <COMMON PARAMETERS>
```

oder
  
```PowerShell
Export-CsPersistentChatData [-AsBytes <SwitchParameter>] <COMMON PARAMETERS>
```

Der folgende Befehl exportiert beispielsweise Daten für beständigen Chat aus der Datenbank für beständigen Chat, die sich auf dem Server atl-sql-001.contoso.com befindet. die exportierten Daten werden in der Datei C:\Logs\PersistentChatData.zip gespeichert. Da der Level-Parameter nicht angegeben wurde, führt der Befehl einen vollständigen Export der Informationen für beständigen Chat durch:
  
```PowerShell
Export-CsPersistentChatData -DBInstance "atl-sql-001.contoso.com\rtc" -FileName "C:\Logs\PersistentChatData.zip"
```

## <a name="restore-the-databases"></a>Wiederherstellen der Datenbanken

Wie Sie Ihre Daten für beständigen Chat wiederherstellen, hängt von der Methode ab, die Sie zum Sichern verwendet haben. Wenn Sie SQL Server Sicherungsverfahren verwendet haben, müssen Sie SQL Server Wiederherstellungsverfahren verwenden. Wenn Sie das Cmdlet **"Export-CsPersistentChatData"** zum Sichern von Daten für beständigen Chat verwendet haben, müssen Sie das Cmdlet **"Import-CsPersistentChatData"** verwenden, um die Daten wiederherzustellen:
  
```PowerShell
Import-CsPersistentChatData -FileName <String> <COMMON PARAMETERS>
```

oder
  
```PowerShell
Import-CsPersistentChatData -ByteInput <Byte > <COMMON PARAMETERS>
```
