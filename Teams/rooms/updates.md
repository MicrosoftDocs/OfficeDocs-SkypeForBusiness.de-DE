---
title: Verwalten Windows Updates für Microsoft Teams-Räume
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.assetid: ''
description: Administratoren können erfahren, wie Sie Windows Updates und Windows featureupdates für Microsoft Teams-Räume.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c904db6b168280619b203a1327d6477736077efe
ms.sourcegitcommit: d2c76fe7705acf6e53f7673861671b1b018813dd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/13/2022
ms.locfileid: "62015005"
---
# <a name="manage-windows-updates"></a>Verwalten Windows Updates

Microsoft Teams-Räume wird auf Windows 10 Enterprise IoT oder Windows 10 Enterprise (VL) ausgeführt und empfängt die gleichen Windows-Updates und Betriebssystembuilds wie ein Standarddesktopcomputer.

Windows Updates können wie in den folgenden Abschnitten erläutert verwaltet werden:

## <a name="hands-off-approach"></a>Praktischer Ansatz 

- Standardmäßig werden Updates direkt aus Windows Updates heruntergeladen und während der Arbeitszeiten installiert.
- Nicht deferierbare Updates werden am 1. Tag der Veröffentlichung automatisch installiert.
- Qualitätsupdates und Treiber werden automatisch am ersten Tag heruntergeladen und installiert.
- Featureupdates. Schauen Sie sich die folgenden Notizen an.

## <a name="windows-updates-for-business-gpo-or-intune"></a>Windows Von Updates für Unternehmen (GPO oder Intune)  

- [Windows Updates für Unternehmen](/windows/deployment/update/waas-manage-updates-wufb) herunterladen
- Updates werden aus Windows Update oder Ihren Windows Server Update Services (WSUS) heruntergeladen, jedoch mit konfigurierten Verzögerungen nach dem ursprünglichen Veröffentlichungsdatum.
- Sie können mehrere OUs oder gefilterte Richtlinien verwenden, um Bereitstellungs-Ringe zu erstellen, in denen Administratoren angeben können, welche Teams-Räume-Geräte zuerst Qualitätsupdates installieren und welche später installiert werden. Zuverlässigkeit und Leistung können auf einer Teilmenge von Geräten getestet werden, bevor Updates für die gesamte Bereitstellung ohne den Aufwand für die Verwaltung Windows Updates in Configuration Manager veröffentlicht werden.
- WSUS und Windows Updates for Business [](/windows/deployment/update/waas-integrate-wufb) können gleichzeitig konfiguriert werden, wenn Sie sowohl die Bandbreitenverwaltung als auch das Windows Updates for Business nutzen möchten.
- Featureupdates. Schauen Sie sich die folgenden Notizen an.

## <a name="wsusconfiguration-manager"></a>WSUS/Configuration Manager

- [WSUS/Configuration Manager herunterladen](/windows/deployment/update/waas-manage-updates-configuration-manager)
- Ähnlich wie Windows Update for Business, aber mit der zusätzlichen Option, bestimmte KB-Daten in jedem "Ring" oder in der gesamten Bereitstellung als Ziel zu verwenden. Jedes Update kann einzeln bereitgestellt und getestet werden, anstatt nur von einer Verzögerung zu kommen.
- Featureupdates. Schauen Sie sich die folgenden Notizen an.

### <a name="feature-updates"></a>Featureupdates

Im Gegensatz zu Qualitätsupdates und nicht deferrierbaren Updates werden Windows 10 Featureupdates (Hauptversionen des Betriebssystems) nur installiert, nachdem Microsoft eine bestimmte Aktualisierungsfunktionalität mit einer anderen Microsoft Teams-Räume. Auch wenn das Update im Semi-Annual-Kanal veröffentlicht (oder targeted, wenn Sie Systeme zum Testen auf diesen Kanal festgelegt haben) oder manuell übertragen wird, lässt Microsoft Teams-Räume die Installation des nicht getesteten Updates nicht zu.

Microsoft Teams-Räume funktionen "out-of-box" mit einem praktischen Ansatz. Teams-Räume Ein Update herunterladen und auf den nächsten Neustart warten, um es zu installieren. Sofern kein manueller Neustart durchgeführt wird, erfolgt die Installation nur bei einem automatischen nächtlichen Neustart. Windows Updates sollten im Raum transparent sein, und der normale Vorgang sollte niemals von anderen Windows werden.

Wenn Sie sich für die Teilnahme an Geräten in einer Domäne entscheiden, können Sie Microsoft Endpoint Configuration Manager oder WSUS verwenden. Achten Sie besonders auf Richtlinien oder Aktionen, die zu einem Geräteupdate oder einem erzwungenen Neustart während der Geschäftszeiten führen. Teams-Räume sollten während der Nutzung oder Benachrichtigung über Updates Windows benutzeroberfläche während der Nutzungszeiten nicht neu gestartet werden. Überprüfen Sie ihre Konfiguration, wenn dieses Verhalten vor sich geht.
