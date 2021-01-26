---
title: Verwalten von Windows Updates für Microsoft Teams Rooms
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
description: Verwalten von Windows Updates für Microsoft Teams Rooms
ms.openlocfilehash: 4f7fd6d49c78b229a3909e88689423dc95ce2c48
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832875"
---
# <a name="manage-windows-updates"></a>Verwalten von Windows Updates

Microsoft Teams Rooms wird unter Windows 10 Enterprise IoT oder Windows 10 Enterprise (VL) ausgeführt und erhält die gleichen Windows-Updates und Betriebssystembuilds wie ein Standarddesktop.

Windows Updates können auf verschiedene Weise verwaltet werden:

## <a name="hands-off-approach"></a>Praktischer Ansatz 
- Updates können direkt von Den Windows Updates automatisch heruntergeladen und während der Nebenzeiten installiert werden. Wenn keine Änderungen an der Konfiguration vorgenommen werden, ist dies der Standardzustand.
- Nicht verfebbare Updates werden am ersten Tag der Veröffentlichung automatisch installiert. 
- Qualitätsupdates und Treiber laden den ersten Tag automatisch herunter und installieren sie. 
- Featureupdates. Weitere Hinweise finden Sie weiter unten. 

## <a name="windows-updates-for-business-gpo-or-intune"></a>[Windows Updates for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) (GPO oder Intune)   
- Updates werden von WU oder WSUS heruntergeladen, jedoch mit konfigurierten Verzögerungen, die über das ursprüngliche Veröffentlichungsdatum der KB liegen. 
- In Kombination mit mehreren Organisationseinheiten oder gefilterten Richtlinien ermöglicht dies die Erstellung von Bereitstellungsringen, in denen Administratoren angeben können, auf welchen Geräten zuerst Qualitätsupdates installiert werden und welche später installiert werden. Dies ermöglicht Zuverlässigkeits- und Leistungstests auf einer Teilmenge von Systemen, bevor Updates für die gesamte Bereitstellung ohne den Aufwand für die Verwaltung von Windows Updates in Microsoft Endpoint Configuration Manager (Z. B. ) ausgeführt werden.
- WSUS und Windows Updates [](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb) for Business können gleichzeitig konfiguriert werden, wenn Sie sowohl bandbreitenverwaltung als auch das Steuerelement wünschen, das Windows Updates for Business bietet.
- Featureupdates. Weitere Hinweise finden Sie weiter unten.

## <a name="wsusconfiguration-manager"></a>[WSUS/Configuration Manager](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)
- Ähnlich wie Windows Update for Business, aber mit der zusätzlichen Option, bestimmte KBs innerhalb jedes "Rings" oder der gesamten Bereitstellung zu verwenden. Jedes Update kann einzeln bereitgestellt und getestet werden, anstatt nur auf eine Verzögerung zu vertrauen. 
- Featureupdates. Weitere Hinweise finden Sie weiter unten.


### <a name="feature-updates"></a>Featureupdates

Im Gegensatz zu Qualitäts- und nicht verhebbaren Updates werden "Featureupdates" (Hauptversionen des Betriebssystems) von Windows 10 erst installiert, nachdem Microsoft eine bestimmte Updatefunktionalität mit Microsoft Teams Rooms getestet und überprüft hat. Selbst wenn es für den Semi-Annual Channel freigegeben (oder gezielt, wenn Sie Systeme zu Testzwecken auf diesen Kanal festgelegt haben) oder sogar manuell von Ihren eigenen Versuchen oder Konfigurationen per Push übertragen werden, lässt dies die Installation erst zu, wenn der Block am Ende entfernt wird.

"Out-of-Box" von Microsoft Teams Room installiert windows Update und startet ein Gerät aufgrund von Windows Update nicht automatisch. Systeme können jedoch ein Update herunterladen und auf den nächsten Neustart warten, um es zu installieren. Wenn sie nicht manuell neu gestartet wird, sollte die Installation beim automatischen nächtlichen Neustart erfolgen. Windows Updates sollten im Raum transparent sein, die Benutzeroberfläche sollte nie durch Windows Updates unterbrochen werden.

Wenn Sie sich für den Domänen beitritt, verwenden Sie Microsoft Endpoint Configuration Manager oder WSUS, und achten Sie besonders auf Richtlinien oder Aktionen, die dazu führen können, dass das Gerät ein Update installiert oder einen Neustart während der Geschäftszeiten erzwingt. Wenn Sie systeme während der Verwendung oder bei Benachrichtigungen über Windows Updates über die Benutzeroberfläche neu starten, sollten Sie ihre Konfiguration überprüfen.
