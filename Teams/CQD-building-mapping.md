---
title: Erstellen eines Gebäudeplans für das Anruf Qualitäts Dashboard (CQD)
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: Hier erfahren Sie, wie Sie ein Gebäude Diagramm erstellen, das Sie zum Hochladen von Mandanten und Erstellen von Daten im Dashboard für die Anrufqualität (CQD) verwenden können.
ms.openlocfilehash: 18e88c2de64d2d63589a3cd2ebddbc9643fe4522
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086101"
---
# <a name="create-a-building-map-for-call-quality-dashboard-cqd"></a><span data-ttu-id="6e477-103">Erstellen eines Gebäudeplans für das Anruf Qualitäts Dashboard (CQD)</span><span class="sxs-lookup"><span data-stu-id="6e477-103">Create a building map for Call Quality Dashboard (CQD)</span></span>

<span data-ttu-id="6e477-104">In einer Microsoft Teams-oder Skype for Business Online-Bereitstellung sind alle Clients extern.</span><span class="sxs-lookup"><span data-stu-id="6e477-104">In a Microsoft Teams or Skype for Business Online deployment, all clients are external.</span></span> <span data-ttu-id="6e477-105">Standardmäßig werden alle Clients als "extern" im Anruf Qualitäts Dashboard (CQD) gemeldet, unabhängig davon, ob der Client in einem internen Unternehmensnetzwerk verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="6e477-105">As a result, by default, all clients are reported as outside in Call Quality Dashboard (CQD), regardless of whether the client is connected on an internal corporate network.</span></span>

<span data-ttu-id="6e477-106">Wenn Sie mit CQD arbeiten, müssen Sie den Standort eines Endpunkts kennen und feststellen, ob er mit einem Netzwerk verbunden ist, das Sie verwalten können, oder ein Netzwerk, das Sie nicht verwalten können, und es wird davon ausgegangen, dass Sie nur Netzwerke verbessern können, die Sie verwalten können.</span><span class="sxs-lookup"><span data-stu-id="6e477-106">When you work with CQD, you need to know the location of an endpoint and whether it was connected to a network you can manage or a network you can't manage, the assumption being that you can only improve networks you can manage.</span></span> <span data-ttu-id="6e477-107">Durch Hochladen von Subnetzen und Erstellen von Informationen in CQD aktivieren Sie CQD, um zu ermitteln, ob der Endpunkt mit einem internen (verwalteten) Netzwerk oder einem externen (nicht verwalteten) Netzwerk verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="6e477-107">By uploading subnet and building information to CQD, you enable CQD to determine whether the endpoint was connected to an internal (managed) network or to an external (unmanaged) network.</span></span> <span data-ttu-id="6e477-108">Aus diesem Grund ist es wichtig, einen Bauplan für Ihre Organisation zu erstellen und [auf CQD hochzuladen](CQD-upload-tenant-building-data.md).</span><span class="sxs-lookup"><span data-stu-id="6e477-108">That's why it's important to create a building map for your organization and [upload it to CQD](CQD-upload-tenant-building-data.md).</span></span>

## <a name="building-mapping-tools"></a><span data-ttu-id="6e477-109">Tools für die Gebäudezuordnung</span><span class="sxs-lookup"><span data-stu-id="6e477-109">Building mapping tools</span></span>

<span data-ttu-id="6e477-110">Es gibt viele Möglichkeiten, die Subnetze Ihrer Organisation zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="6e477-110">There are many ways to map your organization's subnets.</span></span> <span data-ttu-id="6e477-111">Wenn Sie Hilfe benötigen, können Sie das in diesem [Blogbeitrag](https://aka.ms/cqdtools)beschriebene CQDTools-PowerShell-Modul verwenden.</span><span class="sxs-lookup"><span data-stu-id="6e477-111">If you need help, you can use the CQDTools PowerShell Module described in this [blog post](https://aka.ms/cqdtools).</span></span> <span data-ttu-id="6e477-112">Diese Tools basieren auf PowerShell und verwenden Active Directory (AD)-Websites und-Dienste sowie Microsoft DHCP-Dienste, um ihre Gebäude Datei vorab auszufüllen.</span><span class="sxs-lookup"><span data-stu-id="6e477-112">These tools are based on PowerShell and use Active Directory (AD) Sites and Services and Microsoft DHCP services to help pre-populate your building file.</span></span> <span data-ttu-id="6e477-113">Diese Tools können Ihnen bei den folgenden Aufgaben helfen:</span><span class="sxs-lookup"><span data-stu-id="6e477-113">These tools will help with the following tasks:</span></span>

1. <span data-ttu-id="6e477-114">AD-Websites und -Dienste abfragen und basierend auf den darin enthaltenen Informationen eine Gebäudedatei erstellen.</span><span class="sxs-lookup"><span data-stu-id="6e477-114">Query AD Sites and Services, and create a building file based on the information contained within.</span></span>
1. <span data-ttu-id="6e477-115">Abfragen eines Microsoft DHCP-Servers oder mehrerer Server ab, um Subnetzinformationen abzurufen, und automatisches Erstellen einer Gebäudedatei.</span><span class="sxs-lookup"><span data-stu-id="6e477-115">Query a Microsoft DHCP server or servers to pull subnet information and automatically create a building file.</span></span>
1. <span data-ttu-id="6e477-116">Validieren einer vorhandenen Gebäudedatei, Durchsuchen nach Duplikaten und Überlappungen.</span><span class="sxs-lookup"><span data-stu-id="6e477-116">Validate an existing building file, checking for duplicates and overlaps.</span></span>
1. <span data-ttu-id="6e477-117">Suchen nach nicht zugeordneten Subnetzen in CQD.</span><span class="sxs-lookup"><span data-stu-id="6e477-117">Find unmapped subnets in CQD.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6e477-118">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="6e477-118">Related topics</span></span>

[<span data-ttu-id="6e477-119">Hochladen von Mandanten und Erstellen von Daten in CQD</span><span class="sxs-lookup"><span data-stu-id="6e477-119">Upload tenant and building data in CQD</span></span>](CQD-upload-tenant-building-data.md)