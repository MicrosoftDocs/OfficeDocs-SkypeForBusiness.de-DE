---
title: Installieren des lokalen Konfigurationsspeichers
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 4/13/2015
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
description: 'Um mit der Installation eines neuen Skype for Business Server 2015-Rollenservers zu beginnen, müssen Sie zuerst die lokale SQL Server installieren, die den lokalen Konfigurationsspeicher hosten soll. Der lokale Konfigurationsspeicher fungiert als schreibgeschütztes Replikat des Skype for Business Server zentralen Verwaltungsspeichers (CMS). Sie müssen auf dem Server, auf dem Sie den Schritt Lokalen Konfigurationsspeicher installieren ausführen, als lokaler Administrator angemeldet sein und Mitglied der Gruppe "RTCUniversalServerAdmins" oder "RTCUniversalGlobalReadOnlyGroup" sein. Wenn Sie das Setup auf einem Edgeserver ausführen, müssen Sie kein Mitglied der Gruppe "RTCUniversalServerAdmins" oder "RTCUniversalGlobalReadOnlyGroup" sein. Das Definitionsdokument des Topologie-Generators wird aus dem exportierten Definitionsdokument anstelle des zentralen Verwaltungsspeichers gelesen. Informationen zum Exportieren des Definitionsdokuments des Topologie-Generators und zur Bereitstellung für die Edgeserver finden Sie im Thema "Exportieren Ihrer Topologie und Kopieren in externe Medien für die Edgeinstallation".'
---

# <a name="install-local-configuration-store"></a>Installieren des lokalen Konfigurationsspeichers

Um mit der Installation eines neuen Skype for Business Server 2015-Rollenservers zu beginnen, müssen Sie zuerst die lokale SQL Server installieren, die den lokalen Konfigurationsspeicher hosten soll. Der lokale Konfigurationsspeicher fungiert als schreibgeschütztes Replikat des Skype for Business Server zentralen Verwaltungsspeichers (CMS). Sie müssen auf dem Server, auf dem Sie den Schritt **Lokalen Konfigurationsspeicher installieren** ausführen, als lokaler Administrator angemeldet sein und Mitglied der Gruppe "RTCUniversalServerAdmins" oder "RTCUniversalGlobalReadOnlyGroup" sein. Wenn Sie das Setup auf einem Edgeserver ausführen, müssen Sie kein Mitglied der Gruppe "RTCUniversalServerAdmins" oder "RTCUniversalGlobalReadOnlyGroup" sein. Das Definitionsdokument des Topologie-Generators wird aus dem exportierten Definitionsdokument anstelle des zentralen Verwaltungsspeichers gelesen. Informationen zum Exportieren des Definitionsdokuments des Topologie-Generators und zur Bereitstellung für die Edgeserver finden Sie im Thema ["Exportieren Ihrer Topologie und Kopieren in externe Medien für die Edgeinstallation](/previous-versions/office/lync-server-2013/lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation)".

So starten Sie die Installation

1. Klicken Sie auf der Seite Skype for Business Server 2015 neben **Schritt1: Installieren der lokalen Konfiguration Store** auf **"Ausführen**".

2. Vergewissern Sie sich auf der Seite **Lokale Serverkonfiguration**, dass die Option **Konfiguration automatisch aus dem zentralen Verwaltungsspeicher abrufen** ausgewählt ist, und klicken Sie dann auf **Weiter**.

3. Klicken Sie nach Abschluss der Installation der lokalen Serverkonfiguration auf **Fertig stellen**.

> [!NOTE]
> Die Installation der lokalen SQL Server kann einige Zeit in Anspruch nehmen. Während SQL Server installiert wird, werden auf dem Bildschirm mit der Installationszusammenfassung keine Updates zum Fortschritt angezeigt. Wenn Sie den Fortschritt der Installation überwachen möchten, verwenden Sie den Task-Manager, um das SQL Server Setup zu überwachen.