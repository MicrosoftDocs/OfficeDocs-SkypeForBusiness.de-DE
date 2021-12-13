---
title: Verwenden sie den Onboarding-Assistenten für Frontline Worker, um Die Mitarbeiter an der Frontline mit der Arbeit zu starten
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaglick
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Erfahren Sie, wie Sie mithilfe des Onboarding-Assistenten für Frontline Worker schnell eine Benutzererfahrung in Teams bereitstellen können, die auf Frontline-Mitarbeiter und Manager in Ihrer Organisation zugeschnitten ist.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 056c82b1f2c7a1872693cc9f4298cee6eea1eefb
ms.sourcegitcommit: 11882e93618b8d69d21586c7b1f6a4460b96dd7d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2021
ms.locfileid: "60283029"
---
# <a name="use-the-frontline-worker-onboarding-wizard-to-get-your-frontline-workforce-up-and-running"></a>Verwenden sie den Onboarding-Assistenten für Frontline Worker, um Die Mitarbeiter an der Frontline mit der Arbeit zu starten

## <a name="overview"></a>Übersicht

Der Onboarding-Assistent für Frontline Worker in Microsoft 365 Admin Center Onboarding-Mitarbeiter in Ihrer Organisation vereinfacht. Mit dem Assistenten können Sie schnell eine Benutzererfahrung in Microsoft Teams, die auf Ihre Mitarbeiter in der Frontlinie zugeschnitten ist. Mithilfe des Assistenten können Sie die Pilotbereitstellung von Mitarbeitern Teams Mitarbeitern in der Frontlinie in Ihrer Organisation auf einfache Weise starten.

Der Assistent richtet ein Team für Ihre Frontline-Mitarbeiter ein und weist jedem Teammitglied [Lizenzen](manage-policy-packages.md) und Richtlinienpakete zu. Sie können Ihr Team ganz neu oder aus einer [Teamvorlage](get-started-with-teams-templates-in-the-admin-console.md)erstellen und dann Benutzer hinzufügen und Rollen zuweisen. Die Rolle bestimmt das Richtlinienpaket, das der Assistent jedem Benutzer zu weist.

Derzeit unterstützt der Assistent das Hinzufügen von 100 Benutzern bei jeder Ausführung. Wir arbeiten daran, in Kürze die Anzahl der Benutzer pro Ausführung zu erhöhen. Hier finden Sie die neuesten Updates.

Der Assistent steht allen Organisationen zur Verfügung, die über mindestens eine Lizenz Microsoft 365 F verfügen. Sie können den Assistenten so oft ausführen, wie Sie benötigen, um Teams Mitarbeiter an unterschiedlichen Standorten oder an unterschiedlichen Standorten in ihrer Organisation an vordersten Front zu stellen.

> [!NOTE]
> Mit diesem Assistenten können Sie Ihre Mitarbeiter an vorder frontline schnell integrieren, Teams die Microsoft 365 Admin Center. Informationen zum Bereitstellen von Teams für Ihre Frontline-Workers mithilfe von Skripts finden Sie unter So wird's Teams von Frontline Workers im [Maßstab bereitgestellt.](flw-scripted-deployment.md)

> [!NOTE]
> Vertraulichkeitsbezeichnungen werden vom [Assistenten noch nicht](sensitivity-labels.md) unterstützt. Wenn Ihre Organisation vertraulichkeitsbeschriftungen erfordert, um ein Team zu erstellen, wird der Assistent nicht in der Microsoft 365 Admin Center.

## <a name="run-the-wizard"></a>Ausführen des Assistenten

1. Wählen Sie im linken Navigationsbereich [des Microsoft 365 Admin Center](https://admin.microsoft.com/)die Option **Setup aus.** Wechseln Sie zum **Abschnitt Apps und** E-Mail, und wählen Sie dann unter Erste Mitarbeiter an der **Frontline** mit der Ausführung die Option **Anzeigen aus.** Hier erhalten Sie weitere Informationen zu den Funktionen, die Microsoft 365 Mitarbeitern an vorder frontline bietet.

    :::image type="content" source="media/flw-onboarding-wizard-get-started.png" alt-text="Screenshot der Detailseite für die Onboarding-Erfahrung von Frontline Worker im Microsoft 365 Admin Center":::

2. Wenn Sie fertig sind, wählen Sie **Erste Schritte** aus, um den Assistenten zu starten.

3. Geben Sie einen Namen für Ihr Team ein, fügen Sie einen oder mehrere Teambesitzer hinzu, und wählen Sie eine Datenschutzeinstellung aus. Wählen Sie dann aus, ob Sie Ihr Team ganz neu oder aus einer Teamvorlage erstellen möchten. Teamvorlagen enthalten vordefinierte Kanäle und Registerkarten, die das Team für eine bestimmte Geschäftsbedarf oder ein bestimmtes Projekt optimieren.

    :::image type="content" source="media/flw-onboarding-wizard-set-up-team.png" alt-text="Screenshot der Seite "Team einrichten" des Assistenten":::

4. Hinzufügen von Benutzern zum Team Sie können auch Gruppen hinzufügen. Wenn Sie Gruppen hinzufügen, denken Sie daran, dass Lizenzen und Richtlinienpakete jedem Benutzer in der Gruppe direkt zugewiesen werden, nicht die Gruppe selbst.

    :::image type="content" source="media/flw-onboarding-wizard-add-users.png" alt-text="Screenshot der Seite "Benutzer hinzufügen" des Assistenten, auf der Sie Ihrem Team Benutzer und Gruppen hinzufügen":::

5. Weisen Sie jedem Teammitglied eine der folgenden Rollen zu: Frontline-Worker, Frontline-Manager, Keine. 
  
    :::image type="content" source="media/flw-onboarding-wizard-assign-roles.png" alt-text="Screenshot der Seite "Stellenrollen zuweisen" des Assistenten, auf der Sie Teammitgliedern Rollen, Speicherorte und Lizenzen zuweisen":::

    Durch zuweisen einer Frontline Worker- oder Frontline Manager-Rolle erhält dieser Benutzer ein Richtlinienpaket. Das Richtlinienpaket erstellt eine Benutzererfahrung in Teams, die auf ihre Rolle zugeschnitten ist. Diese Erfahrung umfasst vorinstallierte Apps und Richtlinien für gesunde Frontline-Worker- und Managerkommunikation und -zusammenarbeit.

    Wählen Sie als Nächstes einen Standort aus, und weisen Sie jedem Microsoft 365 F-Lizenz zu. Wenn Sie nicht über genügend Lizenzen verfügen, können Sie Weitere Lizenzen kaufen auswählen, **um** weitere Lizenzen zu erwerben.  

6. Wählen Sie aus, wer die Status-E-Mail erhält, nachdem der Assistent abgeschlossen wurde. Die E-Mail enthält Erfolgs- und Fehlerinformationen zu den Aktionen, die vom Assistenten zum Erstellen des Teams, Hinzufügen von Teammitgliedern sowie Zuweisen eines Lizenz- und Richtlinienpakets zu jedem &mdash; Teammitglied ausgeführt wurden. Verwenden Sie diese Informationen, um eventuell aufgetretene Fehler zu beheben.

    :::image type="content" source="media/flw-onboarding-wizard-email-recipients.png" alt-text="Screenshot der Seite "Status-E-Mail-Empfänger hinzufügen" des Assistenten":::

7. Überprüfen Sie Ihre Auswahl, und wählen Sie dann **Bestätigen aus.**

    :::image type="content" source="media/flw-onboarding-wizard-review-team.png" alt-text="Screenshot der Seite "Team überprüfen" des Assistenten, auf der Sie Ihre Teameinstellungen überprüfen":::

    Der Assistent erstellt Ihr Team und weist Teammitgliedern Lizenzen und Richtlinienpakete zu. Der Vorgang kann einige Minuten dauern, danach erhalten die von Ihnen gewählten Empfänger eine Status-E-Mail.

8. Sie sind auf dem Weg, aber Sie sind noch nicht fertig! Lesen Sie als Nächstes den [Abschnitt Was nach](#what-to-do-after-running-the-wizard) dem Ausführen des Assistenten zu tun ist in diesem Artikel.

## <a name="what-to-do-after-running-the-wizard"></a>Was nach dem Ausführen des Assistenten zu tun ist

Nachdem Sie den Assistenten ausgeführt haben, ist es wichtig, dass Sie:

- Teilen Sie Ihren Mitarbeitern und Vorgesetzten in der Front mit, dass ihnen Lizenzen Teams sind.
- Wenn Sie freigegebene Geräte verwenden, stellen Sie sicher, Teams auf diesen Geräten installiert ist. Wenn Ihre Organisation ein Modell "Bring your own device" verwendet, teilen Sie Ihren Mitarbeitern und Vorgesetzten in der Frontline mit, dass sie Die Teams auf ihre Geräte herunterladen und installieren müssen.

Wenn der Mitarbeiter in der Frontlinie Teams zum ersten Mal öffnet, erhält er eine maßgeschneiderte First Run-Erfahrung, die Chats und Kanäle, Anrufe und Aufgabenmanagement innerhalb der Teams.

## <a name="related-articles"></a>Verwandte Artikel

- [Verwalten von Richtlinienpaketen in Teams](manage-policy-packages.md)
- [Verwenden von Teamvorlagen im Teams Admin Center](get-started-with-teams-templates-in-the-admin-console.md)
