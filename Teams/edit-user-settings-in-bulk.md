---
title: Bearbeiten von Microsoft Teams-Benutzereinstellungen in Sammeleinheiten
author: LanaChin
ms.author: v-lanac
ms.reviewer: jastark
manager: serdars
ms.date: 04/19/2019
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Hier erfahren Sie, wie Sie Microsoft Teams-Benutzereinstellungen im Microsoft Teams Admin Center massenhaft verwalten.
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6177a463bee481812323b2334461f20e7021af84
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41832645"
---
# <a name="edit-microsoft-teams-user-settings-in-bulk"></a>Bearbeiten von Microsoft Teams-Benutzereinstellungen in Massen

Als Administrator verwalten Sie die Benutzereinstellungen für Teams im Microsoft Teams Admin Center. Auf der Seite " **Benutzer** " können Sie Informationen wie Konto-und lizenzierungsdetails anzeigen sowie Richtlinien und andere Einstellungen bearbeiten. Sie können die Einstellungen für Benutzer einzeln oder für mehrere Benutzer gleichzeitig bearbeiten.

## <a name="edit-user-settings-in-bulk"></a>Bearbeiten von Benutzereinstellungen in Massen

Verwenden Sie das Microsoft Teams Admin Center, um die Einstellungen für mehrere Benutzer gleichzeitig zu bearbeiten. Wir empfehlen, Einstellungen für 20 Benutzer gleichzeitig zu bearbeiten. Verwenden Sie PowerShell, um die Einstellungen für eine große Anzahl von Benutzern zu bearbeiten. Weitere Informationen finden Sie unter [Übersicht über Teams PowerShell](teams-powershell-overview.md).

1. Wählen Sie in der linken Navigationsleiste des Microsoft Teams Admin Center die Option **Benutzer**aus.
2. Suchen Sie nach den Benutzern, die Sie bearbeiten oder filtern möchten, um die Benutzer anzuzeigen, die Sie bearbeiten möchten.
3. Wählen Sie in der Spalte **&#x2713;** (Häkchen) die Option Benutzer aus, indem Sie eine der folgenden Aktionen ausführen:
    - Wählen Sie Benutzer einzeln aus. Neben jedem ausgewählten Benutzer wird ein **&#x2713;** angezeigt. Wenn Sie mehr als 20 Benutzer auswählen, werden Sie nicht blockiert, aber denken Sie daran, dass je mehr Benutzer Sie auswählen, desto länger dauert die Ausführung des Vorgangs.

        ![Screenshot der Seite "Benutzer" mit Benutzerauswahl](media/bulk-edit-user-settings-select-users.png)

    - Klicken Sie oben in der Tabelle auf das #a0 (Häkchen), um alle Benutzer (bis maximal 20 Benutzer) auszuwählen, und klicken Sie dann im Dialogfeld **Auswahlgrenze** auf **Alle auswählen** , um die Auswahl abzuschließen.

        ![Screenshot der Seite "Benutzer" mit der Auswahlgrenze](media/bulk-edit-user-settings-select-all-limit.png) <br> Neben den ausgewählten Benutzern wird ein **&#x2713;** angezeigt.

        ![Screenshot der Seite "Benutzer" mit 20 ausgewählten Benutzern](media/bulk-edit-user-settings-select-all.png)
4. Klicken Sie auf **Einstellungen bearbeiten**, nehmen Sie die gewünschten Änderungen vor, und klicken Sie dann auf **Speichern**.

    ![Screenshot des Bereichs "Einstellungen bearbeiten"](media/bulk-edit-user-settings-edit-settings.png)
