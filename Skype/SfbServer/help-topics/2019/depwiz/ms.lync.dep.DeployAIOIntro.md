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
# <a name="prepare-single-standard-edition-server-intro"></a>Vorbereiten eines einzelnen Standard Edition-Servers (Einführung)
 
Wenn Sie mit der Installation eines Skype for Business Server Standard Edition-Servers beginnen möchten, auf dem der zentrale Verwaltungsspeicher und andere von Ihnen ausgewählte ausgewählte Dienste gespeichert sind, müssen Sie als Mitglied der lokalen Gruppe Administratoren auf dem Server angemeldet sein, der dann der Standard Edition-Server. Auf der Server Seite " **Single Standard Edition vorbereiten** " werden die Anforderungen für die Erstinstallation detailliert beschrieben. Der Computer muss ein Mitglied der Domäne sein, in der Sie das Deployment durchführen werden, und Sie müssen das Schema, die Gesamtstruktur und die Domänenvorbereitung für Ihre Gesamtstruktur erfolgreich abgeschlossen haben.
  
Diese spezielle Aufgabe wurde entwickelt, um einen Standard Edition-Server als ersten Server in Ihrer Infrastruktur einzurichten. Dieser Task installiert den zentralen Verwaltungsspeicher, also SQL Server Express, auf dem Standard Edition-Server. Wenn Sie bereits einen anderen Standard Edition-Server oder Front-End-Pool bereitgestellt haben, klicken Sie auf **Abbrechen**.
  
> [!NOTE]
> Nachdem Sie diese Aufgabe abgeschlossen haben, installieren Sie den Topology Builder (sofern Sie ihn noch nicht installiert haben) und konfigurieren Ihr Topologie-Dokument. Sie können Ihr Topologie-Dokument erst veröffentlichen, wenn ein zentraler Verwaltungsspeicher verfügbar ist, der durch Ausführen der in diesem Thema beschriebenen Aufgabe bereitgestellt wird. 
  

