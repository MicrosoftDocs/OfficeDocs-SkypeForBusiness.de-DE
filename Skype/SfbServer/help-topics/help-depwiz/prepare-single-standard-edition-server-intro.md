---
title: Vorbereiten eines einzelnen Standard Edition-Servers (Einführung)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployAIOIntro
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fe11d380-54c9-47e7-a676-02b9a59dc93f
description: Wenn Sie mit der Installation eines Skype for Business Server 2015 Standard Edition-Servers beginnen möchten, auf dem der zentrale Verwaltungsspeicher und andere von Ihnen ausgewählte ausgewählte Dienste gespeichert sind, müssen Sie als Mitglied der lokalen Gruppe Administratoren auf dem Server angemeldet sein, auf dem sich werden Sie zum Standard Edition-Server. Auf der Server Seite "Single Standard Edition vorbereiten" werden die Anforderungen für die Erstinstallation detailliert beschrieben. Der Computer muss ein Mitglied der Domäne sein, in der Sie das Deployment durchführen werden, und Sie müssen das Schema, die Gesamtstruktur und die Domänenvorbereitung für Ihre Gesamtstruktur erfolgreich abgeschlossen haben.
ms.openlocfilehash: a426d734c7644511d31a5b53d3a4939c95f979f3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823469"
---
# <a name="prepare-single-standard-edition-server-intro"></a>Vorbereiten eines einzelnen Standard Edition-Servers (Einführung)
 
Wenn Sie mit der Installation eines Skype for Business Server 2015 Standard Edition-Servers beginnen möchten, auf dem der zentrale Verwaltungsspeicher und andere von Ihnen ausgewählte ausgewählte Dienste gespeichert sind, müssen Sie als Mitglied der lokalen Gruppe Administratoren auf dem Server angemeldet sein, auf dem sich werden Sie zum Standard Edition-Server. Auf der Server Seite " **Single Standard Edition vorbereiten** " werden die Anforderungen für die Erstinstallation detailliert beschrieben. Der Computer muss ein Mitglied der Domäne sein, in der Sie das Deployment durchführen werden, und Sie müssen das Schema, die Gesamtstruktur und die Domänenvorbereitung für Ihre Gesamtstruktur erfolgreich abgeschlossen haben.
  
Diese spezielle Aufgabe wurde entwickelt, um einen Standard Edition-Server als ersten Server in Ihrer Infrastruktur einzurichten. Dieser Task installiert den zentralen Verwaltungsspeicher, also SQL Server Express, auf dem Standard Edition-Server. Wenn Sie bereits einen anderen Standard Edition-Server oder Front-End-Pool bereitgestellt haben, klicken Sie auf **Abbrechen**.
  
> [!NOTE]
> Nachdem Sie diese Aufgabe abgeschlossen haben, installieren Sie den Topology Builder (sofern Sie ihn noch nicht installiert haben) und konfigurieren Ihr Topologie-Dokument. Sie können Ihr Topologie-Dokument erst veröffentlichen, wenn ein zentraler Verwaltungsspeicher verfügbar ist, der durch Ausführen der in diesem Thema beschriebenen Aufgabe bereitgestellt wird. 
  

