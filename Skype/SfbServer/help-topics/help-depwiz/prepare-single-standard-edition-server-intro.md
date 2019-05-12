---
title: Vorbereiten eines einzelnen Standard Edition-Servers (Einführung)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployAIOIntro
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fe11d380-54c9-47e7-a676-02b9a59dc93f
description: Um die Installation von einer Skype für Business Server 2015 Standard Edition-Server beginnen, die enthalten soll, dem zentralen Verwaltungsspeicher und andere verbundenen Dienste, die Sie auswählen, müssen Sie angemeldet sein, als Mitglied der lokalen Gruppe Administratoren auf dem Server, die wird werden Sie Standard Edition-Servers. Die Prepare einzelnen Standard Edition-Server-Seite werden die Anforderungen für die Erstinstallation. Der Computer muss ein Mitglied der Domäne, in der Sie ihn bereitstellen möchten, und Sie müssen erfolgreich abgeschlossen haben die Prep-Schema,-Gesamtstruktur und-Domäne für die Gesamtstruktur.
ms.openlocfilehash: f8a5d3e5d77dcf81675d2e69b70e616614837ed4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924857"
---
# <a name="prepare-single-standard-edition-server-intro"></a><span data-ttu-id="7544c-105">Vorbereiten eines einzelnen Standard Edition-Servers (Einführung)</span><span class="sxs-lookup"><span data-stu-id="7544c-105">Prepare Single Standard Edition Server (Intro)</span></span>
 
<span data-ttu-id="7544c-106">Um die Installation von einer Skype für Business Server 2015 Standard Edition-Server beginnen, die enthalten soll, dem zentralen Verwaltungsspeicher und andere verbundenen Dienste, die Sie auswählen, müssen Sie angemeldet sein, als Mitglied der lokalen Gruppe Administratoren auf dem Server, die wird werden Sie Standard Edition-Servers.</span><span class="sxs-lookup"><span data-stu-id="7544c-106">To begin the installation of a Skype for Business Server 2015 Standard Edition server that will hold the Central Management store and other collocated services that you select, you must be logged in as a member of the local Administrators group on the server that will become the Standard Edition server.</span></span> <span data-ttu-id="7544c-107">Die Seite **Prepare einzelnen Standard Edition-Server** werden die Anforderungen für die Erstinstallation.</span><span class="sxs-lookup"><span data-stu-id="7544c-107">The **Prepare single Standard Edition Server** page details the requirements for the initial install.</span></span> <span data-ttu-id="7544c-108">Der Computer muss ein Mitglied der Domäne, in der Sie ihn bereitstellen möchten, und Sie müssen erfolgreich abgeschlossen haben die Prep-Schema,-Gesamtstruktur und-Domäne für die Gesamtstruktur.</span><span class="sxs-lookup"><span data-stu-id="7544c-108">The computer must be a member of the domain in which you are going to deploy it, and you must have successfully completed the Schema, Forest, and Domain prep for your forest.</span></span>
  
<span data-ttu-id="7544c-109">Diese Aufgabe ist darauf ausgelegt, Standard Edition-Server als der erste Server in Ihrer Infrastruktur einrichten.</span><span class="sxs-lookup"><span data-stu-id="7544c-109">This particular task is designed to set up a Standard Edition server as the first server in your infrastructure.</span></span> <span data-ttu-id="7544c-110">Für diese Aufgabe wird den zentralen Verwaltungsspeicher, der SQL Server Express, auf dem Standard Edition-Server ist installiert.</span><span class="sxs-lookup"><span data-stu-id="7544c-110">This task installs the Central Management store, which is SQL Server Express, onto the Standard Edition server.</span></span> <span data-ttu-id="7544c-111">Wenn Sie einen anderen bereits Standard Edition-Server oder Front-End-Pool bereitgestellt haben, klicken Sie auf **Abbrechen**.</span><span class="sxs-lookup"><span data-stu-id="7544c-111">If you already have another Standard Edition server or Front End pool deployed, you should click **Cancel**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7544c-112">Klicken Sie nach Abschluss dieser Aufgabe, Topologie-Generator installieren, (Wenn Sie nicht bereits installiert haben) und konfigurieren Sie Ihre topologiedokument.</span><span class="sxs-lookup"><span data-stu-id="7544c-112">After completing this task, you will install Topology Builder (if you have not already installed it) and configure your topology document.</span></span> <span data-ttu-id="7544c-113">Ihre topologiedokument kann nicht veröffentlicht werden, bis Sie einen zentralen Verwaltungsspeicher haben – die mithilfe der Aufgabe in diesem Thema beschriebenen bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="7544c-113">You cannot publish your topology document until you have a Central Management store available—which is deployed by completing the task described in this topic.</span></span> 
  

