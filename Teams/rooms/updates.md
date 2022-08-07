---
title: Verwalten von Windows Aktualisierungen für Microsoft Teams-Räume
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
- Teams_ITAdmin_Rooms
ms.assetid: ''
description: Admin erfahren, wie Sie Windows Aktualisierungen- und Windows-Featureupdates für Microsoft Teams-Räume verwalten.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1df5521bdfafe38854a0b6a3821e86218ce95a0b
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2022
ms.locfileid: "67272180"
---
# <a name="manage-windows-updates"></a>Verwalten von Windows Aktualisierungen

Microsoft Teams-Räume wird auf Windows 10 Enterprise IoT oder Windows 10 Enterprise (VL) ausgeführt und empfängt die gleichen Windows Aktualisierungen- und BS-Builds wie ein Standarddesktopcomputer.

Windows Aktualisierungen kann wie in den folgenden Abschnitten erläutert verwaltet werden:

## <a name="hands-off-approach"></a>Praktischer Ansatz 

- Standardmäßig werden Updates direkt aus Windows heruntergeladen Aktualisierungen automatisch und außerhalb der Geschäftszeiten installiert.
- Nicht zurücksetzbare Aktualisierungen automatisch den ersten Tag der Veröffentlichung installieren.
- Qualitäts-Aktualisierungen und Treiber laden tag-1 automatisch herunter und installieren sie.
- Feature-Aktualisierungen. Sehen Sie sich die folgenden Notizen an.

## <a name="windows-updates-for-business-gpo-or-intune"></a>Windows Aktualisierungen for Business (GPO oder Intune)  

- [Herunterladen von Windows Aktualisierungen for Business](/windows/deployment/update/waas-manage-updates-wufb)
- Aktualisierungen werden von Windows Update oder Ihrem Windows Server Update Services (WSUS) heruntergeladen, jedoch mit konfigurierten Verzögerungen nach dem ursprünglichen Veröffentlichungsdatum.
- Sie können mehrere OUs oder gefilterte Richtlinien verwenden, um Bereitstellungsringe zu erstellen, in denen Administratoren angeben können, welche Teams-Räume Geräte zuerst Quality Aktualisierungen installieren und welche später installiert werden. Zuverlässigkeit und Leistung können auf einer Teilmenge von Geräten getestet werden, bevor Updates für die gesamte Bereitstellung bereitgestellt werden, ohne dass der Aufwand für die Verwaltung von Windows Aktualisierungen in Configuration Manager entsteht.
- WSUS und Windows Aktualisierungen for Business können [gleichzeitig konfiguriert](/windows/deployment/update/waas-integrate-wufb) werden, wenn Sie sowohl die Bandbreitenverwaltung als auch die Von Windows Aktualisierungen for Business bereitgestellte Steuerung wünschen.
- Funktionsupdates. Sehen Sie sich die folgenden Notizen an.

## <a name="wsusconfiguration-manager"></a>WSUS/Configuration Manager

- [WSUS/Configuration Manager](/windows/deployment/update/waas-manage-updates-configuration-manager) Herunterladen
- Ähnlich wie Windows Update für Unternehmen, aber mit der zusätzlichen Option, bestimmte KB innerhalb jedes "Rings" oder der gesamten Bereitstellung auszurichten. Jedes Update kann einzeln bereitgestellt und nach Be willen getestet werden, anstatt sich nur auf eine Verzögerung zu verlassen.
- Funktionsupdates. Sehen Sie sich die folgenden Notizen an.

### <a name="feature-updates"></a>Featureupdates

Im Gegensatz zu Qualitäts- und nicht zurücksetzbaren Updates wird Windows 10 "Feature Aktualisierungen" (Hauptversionen des Betriebssystems) erst installiert, nachdem Microsoft eine bestimmte Updatefunktionalität mit Microsoft Teams-Räume getestet und überprüft hat. Auch wenn das Update im Semi-Annual-Kanal veröffentlicht wird (oder gezielt, wenn Systeme zu Testzwecken auf diesen Kanal festgelegt sind) oder manuell übertragen wird, lässt Microsoft Teams-Räume die Installation des nicht getesteten Updates nicht zu.

Microsoft Teams-Räume funktioniert "out-of-box" mit einem praktischen Ansatz. Teams-Räume ein Update herunterladen und auf den nächsten Neustart warten, um es zu installieren. Wenn die Installation nicht manuell neu gestartet wird, erfolgt die Installation nur beim automatischen nächtlichen Neustart. Windows Aktualisierungen sollte im Raum transparent sein, und der normale Betrieb sollte nie von Windows Aktualisierungen unterbrochen werden.

Wenn Sie sich für domänenverbundene Geräte entscheiden, können Sie Microsoft Endpoint Configuration Manager oder WSUS verwenden. Achten Sie besonders auf Richtlinien oder Aktionen, die zu einem Geräteupdate oder einem erzwungenen Neustart während der Geschäftszeiten führen. Teams-Räume sollten während der Verwendung nicht neu gestartet werden oder während der Nutzungszeit über die Benutzeroberfläche über Windows Aktualisierungen benachrichtigen. Überprüfen Sie Ihre Konfiguration, wenn dieses Verhalten auftritt.
