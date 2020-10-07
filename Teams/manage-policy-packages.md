---
title: Verwalten von Richtlinien Paketen in Microsoft Teams
author: lanachin
ms.author: v-lanac
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
description: Hier erfahren Sie, wie Sie Richtlinien Pakete in Microsoft Teams verwenden und verwalten, um die Konsistenz beim Verwalten von Richtlinien für Benutzergruppen zu vereinfachen, zu rationalisieren und zu gewährleisten.
ms.openlocfilehash: 866183442d21ad91a83f3e9460ccd257902a0972
ms.sourcegitcommit: f4f5ad1391b472d64390180c81c2680f011a8a10
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/06/2020
ms.locfileid: "48370591"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a>Verwalten von Richtlinien Paketen in Microsoft Teams

> [!NOTE]
> Eines der in diesem Artikel beschriebenen Features, [benutzerdefinierte Richtlinien Pakete](#custom-policy-packages), wurde noch nicht veröffentlicht. Es kommt bald zur privaten Vorschau.

Ein Richtlinienpaket in Microsoft Teams ist eine Sammlung vordefinierter Richtlinien und Richtlinieneinstellungen, die Sie Benutzern zuweisen können, die ähnliche Rollen in Ihrer Organisation aufweisen. Wir haben Richtlinien Pakete entwickelt, um die Konsistenz beim Verwalten von Richtlinien für Gruppen von Benutzern in Ihrer Organisation zu vereinfachen, zu rationalisieren und zu gewährleisten.  

Sie können die [in Teams enthaltenen Richtlinien Pakete](#policy-packages-included-in-teams) verwenden oder [eigene benutzerdefinierte Richtlinien Pakete](#custom-policy-packages) (in der privaten Vorschau) erstellen.

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="Screenshot der Seite "Richtlinien Pakete" im Admin Center":::

Sie können die Einstellungen der Richtlinien in einem Richtlinienpaket so anpassen, dass Sie den Anforderungen Ihrer Benutzer entsprechen. Wenn Sie die Einstellungen von Richtlinien in einem Paket ändern, erhalten alle Benutzer, die diesem Paket zugewiesen sind, die aktualisierten Einstellungen. Sie verwalten Richtlinien Pakete mithilfe des Microsoft Teams Admin Center oder PowerShell.

## <a name="what-is-a-policy-package"></a>Was ist ein Richtlinienpaket?

Mit Richtlinien Paketen können Sie die Teamfunktionen steuern, die Sie für bestimmte Gruppen von Personen in Ihrer Organisation zulassen oder einschränken möchten. Jedes Richtlinienpaket in Teams ist auf eine Benutzerrolle zugeschnitten und enthält vordefinierte Richtlinien und Richtlinieneinstellungen, die die für diese Rolle typischen Aktivitäten für Zusammenarbeit und Kommunikation unterstützen.

Richtlinien Pakete unterstützen die folgenden Teams-Richtlinientypen:

- Messagingrichtlinie
- Besprechungsrichtlinie
- App-Setup Richtlinie
- Anrufrichtlinie
- Richtlinie für Liveereignisse

## <a name="policy-packages-included-in-teams"></a>In Teams enthaltene Richtlinien Pakete

Teams umfasst derzeit die folgenden Richtlinien Pakete.

|**Paket Name**  |**Beschreibung** |
|---------|---------|
|Bildung (Hochschulstudent)    |Erstellt einen Satz von Richtlinien und Richtlinieneinstellungen, die für Schüler in der Hochschulbildung gelten.|
|Education (Primary School Student)   |Erstellt einen Satz von Richtlinien und Richtlinieneinstellungen, die für primäre Kursteilnehmer gelten.|
|Bildung (Secondary School Student)    |Erstellt einen Satz von Richtlinien und Richtlinieneinstellungen, die für sekundäre Kursteilnehmer gelten.         |
|Bildung (Lehrer)    |Erstellt einen Satz von Richtlinien und Richtlinieneinstellungen, die für Lehrer gelten.      |
|Bildung (Grundschullehrer mit Remote-lernen)    |Erstellt eine Reihe von Richtlinien, um die Sicherheit und Zusammenarbeit der Lehrkräfte beim Lernen per Fernzugriff zu maximieren.      |
|Education (Primary School Student using Remote Learning)    |Erstellt eine Reihe von Richtlinien, um die Sicherheit und Zusammenarbeit der Schüler beim Lernen per Fernzugriff zu maximieren.      |
|First-Manager |Erstellt eine Reihe von Richtlinien und wendet diese Einstellungen auf First-Manager in Ihrer Organisation an. |
|First-Worker |Erstellt eine Reihe von Richtlinien und wendet diese Einstellungen auf Mitarbeiter in Ihrer Organisation in erster Linie an. |
|Klinischer Mitarbeiter im Gesundheitswesen  |Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, die klinischen Mitarbeitern wie registrierten Krankenschwestern, Krankenschwestern, Ärzten und Sozialarbeitern vollen Zugriff auf Chats, Anrufe, Schicht Verwaltung und Besprechungen ermöglichen. |
|Healthcare Information Worker  |Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, die Information Worker wie IT-Personal, Informatik Personal, Finanz Personal und Compliance Officer, vollständigen Zugriff auf Chats, Anrufe und Besprechungen bereitstellen.|
|Patientenzimmer im Gesundheitswesen  |Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, die für Patienten Räume in Ihrer Gesundheitsorganisation gelten.|
|Benutzer für kleine und mittelständische Unternehmen (Business-VoIP) |Erstellt eine APP-Setup-Richtlinie, die die apps für ein Business-VoIP-Erlebnis umfasst.|
|Benutzer für kleine und mittelständische Unternehmen (ohne Business-VoIP) |Erstellt eine Richtlinie für die APP-Einrichtung, die für Benutzer von kleinen und mittleren Unternehmen relevant ist (Non-Business-VoIP-Erfahrung).
|Beauftragter für öffentliche Sicherheit   |Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, die für öffentliche Sicherheitsbeauftragte in Ihrer Organisation gelten.|

> [!NOTE]
> Es werden weitere Richtlinien Pakete in zukünftigen Versionen von Teams hinzugefügt, daher sollten Sie sich über die neuesten Informationen informieren.  

Jede einzelne Richtlinie erhält den Namen des Richtlinienpakets, sodass Sie die Richtlinien, die mit einem Richtlinienpaket verknüpft sind, einfach identifizieren können.
Wenn Sie beispielsweise Lehrern in ihrer Schule das Richtlinienpaket Education (Lehrer) zuweisen, wird eine Richtlinie mit dem Namen Education_Teacher für jede Richtlinie im Paket erstellt.

![Screenshot des Richtlinienpakets Education (Lehrer)](media/policy-packages-education_teacher.png)

## <a name="custom-policy-packages"></a>Benutzerdefinierte Richtlinien Pakete

**Dieses Feature befindet sich in der privaten Vorschau**

Mit benutzerdefinierten Richtlinien Paketen können Sie Ihren eigenen Satz von Richtlinien für Benutzer mit ähnlichen Rollen in Ihrer Organisation bündeln. Erstellen Sie eigene Richtlinien Pakete, indem Sie die erforderlichen Richtlinientypen und Richtlinien hinzufügen.

So erstellen Sie ein neues benutzerdefiniertes Richtlinienpaket:

1. Wählen Sie in der linken Navigationsleiste des Microsoft Teams admin Centers **Richtlinien Pakete**aus, und klicken Sie dann auf **Hinzufügen**.
    :::image type="content" source="media/policy-packages-add.png" alt-text="Screenshot der Schaltfläche "hinzufügen" auf der Seite "Richtlinien Pakete" im Admin Center":::
2. Geben Sie einen Namen und eine Beschreibung für Ihr Paket ein.
    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="Screenshot des Hinzufügens eines neuen benutzerdefinierten Richtlinienpakets":::
3. Wählen Sie die Richtlinientypen und Richtliniennamen aus, die in das Paket eingeschlossen werden sollen.
4. Klicken Sie auf **Speichern**.

## <a name="how-to-use-policy-packages"></a>Verwenden von Richtlinien Paketen

Im folgenden wird beschrieben, wie Sie Richtlinien Pakete in Ihrer Organisation verwenden.

![Übersicht über das Verwenden von Richtlinien Paketen](media/manage-policy-packages-overview.png)

- **[Ansicht](#view-the-settings-of-a-policy-in-a-policy-package)**: zeigen Sie die Richtlinien in einem Richtlinienpaket an. Zeigen Sie dann die Einstellungen der einzelnen Richtlinien in einem Paket an, bevor Sie das Paket zuweisen. Stellen Sie sicher, dass Sie die einzelnen Einstellungen verstehen. Entscheiden Sie, ob die vordefinierten Werte für Ihre Organisation geeignet sind, oder ob Sie Sie entsprechend den Anforderungen Ihrer Organisation restriktiver oder nachsichtig ändern müssen.

    Wenn eine Richtlinie gelöscht wird, können Sie weiterhin die Einstellungen anzeigen, aber Sie können keine Einstellungen ändern. Eine gelöschte Richtlinie wird mit den vordefinierten Einstellungen neu erstellt, wenn Sie das Richtlinienpaket zuweisen.

- **[Anpassen](#customize-policies-in-a-policy-package)**: passen Sie die Einstellungen der Richtlinien im Richtlinienpaket an die Anforderungen Ihrer Organisation an.

- **[Zuweisen](#assign-a-policy-package)**: weisen Sie das Richtlinienpaket Benutzern zu.  

> [!NOTE]
> Sie können auch die Einstellungen von Richtlinien in einem Richtlinienpaket ändern, nachdem Sie ein Paket zugewiesen haben. Alle Änderungen, die Sie an Richtlinieneinstellungen vornehmen, werden automatisch auf Benutzer angewendet, denen das Paket zugewiesen ist.

Im folgenden finden Sie die Schritte zum Anzeigen, zuweisen und Anpassen von Richtlinien Paketen im Microsoft Teams Admin Center.

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a>Anzeigen der Einstellungen einer Richtlinie in einem Richtlinienpaket

1. Wählen Sie in der linken Navigationsleiste des Microsoft Teams admin Centers **Richtlinien Pakete**aus, und wählen Sie dann ein Richtlinienpaket aus, indem Sie links neben dem Paketnamen klicken.
2. Klicken Sie auf die Richtlinie, die Sie anzeigen möchten.

### <a name="customize-policies-in-a-policy-package"></a>Anpassen von Richtlinien in einem Richtlinienpaket

Sie können die Einstellungen einer Richtlinie über die Seite " **Richtlinien Pakete** " Bearbeiten oder direkt zur Seite "Richtlinie" im Microsoft Teams Admin Center wechseln.

1. Führen Sie in der linken Navigationsleiste des Microsoft Teams Admin Center eine der folgenden Aktionen aus:
    - Klicken Sie auf **Richtlinien Pakete**, und wählen Sie dann das Richtlinienpaket aus, indem Sie links neben dem Paketnamen klicken.
    - Klicken Sie auf den Richtlinientyp.  Klicken Sie beispielsweise auf **Messaging Richtlinien**.
2. Wählen Sie die Richtlinie aus, die Sie bearbeiten möchten. Richtlinien, die mit einem Richtlinienpaket verknüpft sind, haben denselben Namen wie das Richtlinienpaket.
3. Nehmen Sie die gewünschten Änderungen vor, und klicken Sie dann auf **Speichern**.

### <a name="assign-a-policy-package"></a>Zuweisen eines Richtlinienpakets

#### <a name="assign-a-policy-package-to-one-user"></a>Zuweisen eines Richtlinienpakets zu einem Benutzer

1. Wechseln Sie in der linken Navigation des Microsoft Teams Admin Centers zu **Nutzer**, und klicken Sie dann den gewünschten Nutzer an.
2. Klicken Sie auf der Seite des Benutzers auf **Richtlinien**, und klicken Sie dann neben **Richtlinienpaket**auf **Bearbeiten**.
3. Wählen Sie im Bereich **Richtlinienpaket zuweisen** das Paket aus, das Sie zuweisen möchten, und klicken Sie dann auf **Speichern**.

#### <a name="assign-a-policy-package-to-multiple-users"></a>Zuweisen eines Richtlinienpakets zu mehreren Benutzern

1. Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Richtlinien Paketen**, und wählen Sie dann das Richtlinienpaket aus, das Sie zuweisen möchten, indem Sie links neben dem Paketnamen klicken.
2. Klicken Sie auf **Benutzer verwalten**.
3. Suchen Sie im Bereich **Nutzer verwalten** anhand des Anzeigenamens oder des Nutzernamens nach dem Nutzer, wählen Sie den Namen und dann **Hinzufügen** aus. Wiederholen Sie diesen Schritt für jeden Nutzer, den Sie hinzufügen möchten.
4. Wenn Sie alle gewünschten Benutzer hinzugefügt haben, klicken Sie auf **Speichern**.

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a>Zuweisen eines Richtlinienpakets zu einem umfangreichen Satz (Batch) von Benutzern

Verwenden Sie die Batch Richtlinien-Paket Zuweisung, um einem Richtlinienpaket große Gruppen von Benutzern gleichzeitig zuzuweisen. Sie verwenden das Cmdlet [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) , um einen Benutzer Batch und das Richtlinienpaket, das Sie zuweisen möchten, zu übermitteln. Die Aufgaben werden als Hintergrundvorgang verarbeitet, und für jeden Batch wird eine Vorgangs-ID generiert.

Ein Batch kann bis zu 5.000-Benutzer enthalten. Sie können Benutzer anhand ihrer Objekt-ID, Ihres UPN, ihrer SIP-Adresse oder Ihrer e-Mail-Adresse angeben. Weitere Informationen finden Sie unter [Zuweisen eines Richtlinienpakets zu einem Batch von Benutzern](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).

## <a name="troubleshooting"></a>Problembehandlung

**Beim Zuweisen eines Richtlinienpakets wird eine Fehlermeldung angezeigt**

Dies kann auftreten, wenn eine oder mehrere Richtlinien im Paket nicht erstellt oder erfolgreich angewendet wurden. Weisen Sie den Benutzern das Richtlinienpaket erneut zu. Das erneute Testen des Vorgangs behebt dieses Problem in der Regel.

## <a name="related-topics"></a>Verwandte Themen

[Zuweisen von Richtlinien zu Ihren Benutzern in Microsoft Teams](assign-policies.md)

[Teams-Richtlinien Pakete für edu-Administratoren](policy-packages-edu.md)

[Teams-Richtlinien Pakete für Healthcare](policy-packages-healthcare.md)

[Teams-Richtlinien Pakete für Behörden](policy-packages-gov.md)
