---
title: Erstellen einer benutzerdefinierten Teamvorlage in Microsoft Teams
author: LanaChin
ms.author: v-lanachin
manager: samanro
ms.reviewer: aaglick
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Erfahren Sie, wie Sie eine benutzerdefinierte Teamvorlage in Microsoft Teams erstellen.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6a6d5d119d3b941bae1f3eedc3033a364df2b18a
ms.sourcegitcommit: 9532eb79310cd653010565607fa394f2b8dd182d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/23/2022
ms.locfileid: "65646284"
---
# <a name="create-a-custom-team-template-in-microsoft-teams"></a>Erstellen einer benutzerdefinierten Teamvorlage in Microsoft Teams

**Benutzerdefinierte Vorlagen werden für EDU-Kunden noch nicht unterstützt.**

Eine benutzerdefinierte Teamvorlage ist eine vordefinierte Teamstruktur mit einer Reihe von Kanälen, Registerkarten und Apps. Sie können eine Vorlage entwickeln, die Ihnen hilft, schnell den richtigen Platz für die Zusammenarbeit zu schaffen. Ihre benutzerdefinierte Teamvorlage verwendet Ihre bevorzugten Einstellungen.  

<br>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4P5rx]


So beginnen Sie:

1. Melden Sie sich beim Microsoft Teams Admin Center an.

2. Erweitern Sie im linken Navigationsbereich **Teams** >  **Teamvorlagen**.

3. Klicken Sie auf **Hinzufügen**.

    ![Abbildung des Dialogfelds "Teamvorlagen" mit hervorgehobener Option "Hinzufügen".](media/team-templates-new.png)

4. Wählen Sie im Abschnitt **"Teamvorlagen** " die Option " **Neue Vorlage erstellen" aus**.

5. Füllen Sie im Abschnitt **"Vorlageneinstellungen"** die folgenden Felder aus, und wählen Sie dann **"Weiter**" aus:
    - Vorlagenname
    - Kurze und lange Beschreibungen der Vorlage
    - Sichtbarkeit des Gebietsschemas  

    ![Abbildung des Dialogfelds für die Benennung von Teamvorlageneinstellungen.](media/template-add-a-name.png)

6. Fügen Sie im Abschnitt **"Kanäle, Registerkarten und Apps** " alle Kanäle und Apps hinzu, die Ihr Team benötigt.

    1. Wählen Sie im Abschnitt **"Kanäle** " die Option **"Hinzufügen"** aus.
    2. Geben Sie im Dialogfeld **"Hinzufügen** " den Namen des Kanals ein.
    3. Fügen Sie eine Beschreibung hinzu.
    4. Entscheiden Sie, ob der Kanal standardmäßig angezeigt werden soll.
    5. Suchen Sie nach einem App-Namen, den Sie dem Kanal hinzufügen möchten.
    6. Wählen Sie **"Übernehmen** " aus, wenn Sie fertig sind.

    ![Abbildung des Bildschirms "Teamvorlagen", "Kanäle", "Registerkarten" und "Apps".](media/template-channels-tabs-apps.png)

8. Wählen Sie **"Absenden** " aus, wenn Sie fertig sind.

Ihre neue Vorlage wird in der **Teamvorlagenliste** angezeigt. Die Vorlage kann zum Erstellen eines Teams in Teams verwendet werden.

> [!Note]
> Es kann bis zu 24 Stunden dauern, bis Teams-Benutzer eine benutzerdefinierte Vorlagenänderung im Katalog sehen.

## <a name="customizing-website-tab-apps"></a>Anpassen von Websiteregisterkarten-Apps

> [!Note]
> Dieses Feature befindet sich in der frühen Vorschau

Möglicherweise möchten Sie URLs für Websiteregisterkarten für Kanäle in benutzerdefinierten Teamvorlagen angeben. Endbenutzer, die Teams mit Vorlagen erstellen, verfügen über Websiteregisterkarten, die auf die angegebene Website-URL voreingestellt sind.

So beginnen Sie:

1. Erstellen Sie eine neue Teamvorlage, oder bearbeiten Sie eine vorhandene Teamvorlage.

2. Fügen Sie im Abschnitt "Kanäle" einen neuen Kanal hinzu, oder wählen Sie einen vorhandenen Kanal aus, und wählen Sie **"Bearbeiten"** aus.

3. Fügen Sie im Abschnitt **"App für diese Vorlage hinzufügen** " eine Website-App hinzu.

    ![fügen Sie eine App für diese Vorlagenoption hinzu.](media/add-an-app-template.png)

4. Wählen Sie das Bearbeitungssymbol aus, und geben Sie die URL Ihrer Wahl ein.

    ![fügen Sie eine App-URL hinzu.](media/add-url-app-template.png)

5. Wählen Sie "Für die Bearbeitungen ihrer Registerkarten-App **speichern** " und dann " **Übernehmen"** aus, um Ihre Änderungen zu speichern.

## <a name="known-issues"></a>Bekannte Probleme

**Problem**: Wenn Sie ein Team anhand einer benutzerdefinierten Vorlage erstellt haben, die zusätzliche benutzerdefinierte Registerkarten enthielt, werden möglicherweise leere Registerkarten anstelle Ihrer benutzerdefinierten Registerkarten-Apps angezeigt. Ihre Standardregisterkarten (z. B. **Beiträge**, **Dateien** und **Wiki**) werden wie erwartet angezeigt.

**Lösung**: Um dieses Problem zu beheben, entfernen Sie die benutzerdefinierte Registerkarte, und fügen Sie eine neue Registerkarte mit derselben App hinzu. Wenn Sie nicht über die Berechtigung zum Entfernen der benutzerdefinierten Registerkarte und hinzufügen einer neuen Registerkarte verfügen, wenden Sie sich an den Teambesitzer, um Hilfe zu erhalten.

Wir arbeiten derzeit an einem Fix für zukünftige Teams, die aus benutzerdefinierten Vorlagen erstellt wurden.

**Problem**: Bei Verwendung von Teams im Browser wird das Rendern auf einer Teams Registerkarte von einigen Websites nicht unterstützt.

![Browserfehlermeldung.](media/browser-error-message.png)

**Lösung**: Wenn Sie Probleme beim Anzeigen der Inhalte der Websiteregisterkarte haben, werden Sie umgeleitet, um entweder die Registerkarte auf einer separaten Webseite zu öffnen oder Teams stattdessen in der Desktop-App zu öffnen, um Ihre Website-Registerkarten-App anzuzeigen.

## <a name="related-topics"></a>Verwandte Themen

- [Erste Schritte mit Teamvorlagen im Admin Center](get-started-with-teams-templates-in-the-admin-console.md)
- [Erstellen einer Vorlage aus einem vorhandenen Team](create-template-from-existing-team.md)
- [Erstellen einer Teamvorlage aus einer vorhandenen Teamvorlage](create-template-from-existing-template.md)
