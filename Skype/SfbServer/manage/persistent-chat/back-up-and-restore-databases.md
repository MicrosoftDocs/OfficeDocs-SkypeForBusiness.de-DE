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
ms.openlocfilehash: 0bb4895ef85ac9f38f2f9ef414769efcac6894b4
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2019
ms.locfileid: "35417960"
---
# <a name="back-up-and-restore-persistent-chat-databases-in-skype-for-business-server-2015"></a><span data-ttu-id="74e93-103">Sichern und Wiederherstellen von Datenbanken für beständigen Chat in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="74e93-103">Back up and restore Persistent Chat databases in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="74e93-104">**Zusammenfassung:** Erfahren Sie, wie Sie persistente Chat Server-Datenbanken in Skype for Business Server 2015 sichern und wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="74e93-104">**Summary:** Learn how to back up and restore Persistent Chat Server databases in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="74e93-105">Der Server für beständigen Chat erfordert, dass die SQL Server-Datenbanksoftware chatroomdaten wie Verlauf und Inhalt, Konfiguration, Benutzerbereitstellung und andere relevante Metadaten speichert.</span><span class="sxs-lookup"><span data-stu-id="74e93-105">Persistent Chat Server requires SQL Server database software to store chat room data, such as history and content, configuration, user provisioning, and other relevant metadata.</span></span> <span data-ttu-id="74e93-106">Wenn Ihre Organisation zudem über Regelungen verfügt, die das Archivieren beständiger Chat Aktivitäten erfordern, und der optionale Kompatibilitätsdienst aktiviert ist, wird die SQL Server-Datenbanksoftware zum Speichern von Kompatibilitätsdaten verwendet, einschließlich Chat Inhalten und Ereignissen wie betreten und verlassen von Räumen.</span><span class="sxs-lookup"><span data-stu-id="74e93-106">In addition, if your organization has regulations that require Persistent Chat activity to be archived, and the optional Compliance service is enabled, SQL Server database software is used to store compliance data, including chat content and events, such as joining and leaving rooms.</span></span> <span data-ttu-id="74e93-107">Chatroom-Inhalte werden in der persistent Chat-Datenbank (MGC) gespeichert.</span><span class="sxs-lookup"><span data-stu-id="74e93-107">Chat room content is stored in the Persistent Chat database (mgc).</span></span> <span data-ttu-id="74e93-108">Die Konformitätsdaten werden in der Konformitätsdatenbank (mgccomp) gespeichert.</span><span class="sxs-lookup"><span data-stu-id="74e93-108">Compliance data is stored in the Compliance database (mgccomp).</span></span> <span data-ttu-id="74e93-109">Es handelt sich hierbei um unternehmenswichtige Daten, die regelmäßig gesichert werden sollten.</span><span class="sxs-lookup"><span data-stu-id="74e93-109">This is business-critical data that should be backed up regularly.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="74e93-110">Der beständige Chat ist in Skype for Business Server 2015 verfügbar, wird aber in Skype for Business Server 2019 nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="74e93-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="74e93-111">In Teams steht dieselbe Funktionalität zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="74e93-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="74e93-112">Weitere Informationen finden Sie unter [Erste Schritte mit dem Upgrade für Microsoft Teams](/microsoftteams/upgrade-start-here).</span><span class="sxs-lookup"><span data-stu-id="74e93-112">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="74e93-113">Wenn Sie den beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktion für Teams benötigen, oder die Verwendung von Skype for Business Server 2015 fortsetzen.</span><span class="sxs-lookup"><span data-stu-id="74e93-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="back-up-the-databases"></a><span data-ttu-id="74e93-114">Sichern von Datenbanken</span><span class="sxs-lookup"><span data-stu-id="74e93-114">Back up the databases</span></span>

<span data-ttu-id="74e93-115">Es gibt zwei Möglichkeiten, persistente Chat-Daten zu sichern.</span><span class="sxs-lookup"><span data-stu-id="74e93-115">There are two ways of backing up Persistent Chat data.</span></span> 
  
- <span data-ttu-id="74e93-116">Die SQL Server-Sicherung</span><span class="sxs-lookup"><span data-stu-id="74e93-116">SQL Server Backup</span></span>
    
- <span data-ttu-id="74e93-117">Das Cmdlet " **Export-CsPersistentChatData** ", das persistente Chat-Daten als Datei exportiert</span><span class="sxs-lookup"><span data-stu-id="74e93-117">The **Export-CsPersistentChatData** cmdlet, which exports Persistent Chat data as a file</span></span>
    
<span data-ttu-id="74e93-118">Die mithilfe der SQL Server-Sicherung erstellten Daten belegen sehr viel mehr – ca. 20 mal mehr – Speicherplatz als die Daten, die mit dem Cmdlet **Export-CsPersistentChatData** exportiert werden. Die SQL Server-Sicherung ist aber vermutlich das Verfahren, mit dem Sie vertraut sind.</span><span class="sxs-lookup"><span data-stu-id="74e93-118">Data that is created by using SQL Server backup requires significantly more disk space—possibly 20 times more—than that created by the **Export-CsPersistentChatData** cmdlet, but SQL Server backup is likely to be a procedure with which you are familiar.</span></span>
  
<span data-ttu-id="74e93-119">Wenn Sie SQL Server-Sicherungsverfahren einsetzen möchten, lesen Sie in Ihrer SQL-Dokumentation nach.</span><span class="sxs-lookup"><span data-stu-id="74e93-119">If you want to use SQL Server backup procedures, see your SQL documentation for more information.</span></span> 
  
<span data-ttu-id="74e93-120">Wenn Sie das Cmdlet **Export-CsPersistentChatData** verwenden möchten, können Sie den Befehl wie folgt festlegen:</span><span class="sxs-lookup"><span data-stu-id="74e93-120">If you want to use the **Export-CsPersistentChatData** cmdlet, you can specify the command as follows:</span></span>
  
```
Export-CsPersistentChatData [-FileName <String>] <COMMON PARAMETERS>
```

<span data-ttu-id="74e93-121">oder</span><span class="sxs-lookup"><span data-stu-id="74e93-121">or</span></span>
  
```
Export-CsPersistentChatData [-AsBytes <SwitchParameter>] <COMMON PARAMETERS>
```

<span data-ttu-id="74e93-p103">Der folgende Befehl exportiert beispielsweise Daten zum beständigen Chat aus der Datenbank für beständigen Chat auf dem Server „atl-sql-001.contoso.com“. Die exportierten Daten werden in der Datei „C:\Logs\PersistentChatData.zip“ gespeichert. Da der Parameter „Level“ nicht angegeben wurde, führt der Befehl einen vollständigen Export der Informationen zum beständigen Chat aus.</span><span class="sxs-lookup"><span data-stu-id="74e93-p103">For example, the following command exports Persistent Chat data from the Persistent Chat database located on the server atl-sql-001.contoso.com; the exported data will be stored in the file C:\Logs\PersistentChatData.zip. Because the Level parameter was not specified, the command will do a full export of the Persistent Chat information:</span></span>
  
```
Export-CsPersistentChatData -DBInstance "atl-sql-001.contoso.com\rtc" -FileName "C:\Logs\PersistentChatData.zip"
```

## <a name="restore-the-databases"></a><span data-ttu-id="74e93-124">Wiederherstellen von Datenbanken</span><span class="sxs-lookup"><span data-stu-id="74e93-124">Restore the databases</span></span>

<span data-ttu-id="74e93-125">Wie Sie Ihre beständigen Chat-Daten wiederherstellen, hängt von der Methode ab, die Sie zum Sichern verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="74e93-125">How you restore your Persistent Chat data depends on the method that you used to back it up.</span></span> <span data-ttu-id="74e93-126">Wenn Sie SQL Server-Sicherungsverfahren verwendet haben, müssen Sie SQL Server-Wiederherstellungsverfahren verwenden.</span><span class="sxs-lookup"><span data-stu-id="74e93-126">If you used SQL Server backup procedures, you must use SQL Server restore procedures.</span></span> <span data-ttu-id="74e93-127">Wenn Sie das Cmdlet **Export-CsPersistentChatData** zum Sichern beständiger Chat-Daten verwendet haben, müssen Sie die Daten mithilfe des Cmdlets **Import-CsPersistentChatData** wiederherstellen:</span><span class="sxs-lookup"><span data-stu-id="74e93-127">If you used the **Export-CsPersistentChatData** cmdlet to back up Persistent Chat data, then you must use the **Import-CsPersistentChatData** cmdlet to restore the data:</span></span>
  
```
Import-CsPersistentChatData -FileName <String> <COMMON PARAMETERS>
```

<span data-ttu-id="74e93-128">oder</span><span class="sxs-lookup"><span data-stu-id="74e93-128">or</span></span>
  
```
Import-CsPersistentChatData -ByteInput <Byte > <COMMON PARAMETERS>
```
