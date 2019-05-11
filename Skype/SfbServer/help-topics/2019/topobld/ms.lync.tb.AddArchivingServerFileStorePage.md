---
title: Hinzufügen eines Dateispeichers für den Archivierungsserver
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddArchivingServerFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e95f938e-4dd2-48b8-95a3-05b4c63d4810
ROBOTS: NOINDEX, NOFOLLOW
description: Um eine Archivierung des Inhalts von Chats und Webkonferenzen zu ermöglichen, müssen Sie eine Dateifreigabe angeben, die als Dateispeicher der Kopien aller Webkonferenz- bzw. Besprechungsinhalte dienen soll. Sie können als Archivierungsdateispeicher eine vorhandene Dateifreigabe oder eine neue Dateifreigabe auswählen, indem Sie den vollqualifizierten Domänennamen des Dateiservers, auf dem sich die Dateifreigabe befindet, und einen Ordnernamen für die neue Dateifreigabe angeben.
ms.openlocfilehash: b59850988e2c863d599fb608c06446e102490f44
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33889227"
---
# <a name="add-archiving-server-file-store"></a><span data-ttu-id="1f7cd-104">Hinzufügen eines Dateispeichers für den Archivierungsserver</span><span class="sxs-lookup"><span data-stu-id="1f7cd-104">Add Archiving Server File Store</span></span>

<span data-ttu-id="1f7cd-p102">Um eine Archivierung des Inhalts von Chats und Webkonferenzen zu ermöglichen, müssen Sie eine Dateifreigabe angeben, die als Dateispeicher der Kopien aller Webkonferenz- bzw. Besprechungsinhalte dienen soll. Sie können als Archivierungsdateispeicher eine vorhandene Dateifreigabe oder eine neue Dateifreigabe auswählen, indem Sie den vollqualifizierten Domänennamen des Dateiservers, auf dem sich die Dateifreigabe befindet, und einen Ordnernamen für die neue Dateifreigabe angeben.</span><span class="sxs-lookup"><span data-stu-id="1f7cd-p102">To enable the archiving of both instant messaging (IM) and web conferencing (meeting) content, you must specify a file share to be used as the file store for copies of all web conferencing content. You can use an existing file share for the archiving file store, or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1f7cd-107">Sie können die Dateifreigabe im Topologie-Generator definieren, bevor Sie die Dateifreigabe erstellen, aber Sie müssen die Dateifreigabe am angegebenen Speicherort erstellen, ehe Sie die Topologie veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="1f7cd-107">You can define the file share in Topology Builder before you create the file share, but you must create the file share in the defined location before you publish the topology.</span></span> <span data-ttu-id="1f7cd-108">> beim Hinzufügen eines Archivierungsservers zu einer Topologie, Topologie-Generator muss möglicherweise der Datei Archivierungsspeicher einrichten und Konfigurieren von freigegebenen Zugriffssteuerungslisten (DACL) für die Dateifreigabe für den Dateispeicher verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="1f7cd-108">> When you add an Archiving Server to your topology, Topology Builder must be able to set up the Archiving file store and configure discretionary access control lists (DACLs) on the file share to be used for the file store.</span></span> <span data-ttu-id="1f7cd-109">Deshalb müssen Sie bei Ausführung des Topologie-Generators zum Veröffentlichen der neuen Topologie mit einem Konto mit Vollzugriffsberechtigungen (Lesen/Schreiben/Ändern) für die Dateifreigabe angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="1f7cd-109">This requires that, when you run Topology Builder to publish the new topology, you are logged on with an account that has full control permissions (read/write/modify) for the file share.</span></span>

<span data-ttu-id="1f7cd-p104">Ausführliche Informationen zur Speicherunterstützung für Dateifreigaben finden Sie in der Unterstützungsdokumentation unter [File Storage Support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) und in der Bereitstellungsdokumentation unter [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx). Ausführliche Informationen zur Kollokation der Dateifreigabe finden Sie in der Unterstützungsdokumentation unter [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx).</span><span class="sxs-lookup"><span data-stu-id="1f7cd-p104">For details about storage support for file shares, see [File Storage Support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) in the Supportability documentation and [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation. For details about collocation of the file share, see [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) in the Supportability documentation.</span></span>


