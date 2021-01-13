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
description: Erfahren Sie, wie Sie Richtlinienpakete in Microsoft Teams verwenden und verwalten, um die Verwaltung von Richtlinien für Benutzergruppen zu vereinfachen, zu optimieren und für Einheitlichkeit zu sorgen.
ms.openlocfilehash: 62250644d29f65a9c650db0e80477eec6baf4f3d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49839450"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a>Verwalten von Richtlinienpaketen in Microsoft Teams

> [!NOTE]
> Eines der in diesem Artikel erläuterten Features, benutzerdefinierte [Richtlinienpakete,](#custom-policy-packages)befindet sich derzeit in der privaten Vorschau.

Ein Richtlinienpaket in Microsoft Teams ist eine Sammlung vordefinierter Richtlinien und Richtlinieneinstellungen, die Sie Benutzern zuweisen können, die ähnliche Rollen in Ihrer Organisation haben. Wir haben Richtlinienpakete erstellt, um die Benutzer zu vereinfachen, zu rationalisieren und die Konsistenz beim Verwalten von Richtlinien für Benutzergruppen in der gesamten Organisation zu gewährleisten.  

Sie können die in Teams enthaltenen [Richtlinienpakete verwenden](#policy-packages-included-in-teams) oder eigene benutzerdefinierte Richtlinienpakete [(in](#custom-policy-packages) der privaten Vorschau) erstellen.

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="Screenshot der Seite "Richtlinienpakete" im Admin Center":::

Sie können die Einstellungen der Richtlinien in einem Richtlinienpaket an die Anforderungen Ihrer Benutzer anpassen. Wenn Sie die Einstellungen von Richtlinien in einem Paket ändern, erhalten alle Benutzer, denen dieses Paket zugewiesen ist, die aktualisierten Einstellungen. Sie verwalten Richtlinienpakete über das Microsoft Teams Admin Center oder PowerShell.

## <a name="what-is-a-policy-package"></a>Was ist ein Richtlinienpaket?

Mit Richtlinienpaketen können Sie die Features von Teams steuern, die Sie für bestimmte Personengruppen in Ihrer Organisation zulassen oder einschränken möchten. Jedes Richtlinienpaket in Teams ist auf eine Benutzerrolle ausgelegt und enthält vordefinierte Richtlinien und Richtlinieneinstellungen, die für diese Rolle typische Zusammenarbeits- und Kommunikationsaktivitäten unterstützen.

Richtlinienpakete unterstützen die folgenden Teams-Richtlinientypen:

- Messagingrichtlinie
- Besprechungsrichtlinie
- App-Setup-Richtlinie
- Anrufrichtlinie
- Richtlinie für Liveereignisse

## <a name="policy-packages-included-in-teams"></a>In Teams enthaltene Richtlinienpakete

Teams enthält derzeit die folgenden Richtlinienpakete.

|**Paketname**  |**Beschreibung** |
|---------|---------|
|Bildung (Student im höheren Bildungsbereich)    |Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, die für Studierende an höheren Bildungseinrichtungen gelten.|
|Bildung (Grundschüler)   |Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, die für Hauptschüler gelten.|
|Education (Schüler an sekundären Bildungseinrichtungen)    |Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, die für sekundäre Schüler/Studenten gelten.         |
|Bildung (Lehrer)    |Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, die für Lehrkräfte gelten.      |
|Bildung (Lehrkraft an einer Grundschule mithilfe von Fernunterricht)    |Erstellt eine Reihe von Richtlinien, um die Sicherheit und Zusammenarbeit der Lehrkräfte beim Lernen per Fernzugriff zu maximieren.      |
|Bildung (Grundschüler mit Fernunterricht)    |Erstellt eine Reihe von Richtlinien, um die Sicherheit und Zusammenarbeit der Schüler beim Lernen per Fernzugriff zu maximieren.      |
|Firstline Manager |Erstellt einen Satz von Richtlinien und wendet diese Einstellungen auf Firstline Manager in Ihrer Organisation an. |
|Mitarbeiter in Firstline |Erstellt einen Satz von Richtlinien und wendet diese Einstellungen auf Firstline Workers in Ihrer Organisation an. |
|Klinischer Mitarbeiter im Gesundheitswesen  |Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, die klinischen Mitarbeitern, z. B. registrierten Krankenschwestern, Krankenschwestern, Ärzten und Sozialarbeitern, vollständigen Zugriff auf Chats, Anrufe, Schichtverwaltung und Besprechungen geben. |
|Information Worker im Gesundheitswesen  |Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, die Information Workers wie IT-Personal, Mitarbeiter, Mitarbeiter der Finanzabteilung und Compliance Officers, vollständigen Zugriff auf Chats, Anrufe und Besprechungen bieten.|
|Patientenzimmer im Gesundheitswesen  |Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, die für Patientenräume in Ihrer Gesundheitsorganisation gelten.|
|Benutzer für kleine und mittelständische Unternehmen (Business Voice) |Erstellt eine App-Setuprichtlinie, die die Apps für eine Unternehmens-Spracherfahrung enthält.|
|Benutzer für kleine und mittelständische Unternehmen (ohne Business Voice) |Erstellt eine App-Setuprichtlinie, die für Benutzer von Teams für kleine und mittelständische Unternehmen relevant ist (nicht für die Spracherfahrung in Unternehmen).
|Public Safety Officer   |Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, die für öffentliche Sicherheitsbeauftragte in Ihrer Organisation gelten.|

> [!NOTE]
> Wir werden in zukünftigen Versionen von Teams weitere Richtlinienpakete hinzufügen. Sehen Sie sich also die neuesten Informationen an.  

Jede einzelne Richtlinie wird mit dem Namen des Richtlinienpakets bezeichnet, sodass Sie die Mit einem Richtlinienpaket verknüpften Richtlinien leicht erkennen können.
Wenn Sie beispielsweise Lehrkräften in Ihrer Schule das Richtlinienpaket für Bildungseinrichtungen (Lehrer) zuweisen, wird für jede Richtlinie im Paket eine Richtlinie mit dem Namen Education_Teacher erstellt.

![Screenshot des Richtlinienpakets für Bildungseinrichtungen (Lehrer)](media/policy-packages-education_teacher.png)

## <a name="custom-policy-packages"></a>Benutzerdefinierte Richtlinienpakete

**Dieses Feature ist derzeit lediglich als private Vorschau verfügbar**

Mit benutzerdefinierten Richtlinienpaketen können Sie Eigene Richtlinien für Benutzer mit ähnlichen Rollen in Ihrer Organisation bündeln. Erstellen Sie eigene Richtlinienpakete, indem Sie die benötigten Richtlinientypen und Richtlinien hinzufügen.

So erstellen Sie ein neues benutzerdefiniertes Richtlinienpaket:

1. Wählen Sie im linken Navigationsbereich des Microsoft Teams Admin Centers "Richtlinienpakete" aus, und klicken Sie dann auf **"Hinzufügen".**
    :::image type="content" source="media/policy-packages-add.png" alt-text="Screenshot der Schaltfläche "Hinzufügen" auf der Seite "Richtlinienpakete" im Admin Center":::
2. Geben Sie einen Namen und eine Beschreibung für ihr Paket ein.
    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="Screenshot zum Hinzufügen eines neuen benutzerdefinierten Richtlinienpakets":::
3. Wählen Sie die Richtlinientypen und Richtliniennamen aus, die in das Paket enthalten sein müssen.
4. Klicken Sie auf **Speichern**.

## <a name="how-to-use-policy-packages"></a>Verwenden von Richtlinienpaketen

Im Folgenden wird die Verwendung von Richtlinienpaketen in Ihrer Organisation erläutert.

![Übersicht über die Verwendung von Richtlinienpaketen](media/manage-policy-packages-overview.png)

- **[Ansicht:](#view-the-settings-of-a-policy-in-a-policy-package)** Anzeigen der Richtlinien in einem Richtlinienpaket. Zeigen Sie dann die Einstellungen jeder Richtlinie in einem Paket an, bevor Sie das Paket zuweisen. Stellen Sie sicher, dass Sie die einzelnen Einstellungen verstehen. Entscheiden Sie, ob die vordefinierten Werte für Ihre Organisation geeignet sind oder ob sie je nach Anforderungen Ihrer Organisation restriktiver oder nachsichtig sein müssen.

    Wenn eine Richtlinie gelöscht wird, können Sie die Einstellungen zwar weiterhin anzeigen, aber keine Einstellungen ändern. Beim Zuweisen des Richtlinienpakets wird eine gelöschte Richtlinie mit den vordefinierten Einstellungen neu erstellt.

- **[Anpassen:](#customize-policies-in-a-policy-package)** Passen Sie die Einstellungen der Richtlinien im Richtlinienpaket an die Anforderungen Ihrer Organisation an.

- **[Zuweisen:](#assign-a-policy-package)** Zuweisen des Richtlinienpakets zu Benutzern.  

> [!NOTE]
> Sie können auch die Einstellungen von Richtlinien in einem Richtlinienpaket ändern, nachdem Sie ein Paket zugewiesen haben. Alle Änderungen, die Sie an den Richtlinieneinstellungen vornehmen, werden automatisch auf Benutzer angewendet, denen das Paket zugewiesen wird.

Hier sind die Schritte zum Anzeigen, Zuweisen und Anpassen von Richtlinienpaketen im Microsoft Teams Admin Center.

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a>Anzeigen der Einstellungen einer Richtlinie in einem Richtlinienpaket

1. Wählen Sie im linken Navigationsbereich des Microsoft Teams Admin Centers "Richtlinienpakete" **aus,** und wählen Sie dann ein Richtlinienpaket aus, indem Sie links neben dem Paketnamen klicken.
2. Klicken Sie auf die Richtlinie, die Sie anzeigen möchten.

### <a name="customize-policies-in-a-policy-package"></a>Anpassen von Richtlinien in einem Richtlinienpaket

Sie können die Einstellungen einer  Richtlinie über die Seite "Richtlinienpakete" bearbeiten oder direkt zur Richtlinienseite im Microsoft Teams Admin Center gelangen.

1. Gehen Sie im linken Navigationsbereich des Microsoft Teams Admin Centers wie folgt vor:
    - Klicken **Sie auf "Richtlinienpakete",** und wählen Sie dann das Richtlinienpaket aus, indem Sie links des Paketnamens klicken.
    - Klicken Sie auf den Richtlinientyp.  Klicken Sie beispielsweise auf **"Messagingrichtlinien".**
2. Wählen Sie die Richtlinie aus, die Sie bearbeiten möchten. Richtlinien, die mit einem Richtlinienpaket verknüpft sind, haben denselben Namen wie das Richtlinienpaket.
3. Nehmen Sie die von Ihnen vorgenommenen Änderungen vor, und klicken Sie dann auf **"Speichern".**

### <a name="assign-a-policy-package"></a>Zuweisen eines Richtlinienpakets 

#### <a name="assign-a-policy-package-to-one-user"></a>Zuweisen eines Richtlinienpakets zu einem Benutzer

1. Wechseln Sie in der linken Navigation des Microsoft Teams Admin Centers zu **Nutzer**, und klicken Sie dann den gewünschten Nutzer an.
2. Klicken Sie auf der Seite des Benutzers auf  "Richtlinien", und klicken Sie dann neben "Richtlinienpaket" auf **"Bearbeiten".**
3. Wählen Sie **im Bereich "Richtlinienpaket zuweisen"** das Paket aus, das Sie zuweisen möchten, und klicken Sie dann auf **"Speichern".**

#### <a name="assign-a-policy-package-to-multiple-users"></a>Zuweisen eines Richtlinienpakets zu mehreren Benutzern

1. Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu "Richtlinienpakete", und wählen Sie dann das Richtlinienpaket aus, das Sie zuweisen möchten, indem Sie links neben dem Paketnamen klicken.
2. Klicken Sie **auf "Benutzer verwalten".**
3. Suchen Sie im Bereich **Nutzer verwalten** anhand des Anzeigenamens oder des Nutzernamens nach dem Nutzer, wählen Sie den Namen und dann **Hinzufügen** aus. Wiederholen Sie diesen Schritt für jeden Nutzer, den Sie hinzufügen möchten.
4. Wenn Sie alle gewünschten Benutzer hinzugefügt haben, klicken Sie auf **Speichern**.

#### <a name="assign-a-policy-package-to-a-group"></a>Ein Richtlinienpaket einer Gruppe zuweisen

**Dieses Feature ist derzeit lediglich als private Vorschau verfügbar**

Die Gruppenzuweisung von Richtlinienpaketen ermöglicht es Ihnen, mehrere Richtlinien einer Gruppe von Benutzern wie z. B. einer Sicherheitsgruppe oder einer Verteilerliste zuzuweisen. Die Richtlinienzuweisung wird anhand von Prioritätsregeln an die Mitglieder der Gruppe weitergegeben. Wenn Mitglieder einer Gruppe hinzugefügt oder daraus entfernt werden, werden ihre geerbten Richtlinienzuweisungen entsprechend aktualisiert. Diese Methode wird für Gruppen mit bis zu 50.000 Benutzern empfohlen, sie eignet sich aber auch für größere Gruppen.

Weitere Informationen hierzu finden Sie unter [Ein Richtlinienpaket einer Gruppe zuweisen](assign-policies.md#assign-a-policy-package-to-a-group).

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a>Ein Richtlinienpaket einer großen Anzahl von Benutzern (Batch) zuweisen

Wenn Sie ein Richtlinienpaket einer großen Anzahl von Benutzern gleichzeitig zuweisen möchten, verwenden Sie hierfür die Richtlinienpaket-Batch-Zuweisung. Verwenden Sie das Cmdlet [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation), um einen Benutzer-Batch und das Richtlinienpaket zu senden, das Sie zuweisen möchten. Die Zuweisungen werden als Hintergrundvorgänge verarbeitet, und für jeden Batch wird eine Vorgangs-ID generiert.

Ein Batch kann bis zu 5.000 Benutzer umfassen. Sie können Benutzer durch Angabe ihrer Objekt-ID, des UPN, der SIP-Adresse oder der E-Mail-Adresse hinzufügen. Weitere Informationen hierzu finden Sie unter [Ein Richtlinienpaket einem Batch von Benutzern zuweisen](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).

## <a name="troubleshooting"></a>Problembehandlung

**Beim Zuweisen eines Richtlinienpakets wird eine Fehlermeldung angezeigt**

Dies kann vorkommen, wenn eine oder mehrere Richtlinien im Paket nicht erstellt oder erfolgreich angewendet wurden. Zuweisen des Richtlinienpakets zu Ihren Benutzern Durch das Wiederholen des Vorgangs wird dieses Problem in der Regel behoben.

## <a name="related-topics"></a>Verwandte Themen

[Benutzern in Microsoft Teams Richtlinien zuweisen](assign-policies.md)

[Richtlinienpakete für Teams für EDU-Administratoren](policy-packages-edu.md)

[Richtlinienpakete für Teams im Gesundheitswesen](policy-packages-healthcare.md)

[Richtlinienpakete für Teams für Behörden](policy-packages-gov.md)
