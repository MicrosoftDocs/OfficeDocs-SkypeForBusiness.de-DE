---
title: Verwalten von Windows-Updates für Microsoft Teams-Chatrooms
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 10/10/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: M365-voice
ms.assetid: ''
description: Verwalten von Windows-Updates für Microsoft Teams-Chatrooms
ms.openlocfilehash: 434e6d28796662c1cc8904b7ad94f059d7d447b0
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243278"
---
# <a name="manage-windows-updates"></a>Verwalten von Windows-Updates

Microsoft Teams rooms läuft unter Windows 10 Enterprise-oder Windows 10 Enterprise (VL) und empfängt dieselben Windows-Updates und Betriebssystem-Builds wie ein Standard-Desktop.

Windows-Updates können auf verschiedene Arten verwaltet werden:

## <a name="hands-off-approach"></a>Hands-Off-Ansatz 

- Updates können direkt von Windows-Updates automatisch heruntergeladen und außerhalb der Arbeitszeiten installiert werden. Dies ist die Standardkonfiguration.
- Nicht verzögerungsfreie Updates installieren den Tag – einer der Versionen automatisch.
- Qualitäts Updates und-Treiber laden Sie den Tag automatisch herunter, und installieren Sie ihn.
- Funktions Updates. Lesen Sie die folgenden Hinweise.

## <a name="windows-updates-for-business-gpo-or-intune"></a>Windows-Updates für Unternehmen (GPO oder InTune)  

- [Windows-Updates für Unternehmen](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) herunterladen
- Updates werden von Wu oder Ihrem WSUS heruntergeladen, aber mit konfigurierten Verzögerungen nach dem ursprünglichen Veröffentlichungsdatum der KB.
- Mit mehreren ou-oder gefilterten Richtlinien können Sie die Bereitstellung "Ringe" erstellen, in denen Administratoren angeben können, welche Geräte zuerst Qualitäts Updates installieren und welche später installiert werden. Auf diese Weise können Zuverlässigkeits-und Leistungstests für eine Teilmenge von Systemen durchgeführt werden, bevor Updates für die gesamte Bereitstellung ohne den Aufwand für die Verwaltung von Windows-Updates in SCCM bereitgestellt werden.
- WSUS und Windows-Updates für Unternehmen können [gleichzeitig konfiguriert](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb) werden, wenn Sie sowohl die Bandbreitenverwaltung als auch die Steuerung von Windows-Updates für Unternehmen wünschen.
- Funktionsupdates. Lesen Sie die folgenden Hinweise.

## <a name="wsussccm"></a>WSUS/SCCM

- [WSUS/SCCM-](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager) Download
- Ähnlich wie Windows Update für Unternehmen, aber mit der zusätzlichen Option zur Zielgruppenadressierung spezifischer KB-Daten in jedem "Ring" oder der gesamten Bereitstellung. Jedes Update kann einzeln bereitgestellt und getestet werden, anstatt sich nur auf eine Verzögerung zu verlassen.
- Funktionsupdates. Lesen Sie die folgenden Hinweise.

### <a name="feature-updates"></a>Funktionsupdates

Im Gegensatz zu Qualitäts-und nicht verzögerten Updates werden die Windows 10-Feature-Updates (Major OS-Versionen) erst nach dem Microsoft-Test installiert, und es wird eine bestimmte Aktualisierungsfunktionalität mit Microsoft Teams-Räumen überprüft. Auch wenn das Update für den halbjährlichen Kanal freigegeben wird (oder gezielt, wenn Sie Systeme für Tests auf diesen Kanal festgesetzt haben) oder manuell gedrückt wird, lässt ein Microsoft Room Systems-Gerät das Installieren des nicht getesteten Updates nicht zu.

Microsoft Teams-Räume "Out-of-Box" mit dem Ansatz "Hands Off" wird kein Windows-Update installiert oder ein Gerät wird automatisch für ein Windows-Update neu gestartet. Systeme können ein Update herunterladen und warten, bis der nächste Neustart installiert ist. Wenn jemand die Datei nicht manuell neu startet, sollte die Installation beim automatischen nächtlichen Neustart erfolgen. Windows-Updates sollten im Raum transparent sein, die Benutzeroberfläche sollte niemals von Windows-Updates unterbrochen werden.

Verwenden Sie SCCM oder WSUS, wenn Sie sich für die Domäne verbundener Geräte entscheiden. Achten Sie besonders auf Richtlinien oder Aktionen, die dazu führen können, dass das Gerät ein Update installiert oder während der Geschäftszeiten einen Neustart erzwungen. Systeme in Ihrer Bereitstellung sollten während der Verwendung oder Benachrichtigung über Windows-Updates über die Benutzeroberfläche während der Nutzungszeiten nicht neu gestartet werden, überprüfen Sie Ihre Konfiguration, wenn dieses Verhalten eintritt.