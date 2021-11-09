---
title: Verwalten Windows Updates für Microsoft Teams-Räume
ms.author: v-mahoffman
author: HowlinWolf-92
ms.reviewer: sohailta
manager: serdars
ms.date: 10/10/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: M365-voice
ms.assetid: ''
description: Verwalten Windows Updates für Microsoft Teams-Räume
ms.openlocfilehash: 1a5e665546c00525939585f4655fcdf404e5786f
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60859992"
---
# <a name="manage-windows-updates"></a>Verwalten Windows Updates

Microsoft Teams-Räume wird auf Windows 10 Enterprise IoT oder Windows 10 Enterprise (VL) ausgeführt und erhält die gleichen Windows Updates und Betriebssystembuilds wie ein Standarddesktop.

Windows Updates können auf verschiedene Arten verwaltet werden:

## <a name="hands-off-approach"></a>Praktische Vorgehensweise 
- Updates können direkt aus Windows Updates automatisch heruntergeladen und außerhalb der Geschäftszeiten installiert werden. Wenn keine Änderung an der Konfiguration vorgenommen wird, ist dies der Standardstatus.
- Nicht zurückstellbare Updates installieren automatisch den ersten Tag der Veröffentlichung. 
- Qualitätsupdates und Treiber laden den ersten Tag automatisch herunter und installieren sie. 
- Featureupdates. Weitere Hinweise finden Sie weiter unten. 

## <a name="windows-updates-for-business-gpo-or-intune"></a>[Windows Updates für Unternehmen](/windows/deployment/update/waas-manage-updates-wufb) (GPO oder Intune)   
- Updates werden von WU oder Ihrem WSUS heruntergeladen, jedoch mit konfigurierten Verzögerungen nach dem ursprünglichen Veröffentlichungsdatum des KB. 
- In Kombination mit mehreren OU-Richtlinien oder gefilterten Richtlinien ermöglicht dies die Erstellung von Bereitstellungsringen, bei denen Administratoren angeben können, welche Geräte Zuerst Qualitätsupdates installieren und welche später installiert werden. Dies ermöglicht Zuverlässigkeits- und Leistungstests für eine Teilmenge von Systemen, bevor Updates für die gesamte Bereitstellung bereitgestellt werden, ohne dass beispielsweise Windows Updates in Microsoft Endpoint Configuration Manager verwaltet werden müssen.
- WSUS- und Windows Updates for Business können [gleichzeitig konfiguriert](/windows/deployment/update/waas-integrate-wufb) werden, wenn Sie sowohl die Bandbreitenverwaltung als auch das Steuerelement wünschen, das Windows Updates for Business bereitstellt.
- Featureupdates. Weitere Hinweise finden Sie weiter unten.

## <a name="wsusconfiguration-manager"></a>[WSUS/Configuration Manager](/windows/deployment/update/waas-manage-updates-configuration-manager)
- Ähnlich wie Windows Update for Business, jedoch mit der zusätzlichen Option, bestimmte KB-Daten innerhalb jedes "Rings" oder der gesamten Bereitstellung auszurichten. Jedes Update kann einzeln bereitgestellt und getestet werden, anstatt sich nur auf eine Verzögerung zu verlassen. 
- Featureupdates. Weitere Hinweise finden Sie weiter unten.


### <a name="feature-updates"></a>Featureupdates

Im Gegensatz zu Qualitätsupdates und nicht zurückstellbaren Updates werden Windows 10 "Featureupdates" (hauptversionen des Betriebssystems) erst installiert, nachdem Microsoft eine bestimmte Updatefunktionalität mit Microsoft Teams-Räume getestet und überprüft hat. Selbst wenn es für den Semi-Annual Kanal freigegeben wird (oder gezielt, wenn Sie Systeme zu Testzwecken auf diesen Kanal festgelegt haben) oder sogar manuell von Ihren eigenen Versuchen oder Konfigurationen übertragen wird, wird die Installation erst zugelassen, wenn der Block auf unserem Ende entfernt wird.

Microsoft Teams "Out-of-Box"-Raum wird bei Verwendung des Hands-off-Ansatzes aufgrund eines Windows Updates kein Windows Update installieren oder ein Gerät automatisch neu starten. Systeme können jedoch ein Update herunterladen und auf den nächsten Neustart warten, um es zu installieren. Wenn sie nicht manuell neu gestartet wird, sollte die Installation beim automatischen Neustart in der Nacht erfolgen. Windows Updates sollten im Raum transparent sein, die Benutzeroberfläche sollte niemals durch Windows Updates unterbrochen werden.

Wenn Sie sich für den Domänenbeitritt entscheiden, verwenden Sie Microsoft Endpoint Configuration Manager oder WSUS, und achten Sie besonders auf Richtlinien oder Aktionen, die dazu führen können, dass das Gerät während der Geschäftszeiten ein Update installiert oder einen Neustart erzwingt. Wenn Während der Verwendung Systeme in Ihrer Bereitstellung neu gestartet werden oder sie über Windows Updates über die Benutzeroberfläche informiert werden, sollten Sie sich ihre Konfiguration ansehen.