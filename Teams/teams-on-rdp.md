---
title: Verwenden von Teams mit Remotedesktopdiensten
ms.author: mikeplum
author: MikePlumleyMSFT
ms.reviewer: alivano
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Erfahren Sie, wie Sie Microsoft Teams mit Remotedesktopdiensten verwenden.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7e18aa0ad95033550d0ef2f7c6049e700d917798
ms.sourcegitcommit: 79ada2140b110239deff96e4854ebd5dd9b77881
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2022
ms.locfileid: "66606094"
---
# <a name="teams-in-remote-desktop-services"></a>Teams in Remotedesktopdiensten

In diesem Artikel werden die Anforderungen und Einschränkungen für die Verwendung von Microsoft Teams in einer RdS-Umgebung (Remotedesktopdienste) beschrieben.

## <a name="what-is-rds"></a>Was ist RDS?

Remotedesktopdienste (RDS) ist die Plattform der Wahl für die Erstellung von Virtualisierungslösungen für jeden Endbenutzerbedarf. MIT RDS können Sie einzelne virtualisierte Anwendungen bereitstellen, sicheren Mobilen und Remotedesktopzugriff bereitstellen und Endbenutzern die Möglichkeit bieten, ihre Anwendungen und Desktops über die Cloud auszuführen.

RDS bietet Flexibilität bei der Bereitstellung, Kosteneffizienz und Erweiterbarkeit. RDS wird über eine Vielzahl von Bereitstellungsoptionen bereitgestellt, einschließlich Windows Server 2016 für lokale Bereitstellungen, Microsoft Azure für Cloudbereitstellungen und ein robustes Array von Partnerlösungen.
Je nach Umgebung und Präferenzen können Sie die RDS-Lösung für die sitzungsbasierte Virtualisierung als virtuelle Desktopinfrastruktur (VDI) einrichten.

Derzeit ist Teams in einer Remotedesktopdienstumgebung mit Unterstützung für Zusammenarbeits- und Chatfunktionen verfügbar. Um eine optimale Benutzererfahrung sicherzustellen, folgen Sie den Anweisungen in diesem Artikel.

## <a name="teams-on-rds-with-chat-and-collaboration"></a>Teams auf RDS mit Chat und Zusammenarbeit

Wenn Ihre Organisation nur die Chat- und Zusammenarbeitsfeatures in Teams verwenden möchte, können Sie Richtlinien auf Benutzerebene festlegen, um Anruf- und Besprechungsfunktionen in Teams zu deaktivieren.

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a>Festlegen von Richtlinien zum Deaktivieren von Anruf- und Besprechungsfunktionen

Sie können Richtlinien mithilfe des Microsoft Teams Admin Centers oder mit PowerShell einrichten. Es kann einige Zeit (ein paar Stunden) dauern, bis die Richtlinienänderungen aktualisiert wurden. Wenn Sie Änderungen für ein bestimmtes Konto nicht sofort sehen, versuchen Sie es nach ein paar Stunden erneut.

[**Anrufrichtlinien**](teams-calling-policy.md): Teams enthält die integrierte Anrufrichtlinie DisallowCalling, in der alle Anruffeatures deaktiviert sind. Weisen Sie die DisallowCalling-Richtlinie allen Benutzern in Ihrer Organisation zu, die Teams in einer virtualisierten Umgebung verwenden.

[**Besprechungsrichtlinien**](meeting-policies-overview.md): Teams enthält die integrierte Besprechungsrichtlinie AllOff, in der alle Anruffeatures deaktiviert sind. Weisen Sie die AllOff-Richtlinie allen Benutzern in Ihrer Organisation zu, die Teams in einer virtualisierten Umgebung verwenden.

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>Zuweisen von Richtlinien mithilfe des Microsoft Teams Admin Centers

So weisen Sie einem Benutzer die DisallowCalling-Anrufrichtlinie und die AllOff-Besprechungsrichtlinie zu:

1. Wechseln Sie in der linken Navigation des Microsoft Teams Admin Centers zu **Nutzer**.
2. Wählen Sie den Benutzer aus, indem Sie links neben dem Benutzernamen die Option " **Einstellungen bearbeiten"** auswählen.
3. Führen Sie die folgenden Schritte aus:

    a.  Wählen Sie unter **"Anrufrichtlinie**" die Option **"DisallowCalling**" aus.

    b.  Wählen Sie unter "**Besprechungsrichtlinie****" die Option "AllOff" aus**.

4. Wählen Sie **"Übernehmen" aus**.

So weisen Sie mehreren Benutzern gleichzeitig eine Richtlinie zu

1. Wechseln Sie in der linken Navigation des Microsoft Teams Admin Center zu **Benutzer**, und suchen Sie dann nach den gewünschten Benutzern, oder filtern Sie die Ansicht, um die gewünschten Benutzer anzuzeigen.
2. Wählen Sie in der Spalte **&#x2713;** (Häkchen) die Benutzer aus. Um alle Benutzer auszuwählen, wählen Sie oben in der Tabelle das &#x2713; (Häkchen) aus.
3. Wählen Sie **"Einstellungen bearbeiten"** aus, nehmen Sie die gewünschten Änderungen vor, und wählen Sie dann **"Übernehmen"** aus.

Sie können auch die folgenden Schritte ausführen:

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu der Richtlinie, die Sie zuweisen möchten. Beispiel:

    - Wechseln Sie zu VoIP-Anrufrichtlinien > , und wählen Sie dann **DisallowCalling** aus.
    - Wechseln Sie zu **Besprechungsbesprechungsrichtlinien** > , und wählen Sie dann **"AllOff" aus**.

2. Wählen Sie **Nutzer verwalten** aus.
3. Suchen Sie im Bereich **Benutzer verwalten** anhand des Anzeigenamens oder des Benutzernamens nach dem Benutzer, wählen Sie den Namen aus, und klicken Sie auf **Hinzufügen**. Wiederholen Sie diesen Schritt für jeden Benutzer, den Sie hinzufügen wollen.
4. Wenn Sie mit dem Hinzufügen von Benutzern fertig sind, wählen Sie **"Speichern"** aus.

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