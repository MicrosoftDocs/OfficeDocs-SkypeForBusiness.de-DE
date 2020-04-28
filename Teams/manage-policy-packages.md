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
ms.openlocfilehash: b69ce06d01af624ff73386531d7ef2b77bef3b4e
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2020
ms.locfileid: "43914069"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a>Verwalten von Richtlinien Paketen in Microsoft Teams

Ein Richtlinienpaket in Microsoft Teams ist eine Sammlung vordefinierter Richtlinien und Richtlinieneinstellungen, die Sie Benutzern zuweisen können, die ähnliche Rollen in Ihrer Organisation aufweisen. Wir haben Richtlinien Pakete entwickelt, um die Konsistenz beim Verwalten von Richtlinien für Gruppen von Benutzern in Ihrer Organisation zu vereinfachen, zu rationalisieren und zu gewährleisten.  

Wenn Sie Benutzern ein Richtlinienpaket zuweisen, werden die Richtlinien im Paket erstellt, und Sie können dann die Einstellungen der Richtlinien im Paket anpassen, um die Anforderungen Ihrer Organisation zu erfüllen.

Richtlinien Pakete sind für Organisationen der US Government Cloud Community (gcc) nicht verfügbar.

## <a name="what-is-a-policy-package"></a>Was ist ein Richtlinienpaket?

Mit Richtlinien Paketen können Sie die Teamfunktionen steuern, die Sie für bestimmte Gruppen von Personen in Ihrer Organisation zulassen oder einschränken möchten. Jedes Richtlinienpaket in Teams ist auf eine Benutzerrolle zugeschnitten und enthält vordefinierte Richtlinien und Richtlinieneinstellungen, die die für diese Rolle typischen Aktivitäten für Zusammenarbeit und Kommunikation unterstützen.

Teams umfasst derzeit die folgenden Richtlinien Pakete.

|**Paket Name**  |**Beschreibung** |
|---------|---------|
|Bildung (Hochschulstudent)    |Erstellt einen Satz von Richtlinien und Richtlinieneinstellungen, die für Schüler in der Hochschulbildung gelten.|
|Education (Primary School Student)   |Erstellt einen Satz von Richtlinien und Richtlinieneinstellungen, die für primäre Kursteilnehmer gelten.|
|Bildung (Secondary School Student)    |Erstellt einen Satz von Richtlinien und Richtlinieneinstellungen, die für sekundäre Kursteilnehmer gelten.         |
|Bildung (Lehrer)    |Erstellt einen Satz von Richtlinien und Richtlinieneinstellungen, die für Lehrer gelten.      |
|Benutzer für kleine und mittelständische Unternehmen (Business-VoIP) |Erstellt eine APP-Setup-Richtlinie, die die apps für ein Business-VoIP-Erlebnis umfasst.|
|Benutzer für kleine und mittelständische Unternehmen (ohne Business-VoIP) |Dieses Richtlinienpaket wurde entwickelt, um eine Reihe von Richtlinien zu erstellen und diese Einstellungen auf kleine und mittelständische Unternehmen anzuwenden, die über keine geschäftlichen Sprachfeatures verfügen.|
|Beauftragter für öffentliche Sicherheit   |Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, die für öffentliche Sicherheitsbeauftragte in Ihrer Organisation gelten.|
|Gesundheitswesen (klinischer Mitarbeiter)  |Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, die klinischen Mitarbeitern wie registrierten Krankenschwestern, Krankenschwestern, Ärzten und Sozialarbeitern vollen Zugriff auf Chats, Anrufe, Schicht Verwaltung und Besprechungen ermöglichen. |
|Gesundheitswesen (Information Worker)  |Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, die Information Worker wie IT-Personal, Informatik Personal, Finanz Personal und Compliance Officer, vollständigen Zugriff auf Chats, Anrufe und Besprechungen bereitstellen.|


> [!NOTE]
> Es werden weitere Richtlinien Pakete in zukünftigen Versionen von Teams hinzugefügt, daher sollten Sie sich über die neuesten Informationen informieren.  

Jede einzelne Richtlinie erhält den Namen des Richtlinienpakets, sodass Sie die Richtlinien, die mit einem Richtlinienpaket verknüpft sind, einfach identifizieren können.
Wenn Sie beispielsweise Lehrern in ihrer Schule das Richtlinienpaket Education (Lehrer) zuweisen, wird eine Richtlinie mit dem Namen Education_Teacher für jede Richtlinie im Paket erstellt.

![Screenshot des Richtlinienpakets Education (Lehrer)](media/policy-packages-education_teacher.png)

## <a name="how-to-use-policy-packages"></a>Verwenden von Richtlinien Paketen

Im folgenden wird beschrieben, wie Sie Richtlinien Pakete in Ihrer Organisation verwenden.

![Übersicht über das Verwenden von Richtlinien Paketen](media/manage-policy-packages-overview.png)

- **[Ansicht](#view-the-settings-of-a-policy-in-a-policy-package)**: zeigen Sie die Einstellungen der einzelnen Richtlinien in einem Richtlinienpaket an, bevor Sie ein Paket zuweisen. Stellen Sie sicher, dass Sie jede Einstellung verstehen, und entscheiden Sie dann, ob die vordefinierten Werte für Ihre Organisation geeignet sind, oder ob Sie Sie entsprechend den Anforderungen Ihrer Organisation restriktiver oder nachsichtig gestalten müssen.

    Wenn eine Richtlinie gelöscht wird, können Sie weiterhin die Einstellungen anzeigen, aber Sie können keine Einstellungen ändern. Eine gelöschte Richtlinie wird mit den vordefinierten Einstellungen neu erstellt, wenn Sie das Richtlinienpaket zuweisen.

- **[Zuweisen](#assign-a-policy-package)**: weisen Sie das Richtlinienpaket Benutzern zu. Beachten Sie, dass Richtlinien in einem Richtlinienpaket erst erstellt werden, nachdem Sie das Paket zugewiesen haben, nach dem Sie die Einstellungen einzelner Richtlinien im Paket ändern können.  

- **[Anpassen](#customize-policies-in-a-policy-package)**: passen Sie die Einstellungen der Richtlinien im Richtlinienpaket an die Anforderungen Ihrer Organisation an. Alle Änderungen, die Sie an Richtlinieneinstellungen vornehmen, werden automatisch auf Benutzer angewendet, denen das Paket zugewiesen ist.

Im folgenden finden Sie die Schritte zum Anzeigen, zuweisen und Anpassen von Richtlinien Paketen im Microsoft Teams Admin Center.

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a>Anzeigen der Einstellungen einer Richtlinie in einem Richtlinienpaket

1. Klicken Sie in der linken Navigationsleiste des Microsoft Teams admin Centers auf **Richtlinien Pakete**, und wählen Sie dann ein Richtlinienpaket aus, indem Sie links neben dem Paketnamen klicken.
2. Klicken Sie auf die Richtlinie, die Sie anzeigen möchten.

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

### <a name="customize-policies-in-a-policy-package"></a>Anpassen von Richtlinien in einem Richtlinienpaket

Sie können die Einstellungen einer Richtlinie über die Seite " **Richtlinien Pakete** " Bearbeiten oder direkt zur Seite "Richtlinie" im Microsoft Teams Admin Center wechseln.

1. Führen Sie in der linken Navigationsleiste des Microsoft Teams Admin Center eine der folgenden Aktionen aus:
    - Klicken Sie auf **Richtlinien Pakete**, und wählen Sie dann das Richtlinienpaket aus, indem Sie links neben dem Paketnamen klicken.
    - Klicken Sie auf den Richtlinientyp.  Klicken Sie beispielsweise auf **Messaging Richtlinien**.
2. Klicken Sie auf die Richtlinie, die Sie bearbeiten möchten. Richtlinien, die mit einem Richtlinienpaket verknüpft sind, haben denselben Namen wie das Richtlinienpaket.
3. Nehmen Sie die gewünschten Änderungen vor, und klicken Sie dann auf **Speichern**.

## <a name="troubleshooting"></a>Problembehandlung

**Beim Zuweisen eines Richtlinienpakets wird eine Fehlermeldung angezeigt**

Dies kann auftreten, wenn eine oder mehrere Richtlinien im Paket nicht erstellt oder erfolgreich angewendet wurden. Weisen Sie den Benutzern das Richtlinienpaket erneut zu. Das erneute Testen des Vorgangs behebt dieses Problem in der Regel.

## <a name="related-topics"></a>Verwandte Themen

[Microsoft Teams-Richtlinienpakete für EDU-Administratoren](policy-packages-edu.md)
