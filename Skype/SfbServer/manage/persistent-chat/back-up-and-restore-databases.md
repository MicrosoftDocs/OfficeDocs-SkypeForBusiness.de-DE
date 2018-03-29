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
ms.openlocfilehash: 419085219ea995c680fe31fcca3597a884ceba5d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="back-up-and-restore-persistent-chat-databases-in-skype-for-business-server-2015"></a><span data-ttu-id="ad326-103">Sichern und Wiederherstellen von Datenbanken für beständigen Chat in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="ad326-103">Back up and restore Persistent Chat databases in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="ad326-104">**Zusammenfassung:** Informationen Sie zum Sichern und Wiederherstellen von Datenbanken in Skype Persistent Chat Server for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="ad326-104">**Summary:** Learn how to back up and restore Persistent Chat Server databases in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="ad326-105">Persistent Chat-Server erfordert SQL Server-Datenbanksoftware Chatroom Daten, beispielsweise Verlauf und Inhalte, Konfiguration, benutzerbereitstellung und anderen relevanten Metadaten gespeichert.</span><span class="sxs-lookup"><span data-stu-id="ad326-105">Persistent Chat Server requires SQL Server database software to store chat room data, such as history and content, configuration, user provisioning, and other relevant metadata.</span></span> <span data-ttu-id="ad326-106">Darüber hinaus wird, wenn Ihre Organisation verfügt Vorschriften, die erfordern Persistent Chat-Aktivität archiviert werden sollen, und der optionale kompatibilitätsdienst aktiviert ist, SQL Server-Datenbanksoftware verwendet zum Speichern von Compliance-Daten, einschließlich chatinhalte und Ereignisse, wie z. B. Teilnehmen an, und lassen Chatrooms.</span><span class="sxs-lookup"><span data-stu-id="ad326-106">In addition, if your organization has regulations that require Persistent Chat activity to be archived, and the optional Compliance service is enabled, SQL Server database software is used to store compliance data, including chat content and events, such as joining and leaving rooms.</span></span> <span data-ttu-id="ad326-107">Inhalt des Chatrooms wird in der Datenbank für beständigen Chat (Mgc) gespeichert.</span><span class="sxs-lookup"><span data-stu-id="ad326-107">Chat room content is stored in the Persistent Chat database (mgc).</span></span> <span data-ttu-id="ad326-108">Die Konformitätsdaten werden in der Konformitätsdatenbank (mgccomp) gespeichert.</span><span class="sxs-lookup"><span data-stu-id="ad326-108">Compliance data is stored in the Compliance database (mgccomp).</span></span> <span data-ttu-id="ad326-109">Es handelt sich hierbei um unternehmenswichtige Daten, die regelmäßig gesichert werden sollten.</span><span class="sxs-lookup"><span data-stu-id="ad326-109">This is business-critical data that should be backed up regularly.</span></span> 
  
## <a name="back-up-the-databases"></a><span data-ttu-id="ad326-110">Sichern von Datenbanken</span><span class="sxs-lookup"><span data-stu-id="ad326-110">Back up the databases</span></span>

<span data-ttu-id="ad326-111">Es gibt zwei Methoden zum Sichern der Daten für beständigen Chat.</span><span class="sxs-lookup"><span data-stu-id="ad326-111">There are two ways of backing up Persistent Chat data.</span></span> 
  
- <span data-ttu-id="ad326-112">Die SQL Server-Sicherung</span><span class="sxs-lookup"><span data-stu-id="ad326-112">SQL Server Backup</span></span>
    
- <span data-ttu-id="ad326-113">Das **Export-CsPersistentChatData** -Cmdlet, das Daten für beständigen Chat als Datei exportiert</span><span class="sxs-lookup"><span data-stu-id="ad326-113">The **Export-CsPersistentChatData** cmdlet, which exports Persistent Chat data as a file</span></span>
    
<span data-ttu-id="ad326-114">Die mithilfe der SQL Server-Sicherung erstellten Daten belegen sehr viel mehr – ca. 20 mal mehr – Speicherplatz als die Daten, die mit dem Cmdlet **Export-CsPersistentChatData** exportiert werden. Die SQL Server-Sicherung ist aber vermutlich das Verfahren, mit dem Sie vertraut sind.</span><span class="sxs-lookup"><span data-stu-id="ad326-114">Data that is created by using SQL Server backup requires significantly more disk space—possibly 20 times more—than that created by the **Export-CsPersistentChatData** cmdlet, but SQL Server backup is likely to be a procedure with which you are familiar.</span></span>
  
<span data-ttu-id="ad326-115">Wenn Sie SQL Server-Sicherungsverfahren einsetzen möchten, lesen Sie in Ihrer SQL-Dokumentation nach.</span><span class="sxs-lookup"><span data-stu-id="ad326-115">If you want to use SQL Server backup procedures, see your SQL documentation for more information.</span></span> 
  
<span data-ttu-id="ad326-116">Wenn Sie das Cmdlet **Export-CsPersistentChatData** verwenden möchten, können Sie den Befehl wie folgt festlegen:</span><span class="sxs-lookup"><span data-stu-id="ad326-116">If you want to use the **Export-CsPersistentChatData** cmdlet, you can specify the command as follows:</span></span>
  
```
Export-CsPersistentChatData [-FileName <String>] <COMMON PARAMETERS>
```

<span data-ttu-id="ad326-117">oder</span><span class="sxs-lookup"><span data-stu-id="ad326-117">or</span></span>
  
```
Export-CsPersistentChatData [-AsBytes <SwitchParameter>] <COMMON PARAMETERS>
```

<span data-ttu-id="ad326-p102">Der folgende Befehl exportiert beispielsweise Daten zum beständigen Chat aus der Datenbank für beständigen Chat auf dem Server „atl-sql-001.contoso.com“. Die exportierten Daten werden in der Datei „C:\Logs\PersistentChatData.zip“ gespeichert. Da der Parameter „Level“ nicht angegeben wurde, führt der Befehl einen vollständigen Export der Informationen zum beständigen Chat aus.</span><span class="sxs-lookup"><span data-stu-id="ad326-p102">For example, the following command exports Persistent Chat data from the Persistent Chat database located on the server atl-sql-001.contoso.com; the exported data will be stored in the file C:\Logs\PersistentChatData.zip. Because the Level parameter was not specified, the command will do a full export of the Persistent Chat information:</span></span>
  
```
Export-CsPersistentChatData -DBInstance "atl-sql-001.contoso.com\rtc" -FileName "C:\Logs\PersistentChatData.zip"
```

## <a name="restore-the-databases"></a><span data-ttu-id="ad326-120">Wiederherstellen von Datenbanken</span><span class="sxs-lookup"><span data-stu-id="ad326-120">Restore the databases</span></span>

<span data-ttu-id="ad326-121">Wie Sie Ihre Daten beständigen Chat wiederherstellen, hängt von der-Methode, mit der Sie eine Sicherungskopie erstellen.</span><span class="sxs-lookup"><span data-stu-id="ad326-121">How you restore your Persistent Chat data depends on the method that you used to back it up.</span></span> <span data-ttu-id="ad326-122">Wenn Sie SQL Server-Sicherungsverfahren verwendet haben, müssen Sie SQL Server-Wiederherstellungsverfahren verwenden.</span><span class="sxs-lookup"><span data-stu-id="ad326-122">If you used SQL Server backup procedures, you must use SQL Server restore procedures.</span></span> <span data-ttu-id="ad326-123">Wenn Sie das Cmdlet " **Export-CsPersistentChatData** " verwendet, um Daten für beständigen Chat zu sichern, müssen Sie das Cmdlet **Import-CsPersistentChatData** verwenden, um die Daten wiederherzustellen:</span><span class="sxs-lookup"><span data-stu-id="ad326-123">If you used the **Export-CsPersistentChatData** cmdlet to back up Persistent Chat data, then you must use the **Import-CsPersistentChatData** cmdlet to restore the data:</span></span>
  
```
Import-CsPersistentChatData -FileName <String> <COMMON PARAMETERS>
```

<span data-ttu-id="ad326-124">oder</span><span class="sxs-lookup"><span data-stu-id="ad326-124">or</span></span>
  
```
Import-CsPersistentChatData -ByteInput <Byte > <COMMON PARAMETERS>
```


