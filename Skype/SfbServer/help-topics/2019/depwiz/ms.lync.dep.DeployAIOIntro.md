---
title: Vorbereiten eines einzelnen Standard Edition-Servers (Einführung)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployAIOIntro
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: fe11d380-54c9-47e7-a676-02b9a59dc93f
ROBOTS: NOINDEX, NOFOLLOW
description: Wenn Sie mit der Installation eines Skype for Business Server Standard Edition-Servers beginnen möchten, auf dem der zentrale Verwaltungsspeicher und andere von Ihnen ausgewählte ausgewählte Dienste gespeichert sind, müssen Sie als Mitglied der lokalen Gruppe Administratoren auf dem Server angemeldet sein, der dann der Standard Edition-Server. Auf der Server Seite "Single Standard Edition vorbereiten" werden die Anforderungen für die Erstinstallation detailliert beschrieben. Der Computer muss ein Mitglied der Domäne sein, in der Sie das Deployment durchführen werden, und Sie müssen das Schema, die Gesamtstruktur und die Domänenvorbereitung für Ihre Gesamtstruktur erfolgreich abgeschlossen haben.
ms.openlocfilehash: 437f90fa99efa920479e7c0dc966c3c63fd5eed1
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41796976"
---
# <a name="prepare-single-standard-edition-server-intro"></a>Vorbereiten eines einzelnen Standard Edition-Servers (Einführung)
 
Wenn Sie mit der Installation eines Skype for Business Server Standard Edition-Servers beginnen möchten, auf dem der zentrale Verwaltungsspeicher und andere von Ihnen ausgewählte ausgewählte Dienste gespeichert sind, müssen Sie als Mitglied der lokalen Gruppe Administratoren auf dem Server angemeldet sein, der dann der Standard Edition-Server. Auf der Server Seite " **Single Standard Edition vorbereiten** " werden die Anforderungen für die Erstinstallation detailliert beschrieben. Der Computer muss ein Mitglied der Domäne sein, in der Sie das Deployment durchführen werden, und Sie müssen das Schema, die Gesamtstruktur und die Domänenvorbereitung für Ihre Gesamtstruktur erfolgreich abgeschlossen haben.
  
Diese spezielle Aufgabe wurde entwickelt, um einen Standard Edition-Server als ersten Server in Ihrer Infrastruktur einzurichten. Dieser Task installiert den zentralen Verwaltungsspeicher, also SQL Server Express, auf dem Standard Edition-Server. Wenn Sie bereits einen anderen Standard Edition-Server oder Front-End-Pool bereitgestellt haben, klicken Sie auf **Abbrechen**.
  
> [!NOTE]
> Nachdem Sie diese Aufgabe abgeschlossen haben, installieren Sie den Topology Builder (sofern Sie ihn noch nicht installiert haben) und konfigurieren Ihr Topologie-Dokument. Sie können Ihr Topologie-Dokument erst veröffentlichen, wenn ein zentraler Verwaltungsspeicher verfügbar ist, der durch Ausführen der in diesem Thema beschriebenen Aufgabe bereitgestellt wird. 
  

