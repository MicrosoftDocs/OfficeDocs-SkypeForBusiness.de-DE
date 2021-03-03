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
ms.openlocfilehash: 5ac88778fca7034446d0ec42a0a4a65d7c76f979
ms.sourcegitcommit: 414d077b16a0ae4ea6a49e3b3d0082858174cacb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/17/2021
ms.locfileid: "50278897"
---
# <a name="teams-in-remote-desktop-services"></a>Teams in Remotedesktopdiensten

In diesem Artikel werden die Anforderungen und Einschränkungen für die Verwendung von Microsoft Teams in einer Remotedesktopdienstumgebung (RDS) beschrieben.

## <a name="what-is-rds"></a>Was ist RDS?

Remote Desktop Services (RDS) ist die Plattform ihrer Wahl zum Erstellen von Virtualisierungslösungen für alle Kundenanforderungen. MIT RDS können Sie einzelne virtualisierte Anwendungen bereitstellen, sicheren Zugriff auf mobile Geräte und Remotedesktops bereitstellen und Endbenutzern die Möglichkeit bieten, ihre Anwendungen und Desktops aus der Cloud ausführen zu können.

RDS bietet Flexibilität, Kosteneffizienz und Erweiterbarkeit für die Bereitstellung. RDS wird über eine Vielzahl von Bereitstellungsoptionen bereitgestellt, darunter Windows Server 2016 für lokale Bereitstellungen, Microsoft Azure für Cloudbereitstellungen und ein stabiles Array von Partnerlösungen.
Abhängig von Ihrer Umgebung und Ihren Vorlieben können Sie die RDS-Lösung für sitzungsbasierte Virtualisierung als virtuelle Desktopinfrastruktur (VDI) einrichten.

Derzeit steht Teams in einer Remotedesktopdienstumgebung mit Unterstützung für Zusammenarbeit und Chatfunktionen zur Verfügung. Befolgen Sie die Anweisungen in diesem Artikel, um eine optimale Benutzererfahrung zu gewährleisten.

## <a name="teams-on-vdi-with-chat-and-collaboration"></a>Teams auf VDI mit Chat und Zusammenarbeit

Wenn Ihre Organisation nur Chat- und Zusammenarbeitsfeatures in Teams verwenden möchte, können Sie Richtlinien auf Benutzerebene festlegen, um die Anruf- und Besprechungsfunktionen in Teams zu deaktivieren.

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a>Festlegen von Richtlinien zum Deaktivieren von Anruf- und Besprechungsfunktionen

Sie können Richtlinien über das Microsoft Teams Admin Center oder PowerShell festlegen. Es kann einige Zeit (einige Stunden) dauern, bis die Richtlinienänderungen weitervererbt wurden. Wenn die Änderungen für ein bestimmtes Konto nicht sofort zu sehen sind, versuchen Sie es in ein paar Stunden erneut.

[**Anrufrichtlinien:**](teams-calling-policy.md)Teams enthält die integrierte Anrufrichtlinie "Anruf unter Ungernerufe", in der alle Anruffunktionen deaktiviert sind. Weisen Sie die Richtlinie "DisallowCalling" allen Benutzern in Ihrer Organisation zu, die Teams in einer virtualisierten Umgebung verwenden.

[**Besprechungsrichtlinien:**](meeting-policies-in-teams.md)Teams enthält die integrierte AllOff-Besprechungsrichtlinie, in der alle Besprechungsfeatures deaktiviert sind. Weisen Sie die "AllOff"-Richtlinie allen Benutzern in Ihrer Organisation zu, die Teams in einer virtualisierten Umgebung verwenden.

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>Zuweisen von Richtlinien über das Microsoft Teams Admin Center

So weisen Sie einem Benutzer die Anrufrichtlinie "DisallowCalling Calling" und die Besprechungsrichtlinie "AllOff" zu:

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **"Benutzer".**
2. Wählen Sie den Benutzer aus, indem Sie links des Benutzernamens und dann **"Einstellungen bearbeiten" auswählen.**
3. Gehen Sie wie folgt vor:

    a.  Wählen **Sie unter "Anrufrichtlinie"** die **Option "DisallowCalling" aus.**

    b.  Wählen **Sie unter "Besprechungsrichtlinie"** die Option **"AllOff" aus.**

4. Wählen Sie **"Übernehmen"** aus.

So weisen Sie mehreren Benutzern gleichzeitig eine Richtlinie zu

1. Wechseln Sie in der linken Navigation des Microsoft Teams Admin Center zu **Benutzer**, und suchen Sie dann nach den gewünschten Benutzern, oder filtern Sie die Ansicht, um die gewünschten Benutzer anzuzeigen.
2. Wählen Sie in der Spalte **&#x2713;** (Häkchen) die Benutzer aus. Um alle Benutzer auszuwählen, wählen Sie das &#x2713; (Häkchen) am Anfang der Tabelle aus.
3. Wählen **Sie "Einstellungen bearbeiten"** aus, nehmen Sie die änderungen vor, und wählen Sie dann "Übernehmen" **aus.**

Sie können auch die folgenden Schritte ausführen:

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu der Richtlinie, die Sie zuweisen möchten. Beispiel:

    - Wechseln Sie zu **den**  >  **Sprachanrufrichtlinien,** und wählen Sie **"DisallowCalling" aus.**
    - Wechseln Sie zu  >  **Besprechungsrichtlinien** für Besprechungen, und wählen Sie **"AllOff" aus.**

2. Wählen Sie **Benutzer verwalten** aus.
3. Suchen Sie im Bereich **Benutzer verwalten** anhand des Anzeigenamens oder des Benutzernamens nach dem Benutzer, wählen Sie den Namen aus, und klicken Sie auf **Hinzufügen**. Wiederholen Sie diesen Schritt für jeden Benutzer, den Sie hinzufügen wollen.
4. Wenn Sie mit dem Hinzufügen von Benutzern fertig sind, wählen Sie **"Speichern" aus.**

#### <a name="assign-policies-using-powershell"></a>Zuweisen von Richtlinien mithilfe von PowerShell

Das folgende Beispiel zeigt, wie Sie einem Benutzer mithilfe von [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) die Richtlinie "DisallowCalling calling" zuweisen.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

Weitere Informationen zur Verwendung von PowerShell zum Verwalten von Anrufrichtlinien finden Sie unter [Set-CsTeamsCallingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)

Das folgende Beispiel zeigt, wie Sie einem Benutzer mithilfe von [Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) die Besprechungsrichtlinie "AllOff" zuweisen.

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

Weitere Informationen zur Verwendung von PowerShell zum Verwalten von Besprechungsrichtlinien finden Sie unter [Set-CsTeamsMeetingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)
