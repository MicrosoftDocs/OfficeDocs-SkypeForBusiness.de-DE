---
title: Verwalten von Richtlinienpaketen in Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: sekrantz, aaglick
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.policypackages.overview
- seo-marvel-apr2020
localization_priority: Normal
search.appverid: MET150
description: Erfahren Sie, wie Sie Richtlinienpakete in Microsoft Teams verwenden und verwalten, um Richtlinien für Benutzergruppen zu vereinfachen, zu rationalisieren und für Konsistenz zu sorgen.
ms.openlocfilehash: 1b7e6e5c6311ebd51b0f00b86953291ed4ac63b3
ms.sourcegitcommit: b52b6aba289396c4fc10dd856817137eb1bc1f67
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/07/2021
ms.locfileid: "51634230"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a>Verwalten von Richtlinienpaketen in Microsoft Teams

Ein Richtlinienpaket in Microsoft Teams ist eine Sammlung vordefinierter Richtlinien und Richtlinieneinstellungen, die Sie Benutzern zuweisen können, die ähnliche Rollen in Ihrer Organisation haben. Wir haben Richtlinienpakete erstellt, um Richtlinien zu vereinfachen, zu rationalisieren und die Konsistenz beim Verwalten von Richtlinien für Benutzergruppen in Der gesamten Organisation zu gewährleisten.  

Sie können die in [Teams enthaltenen Richtlinienpakete](#policy-packages-included-in-teams) verwenden oder eigene benutzerdefinierte [Richtlinienpakete](#custom-policy-packages) (in der privaten Vorschau) erstellen.

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="Screenshot der Seite "Richtlinienpakete" im Admin Center":::

Sie können die Einstellungen der Richtlinien in einem Richtlinienpaket an die Anforderungen Ihrer Benutzer anpassen. Wenn Sie die Einstellungen von Richtlinien in einem Paket ändern, erhalten alle Benutzer, die diesem Paket zugewiesen sind, die aktualisierten Einstellungen. Sie verwalten Richtlinienpakete über das Microsoft Teams Admin Center oder PowerShell.

## <a name="what-is-a-policy-package"></a>Was ist ein Richtlinienpaket?

Mit Richtlinienpaketen können Sie Teams-Features steuern, die Sie für bestimmte Gruppen von Personen in Ihrer Organisation zulassen oder einschränken möchten. Jedes Richtlinienpaket in Teams ist auf eine Benutzerrolle ausgelegt und enthält vordefinierte Richtlinien und Richtlinieneinstellungen, die die für diese Rolle typischen Zusammenarbeits- und Kommunikationsaktivitäten unterstützen.

Richtlinienpakete unterstützen die folgenden Teams-Richtlinientypen:

- Messagingrichtlinie
- Besprechungsrichtlinie
- App-Setuprichtlinie
- Anrufrichtlinie
- Richtlinie für Liveereignisse

## <a name="policy-packages-included-in-teams"></a>In Teams enthaltene Richtlinienpakete

Teams enthält derzeit die folgenden Richtlinienpakete.

| Paketname | Beschreibung |
|---------|---------|
|Bildungseinrichtungen (Studierender der Höheren Bildungseinrichtungen)    |Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, die für Studierende an höheren Bildungseinrichtungen gelten.|
|Ausbildung (Grundschüler)   |Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, die für Grundschüler gelten.|
|Bildungseinrichtungen (Schüler/Studenten der Sekundarstufe)    |Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, die für sekundäre Kursteilnehmer gelten.         |
|Education (Teacher)    |Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, die für Lehrkräfte gelten.      |
|Ausbildung (Grundschullehrer mit Remotelernen)    |Erstellt eine Reihe von Richtlinien, um die Sicherheit und Zusammenarbeit der Lehrkräfte beim Lernen per Fernzugriff zu maximieren.      |
|Ausbildung (Grundschüler mit Remotelernen)    |Erstellt eine Reihe von Richtlinien, um die Sicherheit und Zusammenarbeit der Schüler beim Lernen per Fernzugriff zu maximieren.      |
|Frontline-Manager |Erstellt eine Reihe von Richtlinien und wendet diese Einstellungen auf Frontline-Manager in Ihrer Organisation an. |
|Frontlinemitarbeiter |Erstellt eine Reihe von Richtlinien und wendet diese Einstellungen auf Frontline-Mitarbeiter in Ihrer Organisation an. |
|Klinischer Mitarbeiter im Gesundheitswesen  |Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, mit denen klinische Mitarbeiter wie Krankenschwestern, Krankenschwestern, Ärzte und Sozialarbeiter uneingeschränkten Zugriff auf Chat, Anrufe, Schichtmanagement und Besprechungen erhalten. |
|Informationsbeauftragter für das Gesundheitswesen  |Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, mit denen Informationsbeauftragte wie IT-Personal, Informatikpersonal, Finanzpersonal und Compliance-Beauftragte uneingeschränkten Zugriff auf Chat, Anrufe und Besprechungen erhalten.|
|Patientenzimmer im Gesundheitswesen  |Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, die für Patientenzimmer in Ihrer Gesundheitsorganisation gelten.|
|Benutzer für kleine und mittelständische Unternehmen (Business Voice) |Erstellt eine App-Setuprichtlinie, die die Apps für eine Unternehmensstimmenerfahrung enthält.|
|Benutzer kleiner und mittlerer Unternehmen (ohne Business Voice) |Erstellt eine App-Einrichtungsrichtlinie, die für kleine und mittelständische Teams-Benutzer relevant ist (Nicht-Business-Spracherfahrung).
|Referent für öffentliche Sicherheit   |Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, die für Mitarbeiter der öffentlichen Sicherheit in Ihrer Organisation gelten.|

> [!NOTE]
> Wir werden in zukünftigen Versionen von Teams weitere Richtlinienpakete hinzufügen, daher suchen Sie nach den neuesten Informationen.  

Jede einzelne Richtlinie erhält den Namen des Richtlinienpakets, sodass Sie die Richtlinien, die mit einem Richtlinienpaket verknüpft sind, leicht identifizieren können.
Wenn Sie beispielsweise lehrkräften Lehrkräften in Ihrer Schule das Richtlinienpaket "Bildungseinrichtungen" zuweisen, wird für jede Richtlinie im Paket eine Richtlinie mit dem Namen Education_Teacher erstellt.

![Screenshot des Richtlinienpakets Für Bildungseinrichtungen (Lehrer)](media/policy-packages-education_teacher.png)

## <a name="custom-policy-packages"></a>Benutzerdefinierte Richtlinienpakete

**Benutzerdefinierte Richtlinienpakete sind für die Government Community Cloud (GCC) noch nicht verfügbar.**

Mit benutzerdefinierten Richtlinienpaketen können Sie Eigene Richtlinien für Benutzer mit ähnlichen Rollen in Ihrer Organisation bündeln. Erstellen Sie eigene Richtlinienpakete, indem Sie die benötigten Richtlinientypen und Richtlinien hinzufügen.

So erstellen Sie ein neues benutzerdefiniertes Richtlinienpaket:

1. Wählen Sie im linken Navigationsbereich des Microsoft Teams Admin Center die Option **Richtlinienpakete** aus, und klicken Sie dann auf **Hinzufügen.**

    :::image type="content" source="media/policy-packages-add.png" alt-text="Screenshot der Schaltfläche "Hinzufügen" auf der Seite "Richtlinienpakete" im Admin Center":::

2. Geben Sie einen Namen und eine Beschreibung für Ihr Paket ein.

    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="Screenshot des Hinzufügens eines neuen benutzerdefinierten Richtlinienpakets":::

3. Wählen Sie die Richtlinientypen und Richtliniennamen aus, die in das Paket enthalten sein müssen.

4. Klicken Sie auf **Speichern**.

## <a name="how-to-use-policy-packages"></a>Verwenden von Richtlinienpaketen

Im Folgenden wird die Verwendung von Richtlinienpaketen in Ihrer Organisation erläutert.

![Übersicht über die Verwendung von Richtlinienpaketen](media/manage-policy-packages-overview.png)

- **[Ansicht:](#view-the-settings-of-a-policy-in-a-policy-package)** Zeigen Sie die Richtlinien in einem Richtlinienpaket an. Zeigen Sie dann die Einstellungen jeder Richtlinie in einem Paket an, bevor Sie das Paket zuweisen. Stellen Sie sicher, dass Sie die einzelnen Einstellungen verstehen. Entscheiden Sie, ob die vordefinierten Werte für Ihre Organisation geeignet sind oder ob Sie sie entsprechend den Anforderungen Ihrer Organisation als restriktiver oder nachsichtig ändern müssen.

    Wenn eine Richtlinie gelöscht wird, können Sie die Einstellungen weiterhin anzeigen, aber keine Einstellungen ändern. Beim Zuweisen des Richtlinienpakets wird eine gelöschte Richtlinie mit den vordefinierten Einstellungen neu erstellt.

- **[Anpassen:](#customize-policies-in-a-policy-package)** Passen Sie die Einstellungen der Richtlinien im Richtlinienpaket an die Anforderungen Ihrer Organisation an.

- **[Zuweisen:](#assign-a-policy-package)** Weisen Sie das Richtlinienpaket Benutzern zu.  

> [!NOTE]
> Sie können auch die Einstellungen von Richtlinien in einem Richtlinienpaket ändern, nachdem Sie ein Paket zugewiesen haben. Alle Änderungen, die Sie an den Richtlinieneinstellungen vornehmen, werden automatisch auf Benutzer angewendet, denen das Paket zugewiesen wird.

Hier sind die Schritte zum Anzeigen, Zuweisen und Anpassen von Richtlinienpaketen im Microsoft Teams Admin Center.

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a>Anzeigen der Einstellungen einer Richtlinie in einem Richtlinienpaket

1. Wählen Sie im linken Navigationsbereich des Microsoft Teams Admin Center die Option Richtlinienpakete **aus,** und wählen Sie dann ein Richtlinienpaket aus, indem Sie links neben dem Paketnamen klicken.

2. Klicken Sie auf die Richtlinie, die Sie anzeigen möchten.

### <a name="customize-policies-in-a-policy-package"></a>Anpassen von Richtlinien in einem Richtlinienpaket

Sie können die Einstellungen einer  Richtlinie über die Seite Richtlinienpakete oder direkt zur Richtlinienseite im Microsoft Teams Admin Center bearbeiten.

1. Gehen Sie im linken Navigationsbereich des Microsoft Teams Admin Centers wie folgt vor:
    - Klicken **Sie auf Richtlinienpakete**, und wählen Sie dann das Richtlinienpaket aus, indem Sie links vom Paketnamen klicken.
    - Klicken Sie auf den Richtlinientyp.  Klicken Sie beispielsweise auf **Messagingrichtlinien**.

2. Wählen Sie die Richtlinie aus, die Sie bearbeiten möchten. Richtlinien, die mit einem Richtlinienpaket verknüpft sind, haben denselben Namen wie das Richtlinienpaket.

3. Nehmen Sie die von Ihnen vorgenommenen Änderungen vor, und klicken Sie dann auf **Speichern.**

### <a name="assign-a-policy-package"></a>Zuweisen eines Richtlinienpakets

Sie können einem einzelnen Benutzer, einer Gruppe oder einer Gruppe von Benutzern ein Richtlinienpaket zuweisen. Weitere Informationen zum Zuweisen von Richtlinienpaketen finden Sie unter Zuweisen von [Richtlinienpaketen zu Benutzern und Gruppen.](assign-policy-packages.md)

## <a name="related-topics"></a>Verwandte Themen

- [Zuweisen von Richtlinienpaketen](assign-policy-packages.md)
- [Teams-Richtlinienpakete für EDU-Administratoren](policy-packages-edu.md)
- [Teams Richtlinienpakete-Pakete für das Gesundheitswesen](policy-packages-healthcare.md)
- [Teams-Richtlinienpakete für Behörden](policy-packages-gov.md)
