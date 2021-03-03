---
title: Erstellen einer benutzerdefinierten Teamvorlage in Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: aaglick
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Erfahren Sie, wie Sie eine benutzerdefinierte Teamvorlage in Microsoft Teams erstellen.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f22b2c53ab6f3c3c90e1720313c135c2106b1a49
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196529"
---
# <a name="create-a-custom-team-template-in-microsoft-teams"></a>Erstellen einer benutzerdefinierten Teamvorlage in Microsoft Teams

**Benutzerdefinierte Vorlagen werden für Edu-Kunden noch nicht unterstützt.**

Eine benutzerdefinierte Teamvorlage ist eine vordefinierte Teamstruktur mit einer Reihe von Kanälen, Registerkarten und Apps. Sie können eine Vorlage entwickeln, die Ihnen hilft, schnell den richtigen Platz zur Zusammenarbeit zu schaffen. Ihre benutzerdefinierte Teamvorlage verwendet Ihre bevorzugten Einstellungen.  

Erste Schritte:

1. Melden Sie sich beim Teams Admin Center an.

2. Erweitern Sie im linken Navigationsbereich die  >  **Teams-Teamvorlagen.**

3. Klicken Sie auf **Hinzufügen**.

![Abbildung des Dialogfelds "Teamvorlagen" mit hervorgehobener Hervorhebung "Hinzufügen".](media/team-templates-new.png)

4. Wählen Sie **im Abschnitt "Teamvorlagen"** die Option **"Neue Vorlage erstellen" aus.**

5. Füllen Sie im **Abschnitt "Vorlageneinstellungen"** die folgenden Felder aus, und klicken Sie dann auf **"Weiter":**
    - Vorlagenname
    - Kurze und lange Beschreibungen von Vorlagen
    - Sichtbarkeit des Locale  

![Abbildung des Dialogfelds "Einstellungen für Teamvorlagen".](media/template-add-a-name.png)

6. Fügen Sie **im Abschnitt "Kanäle, Registerkarten und Apps"** alle Kanäle und Apps hinzu, die Ihr Team benötigt.

    1. Klicken Sie **im Abschnitt "Kanäle"** auf **"Hinzufügen".**
    2. Geben Sie **dem Kanal** im Dialogfeld "Hinzufügen" einen Namen.
    3. Fügen Sie eine Beschreibung hinzu.
    4. Entscheiden Sie, ob der Kanal standardmäßig angezeigt werden soll.
    5. Suchen Sie nach einem App-Namen, den Sie dem Kanal hinzufügen möchten.
    6. Klicken Sie **auf "Übernehmen",** wenn Sie fertig sind.

![Abbildung des Bildschirms für Teamvorlagenkanäle, Registerkarten und Apps.](media/template-channels-tabs-apps.png)

8. Klicken Sie **auf "Absenden",** wenn der Abschluss abgeschlossen ist.

Ihre neue Vorlage wird in der Liste der **Teamvorlagen** angezeigt. Die Vorlage kann zum Erstellen eines Teams in Teams verwendet werden.

> [!Note]
> Es kann bis zu 24 Stunden dauern, bis Teambenutzer eine benutzerdefinierte Vorlage im Katalog sehen.

## <a name="known-issues"></a>Bekannte Probleme 

**Problem:** Wenn Sie ein Team aus einer benutzerdefinierten Vorlage erstellt haben, die zusätzliche benutzerdefinierte Registerkarten enthält, werden möglicherweise leere Registerkarten statt Ihrer benutzerdefinierten Registerkarten-Apps angezeigt. Ihre Standardregisterkarten (z. B. **Beiträge,** Dateien und **Wiki)** werden wie erwartet angezeigt. 

**Lösung:** Wenn Sie ein Team aus einer benutzerdefinierten Vorlage erstellt haben, die zusätzliche benutzerdefinierte Registerkarten enthält, werden möglicherweise leere Registerkarten statt Ihrer benutzerdefinierten Registerkarten-Apps angezeigt. Ihre Standardregisterkarten (z. B. Beiträge, Dateien und Wiki) werden wie erwartet angezeigt.

Um dieses Problem zu beheben, entfernen Sie die benutzerdefinierte Registerkarte, und fügen Sie eine neue Registerkarte mit derselben App hinzu. Wenn Sie nicht über die Berechtigung zum Entfernen der benutzerdefinierten Registerkarte und zum Hinzufügen einer neuen Registerkarte verfügen, wenden Sie sich an den Teambesitzer, und bitten Sie ihn, dies zu tun.

Wir arbeiten derzeit an einer Lösung für zukünftige Teams, die aus benutzerdefinierten Vorlagen erstellt wurden.

## <a name="related-topics"></a>Verwandte Themen

- [Erste Schritte mit Teamvorlagen im Admin Center](get-started-with-teams-templates-in-the-admin-console.md)
- [Erstellen einer Vorlage aus einem vorhandenen Team](create-template-from-existing-team.md)
- [Erstellen einer Teamvorlage aus einer vorhandenen Teamvorlage](create-template-from-existing-template.md)
