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
description: Erfahren Sie, wie Sie eine benutzerdefinierte Teamvorlage in einer Microsoft Teams.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e8733dde289cfc595d8db7b56652cb28dcc646b8
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58589769"
---
# <a name="create-a-custom-team-template-in-microsoft-teams"></a>Erstellen einer benutzerdefinierten Teamvorlage in Microsoft Teams

**Benutzerdefinierte Vorlagen werden für EDU-Kunden noch nicht unterstützt.**

Eine benutzerdefinierte Teamvorlage ist eine vordefinierte Teamstruktur mit einer Reihe von Kanälen, Registerkarten und Apps. Sie können eine Vorlage entwickeln, die Ihnen hilft, schnell den richtigen Platz zur Zusammenarbeit zu schaffen. Ihre benutzerdefinierte Teamvorlage verwendet Ihre bevorzugten Einstellungen.  

<br>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4P5rx]


Erste Schritte:

1. Melden Sie sich beim Microsoft Teams Admin Center an.

2. Erweitern Sie im linken Navigationsbereich die **Teams**  >  **Teamvorlagen**.

3. Klicken Sie auf **Hinzufügen**.

    ![Abbildung des Dialogfelds "Teamvorlagen" mit hervorgehobener Hervorhebung "Hinzufügen".](media/team-templates-new.png)

4. Wählen Sie **im Abschnitt Teamvorlagen** die Option **Neue Vorlage erstellen aus.**

5. Füllen Sie **im Abschnitt Vorlageneinstellungen** die folgenden Felder aus, und wählen Sie dann Weiter **aus:**
    - Vorlagenname
    - Kurze und lange Beschreibungen von Vorlagen
    - Sichtbarkeit des Locale  

    ![Abbildung des Einstellungsdialogfelds für Teamvorlagen](media/template-add-a-name.png)

6. Fügen Sie **im Abschnitt Kanäle, Registerkarten** und Apps alle Kanäle und Apps hinzu, die Ihr Team benötigt.

    1. Wählen Sie **im Abschnitt** Kanäle die Option **Hinzufügen aus.**
    2. Geben Sie **dem Kanal** im Dialogfeld Hinzufügen einen Namen.
    3. Fügen Sie eine Beschreibung hinzu.
    4. Entscheiden Sie, ob der Kanal standardmäßig angezeigt werden soll.
    5. Suchen Sie nach einem App-Namen, den Sie dem Kanal hinzufügen möchten.
    6. Wenn Sie **fertig sind,** wählen Sie Übernehmen aus.

    ![Abbildung des Bildschirms für Teamvorlagenkanäle, Registerkarten und Apps.](media/template-channels-tabs-apps.png)

8. Wählen Sie **Absenden** aus, wenn der Abschluss abgeschlossen ist.

Ihre neue Vorlage wird in der Liste **der Teamvorlagen** angezeigt. Die Vorlage kann zum Erstellen eines Teams in einer Teams.

> [!Note]
> Es kann bis zu 24 Stunden dauern, bis Teambenutzer eine benutzerdefinierte Vorlagenänderung im Katalog sehen.

## <a name="customizing-website-tab-apps"></a>Anpassen von Apps auf der Registerkarte "Website"

> [!Note]
> Dieses Feature wird in der Vorschauversion angezeigt.

Sie können URLs für Websiteregisterkarten für Kanäle in benutzerdefinierten Teamvorlagen angeben. Endbenutzer, die Teams mit Vorlagen erstellen, verfügen über Websiteregisterkarten, die auf die angegebene Website-URL voreingestellt sind.

Erste Schritte:

1. Erstellen Sie eine neue Teamvorlage, oder bearbeiten Sie eine vorhandene Teamvorlage.

2. Fügen Sie im Abschnitt Kanäle einen neuen Kanal hinzu, oder wählen Sie einen vorhandenen Kanal und dann **Bearbeiten aus.**

3. Fügen Sie **im Abschnitt App für diese Vorlage hinzufügen** eine Website-App hinzu.

    ![Option "App für diese Vorlage hinzufügen"](media/add-an-app-template.png)

4. Wählen Sie das Symbol "Bearbeiten" aus, und geben Sie die URL Ihrer Wahl ein.

    ![Hinzufügen einer App-URL](media/add-url-app-template.png)

5. Wählen **Sie speichern** aus, um Änderungen an Ihrer Registerkarten-App vorzunehmen, und wählen Sie dann Übernehmen **aus,** um Ihre Änderungen zu speichern.

## <a name="known-issues"></a>Bekannte Probleme

**Problem:** Wenn Sie ein Team aus einer benutzerdefinierten Vorlage erstellt haben, die zusätzliche benutzerdefinierte Registerkarten enthielt, werden möglicherweise leere Registerkarten statt Ihrer benutzerdefinierten Registerkarten-Apps angezeigt. Ihre Standardregisterkarten (z. **B. Beiträge,** **Dateien** und **Wiki)** werden wie erwartet angezeigt.

**Lösung:** Um dieses Problem zu beheben, entfernen Sie die benutzerdefinierte Registerkarte, und fügen Sie eine neue Registerkarte mit derselben App hinzu. Wenn Sie nicht über die Berechtigungen zum Entfernen der benutzerdefinierten Registerkarte und zum Hinzufügen einer neuen Registerkarte verfügen, bitten Sie den Teambesitzer um Unterstützung.

Wir arbeiten derzeit an einer Lösung für zukünftige Teams, die aus benutzerdefinierten Vorlagen erstellt wurden.

**Problem:** Wenn Sie Teams Browser verwenden, wird das Rendern auf einer Registerkarte mit Teams unterstützt.

![Browserfehlermeldung](media/browser-error-message.png)

**Lösung:** Wenn Sie Probleme beim Anzeigen der Inhalte der Websiteregisterkarte haben, werden Sie umgeleitet, um die Registerkarte entweder auf einer separaten Webseite zu öffnen, oder öffnen Sie Teams stattdessen in der Desktop-App, um ihre App für Websiteregisterkarten anzuzeigen.

## <a name="related-topics"></a>Verwandte Themen

- [Erste Schritte mit Teamvorlagen im Admin Center](get-started-with-teams-templates-in-the-admin-console.md)
- [Erstellen einer Vorlage aus einem vorhandenen Team](create-template-from-existing-team.md)
- [Erstellen einer Teamvorlage aus einer vorhandenen Teamvorlage](create-template-from-existing-template.md)
