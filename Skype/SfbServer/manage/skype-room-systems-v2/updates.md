---
title: Verwalten von Windows-Updates für Microsoft Teams-Chatrooms
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
ms.date: 10/10/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: M365-voice
ms.assetid: ''
description: Verwalten von Windows-Updates für Microsoft Teams-Chatrooms
ms.openlocfilehash: 9b195b4158f234146c362b65642d53960c9f5c24
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817196"
---
# <a name="manage-windows-updates"></a>Verwalten von Windows-Updates

Microsoft Teams rooms läuft unter Windows 10 Enterprise-oder Windows 10 Enterprise (VL) und empfängt dieselben Windows-Updates und Betriebssystem-Builds wie ein Standard-Desktop.

Windows-Updates können auf verschiedene Arten verwaltet werden:

## <a name="hands-off-approach"></a>Hands-Off-Ansatz 
- Updates können direkt von Windows-Updates automatisch heruntergeladen und außerhalb der Arbeitszeiten installiert werden. Wenn keine Änderung an der Konfiguration vorgenommen wird, handelt es sich um den Standardzustand.
- Nicht verzögerte Updates installieren Day-One der Veröffentlichung automatisch. 
- Qualitäts Updates und Treiber werden automatisch heruntergeladen und installiert. 
- Funktions Updates. Weitere Informationen finden Sie weiter unten. 

## <a name="windows-updates-for-businesshttpsdocsmicrosoftcomwindowsdeploymentupdatewaas-manage-updates-wufb-gpo-or-intune"></a>[Windows-Updates für Unternehmen](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) (GPO oder InTune)   
- Updates werden von Wu oder Ihrem WSUS heruntergeladen, aber mit konfigurierten Verzögerungen nach dem ursprünglichen Veröffentlichungsdatum der KB. 
- In Kombination mit mehreren ou-oder gefilterten Richtlinien kann dadurch die Bereitstellung von "Ringen" erstellt werden, in denen Administratoren angeben können, welche Geräte zuerst Qualitäts Updates installieren und welche später installiert werden. Auf diese Weise können Zuverlässigkeits-und Leistungstests für eine Teilmenge von Systemen durchgeführt werden, bevor Updates für die gesamte Bereitstellung ohne den Aufwand für die Verwaltung von Windows-Updates im Microsoft Endpoint Configuration Manager bereitgestellt werden.
- WSUS und Windows-Updates für Unternehmen können [gleichzeitig konfiguriert](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb) werden, wenn Sie sowohl die Bandbreitenverwaltung als auch die Steuerung von Windows-Updates für Unternehmen wünschen.
- Funktionsupdates. Weitere Informationen finden Sie weiter unten.

## <a name="wsusconfiguration-managerhttpsdocsmicrosoftcomwindowsdeploymentupdatewaas-manage-updates-configuration-manager"></a>[WSUS/Configuration Manager](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)
- Ähnlich wie Windows Update für Unternehmen, aber mit der zusätzlichen Option zur Zielgruppenadressierung spezifischer KB-Daten in jedem "Ring" oder der gesamten Bereitstellung. Jedes Update kann einzeln bereitgestellt und getestet werden, anstatt sich nur auf eine Verzögerung zu verlassen. 
- Funktionsupdates. Weitere Informationen finden Sie weiter unten.


### <a name="feature-updates"></a>Funktionsupdates

Im Gegensatz zu Qualitäts-und nicht verzögerten Updates werden die Windows 10-Feature-Updates (Major OS-Versionen) erst nach dem Microsoft-Test installiert, und es werden eine bestimmte Aktualisierungsfunktionalität mit Microsoft Teams-Räumen überprüft. Auch wenn Sie für den halbjährlichen Kanal freigegeben wird (oder gezielt, wenn Sie Systeme für Tests auf diesen Kanal festgesetzt haben) oder sogar manuell durch ihre eigenen Versuche oder Konfigurationen gedrückt werden, wird die Installation erst nach dem Entfernen des Blocks an unserem Ende zugelassen.

Der Microsoft Teams-Raum "Out-of-Box" mit dem Ansatz "Hands Off" wird kein Windows-Update installiert oder ein Gerät wird aufgrund eines Windows-Updates automatisch neu gestartet. Systeme können jedoch ein Update herunterladen und auf den nächsten Neustart warten, um es zu installieren. Wenn jemand die Datei nicht manuell neu startet, sollte die Installation beim automatischen nächtlichen Neustart erfolgen. Windows-Updates sollten im Raum transparent sein, die Benutzeroberfläche sollte niemals von Windows-Updates unterbrochen werden.

Wenn Sie sich für den Domänenbeitritt entscheiden, verwenden Sie den Microsoft Endpoint Configuration Manager oder WSUS, und achten Sie besonders auf Richtlinien oder Aktionen, die dazu führen können, dass das Gerät ein Update installiert oder während der Geschäftszeiten einen Neustart erzwungen. Wenn während der Verwendung von Systemen in der Bereitstellung ein Neustart durchführen oder eine Warnung zu Windows-Updates über die Benutzeroberfläche vorhanden ist, sollten Sie sich mit Ihrer Konfiguration vertraut machen.
