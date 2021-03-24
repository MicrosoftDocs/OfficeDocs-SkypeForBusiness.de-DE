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
description: Um mit der Installation eines neuen Skype for Business Server 2015-Rollenservers zu beginnen, müssen Sie zuerst die lokale SQL Server installieren, die den lokalen Konfigurationsspeicher hosten wird. Der lokale Konfigurationsspeicher wird als schreibgeschütztes Replikat des zentralen Skype for Business Server Management Store (CMS) fungieren. Sie müssen auf dem Server, auf dem Sie den Schritt Lokalen Konfigurationsspeicher installieren ausführen, als lokaler Administrator angemeldet sein und Mitglied der Gruppe "RTCUniversalServerAdmins" oder "RTCUniversalGlobalReadOnlyGroup" sein. Wenn Sie das Setup auf einem Edgeserver ausführen, müssen Sie kein Mitglied der Gruppe "RTCUniversalServerAdmins" oder "RTCUniversalGlobalReadOnlyGroup" sein. Das Definitionsdokument des Topologie-Generators wird aus dem exportierten Definitionsdokument statt aus dem zentralen Verwaltungsspeicher gelesen. Informationen zum Exportieren des Definitionsdokuments des Topologie-Generators und zur Verfügung stellen für die Edgeserver finden Sie im Thema Exportieren Ihrer Topologie und Kopieren in externe Medien für die Edgeinstallation.
ms.openlocfilehash: 62a16e441cc95e77aaed7e09152ef2a79221d85f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51108741"
---
# <a name="install-local-configuration-store"></a>Installieren des lokalen Konfigurationsspeichers

Um mit der Installation eines neuen Skype for Business Server 2015-Rollenservers zu beginnen, müssen Sie zuerst die lokale SQL Server installieren, die den lokalen Konfigurationsspeicher hosten wird. Der lokale Konfigurationsspeicher wird als schreibgeschütztes Replikat des zentralen Skype for Business Server Management Store (CMS) fungieren. Sie müssen auf dem Server, auf dem Sie den Schritt **Lokalen Konfigurationsspeicher installieren** ausführen, als lokaler Administrator angemeldet sein und Mitglied der Gruppe "RTCUniversalServerAdmins" oder "RTCUniversalGlobalReadOnlyGroup" sein. Wenn Sie das Setup auf einem Edgeserver ausführen, müssen Sie kein Mitglied der Gruppe "RTCUniversalServerAdmins" oder "RTCUniversalGlobalReadOnlyGroup" sein. Das Definitionsdokument des Topologie-Generators wird aus dem exportierten Definitionsdokument statt aus dem zentralen Verwaltungsspeicher gelesen. Informationen zum Exportieren des Definitionsdokuments des Topologie-Generators und zur Verfügung stellen für die Edgeserver finden Sie im Thema Exportieren Der Topologie und Kopieren in externe Medien [für die Edgeinstallation.](/previous-versions/office/lync-server-2013/lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation)

So starten Sie die Installation

1. Klicken Sie auf der Seite Skype for Business Server 2015 neben **Schritt1: Installieren des lokalen Konfigurationsspeichers** auf **Ausführen**.

2. Vergewissern Sie sich auf der Seite **Lokale Serverkonfiguration**, dass die Option **Konfiguration automatisch aus dem zentralen Verwaltungsspeicher abrufen** ausgewählt ist, und klicken Sie dann auf **Weiter**.

3. Klicken Sie nach Abschluss der Installation der lokalen Serverkonfiguration auf **Fertig stellen**.

> [!NOTE]
> Die Installation der lokalen SQL Server kann einige Zeit dauern. Während der Installation werden keine Updates zum Fortschritt im Installationszusammenfassungsbildschirm SQL Server angezeigt. Wenn Sie den Installationsfortschritt überwachen möchten, können Sie den Vorgangs-Manager verwenden, um die installation SQL Server überwachen.