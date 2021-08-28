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
ms.openlocfilehash: 28f5d9def3a5217d1d34343e27cbaddb6a3433b9
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58602120"
---
# <a name="manage-windows-updates"></a>Verwalten Windows Updates

Microsoft Teams-Räume wird auf Windows 10 Enterprise IoT oder Windows 10 Enterprise (VL) ausgeführt und empfängt die gleichen Windows-Updates und Betriebssystembuilds wie ein Standarddesktopcomputer.

Windows Updates können verwaltet werden, wie in den folgenden Abschnitten erläutert:

## <a name="hands-off-approach"></a>Praktischer Ansatz 

- Standardmäßig werden Updates direkt aus Windows heruntergeladen und während der Arbeitszeiten installiert.
- Nicht deferierbare Updates werden am ersten Tag der Veröffentlichung automatisch installiert.
- Qualitätsupdates und Treiber laden Tag-1 automatisch herunter und installieren sie.
- Featureupdates. Schauen Sie sich die folgenden Notizen an.

## <a name="windows-updates-for-business-gpo-or-intune"></a>Windows Updates für Unternehmen (GPO oder Intune)  

- [Windows Updates für Unternehmen](/windows/deployment/update/waas-manage-updates-wufb) herunterladen
- Updates werden aus Windows Update oder Ihrer WSUS heruntergeladen, jedoch mit konfigurierten Verzögerungen nach dem ursprünglichen Veröffentlichungsdatum.
- Sie können mehrere OUs oder gefilterte Richtlinien verwenden, um Bereitstellungs-Ringe zu erstellen, in denen Administratoren angeben können, auf welchen Geräten Qualitätsupdates zuerst installiert werden und welche später installiert werden. Zuverlässigkeit und Leistung können auf einer Teilmenge von Systemen getestet werden, bevor Updates für die gesamte Bereitstellung ohne den Aufwand für die Verwaltung Windows Updates in Configuration Manager durchgeführt werden.
- WSUS und Windows Updates for Business [](/windows/deployment/update/waas-integrate-wufb) können gleichzeitig konfiguriert werden, wenn Sie sowohl die Bandbreitenverwaltung als auch das -Steuerelement wünschen, das Windows Updates for Business bietet.
- Featureupdates. Schauen Sie sich die folgenden Notizen an.

## <a name="wsusconfiguration-manager"></a>WSUS/Configuration Manager

- [WSUS/Configuration Manager herunterladen](/windows/deployment/update/waas-manage-updates-configuration-manager)
- Ähnlich wie Windows Update for Business, aber mit der zusätzlichen Option, bestimmte KB-Daten in jedem "Ring" oder in der gesamten Bereitstellung als Ziel zu verwenden. Jedes Update kann einzeln bereitgestellt und getestet werden, anstatt nur von einer Verzögerung zu kommen.
- Featureupdates. Schauen Sie sich die folgenden Notizen an.

### <a name="feature-updates"></a>Featureupdates

Im Gegensatz zu Qualitätsupdates und nicht deferrierbaren Updates werden Windows 10 Featureupdates (Hauptversionen des Betriebssystems) nur installiert, nachdem Microsoft eine bestimmte Aktualisierungsfunktionalität mit einem Anderen überprüft Microsoft Teams-Räume. Selbst wenn das Update im Semi-Annual-Kanal veröffentlicht (oder targeted, wenn Sie Systeme zum Testen auf diesen Kanal festgelegt haben) oder manuell übertragen wird, lässt ein Gerät von Microsoft Room Systems die Installation des nicht getesteten Updates nicht zu.

Microsoft Teams-Räume funktionen "out-of-box" mit einem praktischen Ansatz und installieren kein Windows Update oder Neustart eines Geräts automatisch für ein Windows Update. Systeme laden ein Update herunter und warten auf den nächsten Neustart, um es zu installieren. Sofern kein manueller Neustart durchgeführt wird, erfolgt die Installation nur bei einem automatischen nächtlichen Neustart. Windows Updates sollten im Raum transparent sein, und der normale Vorgang sollte niemals durch updates unterbrochen Windows werden.

Wenn Sie sich für die Teilnahme an Geräten in einer Domäne entscheiden, verwenden Microsoft Endpoint Configuration Manager oder WSUS. Achten Sie besonders auf Richtlinien oder Aktionen, die zu einem Geräteupdate oder einem erzwungenen Neustart während der Geschäftszeiten führen. Die Systeme in Ihrer Bereitstellung sollten während der Verwendung oder Benachrichtigung über Windows Updates über die Benutzeroberfläche während der Nutzungszeiten nicht neu gestartet werden, überprüfen Sie Ihre Konfiguration, wenn dieses Verhalten eintritt.