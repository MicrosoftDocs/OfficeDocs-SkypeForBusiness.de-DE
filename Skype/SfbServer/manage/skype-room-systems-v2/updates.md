---
title: Verwalten von Windows-Updates für Skype Raum Systemen v2
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 10/10/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ''
description: Verwalten von Windows-Updates für Skype Raum Systemen v2
ms.openlocfilehash: 4b1b0bc27be3f8277fde0c641efe5359ca002d65
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2018
ms.locfileid: "26532140"
---
# <a name="manage-windows-updates"></a>Verwalten von Windows-Updates

Skype Raum System v2 (SRS v2) auf Windows 10 Enterprise IoT oder Windows 10 Enterprise (VL) ausgeführt wird und die gleichen Windows-Updates und OS Builds als standard Desktop empfängt.

Windows-Updates können in unterschiedliche Weise verwaltet werden:

## <a name="hands-off-approach"></a>Automatische Ansatz 
- Updates können direkt von Windows-Updates automatisch heruntergeladen und installiert außerhalb der Betriebszeiten ausgeführt werden. Ist keine Konfiguration dieser Änderung wird die Standardwerte zurückgesetzt.
- Tag-Eins der Version werden automatisch nicht verzögert werden Updates installiert werden. 
- Qualität Updates und Treiber werden automatisch heruntergeladen und installiert ersten Tag. 
- Feature-Updates. Finden Sie zusätzliche Hinweise unten. 

## <a name="windows-updates-for-businesshttpsdocsmicrosoftcomwindowsdeploymentupdatewaas-manage-updates-wufb-gpo-or-intune"></a>[Windows-Updates für Unternehmen](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) (Gruppenrichtlinienobjekt oder Intune)   
- Updates werden von WU oder Ihre WSUS jedoch mit konfigurierten Verzögerungen über die KB ursprüngliche Version Datum heruntergeladen. 
- In Kombination mit mehreren Organisationseinheit oder gefiltert Richtlinien, dies ermöglicht die Erstellung von Bereitstellung "Klingeltöne", wobei Administratoren festlegen können, welche Geräte Qualität Updates installieren und die Schriftarten später installieren werden. Dies ermöglicht Zuverlässigkeit und Leistung auf eine Teilmenge von Systemen vor der Einführung der Updates über die gesamte Bereitstellung der Mehraufwand von Verwalten von Windows-Updates in SCCM beispielsweise testen.
- WSUS und Windows-Updates für Business kann sein, dass [gleichzeitig konfiguriert](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb) , falls bandbreitenverwaltung und das Windows-Updates für Business-Steuerelement gewünscht enthält.
- Feature-Updates. Finden Sie zusätzliche Hinweise unten.

## <a name="wsussccmhttpsdocsmicrosoftcomwindowsdeploymentupdatewaas-manage-updates-configuration-manager"></a>[WSUS/SCCM](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)
- Ähnlich wie bei Windows Update für Unternehmen, wobei jedoch die Option weitere der Zielgruppenadressierung bestimmte KB innerhalb jedes "Anrufen" oder die gesamte Bereitstellung. Jedes Update kann einzeln bereitgestellt und getestet werden, anstatt sich auf nur eine Verzögerung zu verlassen. 
- Feature-Updates. Finden Sie zusätzliche Hinweise unten.


### <a name="feature-updates"></a>Feature-updates

Im Gegensatz zu Qualität und nicht-Deferable Updates Windows 10 "Feature Updates" (Hauptversionen OS) werden nur nach Microsoft getestet und mit SRS v2-Funktion einen bestimmten Updates validiert installiert. Auch wenn es für die Semikolons jährlichen Channel (oder gezielte, wenn Sie Systeme, die auf diesen Kanal zu Testzwecken festgelegt haben) freigegeben oder auch manuell vom Versuche oder Konfigurationen abgelegt ist, können sie nicht die Installation, bis der Block auf unserer Seite entfernt wird.

Ein SRS v2 "Out-of-Box", die Hände deaktiviert Ansatz mit einem Windows-Update installieren oder ein Gerät aufgrund eines Windows-Updates automatisch neu starten nicht. Systeme können jedoch ein Update herunterladen und warten Sie für den nächsten Neustart, ihn zu installieren. Wenn jemand sie manuell neu gestartet wird, sollte die Installation bei der automatischen nächtlicher Neustart erfolgen. Windows-Updates sollten transparente im Raum, die Benutzeroberfläche sollte niemals von Windows-Updates unterbrochen werden.

Wenn Sie die Option zum Beitreten zu einer Domäne, SCCM oder WSUS und Bitte achten Sie besonders auf Richtlinien oder Aktionen, die in das Gerät ein Update installieren, oder erzwingen einen Neustart während der Geschäftszeit auftreten können. Wenn Sie Systeme in Ihrer Bereitstellung, bei der Verwendung Neustarten oder Warnungen zu Windows-Updates über die Benutzeroberfläche verfügen, werden Sie in Ihrer Konfiguration suchen möchten.