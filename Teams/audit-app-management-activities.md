---
title: Durchsuchen der Überwachungsprotokolle nach App-Verwaltungsereignissen
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
f1keywords: ''
description: Erfahren Sie, wie Sie Teams-App-Aktivitäten von Benutzern und Administratoren in Ihrer Organisation überwachen.
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: d75773db33f1648e3fff0c7bf06944da133f0604
ms.sourcegitcommit: 4be2a5db44972b35bdde5752eea0d74cf831607a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2022
ms.locfileid: "66642887"
---
# <a name="search-the-audit-logs-for-app-events"></a>Durchsuchen der Überwachungsprotokolle nach App-Ereignissen

Mit der Microsoft Purview-Überwachung (Standard) in Microsoft 365 können Sie nach Überwachungsdatensätzen von Aktivitäten suchen, die von Endbenutzern und Administratoren in den verschiedenen Microsoft 365-Diensten ausgeführt wurden.

Bevor Sie die Überwachung durchsuchen können, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

* [Rufen Sie das Organisationsabonnement und die Benutzerlizenzierung ab](/microsoft-365/compliance/set-up-basic-audit).
* [Aktivieren Sie die Überwachung im Microsoft Purview-Complianceportal](/microsoft-365/compliance/turn-audit-log-search-on-or-off).
* [Weisen Sie Berechtigungen zum Durchsuchen des Überwachungsprotokolls zu](/microsoft-365/compliance/set-up-basic-audit).

## <a name="audit-logs-for-app-events-in-teams"></a>Überwachungsprotokolle für App-Ereignisse in Teams

Die Überwachungsprotokolle für App-Ereignisse in Teams helfen Ihnen, bestimmte Aktionen zu untersuchen. Sie können zwar in den Protokollen nach einer Vielzahl von Aktionen suchen, in der folgenden Tabelle sind jedoch einige der protokollierten Teams-App-Aktionen aufgeführt. Darüber hinaus können Sie Aktivitäten im Zusammenhang mit Connectors, Bots, Registerkarten usw. durchsuchen.

| Teams-App-Aktion                  | Name der Aktivität                | Beschreibung                                              |
|-----------------------------------|------------------------------|:---------------------------------------------------------|
| **App installiert**                 | `AppInstalled`               | Eine App ist installiert.                                     |
| **App-Upgrade**                  | `AppUpgraded`                | Eine App wird auf die neueste Version im Katalog aktualisiert. |
| **App deinstalliert**               | `AppUninstalled`             | Eine App wird deinstalliert.                                   |
| **App veröffentlicht**                 | `AppPublishedToCatalog`      | Dem Katalog wird eine App hinzugefügt.                          |
| **App aktualisiert**                   | `AppUpdatedInCatalog`        | Eine App wird im Katalog aktualisiert.                        |
| **App gelöscht**                   | `AppDeletedFromCatalog`      | Eine App wird aus dem Katalog gelöscht.                      |
| **Alle Organisations-Apps gelöscht** | `DeletedAllOrganizationApps` | Alle Organisations-Apps wurden aus dem Katalog gelöscht.          |

Eine vollständige Liste der überwachten Teams-Aktivitäten finden Sie unter [Teams-Aktivitäten](audit-log-events.md#teams-activities) und [Schichten in Teams-Aktivitäten](audit-log-events.md#shifts-in-teams-activities).

> [!NOTE]
> App-Ereignisse aus privaten Kanälen werden ebenfalls protokolliert, da diese Ereignisse für Teams und Standardkanäle sind.

Verwenden Sie das Audit-Protokoll-Suchtool im Complianceportal, um nach Überwachungsdatensätzen zu suchen. Führen Sie die folgenden Schritte aus, um nach Überwachungsprotokollen von App-Ereignissen zu suchen:

1. Melden Sie sich beim Microsoft Purview-Complianceportal an, und wechseln Sie zu **Lösungen** > **[Überwachung](https://compliance.microsoft.com/auditlogsearch)**.
1. Aktualisieren Sie auf der Überwachungsseite die folgenden Felder gemäß Ihrer Anforderung:

   * **Datums- und Uhrzeitbereich**: Wählen Sie das Start- und Enddatum aus.
   * **Aktivitäten**: Geben Sie Microsoft Teams-Aktivitäten ein. Wählen Sie aus der Liste eine oder mehrere App-Aktivitäten aus. Um die Teams-Aktivitäten schnell zu finden, können Sie im Suchfeld **Aktivitäten** nach dem Wort `Teams activities` suchen.
   * **Datei, Ordner oder Website**: Geben Sie den Dateinamen oder eine URL oder einen Teil davon ein.
   * **Benutzer**: Fügen Sie die Benutzer hinzu, deren Überwachungsprotokoll Sie durchsuchen möchten.

1. Wählen Sie **Suchen** aus.

   :::image type="content" source="media/compliance-search-teams-activities-trimmed.png" alt-text="Suchen Sie nach Teams-Aktivitäten im Microsoft Purview-Complianceportal, um Teams-Ereignisse zu überwachen." lightbox="media/compliance-search-teams-activities.png":::

Nachdem Sie das Überwachungsprotokoll im Complianceportal durchsucht haben, können Sie die Überwachungsdatensätze als CSV-Datei exportieren. Weitere Informationen finden Sie unter [Exportieren, Konfigurieren und Anzeigen von Überwachungsprotokollen](/microsoft-365/compliance/export-view-audit-log-records).

> [!NOTE]
> Wenn eine der oben genannten Aktivitäten von einem Benutzer oder Administrator ausgeführt wird, generiert und speichert Teams einen Überwachungsdatensatz. Bei Audit (Standard) werden die Aufzeichnungen 90 Tage lang aufbewahrt, d. h. Sie können nach Aktivitäten suchen, die innerhalb der letzten drei Monate stattgefunden haben.

## <a name="see-also"></a>Siehe auch

* [Durchsuchen Sie das Überwachungsprotokoll im Complianceportal](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).
* [Übersicht über Microsoft Purview Audit Premium](/microsoft-365/compliance/advanced-audit).
* [Aktivieren oder Deaktivieren der Überwachung](/microsoft-365/compliance/turn-audit-log-search-on-or-off).
