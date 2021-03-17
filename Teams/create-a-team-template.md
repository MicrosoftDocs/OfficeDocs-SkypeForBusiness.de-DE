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
ms.openlocfilehash: a596f2755434e7074c4a925f5c7c1dd8b1efbcaf
ms.sourcegitcommit: fdada65628b31e4c267c87f0100e9f046b878c12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/16/2021
ms.locfileid: "50831020"
---
# <a name="create-a-custom-team-template-in-microsoft-teams"></a>Erstellen einer benutzerdefinierten Teamvorlage in Microsoft Teams

**Benutzerdefinierte Vorlagen werden für EDU-Kunden noch nicht unterstützt.**

Eine benutzerdefinierte Teamvorlage ist eine vordefinierte Teamstruktur mit einer Reihe von Kanälen, Registerkarten und Apps. Sie können eine Vorlage entwickeln, die Ihnen hilft, schnell den richtigen Platz für die Zusammenarbeit zu schaffen. Ihre benutzerdefinierte Teamvorlage verwendet Ihre bevorzugten Einstellungen.  

So beginnen Sie:

1. Melden Sie sich beim Microsoft Teams Admin Center an.

2. Erweitern Sie im linken Navigationsbereich **teams**  >  **team templates**.

3. Klicken Sie auf **Hinzufügen**.

    ![Ein Bild des Dialogfelds "Teamvorlagen" mit hervorgehobener Hervorhebung "Hinzufügen".](media/team-templates-new.png)

4. Wählen Sie **im Abschnitt Teamvorlagen** die Option **Neue Vorlage erstellen aus.**

5. Füllen Sie **im Abschnitt** Vorlageneinstellungen die folgenden Felder aus, und wählen Sie dann **Weiter aus:**
    - Vorlagenname
    - Kurze und lange Beschreibungen der Vorlage
    - Sichtbarkeit des Locale  

    ![Abbildung des Dialogfelds "Teamvorlageneinstellungen".](media/template-add-a-name.png)

6. Fügen Sie **im Abschnitt Kanäle, Registerkarten und Apps** alle Kanäle und Apps hinzu, die Ihr Team benötigt.

    1. Wählen Sie **im Abschnitt** Kanäle die Option **Hinzufügen aus.**
    2. Benennen Sie **im** Dialogfeld Hinzufügen den Kanal.
    3. Fügen Sie eine Beschreibung hinzu.
    4. Entscheiden Sie, ob der Kanal standardmäßig angezeigt werden soll.
    5. Suchen Sie nach einem App-Namen, den Sie dem Kanal hinzufügen möchten.
    6. Wählen **Sie Übernehmen** aus, wenn Sie fertig sind.

    ![Abbildung des Bildschirms "Kanäle, Registerkarten und Apps" für Teamvorlagen.](media/template-channels-tabs-apps.png)

8. Wählen Sie **Nach** Abschluss absenden aus.

Ihre neue Vorlage wird in der Liste **Teamvorlagen** angezeigt. Die Vorlage kann zum Erstellen eines Teams in Teams verwendet werden.

> [!Note]
> Es kann bis zu 24 Stunden dauern, bis Teambenutzer eine benutzerdefinierte Vorlage im Katalog anzeigen.

## <a name="customizing-website-tab-apps"></a>Anpassen von Website-Tab-Apps

> [!Note]
> Dieses Feature befindet sich in der frühen Vorschau.

Möglicherweise möchten Sie URLs für Websiteregisterkarten für Kanäle in benutzerdefinierten Teamvorlagen angeben. Endbenutzer, die Teams mit Vorlagen erstellen, verfügen über Websiteregisterkarten, die auf die angegebene Website-URL voreingestellt sind.

So beginnen Sie:

1. Erstellen Sie eine neue Teamvorlage, oder bearbeiten Sie eine vorhandene Teamvorlage.

2. Fügen Sie im Abschnitt Kanäle einen neuen Kanal hinzu, oder wählen Sie einen vorhandenen Kanal aus, und wählen Sie **Bearbeiten aus.**

3. Fügen Sie **im Abschnitt App für diese Vorlage** hinzufügen eine Website-App hinzu.

    ![Hinzufügen einer App für diese Vorlagenoption](media/add-an-app-template.png)

4. Wählen Sie das Bearbeitungssymbol aus, und geben Sie die URL Ihrer Wahl ein.

    ![Hinzufügen einer App-URL](media/add-url-app-template.png)

5. Wählen **Sie Speichern** für Ihre Registerkarten-App-Bearbeitungen und dann Übernehmen **aus,** um Ihre Änderungen zu speichern.

## <a name="known-issues"></a>Bekannte Probleme

**Problem:** Wenn Sie ein Team aus einer benutzerdefinierten Vorlage erstellt haben, die zusätzliche benutzerdefinierte Registerkarten enthält, werden möglicherweise leere Registerkarten statt ihrer benutzerdefinierten Registerkarten-Apps angezeigt. Ihre Standardregisterkarten (z. **B. Beiträge,** **Dateien** und **Wiki)** werden wie erwartet angezeigt.

**Lösung:** Wenn Sie ein Team aus einer benutzerdefinierten Vorlage erstellt haben, die zusätzliche benutzerdefinierte Registerkarten enthält, werden möglicherweise leere Registerkarten statt ihrer benutzerdefinierten Registerkarten-Apps angezeigt. Ihre Standardregisterkarten (z. B. Beiträge, Dateien und Wiki) werden wie erwartet angezeigt.

Um dieses Problem zu beheben, entfernen Sie die benutzerdefinierte Registerkarte, und fügen Sie eine neue Registerkarte mit derselben App hinzu. Wenn Sie nicht über die Berechtigungen zum Entfernen der benutzerdefinierten Registerkarte und zum Hinzufügen einer neuen Registerkarte verfügen, wenden Sie sich an den Teambesitzer, um Unterstützung zu erhalten.

Wir arbeiten derzeit an einem Fix für zukünftige Teams, die aus benutzerdefinierten Vorlagen erstellt wurden.

## <a name="related-topics"></a>Verwandte Themen

- [Erste Schritte mit Teamvorlagen im Admin Center](get-started-with-teams-templates-in-the-admin-console.md)
- [Erstellen einer Vorlage aus einem vorhandenen Team](create-template-from-existing-team.md)
- [Erstellen einer Teamvorlage aus einer vorhandenen Teamvorlage](create-template-from-existing-template.md)
