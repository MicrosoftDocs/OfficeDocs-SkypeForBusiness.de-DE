---
title: Hinzufügen eines Dateispeichers für den Archivierungsserver
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/25/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddArchivingServerFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e95f938e-4dd2-48b8-95a3-05b4c63d4810
description: Um eine Archivierung des Inhalts von Chats und Webkonferenzen zu ermöglichen, müssen Sie eine Dateifreigabe angeben, die als Dateispeicher der Kopien aller Webkonferenz- bzw. Besprechungsinhalte dienen soll. Sie können als Archivierungsdateispeicher eine vorhandene Dateifreigabe oder eine neue Dateifreigabe auswählen, indem Sie den vollqualifizierten Domänennamen des Dateiservers, auf dem sich die Dateifreigabe befindet, und einen Ordnernamen für die neue Dateifreigabe angeben.
ms.openlocfilehash: efa74bab804fee75501cdeb96c00b2055f0461e5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="add-archiving-server-file-store"></a><span data-ttu-id="2984c-104">Hinzufügen eines Dateispeichers für den Archivierungsserver</span><span class="sxs-lookup"><span data-stu-id="2984c-104">Add Archiving Server File Store</span></span>
 
<span data-ttu-id="2984c-p102">Um eine Archivierung des Inhalts von Chats und Webkonferenzen zu ermöglichen, müssen Sie eine Dateifreigabe angeben, die als Dateispeicher der Kopien aller Webkonferenz- bzw. Besprechungsinhalte dienen soll. Sie können als Archivierungsdateispeicher eine vorhandene Dateifreigabe oder eine neue Dateifreigabe auswählen, indem Sie den vollqualifizierten Domänennamen des Dateiservers, auf dem sich die Dateifreigabe befindet, und einen Ordnernamen für die neue Dateifreigabe angeben.</span><span class="sxs-lookup"><span data-stu-id="2984c-p102">To enable the archiving of both instant messaging (IM) and web conferencing (meeting) content, you must specify a file share to be used as the file store for copies of all web conferencing content. You can use an existing file share for the archiving file store, or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="2984c-107">Sie können die Dateifreigabe im Topologie-Generator definieren, bevor Sie die Dateifreigabe erstellen, aber Sie müssen die Dateifreigabe am angegebenen Speicherort erstellen, ehe Sie die Topologie veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="2984c-107">You can define the file share in Topology Builder before you create the file share, but you must create the file share in the defined location before you publish the topology.</span></span> <span data-ttu-id="2984c-108">> Wenn Sie einen Archivierungsserver Ihrer Topologie hinzufügen, müssen Topology Builder werden der Datei Archivierungsspeicher einrichten und Konfigurieren von freigegebenen Zugriffssteuerungslisten (DACL) für die Dateifreigabe für den Dateispeicher verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="2984c-108">> When you add an Archiving Server to your topology, Topology Builder must be able to set up the Archiving file store and configure discretionary access control lists (DACLs) on the file share to be used for the file store.</span></span> <span data-ttu-id="2984c-109">Deshalb müssen Sie bei Ausführung des Topologie-Generators zum Veröffentlichen der neuen Topologie mit einem Konto mit Vollzugriffsberechtigungen (Lesen/Schreiben/Ändern) für die Dateifreigabe angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="2984c-109">This requires that, when you run Topology Builder to publish the new topology, you are logged on with an account that has full control permissions (read/write/modify) for the file share.</span></span> 
  
<span data-ttu-id="2984c-110">Ausführliche Informationen zur Speicherung von Unterstützung für Dateifreigaben finden Sie unter [File Storage Support](http://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) in der Unterstützungsdokumentation und [SQL Server-Daten und Platzieren der Protokolldatei](http://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="2984c-110">For details about storage support for file shares, see [File Storage Support](http://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) in the Supportability documentation and [SQL Server Data and Log File Placement](http://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span> <span data-ttu-id="2984c-111">Ausführliche Informationen zum Verbinden der Dateifreigabe finden Sie unter [Supported Server Collocation](http://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) in der Unterstützungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="2984c-111">For details about collocation of the file share, see [Supported Server Collocation](http://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) in the Supportability documentation.</span></span>
  

