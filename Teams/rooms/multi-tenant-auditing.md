---
title: Microsoft Teams-Räume Portal
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.reviewer: dstrome
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Überwachungsprotokollierung für TRM.
f1keywords: ''
ms.openlocfilehash: e5e5cd25385f6e8a71484c57aa9c44da5d4c9cd8
ms.sourcegitcommit: c8951fe3504c1776d7aec14b79605aaf5d317e7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/08/2021
ms.locfileid: "61331242"
---
# <a name="audit-logging-in-the-teams-rooms-managed-service"></a>Überwachungsprotokollierung im verwalteten Teams-Räume Dienst

Mit überwachung in Teams-Räume verwalteten Dienst (TRM) können Sie nach Überwachungsdatensätzen für Aktivitäten suchen, die von Benutzern und Administratoren im Portal ausgeführt wurden. Dieses Feature ist standardmäßig aktiviert. Nur der Administrator für verwaltete Dienste verfügt über die Berechtigung zum Exportieren und Anzeigen der Protokolle.

> [!NOTE]
> Aktionen, die im TRM-Dienst ausgeführt werden, werden nicht Microsoft 365 oder Office 365 protokolliert. 

## <a name="exporting-logs"></a>Exportieren von Protokollen

Wenn Sie alle Ergebnisse für eine Überwachungsprotokollsuche exportieren, werden die Rohdaten aus dem vereinheitlichten Überwachungsprotokoll in eine CSV-Datei (Durch Kommas getrennte Werte) kopiert, die auf den lokalen Computer heruntergeladen wird. 

**So laden Sie Protokolle herunter** 

1. Wechseln Sie **zu Einstellungen > allgemein > Überwachungsprotokolle**.
1. Geben Sie das Startdatum und das  Enddatum ein, um den Datumsbereich für interessierende Protokolle **zu definieren.**

   > [!NOTE]
   > Protokolle sind nur für bis zu 180 Tage verfügbar.

1. Wählen Sie **Protokolle herunterladen aus.**

   ![Datumsbereich des Überwachungsprotokolls](../media/multi-tenant-auditing.png)

   Eine am unteren Rand des Fensters angezeigte Meldung fordert Sie auf, die CSV-Datei zu öffnen oder zu speichern. 

1. Wählen **Sie Speichern**  >  **unter** aus, und speichern Sie die CSV-Datei auf dem lokalen Computer. 

1. Es dauert eine Weile, viele Suchergebnisse herunterzuladen, wenn Sie nach allen Aktivitäten oder einem breiten Datumsbereich suchen. Wenn der Download der CSV-Datei abgeschlossen ist, wird unten im Fenster eine Meldung angezeigt.

## <a name="detailed-properties-in-the-audit-log"></a>Detaillierte Eigenschaften im Überwachungsprotokoll

In der folgenden Tabelle werden die Eigenschaften beschrieben, die in der CSV-Datei enthalten sind.

|Eigenschaft|Beschreibung|
| - | - |
|activity.category|<p>Die Kategorie des Objekts, für das die Aktion ausgeführt wurde. Mögliche Werte:</p><p>**Benutzer, Zuweisung, PartnerInvitation, Rolle**</p>|
|activity.objectName|Der Name des Objekts, das geändert wurde.|
|activity.operation|Der Typ des ausgeführten Vorgangs. Mögliche Werte sind: **Erstellen, Aktualisieren, Löschen** |
|activity.resultStatus|<p>Gibt an, ob die (in der Eigenschaft **"activity.operation"** angegebene) Aktion erfolgreich war.</p><p>Der Wert ist entweder **Erfolgreich** oder **Fehlgeschlagen.**</p>|
|activity.tenantId|Die GUID des Mandanten, für den die Aktion ausgeführt wurde|
|creationTime|Das Datum und die Uhrzeit in koordinierter Weltzeit (Coordinated Universal Time, UTC) im ISO-Format, als der Benutzer die Aktivität ausgeführt hat.|
|user.userId|Der Benutzer, der die Aktion ausgeführt hat, die zu dem Eintrag im Protokoll geführt hat.|
|user.userTenantId|Die GUID des Mandanten für den Benutzer, der die Aktion ausgeführt hat.|


