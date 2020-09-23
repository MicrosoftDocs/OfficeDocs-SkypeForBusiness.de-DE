---
title: Hinzufügen des Director-Dateispeichers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddDirectorFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a15b69e0-d3d1-4648-af25-1c0f25e5da8e
description: Sie müssen eine Dateifreigabe angeben, die als Dateispeicher für Directors verwendet werden soll. Sie können als Dateispeicher eine vorhandene Dateifreigabe oder eine neue Dateifreigabe auswählen, indem Sie den vollqualifizierten Domänennamen (FQDN) des Dateiservers, auf dem sich die Dateifreigabe befindet, und einen Ordnernamen für die neue Dateifreigabe angeben.
ms.openlocfilehash: 4c68e592568f160575433d5b4f772eadf8c81a2e
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215536"
---
# <a name="add-director-file-store"></a><span data-ttu-id="b9d7e-104">Hinzufügen des Director-Dateispeichers</span><span class="sxs-lookup"><span data-stu-id="b9d7e-104">Add Director File Store</span></span>

<span data-ttu-id="b9d7e-105">Sie müssen eine Dateifreigabe angeben, die als Dateispeicher für Directors verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="b9d7e-105">You must specify a file share to be used as the file store for Directors.</span></span> <span data-ttu-id="b9d7e-106">Sie können als Dateispeicher eine vorhandene Dateifreigabe oder eine neue Dateifreigabe auswählen, indem Sie den vollqualifizierten Domänennamen (FQDN) des Dateiservers, auf dem sich die Dateifreigabe befindet, und einen Ordnernamen für die neue Dateifreigabe angeben.</span><span class="sxs-lookup"><span data-stu-id="b9d7e-106">You can use an existing file share for the file store, or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b9d7e-p103">Wenn Sie Ihrer Topologie Directors hinzufügen, ist für die Topologieveröffentlichung ein entsprechender Zugriff zum Einzurichten des Dateispeichers und zum Konfigurieren besitzerverwalteter Zugriffssteuerungslisten (Discretionary Access Control Lists, DACLs) für die Dateifreigabe erforderlich, die als Dateispeicher verwendet werden soll. Deshalb müssen Sie bei Ausführung des Topologie-Generators und zum Veröffentlichen der neuen Topologie mit einem Konto mit Vollzugriffsberechtigungen (Lesen/Schreiben/Ändern) für die Dateifreigabe angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="b9d7e-p103">When you add Directors to a topology, topology publication requires appropriate access to set up the file store and configure discretionary access control lists (DACLs) on the file share to be used for the file store. This requires that, when you run Topology Builder and publish the new topology, you are logged on with an account that has full control permissions (read/write/modify) for the file share.</span></span>

<span data-ttu-id="b9d7e-109">Ausführliche Informationen zur Speicherunterstützung für Dateifreigaben finden Sie unter [Unterstützung der Dateispeicherung](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) in der Dokumentation zur Unterstützung und [SQL Server der Daten-und Protokolldatei Platzierung](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="b9d7e-109">For details about storage support for file shares, see [File Storage Support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) in the Supportability documentation and [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span> <span data-ttu-id="b9d7e-110">Ausführliche Informationen zur gemeinsamen Verwendung der Dateifreigabe finden Sie unter [Unterstützte gemeinsame Serververwendung](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) in der Unterstützungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="b9d7e-110">For details about collocation of the file share, see [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) in the Supportability documentation.</span></span> <span data-ttu-id="b9d7e-111">Ausführliche Informationen zum Entwerfen der Topologie für Directors finden Sie unter [Definieren eines einzelnen Directors im Topologie-Generator](https://technet.microsoft.com/library/8e9a659d-23b0-401d-b296-59c7df414d49.aspx) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="b9d7e-111">For details about designing the topology for Directors, see [Define a Single Director in Topology Builder](https://technet.microsoft.com/library/8e9a659d-23b0-401d-b296-59c7df414d49.aspx) in the Deployment documentation.</span></span>


