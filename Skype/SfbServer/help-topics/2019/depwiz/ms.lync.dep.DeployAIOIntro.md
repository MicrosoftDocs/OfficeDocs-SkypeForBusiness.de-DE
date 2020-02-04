---
title: Vorbereiten eines einzelnen Standard Edition-Servers (Einführung)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployAIOIntro
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fe11d380-54c9-47e7-a676-02b9a59dc93f
ROBOTS: NOINDEX, NOFOLLOW
description: Wenn Sie mit der Installation eines Skype for Business Server Standard Edition-Servers beginnen möchten, auf dem der zentrale Verwaltungsspeicher und andere von Ihnen ausgewählte ausgewählte Dienste gespeichert sind, müssen Sie als Mitglied der lokalen Gruppe Administratoren auf dem Server angemeldet sein, der dann der Standard Edition-Server. Auf der Server Seite "Single Standard Edition vorbereiten" werden die Anforderungen für die Erstinstallation detailliert beschrieben. Der Computer muss ein Mitglied der Domäne sein, in der Sie das Deployment durchführen werden, und Sie müssen das Schema, die Gesamtstruktur und die Domänenvorbereitung für Ihre Gesamtstruktur erfolgreich abgeschlossen haben.
ms.openlocfilehash: e1d9119e07a813476fddf39ee46e43bc686cab45
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41692230"
---
# <a name="prepare-single-standard-edition-server-intro"></a><span data-ttu-id="622a9-105">Vorbereiten eines einzelnen Standard Edition-Servers (Einführung)</span><span class="sxs-lookup"><span data-stu-id="622a9-105">Prepare Single Standard Edition Server (Intro)</span></span>
 
<span data-ttu-id="622a9-106">Wenn Sie mit der Installation eines Skype for Business Server Standard Edition-Servers beginnen möchten, auf dem der zentrale Verwaltungsspeicher und andere von Ihnen ausgewählte ausgewählte Dienste gespeichert sind, müssen Sie als Mitglied der lokalen Gruppe Administratoren auf dem Server angemeldet sein, der dann der Standard Edition-Server.</span><span class="sxs-lookup"><span data-stu-id="622a9-106">To begin the installation of a Skype for Business Server Standard Edition server that will hold the Central Management store and other collocated services that you select, you must be logged in as a member of the local Administrators group on the server that will become the Standard Edition server.</span></span> <span data-ttu-id="622a9-107">Auf der Server Seite " **Single Standard Edition vorbereiten** " werden die Anforderungen für die Erstinstallation detailliert beschrieben.</span><span class="sxs-lookup"><span data-stu-id="622a9-107">The **Prepare single Standard Edition Server** page details the requirements for the initial install.</span></span> <span data-ttu-id="622a9-108">Der Computer muss ein Mitglied der Domäne sein, in der Sie das Deployment durchführen werden, und Sie müssen das Schema, die Gesamtstruktur und die Domänenvorbereitung für Ihre Gesamtstruktur erfolgreich abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="622a9-108">The computer must be a member of the domain in which you are going to deploy it, and you must have successfully completed the Schema, Forest, and Domain prep for your forest.</span></span>
  
<span data-ttu-id="622a9-109">Diese spezielle Aufgabe wurde entwickelt, um einen Standard Edition-Server als ersten Server in Ihrer Infrastruktur einzurichten.</span><span class="sxs-lookup"><span data-stu-id="622a9-109">This particular task is designed to set up a Standard Edition server as the first server in your infrastructure.</span></span> <span data-ttu-id="622a9-110">Dieser Task installiert den zentralen Verwaltungsspeicher, also SQL Server Express, auf dem Standard Edition-Server.</span><span class="sxs-lookup"><span data-stu-id="622a9-110">This task installs the Central Management store, which is SQL Server Express, onto the Standard Edition server.</span></span> <span data-ttu-id="622a9-111">Wenn Sie bereits einen anderen Standard Edition-Server oder Front-End-Pool bereitgestellt haben, klicken Sie auf **Abbrechen**.</span><span class="sxs-lookup"><span data-stu-id="622a9-111">If you already have another Standard Edition server or Front End pool deployed, you should click **Cancel**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="622a9-112">Nachdem Sie diese Aufgabe abgeschlossen haben, installieren Sie den Topology Builder (sofern Sie ihn noch nicht installiert haben) und konfigurieren Ihr Topologie-Dokument.</span><span class="sxs-lookup"><span data-stu-id="622a9-112">After completing this task, you will install Topology Builder (if you have not already installed it) and configure your topology document.</span></span> <span data-ttu-id="622a9-113">Sie können Ihr Topologie-Dokument erst veröffentlichen, wenn ein zentraler Verwaltungsspeicher verfügbar ist, der durch Ausführen der in diesem Thema beschriebenen Aufgabe bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="622a9-113">You cannot publish your topology document until you have a Central Management store available—which is deployed by completing the task described in this topic.</span></span> 
  

