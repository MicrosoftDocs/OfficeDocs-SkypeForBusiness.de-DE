---
title: Installieren des lokalen Konfigurationsspeichers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
ROBOTS: NOINDEX, NOFOLLOW
description: Um mit der Installation eines neuen Skype for Business Server-Rollen Servers zu beginnen, müssen Sie zuerst den lokalen SQL Server installieren, der den lokalen Konfigurationsspeicher hosten soll. Der lokale Konfigurationsspeicher fungiert als schreibgeschütztes Replikat des Skype for Business Server Central-Verwaltungsspeichers (CMS).
ms.openlocfilehash: 365529c3c9cb15ea50cd6a482bd2a69143daa219
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794794"
---
# <a name="install-local-configuration-store"></a>Lokalen Konfigurationsspeicher installieren

Um mit der Installation eines neuen Skype for Business Server-Rollen Servers zu beginnen, müssen Sie zuerst den lokalen SQL Server installieren, der den lokalen Konfigurationsspeicher hosten soll. Der lokale Konfigurationsspeicher fungiert als schreibgeschütztes Replikat des Skype for Business Server Central-Verwaltungsspeichers (CMS). Sie müssen auf dem Server, auf dem Sie den Schritt **Lokalen Konfigurationsspeicher installieren** ausführen, als lokaler Administrator angemeldet sein und Mitglied der Gruppe „RTCUniversalServerAdmins“ oder „RTCUniversalGlobalReadOnlyGroup“ sein. Wenn Sie das Setup auf einem Edgeserver ausführen, müssen Sie kein Mitglied der Gruppe „RTCUniversalServerAdmins“ oder „RTCUniversalGlobalReadOnlyGroup“ sein. Das Definitions Dokument für das Topologie-Builder wird aus dem exportierten Definitions Dokument anstatt aus dem zentralen Verwaltungsspeicher gelesen. Informationen zum Exportieren des Definitions Dokuments für das Topologie-Builder und zur Bereitstellung für die Edgeserver finden Sie im Thema[Exportieren der Topologie und Kopieren der Topologie auf externe Medien für die Edge-Installation](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).

So starten Sie die Installation:

1. Klicken Sie auf der Seite Skype for Business Server neben Schritt 1 **: lokalen Konfigurationsspeicher installieren**auf **Ausführen**.

2. Vergewissern Sie sich auf der Seite **Lokale Serverkonfiguration**, dass die Option **Konfiguration automatisch aus dem zentralen Verwaltungsspeicher abrufen** ausgewählt ist, und klicken Sie dann auf **Weiter**.

3. Klicken Sie nach Abschluss der Installation der lokalen Serverkonfiguration auf **Fertig stellen**.

> [!NOTE]
> Die Installation des lokalen SQL-Servers kann einige Zeit in Anspruch nehmen. Auf dem Bildschirm "Installationszusammenfassung" werden keine Aktualisierungen des Status angezeigt, während SQL Server installiert wird. Wenn Sie den Status der Installation überwachen möchten, verwenden Sie den Task-Manager, um das SQL Server-Setup zu sehen.


