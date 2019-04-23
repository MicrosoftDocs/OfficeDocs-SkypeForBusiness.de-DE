---
title: Bearbeiten von Microsoft-Teams, Benutzer-Einstellungen in einer Sammeloperation
author: LanaChin
ms.author: v-lanac
ms.reviewer: jastark
manager: serdars
ms.date: 04/19/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Informationen Sie zum Verwalten von Einstellungen für Microsoft-Teams, Benutzer in einer Sammeloperation in der Microsoft-Teams-Verwaltungskonsole.
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.bulkoperations.edit
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4c1dfba0bdaec642b0ea078d7f10ba022c8514da
ms.sourcegitcommit: 3000a661ac420eecd825a8285bdac7b744bd25da
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2019
ms.locfileid: "31988973"
---
# <a name="edit-microsoft-teams-user-settings-in-bulk"></a>Bearbeiten von benutzereinstellungen in einer Sammeloperation Microsoft-Teams

Als Administrator können Sie benutzereinstellungen in der Verwaltungskonsole von Microsoft-Teams, Teams verwalten. Auf der Seite **Benutzer** können Sie Informationen wie Konto- und lizenzierungsdetails anzeigen und Bearbeiten von Richtlinien und andere Einstellungen. Sie können Einstellungen für Benutzer einzeln oder für mehrere Benutzer gleichzeitig bearbeiten.

## <a name="edit-user-settings-in-bulk"></a>Bearbeiten von benutzereinstellungen in einer Sammeloperation

Verwenden Sie das Microsoft-Teams, Administrationscenter, um Einstellungen für mehrere Benutzer gleichzeitig zu bearbeiten. Es wird empfohlen, Einstellungen für 20 Benutzer gleichzeitig bearbeiten. Verwenden von PowerShell, um Einstellungen für eine große Anzahl von Benutzern zu bearbeiten. Weitere Informationen finden Sie unter [Übersicht über die PowerShell Teams](teams-powershell-overview.md).

1. Wählen Sie im linken Navigationsbereich von Microsoft-Teams, Administrationscenter **Benutzer**.
2. Suchen Sie nach dem Benutzer, den, die Sie verwenden möchten, bearbeiten oder Filtern der Ansicht, um die Benutzer anzuzeigen, dass Sie bearbeiten möchten.
3. In der **& #x 2713;** Spalte (Häkchen), wählen Sie Benutzer, indem Sie einen der folgenden Schritte ausführen:
    - Wählen Sie Benutzer zu einem Zeitpunkt aus. Ein **& #x 2713;** wird neben jedem Benutzer angezeigt, die Sie auswählen. Wenn Sie mehr als 20 Benutzer auswählen, Sie werden nicht blockiert werden, aber Bedenken Sie, dass mehr Benutzer Sie auswählen, der Vorgang wird für die Durchführung länger dauern.

        ![Screenshot der Seite Benutzer mit der Auswahl des Benutzers](media/bulk-edit-user-settings-select-users.png)

    - Klicken Sie auf die & #x 2713. (Häkchen) am oberen Rand der Tabelle, wählen Sie alle Benutzer (bis zu maximal 20 Benutzer), und klicken Sie dann im Dialogfeld **Auswahl beschränken** auf **Weiter wählen Sie alle** , um die Auswahl abzuschließen.

        ![Screenshot der Seite Benutzer, die den Grenzwert für die Auswahl anzeigen](media/bulk-edit-user-settings-select-all-limit.png) <br> Ein **& #x 2713;** wird neben den ausgewählten Benutzer angezeigt.

        ![Screenshot der Seite Benutzer, 20 ausgewählten Benutzer anzeigen](media/bulk-edit-user-settings-select-all.png)
4. Klicken Sie auf **Einstellungen bearbeiten**, stellen Sie die gewünschten Änderungen, und klicken Sie dann auf **Speichern**.

    ![Screenshot der Bereich Einstellungen bearbeiten](media/bulk-edit-user-settings-edit-settings.png)
