---
title: Installieren des lokalen Konfigurationsspeichers
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/13/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
description: Um mit der Installation eines neuen Skype for Business Server 2015-Rollenservers zu beginnen, müssen Sie zuerst die lokale SQL Server installieren, die den lokalen Konfigurationsspeicher hosten wird. Der lokale Konfigurationsspeicher wird als schreibgeschütztes Replikat des zentralen Verwaltungsspeichers (Central Management Store, CMS) von Skype for Business Server verwendet. Sie müssen auf dem Server, auf dem Sie den Schritt Lokalen Konfigurationsspeicher installieren ausführen, als lokaler Administrator angemeldet sein und Mitglied der Gruppe "RTCUniversalServerAdmins" oder "RTCUniversalGlobalReadOnlyGroup" sein. Wenn Sie das Setup auf einem Edgeserver ausführen, müssen Sie kein Mitglied der Gruppe "RTCUniversalServerAdmins" oder "RTCUniversalGlobalReadOnlyGroup" sein. Das Definitionsdokument des Topologie-Generators wird aus dem exportierten Definitionsdokument und nicht aus dem zentralen Verwaltungsspeicher gelesen. Informationen zum Exportieren des Definitionsdokuments des Topologie-Generators und zum Verfügbar machen für die Edgeserver finden Sie im Thema "Exportieren Ihrer Topologie und Kopieren auf externe Medien für die Edgeinstallation".
ms.openlocfilehash: 630a3682d3dd5ca12381d5f5b549bb22121b579e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827145"
---
# <a name="install-local-configuration-store"></a>Installieren des lokalen Konfigurationsspeichers

Um mit der Installation eines neuen Skype for Business Server 2015-Rollenservers zu beginnen, müssen Sie zuerst die lokale SQL Server installieren, die den lokalen Konfigurationsspeicher hosten wird. Der lokale Konfigurationsspeicher wird als schreibgeschütztes Replikat des zentralen Verwaltungsspeichers (Central Management Store, CMS) von Skype for Business Server verwendet. Sie müssen auf dem Server, auf dem Sie den Schritt **Lokalen Konfigurationsspeicher installieren** ausführen, als lokaler Administrator angemeldet sein und Mitglied der Gruppe "RTCUniversalServerAdmins" oder "RTCUniversalGlobalReadOnlyGroup" sein. Wenn Sie das Setup auf einem Edgeserver ausführen, müssen Sie kein Mitglied der Gruppe "RTCUniversalServerAdmins" oder "RTCUniversalGlobalReadOnlyGroup" sein. Das Definitionsdokument des Topologie-Generators wird aus dem exportierten Definitionsdokument und nicht aus dem zentralen Verwaltungsspeicher gelesen. Informationen zum Exportieren des Definitionsdokuments des Topologie-Generators und zum Verfügbar machen für die Edgeserver finden Sie im Thema "Exportieren Der Topologie und Kopieren der Topologie auf externe Medien für [die Edgeinstallation".](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx)

So starten Sie die Installation

1. Klicken Sie auf der Seite Skype for Business Server 2015 neben **Schritt1:** Lokalen Konfigurationsspeicher installieren auf **"Ausführen".**

2. Vergewissern Sie sich auf der Seite **Lokale Serverkonfiguration**, dass die Option **Konfiguration automatisch aus dem zentralen Verwaltungsspeicher abrufen** ausgewählt ist, und klicken Sie dann auf **Weiter**.

3. Klicken Sie nach Abschluss der Installation der lokalen Serverkonfiguration auf **Fertig stellen**.

> [!NOTE]
> Die Installation des lokalen SQL Server kann einige Zeit dauern. Während der Installation werden im Zusammenfassungsbildschirm für die Installation keine Updates SQL Server Fortschritt angezeigt. Wenn Sie den Fortschritt der Installation überwachen möchten, verwenden Sie den Task-Manager, um die SQL Server überwachen.


