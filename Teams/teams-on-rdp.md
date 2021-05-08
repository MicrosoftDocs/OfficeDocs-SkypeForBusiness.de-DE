---
title: Verwenden Teams mit Remotedesktopdiensten
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
ms.openlocfilehash: 7090aac3c5e7ff724a079e7f9d9ffe9d712cd447
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119094"
---
# <a name="teams-in-remote-desktop-services"></a>Teams in Remotedesktopdiensten

In diesem Artikel werden die Anforderungen und Einschränkungen für die Verwendung von Microsoft Teams in einer RDS-Umgebung (Remote Desktop Services) beschrieben.

## <a name="what-is-rds"></a>Was ist RDS?

Remotedesktopdienste (Remote Desktop Services, RDS) ist die Plattform ihrer Wahl zum Erstellen von Virtualisierungslösungen für alle Kundenanforderungen. Mit RDS können Sie einzelne virtualisierte Anwendungen bereitstellen, sicheren Zugriff auf mobile Geräte und Remotedesktops bereitstellen und Endbenutzern die Möglichkeit bieten, ihre Anwendungen und Desktops aus der Cloud ausführen zu können.

RDS bietet Flexibilität, Kosteneffizienz und Erweiterbarkeit für die Bereitstellung. RDS wird über eine Vielzahl von Bereitstellungsoptionen geliefert, darunter Windows Server 2016 für lokale Bereitstellungen, Microsoft Azure für Cloudbereitstellungen und ein stabiles Array von Partnerlösungen.
Abhängig von Ihrer Umgebung und Ihren Voreinstellungen können Sie die RDS-Lösung für die sitzungsbasierte Virtualisierung als VDI (Virtual Desktop Infrastructure) einrichten.

Derzeit steht Teams einer Remotedesktopdienste-Umgebung mit Unterstützung für Zusammenarbeit und Chatfunktionen zur Verfügung. Um eine optimale Benutzererfahrung sicherzustellen, folgen Sie den Anweisungen in diesem Artikel.

## <a name="teams-on-rds-with-chat-and-collaboration"></a>Teams über RDS mit Chat und Zusammenarbeit

Wenn Ihre Organisation nur die Chat- und Zusammenarbeitsfeatures in Teams verwenden möchte, können Sie Richtlinien auf Benutzerebene festlegen, um Anruf- und Besprechungsfunktionen in Teams zu deaktivieren.

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a>Festlegen von Richtlinien zum Deaktivieren von Anruf- und Besprechungsfunktionen

Sie können Richtlinien mithilfe des Microsoft Teams Admin Centers oder mit PowerShell einrichten. Es kann einige Zeit (ein paar Stunden) dauern, bis die Richtlinienänderungen aktualisiert wurden. Wenn Sie Änderungen für ein bestimmtes Konto nicht sofort sehen, versuchen Sie es nach ein paar Stunden erneut.

[**Anrufrichtlinien**](teams-calling-policy.md): Teams enthält die integrierte Anrufrichtlinie DisallowCalling, in der alle Anruffeatures deaktiviert sind. Weisen Sie die DisallowCalling-Richtlinie allen Benutzern in Ihrer Organisation zu, die Teams in einer virtualisierten Umgebung verwenden.

[**Besprechungsrichtlinien**](meeting-policies-in-teams.md): Teams enthält die integrierte Besprechungsrichtlinie AllOff, in der alle Anruffeatures deaktiviert sind. Weisen Sie die AllOff-Richtlinie allen Benutzern in Ihrer Organisation zu, die Teams in einer virtualisierten Umgebung verwenden.

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>Zuweisen von Richtlinien mithilfe des Microsoft Teams Admin Centers

So weisen Sie einem Benutzer die DisallowCalling-Anrufrichtlinie und die AllOff-Besprechungsrichtlinie zu:

1. Wechseln Sie in der linken Navigation des Microsoft Teams Admin Centers zu **Nutzer**.
2. Wählen Sie den Benutzer aus, indem Sie links des Benutzernamens und dann Einstellungen **bearbeiten auswählen.**
3. Gehen Sie wie folgt vor:

    a.  Wählen **Sie unter Anrufrichtlinie** die Option **DisallowCalling aus.**

    b.  Wählen **Sie unter Besprechungsrichtlinie** die Option **AllOff aus.**

4. Wählen Sie **Übernehmen aus.**

So weisen Sie mehreren Benutzern gleichzeitig eine Richtlinie zu

1. Wechseln Sie in der linken Navigation des Microsoft Teams Admin Center zu **Benutzer**, und suchen Sie dann nach den gewünschten Benutzern, oder filtern Sie die Ansicht, um die gewünschten Benutzer anzuzeigen.
2. Wählen Sie in der Spalte **&#x2713;** (Häkchen) die Benutzer aus. Um alle Benutzer auszuwählen, wählen Sie &#x2713; (Häkchen) am Anfang der Tabelle aus.
3. Wählen **Sie Einstellungen bearbeiten** aus, nehmen Sie die änderungen vor, und wählen Sie dann Übernehmen **aus.**

Sie können aber auch die folgenden Schritte ausführen:

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu der Richtlinie, die Sie zuweisen möchten. Beispiel:

    - Wechseln Sie **zu Voice**  >  **Calling-Richtlinien**, und wählen Sie dann **DisallowCalling aus.**
    - Wechseln Sie **zu**  >  **Besprechungsrichtlinien** für Besprechungen, und wählen Sie **dann AllOff aus.**

2. Wählen Sie **Benutzer verwalten** aus.
3. Suchen Sie im Bereich **Benutzer verwalten** anhand des Anzeigenamens oder des Benutzernamens nach dem Benutzer, wählen Sie den Namen aus, und klicken Sie auf **Hinzufügen**. Wiederholen Sie diesen Schritt für jeden Benutzer, den Sie hinzufügen wollen.
4. Wenn Sie mit dem Hinzufügen von Benutzern fertig sind, wählen Sie **Speichern aus.**

#### <a name="assign-policies-using-powershell"></a>Zuweisen von Richtlinien mit PowerShell

Im folgenden Beispiel wird gezeigt, wie Sie die [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) verwenden, um einem Benutzer die Anrufrichtlinie DisallowCalling zuzuweisen.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

Weitere Informationen zum Verwenden von PowerShell zum Verwalten von Anrufrichtlinien finden Sie unter [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy).

Im folgenden Beispiel wird gezeigt, wie Sie die [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) verwenden, um einem Benutzer die Besprechungsrichtlinie AllOff zuzuweisen.

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

Weitere Informationen zum Verwenden von PowerShell zum Verwalten von Besprechungsrichtlinien finden Sie unter [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).