---
title: Verwalten Windows Updates für Microsoft Teams-Räume
ms.author: czawideh
author: cazawideh
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
description: Administratoren erfahren, wie Sie Ihre Windows und Windows updates für Microsoft Teams-Räume.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 95b99e8869ed9fa63a372c6c40d1d0d2be28c019
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2022
ms.locfileid: "63503752"
---
# <a name="manage-windows-updates"></a>Verwalten Windows Updates

Microsoft Teams-Räume wird auf Windows 10 Enterprise IoT oder Windows 10 Enterprise (VL) ausgeführt und empfängt die gleichen Windows-Updates und Betriebssystembuilds wie ein Standarddesktopcomputer.

Windows Updates können wie in den folgenden Abschnitten erläutert verwaltet werden:

## <a name="hands-off-approach"></a>Praktischer Ansatz 

- Standardmäßig werden Updates direkt aus Windows Updates automatisch heruntergeladen und während der Arbeitszeiten installiert.
- Nicht deferierbare Updates werden am 1. Tag der Veröffentlichung automatisch installiert.
- Qualitätsupdates und Treiber werden automatisch am ersten Tag heruntergeladen und installiert.
- Featureupdates. Schauen Sie sich die folgenden Notizen an.

## <a name="windows-updates-for-business-gpo-or-intune"></a>Windows von Updates für Unternehmen (GPO oder Intune)  

- [Windows Updates für Unternehmen](/windows/deployment/update/waas-manage-updates-wufb) herunterladen
- Updates werden aus Windows Update oder Ihren Windows Server Update Services (WSUS) heruntergeladen, jedoch mit konfigurierten Verzögerungen nach dem ursprünglichen Veröffentlichungsdatum.
- Sie können mehrere OUs oder gefilterte Richtlinien verwenden, um Bereitstellungs-Ringe zu erstellen, in denen Administratoren angeben können, welche Teams-Räume-Geräte zuerst Qualitätsupdates installieren und welche später installiert werden. Zuverlässigkeit und Leistung können auf einer Teilmenge von Geräten getestet werden, bevor Updates für die gesamte Bereitstellung ohne den Aufwand für die Verwaltung Windows Updates in Configuration Manager veröffentlicht werden.
- WSUS und Windows Updates for Business können gleichzeitig konfiguriert werden, [](/windows/deployment/update/waas-integrate-wufb) wenn Sie sowohl die Bandbreitenverwaltung als auch das Windows Updates for Business nutzen möchten.
- Featureupdates. Schauen Sie sich die folgenden Notizen an.

## <a name="wsusconfiguration-manager"></a>WSUS/Configuration Manager

- [WSUS/Configuration Manager herunterladen](/windows/deployment/update/waas-manage-updates-configuration-manager)
- Ähnlich wie Windows Update for Business, aber mit der zusätzlichen Option, bestimmte KB-Daten in jedem "Ring" oder in der gesamten Bereitstellung als Ziel zu verwenden. Jedes Update kann einzeln bereitgestellt und getestet werden, anstatt nur von einer Verzögerung zu kommen.
- Featureupdates. Schauen Sie sich die folgenden Notizen an.

### <a name="feature-updates"></a>Featureupdates

Im Gegensatz zu Qualitätsupdates und nicht deferrierbaren Updates werden Windows 10 Featureupdates (Hauptversionen des Betriebssystems) nur installiert, nachdem Microsoft eine bestimmte Aktualisierungsfunktionalität mit einem Microsoft Teams-Räume. Selbst wenn das Update im Semi-Annual-Kanal veröffentlicht wird (oder targeted, wenn Sie Systeme zum Testen auf diesen Kanal festgelegt haben) oder manuell per Push übertragen wird, lässt Microsoft Teams-Räume die Installation des nicht getesteten Updates nicht zu.

Microsoft Teams-Räume funktionen "out-of-box" mit einem praktischen Ansatz. Teams-Räume Update herunter, und warten Sie auf den nächsten Neustart, um es zu installieren. Sofern kein manueller Neustart durchgeführt wird, erfolgt die Installation nur bei einem automatischen nächtlichen Neustart. Windows Updates sollten im Raum transparent sein, und der normale Vorgang sollte niemals von anderen Windows werden.

Wenn Sie sich für die Teilnahme an Geräten in einer Domäne entscheiden, können Sie Microsoft Endpoint Configuration Manager oder WSUS verwenden. Achten Sie besonders auf Richtlinien oder Aktionen, die zu einem Geräteupdate oder einem erzwungenen Neustart während der Geschäftszeiten führen. Teams-Räume sollten während der Nutzung oder Benachrichtigung über Windows Updates während der Nutzungszeiten nicht neu gestartet werden. Überprüfen Sie ihre Konfiguration, wenn dieses Verhalten vor sich geht.
