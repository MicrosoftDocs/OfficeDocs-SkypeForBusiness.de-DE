---
title: Verwenden von Teams mit Remotedesktopdiensten
author: cichur
ms.author: v-cichur
ms.reviewer: alivano
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Erfahren Sie, wie Sie Microsoft Teams mit Remotedesktopdiensten verwenden.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: dbf8be686029aa995ac0fb8a9977d129746b0c78
ms.sourcegitcommit: e72599d5437773322ae6ef985f804a19101ed84f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/26/2021
ms.locfileid: "50347876"
---
# <a name="teams-in-remote-desktop-services"></a>Teams in Remotedesktopdiensten

In diesem Artikel werden die Anforderungen und Einschränkungen für die Verwendung von Microsoft Teams in einer Remotedesktopdienstumgebung (RDS) beschrieben.

## <a name="what-is-rds"></a>Was ist RDS?

Remotedesktopdienste (RDS) ist die Plattform der Wahl zum Erstellen von Virtualisierungslösungen für jeden Kundenbedarf. MIT RDS können Sie einzelne virtualisierte Anwendungen bereitstellen, sicheren Mobile- und Remotedesktopzugriff bereitstellen und Endbenutzern die Möglichkeit bieten, ihre Anwendungen und Desktops aus der Cloud ausführen zu können.

RDS bietet Bereitstellungsflexibilität, Kosteneffizienz und Erweiterbarkeit. RDS wird über eine Vielzahl von Bereitstellungsoptionen bereitgestellt, darunter Windows Server 2016 für lokale Bereitstellungen, Microsoft Azure für Cloudbereitstellungen und eine robuste Palette von Partnerlösungen.
Je nach Umgebung und Einstellungen können Sie die RDS-Lösung für die sitzungsbasierte Virtualisierung als virtuelle Desktopinfrastruktur (VDI) einrichten.

Derzeit steht Teams in einer Remotedesktopdienstumgebung mit Unterstützung für Zusammenarbeit und Chatfunktionen zur Verfügung. Um eine optimale Benutzererfahrung zu gewährleisten, folgen Sie den Anweisungen in diesem Artikel.

## <a name="teams-on-rds-with-chat-and-collaboration"></a>Teams auf RDS mit Chat und Zusammenarbeit

Wenn Ihre Organisation nur Chat- und Zusammenarbeitsfunktionen in Teams verwenden möchte, können Sie Richtlinien auf Benutzerebene festlegen, um die Anruf- und Besprechungsfunktionen in Teams zu deaktivieren.

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a>Festlegen von Richtlinien zum Deaktivieren von Anruf- und Besprechungsfunktionen

Sie können Richtlinien über das Microsoft Teams Admin Center oder PowerShell festlegen. Es kann einige Stunden dauern, bis die Richtlinienänderungen weitervererbt werden. Wenn Änderungen für ein bestimmtes Konto nicht sofort zu sehen sind, versuchen Sie es in ein paar Stunden erneut.

[**Anrufrichtlinien:**](teams-calling-policy.md)Teams enthält die integrierte Anrufrichtlinie "DisallowCalling", in der alle Anruffeatures deaktiviert sind. Weisen Sie allen Benutzern in Ihrer Organisation, die Teams in einer virtualisierten Umgebung verwenden, die Richtlinie "DisallowCalling" zu.

[**Besprechungsrichtlinien:**](meeting-policies-in-teams.md)Teams enthält die integrierte AllOff-Besprechungsrichtlinie, in der alle Besprechungsfeatures deaktiviert sind. Weisen Sie die AllOff-Richtlinie allen Benutzern in Ihrer Organisation zu, die Teams in einer virtualisierten Umgebung verwenden.

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>Zuweisen von Richtlinien im Microsoft Teams Admin Center

So weisen Sie einem Benutzer die Anrufrichtlinie "DisallowCalling" und die AllOff-Besprechungsrichtlinie zu:

1. Wechseln Sie im linken Navigationsbereich des Microsoft Teams Admin Centers zu **Benutzer.**
2. Wählen Sie den Benutzer aus, indem Sie links vom Benutzernamen und dann **Einstellungen bearbeiten auswählen.**
3. Gehen Sie wie folgt vor:

    a.  Wählen **Sie unter Anrufrichtlinie** die Option **DisallowCalling aus.**

    b.  Wählen **Sie unter Besprechungsrichtlinie** die Option **AllOff aus.**

4. Wählen Sie **Übernehmen aus.**

So weisen Sie mehreren Benutzern gleichzeitig eine Richtlinie zu

1. Wechseln Sie in der linken Navigation des Microsoft Teams Admin Center zu **Benutzer**, und suchen Sie dann nach den gewünschten Benutzern, oder filtern Sie die Ansicht, um die gewünschten Benutzer anzuzeigen.
2. Wählen Sie in der Spalte **&#x2713;** (Häkchen) die Benutzer aus. Um alle Benutzer auszuwählen, wählen &#x2713; (Häkchen) oben in der Tabelle aus.
3. Wählen **Sie Einstellungen bearbeiten** aus, nehmen Sie die von Ihnen ausgewählten Änderungen vor, und wählen Sie dann Übernehmen **aus.**

Sie können auch die folgenden Schritte ausführen:

1. Wechseln Sie im linken Navigationsbereich des Microsoft Teams Admin Centers zu der Richtlinie, die Sie zuweisen möchten. Beispiel:

    - Wechseln Sie zu  >  **Sprachanrufrichtlinien**, und wählen Sie **dann DisallowCalling aus.**
    - Wechseln Sie zu  >  **Besprechungsrichtlinien** für Besprechungen, und wählen Sie **dann AllOff aus.**

2. Wählen Sie **Benutzer verwalten** aus.
3. Suchen Sie im Bereich **Benutzer verwalten** anhand des Anzeigenamens oder des Benutzernamens nach dem Benutzer, wählen Sie den Namen aus, und klicken Sie auf **Hinzufügen**. Wiederholen Sie diesen Schritt für jeden Benutzer, den Sie hinzufügen wollen.
4. Wenn Sie mit dem Hinzufügen von Benutzern fertig sind, wählen Sie **Speichern aus.**

#### <a name="assign-policies-using-powershell"></a>Zuweisen von Richtlinien mithilfe von PowerShell

Das folgende Beispiel zeigt, wie Sie die [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) verwenden, um einem Benutzer die Anrufrichtlinie "DisallowCalling" zuzuordnen.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

Weitere Informationen zur Verwendung von PowerShell zum Verwalten von Anrufrichtlinien finden Sie unter [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).

Das folgende Beispiel zeigt, wie Sie die [Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) verwenden, um einem Benutzer die AllOff-Besprechungsrichtlinie zuzuordnen.

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

Weitere Informationen zur Verwendung von PowerShell zum Verwalten von Besprechungsrichtlinien finden Sie unter [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).
