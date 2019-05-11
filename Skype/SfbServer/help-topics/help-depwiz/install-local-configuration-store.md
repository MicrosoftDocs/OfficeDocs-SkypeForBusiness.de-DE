---
title: Installieren des lokalen Konfigurationsspeichers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/13/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
description: Um die Installation von einer neuen Skype für Business Server 2015 Rolle Server beginnen, müssen Sie zuerst den lokalen SQL Server installieren, auf denen den lokale Konfigurationsspeicher gehostet wird. Der lokale Konfigurationsspeicher fungiert als ein Replikat der Skype für Business Server zentralen Verwaltungsspeicher (CMS) schreibgeschützt. Sie müssen auf dem Server, auf dem Sie den Schritt Lokalen Konfigurationsspeicher installieren ausführen, als lokaler Administrator angemeldet sein und Mitglied der Gruppe „RTCUniversalServerAdmins“ oder „RTCUniversalGlobalReadOnlyGroup“ sein. Wenn Sie das Setup auf einem Edgeserver ausführen, müssen Sie kein Mitglied der Gruppe „RTCUniversalServerAdmins“ oder „RTCUniversalGlobalReadOnlyGroup“ sein. Topologie-Generator Definition Dokument wird aus dem Dokument exportierten Definition statt aus dem zentralen Verwaltungsspeicher gelesen werden. Exportieren Sie das Dokument der Topologie-Generator-Definition und für den Edge-Servern verfügbar machen, finden im Thema Your Topology exportieren und kopieren Sie es auf externe Medien zur Edgeinstallation.
ms.openlocfilehash: c5c06d47b0deb8e82505567750832762a21200e7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33921027"
---
# <a name="install-local-configuration-store"></a>Lokalen Konfigurationsspeicher installieren

Um die Installation von einer neuen Skype für Business Server 2015 Rolle Server beginnen, müssen Sie zuerst den lokalen SQL Server installieren, auf denen den lokale Konfigurationsspeicher gehostet wird. Der lokale Konfigurationsspeicher fungiert als ein Replikat der Skype für Business Server zentralen Verwaltungsspeicher (CMS) schreibgeschützt. Sie müssen auf dem Server, auf dem Sie den Schritt **Lokalen Konfigurationsspeicher installieren** ausführen, als lokaler Administrator angemeldet sein und Mitglied der Gruppe „RTCUniversalServerAdmins“ oder „RTCUniversalGlobalReadOnlyGroup“ sein. Wenn Sie das Setup auf einem Edgeserver ausführen, müssen Sie kein Mitglied der Gruppe „RTCUniversalServerAdmins“ oder „RTCUniversalGlobalReadOnlyGroup“ sein. Topologie-Generator Definition Dokument wird aus dem Dokument exportierten Definition statt aus dem zentralen Verwaltungsspeicher gelesen werden. Exportieren Sie das Dokument der Topologie-Generator-Definition und für den Edge-Servern verfügbar machen, finden im Thema [Your Topology exportieren und kopieren Sie es auf externe Medien zur Edgeinstallation](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).

So starten Sie die Installation:

1. Klicken Sie auf die Skype für Business Server 2015-Seite neben **Schritt 1: lokalen Konfigurationsspeicher installieren**, klicken Sie auf **Ausführen**.

2. Vergewissern Sie sich auf der Seite **Lokale Serverkonfiguration**, dass die Option **Konfiguration automatisch aus dem zentralen Verwaltungsspeicher abrufen** ausgewählt ist, und klicken Sie dann auf **Weiter**.

3. Klicken Sie nach Abschluss der Installation der lokalen Serverkonfiguration auf **Fertig stellen**.

> [!NOTE]
> Die Installation von der lokalen SQL Server kann eine Weile dauern. Updates werden nicht auf Fortschritte bei der Installation im Fenster Zusammenfassung angezeigt werden, während SQL Server installiert wird. Wenn Sie den Status der Installation überwachen möchten, verwenden Sie Task-Manager überwachen das SQL Server-Setup.


