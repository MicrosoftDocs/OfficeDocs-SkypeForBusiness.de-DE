---
title: Installieren des lokalen Konfigurationsspeichers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/13/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
description: Um mit der Installation eines neuen Skype for Business Server 2015-Rollen Servers zu beginnen, müssen Sie zuerst den lokalen SQL-Server installieren, der den lokalen Konfigurationsspeicher hosten soll. Der lokale Konfigurationsspeicher fungiert als schreibgeschütztes Replikat des Skype for Business Server Central-Verwaltungsspeichers (CMS). Sie müssen auf dem Server, auf dem Sie den Schritt Lokalen Konfigurationsspeicher installieren ausführen, als lokaler Administrator angemeldet sein und Mitglied der Gruppe „RTCUniversalServerAdmins“ oder „RTCUniversalGlobalReadOnlyGroup“ sein. Wenn Sie das Setup auf einem Edgeserver ausführen, müssen Sie kein Mitglied der Gruppe „RTCUniversalServerAdmins“ oder „RTCUniversalGlobalReadOnlyGroup“ sein. Das Definitions Dokument für das Topologie-Builder wird aus dem exportierten Definitions Dokument anstatt aus dem zentralen Verwaltungsspeicher gelesen. Informationen zum Exportieren des Definitions Dokuments für das Topologie-Builder und zur Bereitstellung für die Edgeserver finden Sie im Thema Exportieren der Topologie und Kopieren der Topologie auf externe Medien für die Edge-Installation.
ms.openlocfilehash: 83412bbef1305dab51cbb35ad9044f756154905c
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41687639"
---
# <a name="install-local-configuration-store"></a>Lokalen Konfigurationsspeicher installieren

Um mit der Installation eines neuen Skype for Business Server 2015-Rollen Servers zu beginnen, müssen Sie zuerst den lokalen SQL-Server installieren, der den lokalen Konfigurationsspeicher hosten soll. Der lokale Konfigurationsspeicher fungiert als schreibgeschütztes Replikat des Skype for Business Server Central-Verwaltungsspeichers (CMS). Sie müssen auf dem Server, auf dem Sie den Schritt **Lokalen Konfigurationsspeicher installieren** ausführen, als lokaler Administrator angemeldet sein und Mitglied der Gruppe „RTCUniversalServerAdmins“ oder „RTCUniversalGlobalReadOnlyGroup“ sein. Wenn Sie das Setup auf einem Edgeserver ausführen, müssen Sie kein Mitglied der Gruppe „RTCUniversalServerAdmins“ oder „RTCUniversalGlobalReadOnlyGroup“ sein. Das Definitions Dokument für das Topologie-Builder wird aus dem exportierten Definitions Dokument anstatt aus dem zentralen Verwaltungsspeicher gelesen. Informationen zum Exportieren des Definitions Dokuments für das Topologie-Builder und zur Bereitstellung für die Edgeserver finden Sie im Thema [Exportieren der Topologie und Kopieren der Topologie auf externe Medien für die Edge-Installation](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).

So starten Sie die Installation:

1. Klicken Sie auf der Seite Skype for Business Server 2015 neben Schritt 1 **: lokalen Konfigurationsspeicher installieren**auf **Ausführen**.

2. Vergewissern Sie sich auf der Seite **Lokale Serverkonfiguration**, dass die Option **Konfiguration automatisch aus dem zentralen Verwaltungsspeicher abrufen** ausgewählt ist, und klicken Sie dann auf **Weiter**.

3. Klicken Sie nach Abschluss der Installation der lokalen Serverkonfiguration auf **Fertig stellen**.

> [!NOTE]
> Die Installation des lokalen SQL-Servers kann einige Zeit in Anspruch nehmen. Auf dem Bildschirm "Installationszusammenfassung" werden keine Aktualisierungen des Status angezeigt, während SQL Server installiert wird. Wenn Sie den Status der Installation überwachen möchten, verwenden Sie den Task-Manager, um das SQL Server-Setup zu sehen.


