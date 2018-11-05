---
title: Aktualisieren der Outlook-Aktivierungsliste
TOCTitle: Aktualisieren der Outlook-Aktivierungsliste
ms:assetid: 5db120dc-52f9-4dde-acb9-3824ae245086
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ215438(v=OCS.15)
ms:contentKeyID: 49294145
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Aktualisieren der Outlook-Aktivierungsliste

 

_**Letztes Änderungsdatum des Themas:** 2013-01-07_

Sie können sicherstellen, dass das Onlinebesprechungs-Add-In für Microsoft Lync 2013 für Benutzer immer aktiviert ist, indem Sie eine Richtlinie mit diesem Add-In in der Add-In-Verwaltungsliste für Outlook erstellen. Die Richtlinie für die Add-In-Verwaltungsliste ist in den Dateien der administrativen Office-Vorlagen für die Gruppenrichtlinien-Verwaltungskonsole enthalten. Mit dieser Richtlinie wird ein Registrierungsschlüssel unter "HKCU\\Software\\Policies\\Microsoft\\Office\\15.0\\Outlook15\\Resiliency\\AddinList" erstellt. Sie können diesem Schlüssel einen Wert für "ucaddin.dll" hinzufügen und diesen Wert so konfigurieren, dass er immer aktiviert ist und von Benutzern nicht manuell deaktiviert werden kann.

## So fügen Sie der Outlook-Add-In-Liste die Datei "ucaddin.dll" hinzu

  - Fügen Sie dem Registrierungsschlüssel "AddinList", der sich unter "HKCU\\Software\\Policies\\Microsoft\\Office\\15.0\\Outlook15\\Resiliency\\AddinList" befindet, folgenden Wert hinzu:
    
      - Registry Type = REG\_SZ
    
      - Name = ucaddin.dll
    
      - Value = 1 (gibt an, dass das Add-In immer aktiviert ist und vom Benutzer nicht deaktiviert werden kann)

