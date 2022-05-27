---
title: Mehrinstanzenfähige Überwachung
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
ms.openlocfilehash: 3681f50f0e15a7688a944c14e69907ba53dd2817
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676609"
---
# <a name="audit-logging-in-the-teams-rooms-managed-service"></a>Überwachungsprotokollierung im Teams-Räume verwalteten Dienst

Mit der Überwachung in Teams-Räume Managed (TRM)-Dienst können Sie nach Überwachungsdatensätzen für Aktivitäten suchen, die von Benutzern und Administratoren im Portal ausgeführt werden. Dieses Feature ist standardmäßig aktiviert. Nur der Administrator des verwalteten Diensts verfügt über die Berechtigung zum Exportieren und Anzeigen der Protokolle.

> [!NOTE]
> Im TRM-Dienst ausgeführte Aktionen werden nicht Microsoft 365 oder Office 365 Überwachung protokolliert. 

## <a name="exporting-logs"></a>Exportieren von Protokollen

Wenn Sie alle Ergebnisse für eine Überwachungsprotokollsuche exportieren, werden die Rohdaten aus dem einheitlichen Überwachungsprotokoll in eine CSV-Datei (Comma Separated Value) kopiert, die auf Ihren lokalen Computer heruntergeladen wird. 

**So laden Sie Protokolle herunter** 

1. Wechseln Sie zu **Einstellungen > Allgemeinen > Überwachungsprotokolle**.
1. Um den Datumsbereich für interessante Protokolle zu definieren, geben Sie das **Startdatum** und das **Enddatum ein.**

   > [!NOTE]
   > Protokolle sind nur für bis zu 180 Tage verfügbar.

1. Wählen Sie **"Protokolle herunterladen" aus.**

   ![Datumsbereich des Überwachungsprotokolls](../media/multi-tenant-auditing.png)

   Eine Meldung, die am unteren Rand des Fensters angezeigt wird, fordert Sie auf, die CSV-Datei zu öffnen oder zu speichern. 

1. Wählen Sie **"Speichern unter"** >  aus, und speichern Sie die CSV-Datei auf Ihrem lokalen Computer. 

1. Das Herunterladen vieler Suchergebnisse bei der Suche nach allen Aktivitäten oder in einem breiten Datumsbereich dauert eine Weile. Wenn der Download der CSV-Datei abgeschlossen ist, wird unten im Fenster eine Meldung angezeigt.

## <a name="detailed-properties-in-the-audit-log"></a>Detaillierte Eigenschaften im Überwachungsprotokoll

In der folgenden Tabelle werden die Eigenschaften beschrieben, die in der CSV-Datei enthalten sind.

|Eigenschaft|Beschreibung|
| - | - |
|activity.category|<p>Die Kategorie des Objekts, für das die Aktion ausgeführt wurde. Mögliche Werte:</p><p>**Benutzer, Zuweisung, PartnerInvitation, Rolle**</p>|
|activity.objectName|Der Name des Objekts, das geändert wurde.|
|activity.operation|Der Typ des ausgeführten Vorgangs. Mögliche Werte sind: **Erstellen, Aktualisieren, Löschen** |
|activity.resultStatus|<p>Gibt an, ob die Aktion (in der **Eigenschaft "activity.operation** " angegeben) erfolgreich war oder nicht.</p><p>Der Wert ist entweder **erfolgreich** oder **fehlgeschlagen**.</p>|
|activity.tenantId|Die GUID des Mandanten, für den die Aktion ausgeführt wurde|
|Creationtime|Datum und Uhrzeit in UTC (Coordinated Universal Time) im ISO-Format, wenn der Benutzer die Aktivität ausgeführt hat.|
|user.userId|Der Benutzer, der die Aktion ausgeführt hat, die dazu führte, dass der Datensatz protokolliert wurde.|
|user.userTenantId|Die GUID des Mandanten für den Benutzer, der die Aktion ausgeführt hat|


