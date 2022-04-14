---
title: Verwalten von Richtlinienpaketen in Microsoft Teams
author: SerdarSoysal
ms.author: serdars
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
ms.localizationpriority: medium
search.appverid: MET150
description: Erfahren Sie, wie Sie Richtlinienpakete in Microsoft Teams verwenden und verwalten, um die Konsistenz bei der Verwaltung von Richtlinien für Benutzergruppen zu vereinfachen, zu rationalisieren und zu gewährleisten.
ms.openlocfilehash: 173d5d1488196ea048a64ce12916f8115362c572
ms.sourcegitcommit: 480046a53dfb6e6cf867e1920f8fb43dda9d3774
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2022
ms.locfileid: "63055305"
---
# <a name="manage-policy-packages-for-microsoft-teams"></a>Verwalten von Richtlinienpaketen für Microsoft Teams

Ein Richtlinienpaket in Microsoft Teams ist eine Sammlung vordefinierter Richtlinien und Richtlinieneinstellungen, die Sie Benutzern zuweisen können, die ähnliche Rollen in Ihrer Organisation haben. Wir haben Richtlinienpakete erstellt, um die Verwaltung von Richtlinien für Benutzergruppen in Ihrer Organisation zu vereinfachen, zu rationalisieren und Konsistenz zu gewährleisten.  

Sie können die [in Teams enthaltenen Richtlinienpakete](#policy-packages-included-in-teams) verwenden oder [eigene benutzerdefinierte Richtlinienpakete erstellen](#custom-policy-packages).

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="Screenshot der Seite &quot;Richtlinienpakete&quot; im Admin Center.":::

Sie können die Einstellungen der Richtlinien in einem Richtlinienpaket an die Anforderungen Ihrer Benutzer anpassen. Wenn Sie die Einstellungen von Richtlinien in einem Paket ändern, erhalten alle Benutzer, die diesem Paket zugewiesen sind, die aktualisierten Einstellungen. Sie verwalten Richtlinienpakete über das Microsoft Teams Admin Center oder PowerShell.

> [!NOTE]
> Dieses Feature ist vorübergehend in der öffentlichen Vorschau für alle Microsoft Teams Kunden verfügbar. Um dieses Feature nach der Vorschau zu erhalten, benötigt jeder Benutzer die Add-On-Lizenz "Erweiterte Kommunikation". Weitere Informationen finden Sie unter [Add-On für erweiterte Kommunikation für Microsoft Teams](/microsoftteams/teams-add-on-licensing/advanced-communications).

## <a name="what-is-a-policy-package"></a>Was ist ein Richtlinienpaket?

Mit Richtlinienpaketen können Sie Teams Features steuern, die Sie für bestimmte Gruppen von Personen in Ihrer Organisation zulassen oder einschränken möchten. Jedes Richtlinienpaket in Teams ist auf eine Benutzerrolle ausgelegt und enthält vordefinierte Richtlinien und Richtlinieneinstellungen, die die für diese Rolle typischen Zusammenarbeits- und Kommunikationsaktivitäten unterstützen.

Richtlinienpakete unterstützen die folgenden Teams Richtlinientypen:

- Messagingrichtlinie
- Besprechungsrichtlinie
- App-Setuprichtlinie
- Anrufrichtlinie
- Richtlinie für Liveereignisse

## <a name="policy-packages-included-in-teams"></a>In Teams enthaltene Richtlinienpakete

Teams enthält derzeit die folgenden Richtlinienpakete.

| Paketname | Beschreibung |
|---------|---------|
|Bildung (Hochschulstudent)    |Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, die für Hochschulstudenten gelten.|
|Bildung (Primarschüler)   |Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, die für Schüler/Studenten gelten.|
|Bildung (Sekundarstufe 1)    |Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, die für Schüler/Studenten gelten.         |
|Bildung (Lehrer)    |Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, die für Lehrkräfte gelten.      |
|Bildung (Grundschullehrer mit Fernunterricht)    |Erstellt eine Reihe von Richtlinien, um die Sicherheit und Zusammenarbeit der Lehrkräfte beim Lernen per Fernzugriff zu maximieren.      |
|Bildung (Grundschüler mit Fernunterricht)    |Erstellt eine Reihe von Richtlinien, um die Sicherheit und Zusammenarbeit der Schüler beim Lernen per Fernzugriff zu maximieren.      |
|Vorgesetzter in Service und Produktion |Erstellt eine Reihe von Richtlinien und wendet diese Einstellungen auf Vorgesetzte in Service und Produktion in Ihrer Organisation an. |
|Mitarbeiter in Service und Produktion |Erstellt eine Reihe von Richtlinien und wendet diese Einstellungen auf Mitarbeiter in Service und Produktion in Ihrer Organisation an. |
|Klinischer Mitarbeiter im Gesundheitswesen  |Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, mit denen klinische Mitarbeiter wie Krankenschwestern, Krankenschwestern, Ärzte und Sozialarbeiter uneingeschränkten Zugriff auf Chat, Anrufe, Schichtmanagement und Besprechungen erhalten. |
|Informationsbeauftragter für das Gesundheitswesen  |Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, mit denen Informationsbeauftragte wie IT-Personal, Informatikpersonal, Finanzpersonal und Compliance-Beauftragte uneingeschränkten Zugriff auf Chat, Anrufe und Besprechungen erhalten.|
|Patientenzimmer im Gesundheitswesen  |Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, die für Patientenzimmer in Ihrer Gesundheitsorganisation gelten.|
|Benutzer kleiner und mittlerer Unternehmen (Teams Telefonsystem mit Anrufplan-Bundle) |Erstellt eine App-Setuprichtlinie, die die Apps für eine Teams Telefonsystem mit Anrufplan-Bundle-Erfahrung enthält.|
|Kleine und mittelständische Unternehmen (ohne Teams Telefonsystem mit Anrufplanpaket) |Erstellt eine App-Setuprichtlinie, die für kleine und mittlere Unternehmen Teams Benutzern relevant ist (nicht Teams Telefonsystem mit Anrufplan-Bundle-Erfahrung).
|Öffentlicher Sicherheitsbeauftragter   |Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, die für öffentliche Sicherheitsbeauftragte in Ihrer Organisation gelten.|

> [!NOTE]
> Wir werden in zukünftigen Versionen von Teams weitere Richtlinienpakete hinzufügen. Schauen Sie sich daher die aktuellsten Informationen an.  

Jede einzelne Richtlinie erhält den Namen des Richtlinienpakets, sodass Sie die Richtlinien, die mit einem Richtlinienpaket verknüpft sind, leicht identifizieren können.
Wenn Sie beispielsweise Lehrern in Ihrer Schule das Richtlinienpaket "Bildung" (Lehrer) zuweisen, wird für jede Richtlinie im Paket eine Richtlinie mit dem Namen Education_Teacher erstellt.

![Screenshot des Richtlinienpakets "Education (Teacher)".](media/policy-packages-education_teacher.png)

## <a name="custom-policy-packages"></a>Benutzerdefinierte Richtlinienpakete

Mit benutzerdefinierten Richtlinienpaketen können Sie Ihre eigenen Richtlinien für Benutzer mit ähnlichen Rollen in Ihrer Organisation bündeln. Erstellen Sie eigene Richtlinienpakete, indem Sie die erforderlichen Richtlinientypen und Richtlinien hinzufügen.

So erstellen Sie ein neues benutzerdefiniertes Richtlinienpaket:

1. Wählen Sie im linken Navigationsbereich des Microsoft Teams Admin Center **Richtlinienpakete** aus, und klicken Sie dann auf **"Hinzufügen"**.

    :::image type="content" source="media/policy-packages-add.png" alt-text="Screenshot der Schaltfläche &quot;Hinzufügen&quot; auf der Seite &quot;Richtlinienpakete&quot; im Admin Center.":::

2. Geben Sie einen Namen und eine Beschreibung für Ihr Paket ein.

    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="Screenshot des Hinzufügens eines neuen benutzerdefinierten Richtlinienpakets.":::

3. Wählen Sie die Richtlinientypen und Richtliniennamen aus, die in das Paket eingeschlossen werden sollen.

4. Klicken Sie auf **Speichern**.

## <a name="how-to-use-policy-packages"></a>Verwenden von Richtlinienpaketen

Im Folgenden wird die Verwendung von Richtlinienpaketen in Ihrer Organisation beschrieben.

![Übersicht über die Verwendung von Richtlinienpaketen.](media/manage-policy-packages-overview.png)

- **[Ansicht](#view-the-settings-of-a-policy-in-a-policy-package)**: Anzeigen der Richtlinien in einem Richtlinienpaket. Zeigen Sie dann die Einstellungen der einzelnen Richtlinien in einem Paket an, bevor Sie das Paket zuweisen. Stellen Sie sicher, dass Sie die einzelnen Einstellungen verstehen. Entscheiden Sie, ob die vordefinierten Werte für Ihre Organisation geeignet sind oder ob Sie sie entsprechend den Anforderungen Ihrer Organisation restriktiver oder nachlässiger ändern müssen.

    Wenn eine Richtlinie gelöscht wird, können Sie die Einstellungen weiterhin anzeigen, jedoch keine Einstellungen ändern. Eine gelöschte Richtlinie wird mit den vordefinierten Einstellungen neu erstellt, wenn Sie das Richtlinienpaket zuweisen.

- **[Anpassen](#customize-policies-in-a-policy-package)**: Passen Sie die Einstellungen von Richtlinien im Richtlinienpaket an die Anforderungen Ihrer Organisation an.

- **[Zuweisen](#assign-a-policy-package)**: Weisen Sie das Richtlinienpaket Benutzern zu.  

> [!NOTE]
> Sie können auch die Einstellungen von Richtlinien in einem Richtlinienpaket ändern, nachdem Sie ein Paket zugewiesen haben. Alle Änderungen, die Sie an den Richtlinieneinstellungen vornehmen, werden automatisch auf Benutzer angewendet, denen das Paket zugewiesen wird.

Hier sind die Schritte zum Anzeigen, Zuweisen und Anpassen von Richtlinienpaketen im Microsoft Teams Admin Center.

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a>Anzeigen der Einstellungen einer Richtlinie in einem Richtlinienpaket

1. Wählen Sie im linken Navigationsbereich des Microsoft Teams Admin Center **Richtlinienpakete** aus, und wählen Sie dann ein Richtlinienpaket aus, indem Sie links neben dem Paketnamen klicken.

2. Klicken Sie auf die Richtlinie, die Sie anzeigen möchten.

### <a name="customize-policies-in-a-policy-package"></a>Anpassen von Richtlinien in einem Richtlinienpaket

Sie können die Einstellungen einer Richtlinie über die Seite **"Richtlinienpakete**" oder direkt auf die Richtlinienseite im Microsoft Teams Admin Center bearbeiten.

1. Führen Sie im linken Navigationsbereich des Microsoft Teams Admin Center eine der folgenden Aktionen aus:
    - Klicken Sie auf **"Richtlinienpakete**", und wählen Sie dann das Richtlinienpaket aus, indem Sie links neben dem Paketnamen klicken.
    - Klicken Sie auf den Richtlinientyp.  Klicken Sie beispielsweise auf **"Nachrichtenrichtlinien"**.

2. Wählen Sie die Richtlinie aus, die Sie bearbeiten möchten. Richtlinien, die mit einem Richtlinienpaket verknüpft sind, haben denselben Namen wie das Richtlinienpaket.

3. Nehmen Sie die gewünschten Änderungen vor, und klicken Sie dann auf **"Speichern"**.

### <a name="assign-a-policy-package"></a>Zuweisen eines Richtlinienpakets

Sie können ein Richtlinienpaket einem einzelnen Benutzer, einer Gruppe oder einer Gruppe von Benutzern zuweisen. Weitere Informationen zum Zuweisen von Richtlinienpaketen finden Sie unter [Zuweisen von Richtlinienpaketen zu Benutzern und Gruppen](assign-policy-packages.md).

## <a name="related-topics"></a>Verwandte Themen

- [Zuweisen von Richtlinienpaketen](assign-policy-packages.md)
- [Teams-Richtlinienpakete für EDU-Administratoren](policy-packages-edu.md)
- [Teams Richtlinienpakete-Pakete für das Gesundheitswesen](policy-packages-healthcare.md)
- [Teams-Richtlinienpakete für Behörden](policy-packages-gov.md)
