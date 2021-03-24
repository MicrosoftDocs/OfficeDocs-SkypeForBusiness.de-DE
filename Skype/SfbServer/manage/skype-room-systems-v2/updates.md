---
title: Verwalten von Windows-Updates für Microsoft Teams-Räume
ms.author: v-cichur
author: cichur
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
description: Verwalten von Windows-Updates für Microsoft Teams-Räume
ms.openlocfilehash: cb3007acd31f84cedb8996f440b9634f0551f638
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103201"
---
# <a name="manage-windows-updates"></a>Verwalten von Windows-Updates

Microsoft Teams Rooms wird unter Windows 10 Enterprise IoT oder Windows 10 Enterprise (VL) ausgeführt und empfängt dieselben Windows-Updates und Betriebssystembuilds wie ein Standarddesktop.

Windows-Updates können auf verschiedene Weise verwaltet werden:

## <a name="hands-off-approach"></a>Hands-off-Ansatz 
- Updates können automatisch direkt von Windows Updates heruntergeladen und zu Zeiten installiert werden. Wenn keine Änderungen an der Konfiguration vorgenommen werden, ist dies der Standardzustand.
- Nicht vertagbare Updates installieren den ersten Tag der Veröffentlichung automatisch. 
- Qualitätsupdates und Treiber werden täglich automatisch heruntergeladen und installiert. 
- Featureupdates. Weitere Hinweise finden Sie weiter unten. 

## <a name="windows-updates-for-business-gpo-or-intune"></a>[Windows Updates for Business](/windows/deployment/update/waas-manage-updates-wufb) (GPO oder Intune)   
- Updates werden von WU oder Ihrem WSUS heruntergeladen, aber mit konfigurierten Verzögerungen nach dem ursprünglichen Veröffentlichungsdatum der KB. 
- In Kombination mit mehreren Organisationseinheiten oder gefilterten Richtlinien ermöglicht dies die Erstellung von Bereitstellungsringen, in denen Administratoren angeben können, welche Geräte zuerst Qualitätsupdates installieren und welche später installiert werden. Dies ermöglicht Zuverlässigkeits- und Leistungstests auf einer Teilmenge von Systemen, bevor Updates für die gesamte Bereitstellung ohne den Aufwand für die Verwaltung von Windows-Updates in Microsoft Endpoint Configuration Manager (Z. B. Microsoft Endpoint Configuration Manager) ausgeführt werden.
- WSUS und Windows Updates [](/windows/deployment/update/waas-integrate-wufb) for Business können gleichzeitig konfiguriert werden, wenn Sie die Bandbreitenverwaltung und das Steuerelement wünschen, das Windows Updates for Business bietet.
- Featureupdates. Weitere Hinweise finden Sie weiter unten.

## <a name="wsusconfiguration-manager"></a>[WSUS/Configuration Manager](/windows/deployment/update/waas-manage-updates-configuration-manager)
- Ähnlich wie Windows Update for Business, aber mit der zusätzlichen Option, bestimmte KB in jedem "Ring" oder der gesamten Bereitstellung gezielt zu verwenden. Jedes Update kann einzeln bereitgestellt und nach Beeinanderung getestet werden, anstatt sich nur auf eine Verzögerung zu verlassen. 
- Featureupdates. Weitere Hinweise finden Sie weiter unten.


### <a name="feature-updates"></a>Featureupdates

Im Gegensatz zu Qualitäts- und Nicht-Deferable-Updates werden Windows 10 "FeatureUpdates" (Hauptversionen des Betriebssystems) nur installiert, nachdem Microsoft eine bestimmte Updatesfunktionalität mit Microsoft Teams Rooms getestet und überprüft hat. Auch wenn sie für den Semi-Annual-Kanal freigegeben (oder gezielt, wenn Systeme für Tests auf diesen Kanal festgelegt sind) oder sogar manuell von Ihren eigenen Versuchen oder Konfigurationen pusht, wird die Installation erst dann zulässig, wenn der Block am Ende entfernt wurde.

Microsoft Teams Room "out-of-box" installiert kein Windows Update oder startet ein Gerät aufgrund eines Windows Update automatisch neu. Die Systeme können jedoch ein Update herunterladen und auf den nächsten Neustart warten, um es zu installieren. Wenn sie nicht manuell neu gestartet wird, sollte die Installation beim automatischen nächtlichen Neustart erfolgen. Windows-Updates sollten im Raum transparent sein, die Benutzeroberfläche sollte nie von Windows-Updates unterbrochen werden.

Wenn Sie sich für den Domänen beitritt, verwenden Sie Microsoft Endpoint Configuration Manager oder WSUS, und achten Sie besonders auf Richtlinien oder Aktionen, die dazu führen können, dass das Gerät ein Update installiert oder einen Neustart während der Geschäftszeiten erzwingt. Wenn Systeme während der Verwendung oder Benachrichtigung über windows-Updates über die Benutzeroberfläche neu gestartet werden, sollten Sie ihre Konfiguration überprüfen.