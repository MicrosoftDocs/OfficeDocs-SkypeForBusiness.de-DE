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
description: Erfahren Sie, wie Sie Richtlinienpakete in Microsoft Teams verwenden und verwalten, um Richtlinien für Benutzergruppen zu vereinfachen, zu optimieren und konsistenz zu gewährleisten.
ms.openlocfilehash: 2fd892bc440996c7c1f000402122ad268a402ebb6bf382672813efa296de819f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54341785"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a>Verwalten von Richtlinienpaketen in Microsoft Teams

Ein Richtlinienpaket in Microsoft Teams ist eine Sammlung vordefinierter Richtlinien und Richtlinieneinstellungen, die Sie Benutzern zuweisen können, die in Ihrer Organisation ähnliche Rollen haben. Wir haben Richtlinienpakete entwickelt, um Richtlinien für Benutzergruppen in Ihrer Organisation zu vereinfachen, zu optimieren und konsistenz zu gewährleisten.  

Sie können die [in Teams enthaltenen Richtlinienpakete](#policy-packages-included-in-teams) verwenden oder [eigene benutzerdefinierte Richtlinienpakete erstellen.](#custom-policy-packages)

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="Screenshot der Seite "Richtlinienpakete" im Admin Center":::

Sie können die Einstellungen der Richtlinien in einem Richtlinienpaket an die Anforderungen Ihrer Benutzer anpassen. Wenn Sie die Einstellungen von Richtlinien in einem Paket ändern, erhalten alle Benutzer, die diesem Paket zugewiesen sind, die aktualisierten Einstellungen. Sie verwalten Richtlinienpakete mit dem Microsoft Teams Admin Center oder PowerShell.

> [!NOTE]
> Jeder Benutzer benötigt das Advanced Communications-Add-On, um eine benutzerdefinierte Richtlinienpaketzuweisung zu erhalten. Weitere Informationen finden Sie unter [Advanced Communications-Add-On für Microsoft Teams.](/microsoftteams/teams-add-on-licensing/advanced-communications)

## <a name="what-is-a-policy-package"></a>Was ist ein Richtlinienpaket?

Mit Richtlinienpaketen können Sie Teams Features steuern, die Sie für bestimmte Gruppen von Personen in Ihrer Organisation zulassen oder einschränken möchten. Jedes Richtlinienpaket in Teams basiert auf einer Benutzerrolle und enthält vordefinierte Richtlinien und Richtlinieneinstellungen, die die für diese Rolle typischen Zusammenarbeits- und Kommunikationsaktivitäten unterstützen.

Richtlinienpakete unterstützen die folgenden Teams Richtlinientypen:

- Messaging-Richtlinie
- Besprechungsrichtlinie
- App-Setup-Richtlinie
- Anrufrichtlinie
- Richtlinie für Liveereignisse

## <a name="policy-packages-included-in-teams"></a>In Teams enthaltene Richtlinienpakete

Teams umfasst derzeit die folgenden Richtlinienpakete.

| Paketname | Beschreibung |
|---------|---------|
|Bildungseinrichtungen (Schüler/Studenten)    |Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, die für Schüler/Studenten im Bildungsbereich gelten.|
|Education (Schüler der Primären Schule)   |Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, die für primäre Schüler/Studenten gelten.|
|Bildungseinrichtung (Schüler/Student/in einer weiterführenden Bildungseinrichtung)    |Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, die für sekundäre Schüler/Studenten gelten.         |
|Bildungseinrichtungen (Lehrer)    |Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, die für Lehrer gelten.      |
|Bildungseinrichtungen (Lehrer in der Primären Schule mit Remote learning)    |Erstellt eine Reihe von Richtlinien, die für primäre Lehrer gelten, um die Sicherheit und Zusammenarbeit der Schüler bei Verwendung von Fernunterricht zu maximieren.      |
|Bildungseinrichtungen (Schüler der Primären Schule, die Remote learning verwenden)    |Erstellt eine Reihe von Richtlinien, die für primäre Schüler gelten, um die Sicherheit und Zusammenarbeit der Schüler bei Verwendung von Remote learning zu maximieren.      |
|Vorgesetzter in Service und Produktion |Erstellt eine Reihe von Richtlinien und wendet diese Einstellungen auf Vorgesetzte in Ihrer Organisation an. |
|Mitarbeiter in Service und Produktion |Erstellt eine Reihe von Richtlinien und wendet diese Einstellungen auf Mitarbeiter in Service und Produktion in Ihrer Organisation an. |
|Klinikmitarbeiter im Gesundheitswesen  |Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, die Klinikmitarbeitern, z. B. registrierten Ärzt/inn/en, Ärzt/inn/en, und Mitarbeitern des Sozialen Vollzugriffs auf Chats, Anrufe, Schichtverwaltung und Besprechungen ermöglichen. |
|Information Worker im Gesundheitswesen  |Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, die Information Workern wie IT-Personal, Personal der Abteilungen, Finanzmitarbeitern und Compliance-Beauftragten den vollständigen Zugriff auf Chats, Anrufe und Besprechungen gewähren.|
|Patientenraum im Gesundheitswesen  |Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, die für Patientenräume in Ihrer Organisation im Gesundheitswesen gelten.|
|Kleine und mittlere Unternehmen (Business Voice) |Erstellt eine App-Einrichtungsrichtlinie, die die Apps für eine Business Voice-Umgebung enthält.|
|Kleine und mittlere Unternehmen (ohne Business Voice) |Erstellt eine App-Einrichtungsrichtlinie, die für kleine und mittelständische Unternehmen Teams Benutzer relevant ist (Nicht-Business Voice-Erfahrung).
|Öffentlicher Sicherheitsbeauftragter   |Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, die für öffentliche Sicherheitsbeauftragte in Ihrer Organisation gelten.|

> [!NOTE]
> Wir werden in zukünftigen Versionen von Teams weitere Richtlinienpakete hinzufügen. Schauen Sie sich daher die aktuellsten Informationen an.  

Jede einzelne Richtlinie erhält den Namen des Richtlinienpakets, damit Sie die Richtlinien, die mit einem Richtlinienpaket verknüpft sind, leicht identifizieren können.
Wenn Sie z. B. Lehrern in Ihrer Schule das Richtlinienpaket "Bildung" zuweisen, wird für jede Richtlinie im Paket eine Richtlinie mit dem Namen Education_Teacher erstellt.

![Screenshot des Richtlinienpakets für Bildungseinrichtungen (Lehrer)](media/policy-packages-education_teacher.png)

## <a name="custom-policy-packages"></a>Benutzerdefinierte Richtlinienpakete

**Benutzerdefinierte Richtlinienpakete sind für die Government Community Cloud noch nicht verfügbar (GCC)**

Mit benutzerdefinierten Richtlinienpaketen können Sie Ihre eigenen Richtlinien für Benutzer mit ähnlichen Rollen in Ihrer Organisation bündeln. Erstellen Sie Ihre eigenen Richtlinienpakete, indem Sie die benötigten Richtlinientypen und Richtlinien hinzufügen.

So erstellen Sie ein neues benutzerdefiniertes Richtlinienpaket:

1. Wählen Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers **Richtlinienpakete aus,** und klicken Sie dann auf **"Hinzufügen".**

    :::image type="content" source="media/policy-packages-add.png" alt-text="Screenshot der Schaltfläche "Hinzufügen" auf der Seite "Richtlinienpakete" im Admin Center":::

2. Geben Sie einen Namen und eine Beschreibung für Ihr Paket ein.

    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="Screenshot des Hinzufügens eines neuen benutzerdefinierten Richtlinienpakets":::

3. Wählen Sie die Richtlinientypen und Richtliniennamen aus, die in das Paket aufgenommen werden sollen.

4. Klicken Sie auf **Speichern**.

## <a name="how-to-use-policy-packages"></a>Verwenden von Richtlinienpaketen

Im Folgenden wird die Verwendung von Richtlinienpaketen in Ihrer Organisation beschrieben.

![Übersicht über die Verwendung von Richtlinienpaketen](media/manage-policy-packages-overview.png)

- **[Ansicht:](#view-the-settings-of-a-policy-in-a-policy-package)** Anzeigen der Richtlinien in einem Richtlinienpaket. Zeigen Sie dann die Einstellungen jeder Richtlinie in einem Paket an, bevor Sie das Paket zuweisen. Stellen Sie sicher, dass Sie die einzelnen Einstellungen verstehen. Entscheiden Sie, ob die vordefinierten Werte für Ihre Organisation geeignet sind oder ob Sie sie je nach den Anforderungen Ihrer Organisation restriktiver oder lenienter gestalten müssen.

    Wenn eine Richtlinie gelöscht wird, können Sie die Einstellungen weiterhin anzeigen, aber Sie können keine Einstellungen ändern. Eine gelöschte Richtlinie wird mit den vordefinierten Einstellungen neu erstellt, wenn Sie das Richtlinienpaket zuweisen.

- **[Anpassen:](#customize-policies-in-a-policy-package)** Passen Sie die Einstellungen von Richtlinien im Richtlinienpaket an die Anforderungen Ihrer Organisation an.

- **[Zuweisen:](#assign-a-policy-package)** Weisen Sie benutzern das Richtlinienpaket zu.  

> [!NOTE]
> Sie können auch die Einstellungen von Richtlinien in einem Richtlinienpaket ändern, nachdem Sie ein Paket zugewiesen haben. Alle Änderungen, die Sie an Richtlinieneinstellungen vornehmen, werden automatisch auf Benutzer angewendet, denen das Paket zugewiesen ist.

Hier sind die Schritte zum Anzeigen, Zuweisen und Anpassen von Richtlinienpaketen im Microsoft Teams Admin Center.

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a>Anzeigen der Einstellungen einer Richtlinie in einem Richtlinienpaket

1. Wählen Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers **Richtlinienpakete** aus, und wählen Sie dann ein Richtlinienpaket aus, indem Sie links neben dem Paketnamen klicken.

2. Klicken Sie auf die Richtlinie, die Sie anzeigen möchten.

### <a name="customize-policies-in-a-policy-package"></a>Anpassen von Richtlinien in einem Richtlinienpaket

Sie können die Einstellungen einer Richtlinie über die Seite **"Richtlinienpakete"** oder direkt zur Richtlinienseite im Microsoft Teams Admin Center bearbeiten.

1. Führen Sie im linken Navigationsbereich des Microsoft Teams Admin Centers die folgenden Schritte aus:
    - Klicken Sie auf **"Richtlinienpakete",** und wählen Sie dann das Richtlinienpaket aus, indem Sie links neben dem Paketnamen klicken.
    - Klicken Sie auf den Richtlinientyp.  Klicken Sie beispielsweise auf **Nachrichtenrichtlinien.**

2. Wählen Sie die Richtlinie aus, die Sie bearbeiten möchten. Richtlinien, die mit einem Richtlinienpaket verknüpft sind, haben denselben Namen wie das Richtlinienpaket.

3. Nehmen Sie die gewünschten Änderungen vor, und klicken Sie dann auf **"Speichern".**

### <a name="assign-a-policy-package"></a>Zuweisen eines Richtlinienpakets

Sie können einem einzelnen Benutzer, einer Gruppe oder einer Benutzergruppe ein Richtlinienpaket zuweisen. Weitere Informationen zum Zuweisen von Richtlinienpaketen finden Sie unter [Zuweisen von Richtlinienpaketen zu Benutzern und Gruppen.](assign-policy-packages.md)

## <a name="related-topics"></a>Verwandte Themen

- [Richtlinienpakete zuweisen](assign-policy-packages.md)
- [Teams Richtlinienpakete für EDU-Administratoren](policy-packages-edu.md)
- [Teams-Richtlinienpakete für das Gesundheitswesen](policy-packages-healthcare.md)
- [Teams-Richtlinienpakete für Behörden](policy-packages-gov.md)
