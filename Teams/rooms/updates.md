---
title: Verwalten von Windows-Updates für Microsoft Teams Rooms
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
description: Administrator erfahren, wie Sie Windows-Updates und Windows-Featureupdates für Microsoft Teams Rooms verwalten.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c7bb233ceedadeaf9c7f14ddf831bd9d324d9211
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117363"
---
# <a name="manage-windows-updates"></a>Verwalten von Windows-Updates

Microsoft Teams Rooms wird unter Windows 10 Enterprise IoT oder Windows 10 Enterprise (VL) ausgeführt und empfängt dieselben Windows-Updates und Betriebssystembuilds wie ein Standarddesktopcomputer.

Windows-Updates können wie in den folgenden Abschnitten beschrieben verwaltet werden:

## <a name="hands-off-approach"></a>Praktischer Ansatz 

- Updates werden standardmäßig automatisch direkt aus Windows Updates heruntergeladen und während der Arbeitszeit installiert.
- Nicht vertagbare Updates werden am ersten Tag der Veröffentlichung automatisch installiert.
- Qualitätsupdates und Treiber laden täglich automatisch herunter und installieren sie.
- Featureupdates. Weitere Informationen finden Sie in den folgenden Notizen.

## <a name="windows-updates-for-business-gpo-or-intune"></a>Windows Updates for Business (GPO oder Intune)  

- [Windows Updates for Business](/windows/deployment/update/waas-manage-updates-wufb) herunterladen
- Updates werden aus Windows Update oder Ihrem WSUS heruntergeladen, jedoch mit konfigurierten Verzögerungen, die über das ursprüngliche Veröffentlichungsdatum liegen.
- Sie können mehrere OUs oder gefilterte Richtlinien verwenden, um Bereitstellungsringe zu erstellen, in denen Administratoren angeben können, welche Geräte zuerst Qualitätsupdates installieren und welche später installiert werden. Zuverlässigkeit und Leistung können auf einer Teilmenge von Systemen getestet werden, bevor Updates für die gesamte Bereitstellung ohne den Aufwand für die Verwaltung von Windows-Updates in Configuration Manager durchgeführt werden.
- WSUS und Windows Updates [](/windows/deployment/update/waas-integrate-wufb) for Business können gleichzeitig konfiguriert werden, wenn Sie sowohl die Bandbreitenverwaltung als auch das Steuerelement wünschen, das Windows Updates for Business bietet.
- Featureupdates. Weitere Informationen finden Sie in den folgenden Notizen.

## <a name="wsusconfiguration-manager"></a>WSUS/Configuration Manager

- [WSUS/Configuration Manager](/windows/deployment/update/waas-manage-updates-configuration-manager) herunterladen
- Ähnlich wie Windows Update for Business, aber mit der zusätzlichen Option, bestimmte KB-Daten innerhalb der einzelnen "Ringe" oder der gesamten Bereitstellung zu verwenden. Jedes Update kann einzeln bereitgestellt und nach Beeinanderung getestet werden, anstatt nur auf eine Verzögerung zu setzen.
- Featureupdates. Weitere Informationen finden Sie in den folgenden Notizen.

### <a name="feature-updates"></a>Featureupdates

Im Gegensatz zu Qualitätsupdates und nicht auffingbaren Updates wird Windows 10 "FeatureUpdates" (hauptbetriebliche Betriebssystemversionen) nur installiert, nachdem Microsoft eine bestimmte Aktualisierungsfunktion mit Microsoft Teams Rooms getestet und überprüft hat. Selbst wenn das Update im Semi-Annual-Kanal freigegeben (oder gezielt, wenn Systeme für tests auf diesen Kanal festgelegt sind) oder manuell pusht, lässt ein Microsoft Room Systems-Gerät die Installation des nicht getesteten Updates nicht zu.

Microsoft Teams Rooms funktioniert "out-of-box" mit einem praktischen Ansatz und installiert weder ein Windows Update noch ein Gerät automatisch für ein Windows Update neu. Die Systeme laden ein Update herunter, und warten Sie auf den nächsten Neustart, um es zu installieren. Sofern sie nicht manuell neu gestartet wird, erfolgt die Installation nur beim automatischen nächtlichen Neustart. Windows-Updates sollten im Raum transparent sein, und der normale Betrieb sollte niemals durch Windows-Updates unterbrochen werden.

Verwenden Sie Microsoft Endpoint Configuration Manager oder WSUS, wenn Sie sich für die Domänenregistrierung von Geräten entscheiden. Achten Sie besonders auf Richtlinien oder Aktionen, die zu einem Geräteupdate oder einem erzwungenen Neustart während der Geschäftszeiten führen. Systeme in Ihrer Bereitstellung sollten während der Verwendung nicht neu gestartet oder während der Nutzungszeiten über die UI über Windows-Updates alarmiert werden. Überprüfen Sie ihre Konfiguration, wenn dieses Verhalten vornimmt.