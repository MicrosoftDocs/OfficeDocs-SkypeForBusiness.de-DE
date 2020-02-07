---
title: Verwalten von Windows-Updates für Microsoft Teams-Chatrooms
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: ''
description: Verwalten von Windows-Updates für Microsoft Teams-Chatrooms
ms.openlocfilehash: 2fc96118b70ff7c15e7bde02fdcd048c07581ad3
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41827913"
---
# <a name="manage-windows-updates"></a>Verwalten von Windows-Updates

Microsoft Teams rooms läuft unter Windows 10 Enterprise-oder Windows 10 Enterprise (VL) und erhält dieselben Windows-Updates und Betriebssystem-Builds wie ein Standard-Desktop-Computer.

Windows-Updates können wie in den folgenden Abschnitten beschrieben verwaltet werden:

## <a name="hands-off-approach"></a>Hands-Off-Ansatz 

- Standardmäßig werden Updates direkt von Windows-Updates automatisch heruntergeladen und außerhalb der Arbeitszeiten installiert.
- Nicht verzögerungsfreie Updates installieren den Tag – einer der Versionen automatisch.
- Qualitäts Updates und-Treiber laden Sie den Tag automatisch herunter, und installieren Sie ihn.
- Funktions Updates. Lesen Sie die folgenden Hinweise.

## <a name="windows-updates-for-business-gpo-or-intune"></a>Windows-Updates für Unternehmen (GPO oder InTune)  

- [Windows-Updates für Unternehmen](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) herunterladen
- Updates werden von Windows Update oder WSUS heruntergeladen, jedoch mit konfigurierten Verzögerungen, die über das ursprüngliche Veröffentlichungsdatum hinausgehen.
- Sie können mehrere OUs oder gefilterte Richtlinien verwenden, um die Bereitstellung "Ringe" zu erstellen, in denen Administratoren angeben können, welche Geräte zuerst Qualitäts Updates installieren und welche später installiert werden. Zuverlässigkeit und Leistung können auf einer Teilmenge von Systemen getestet werden, bevor Updates für die gesamte Bereitstellung ohne den Aufwand für die Verwaltung von Windows-Updates in Configuration Manager bereitgestellt werden.
- WSUS und Windows-Updates für Unternehmen können [gleichzeitig konfiguriert](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb) werden, wenn Sie sowohl die Bandbreitenverwaltung als auch die Steuerung von Windows-Updates für Unternehmen wünschen.
- Funktionsupdates. Lesen Sie die folgenden Hinweise.

## <a name="wsusconfiguration-manager"></a>WSUS/Configuration Manager

- [WSUS/Configuration Manager-](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager) Download
- Ähnlich wie Windows Update für Unternehmen, aber mit der zusätzlichen Option zur Zielgruppenadressierung spezifischer KB-Daten in jedem "Ring" oder der gesamten Bereitstellung. Jedes Update kann einzeln bereitgestellt und getestet werden, anstatt sich nur auf eine Verzögerung zu verlassen.
- Funktionsupdates. Lesen Sie die folgenden Hinweise.

### <a name="feature-updates"></a>Funktionsupdates

Im Gegensatz zu Qualitäts-und nicht verzögerten Updates werden die Windows 10-Feature-Updates (Major OS-Versionen) erst nach dem Microsoft-Test installiert, und es wird eine bestimmte Aktualisierungsfunktionalität mit Microsoft Teams-Räumen überprüft. Auch wenn das Update für den halbjährlichen Kanal freigegeben wird (oder gezielt, wenn Sie Systeme für Tests auf diesen Kanal festgesetzt haben) oder manuell gedrückt wird, lässt ein Microsoft Room Systems-Gerät das Installieren des nicht getesteten Updates nicht zu.

Microsoft Teams rooms Funktionen "Out-of-Box" mit einem Hands-Off-Ansatz, und Sie können kein Windows Update installieren oder ein Gerät automatisch für ein Windows-Update neu starten. Systeme laden Sie ein Update herunter, und warten Sie, bis der nächste Neustart installiert ist. Die Installation erfolgt nur beim automatischen nächtlichen Neustart, es sei denn, dass Sie manuell neu gestartet wird. Windows-Updates sollten im Raum transparent sein, und der normale Betrieb sollte niemals von Windows-Updates unterbrochen werden.

Wenn Sie sich für die Verwendung von Domänen-Join-Geräten entscheiden, verwenden Sie den Microsoft Endpoint Configuration Manager oder WSUS. Achten Sie besonders auf Richtlinien oder Aktionen, die zu einem Geräteupdate oder einem erzwungenen Neustart während der Geschäftszeiten führen. Systeme in Ihrer Bereitstellung sollten während der Verwendung oder Benachrichtigung über Windows-Updates über die Benutzeroberfläche während der Nutzungszeiten nicht neu gestartet werden, überprüfen Sie Ihre Konfiguration, wenn dieses Verhalten eintritt.