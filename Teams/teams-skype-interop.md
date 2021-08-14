---
title: Interoperabilität von Teams und Skype
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
description: Informieren Sie sich über die Interoperabilitätsfunktionen zwischen Teams-Benutzern in Ihrem Unternehmen und Skype (Heimanwender)-Benutzern.
localization_priority: Normal
ms.openlocfilehash: 3cef040ac9c4ff399b0a663ae25b29f070eb5300
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2021
ms.locfileid: "58235180"
---
# <a name="teams-and-skype-interoperability"></a>Interoperabilität von Teams und Skype

Dieser Artikel gibt Ihnen einen Überblick über die Interoperabilitätsfunktionen zwischen Microsoft Teams und Skype (Heimanwender). Erfahren Sie, wie Teams- und Skype-Benutzer über Chats und Anrufe kommunizieren können, und wie der Administrator steuert, was möglich ist.

Teams-Benutzer in Ihrer Organisation können über ihre E-Mail-Adressen mit Skype-Benutzern chatten und diese anrufen, und umgekehrt.

- Teams-Benutzer können nach schriftlichen Einzelunterhaltungen oder Audio/Video-Anrufen mit einem Skype-Benutzer suchen und diese starten.
- Skype-Benutzer können nach schriftlichen Einzelunterhaltungen oder Audio/Video-Anrufen mit Teams-Benutzern suchen und diese starten.

Diese Funktionen sind auf Desktop-, Web- und mobilen (Android und iOS) Clients sowohl für Teams wie für Skype verfügbar. Für eine optimale Erfahrung empfehlen wir Skype Version 8.58 und später.

> [!NOTE]
> Die Teams- und Skype-Interoperabilitätsfunktionen, die in diesem Artikel diskutiert werden, sind nicht auf GCC-, GCC High- oder DOD-Bereitstellungen oder in privaten Cloud-Umgebungen verfügbar.

## <a name="chat-and-calling-experience"></a>Chat- und Anruf-Erfahrung

Hier ist ein Überblick über die Chat- und Anruf-Erfahrung.

### <a name="teams-user-starts-a-chat-or-call-with-a-skype-user"></a>Ein Teams-Benutzer startet einen Chat oder Anruf mit einem Skype-Benutzer

Der Teams-Benutzer kann nach einem Skype-Benutzer suchen, indem er dessen E-Mail-Adresse in einen neuen Chat oder in die Suchleiste eingibt.  Der Teams-Benutzer kann dann den Skype-Benutzer aus den Suchergebnissen auswählen, um einen Chat oder Anruf mit diesem zu starten.

Ein Skype-Benutzer kann wählen, nicht in den Suchergebnissen zu erscheinen. In diesem Fall wird er nicht in Suchergebnissen in Teams angezeigt, und Teams-Benutzer werden ihn nicht finden können.

### <a name="skype-user-starts-a-chat-or-call-with-a-teams-user"></a>Ein Skype-Benutzer startet einen Chat oder Anruf mit einem Teams-Benutzer

Skype-Benutzer können über die E-Mail-Adresse nach einem Teams-Benutzer suchen und mit diesem einen Chat starten. Der Teams-Benutzer wird benachrichtigt, dass er eine neue Nachricht von einem Skype-Benutzer hat, und er muss die Nachricht zuerst annehmen, bevor er darauf antworten kann.

- Wenn der Teams-Benutzer **Annehmen** wählt, wird die Unterhaltung angenommen, und beide Benutzer können miteinander chatten und sich anrufen.
- Wenn der Teams-Benutzer **Blockieren** wählt, wird die Unterhaltung blockiert, und nachfolgende Nachrichten und Anrufe von diesem Skype-Benutzer werden blockiert.
- Wenn der Teams-Benutzer **Nachrichten anzeigen** wählt, wird die Nachricht in Teams angezeigt, sodass der Benutzer entscheiden kann, ob er die Unterhaltung annehmen oder blockieren will.

> [!NOTE]
> Wenn Sie ein Upgrade von Skype for Business nach Teams durchgeführt haben, und Ihre Benutzer im „Nur Teams“-Modus sind, werden Chats und Anrufe von Skype-Benutzern für Teams-Benutzer an Teams weitergeleitet. Wenn sich Ihre Benutzer im „Insel“-Modus befinden, dann werden Chats und Anrufe von Skype-Benutzern an Teams-Benutzer an Skype for Business weitergeleitet.

### <a name="teams-user-blocks-or-unblocks-a-skype-user"></a>Ein Teams-Benutzer blockiert einen Skype-Benutzer oder hebt die Blockierung auf

Nachdem ein Teams-Benutzer die ursprüngliche Unterhaltungsanforderung eines Skype-Benutzers angenommen oder blockiert hat, kann er jederzeit entscheiden, diese Person zu blockieren oder die Blockierung aufzuheben. Er kann dies entweder in der Unterhaltung durchführen, oder in den Datenschutzeinstellungen in Teams. Skype-Benutzer werden nicht erfahren, dass sie blockiert wurden.

Blockierte Skype-Benutzer werden zusammen mit anderen Personen und Festnetz (Public Switched Telephone Network, PSTN)-Telefonnummern, die ein Teams-Benutzer blockiert hat, in der Liste der blockierten Kontakte des Benutzers in Teams aufgeführt.

## <a name="limitations"></a>Einschränkungen

- Unterhaltungen sind Nur-Text. Dies bedeutet, dass keine angereicherte Formatierung, @Erwähnungen, Emojis oder andere Chat Features zur Verfügung stehen, die in einer [nativen Teams-Chat-Erfahrung](native-chat-for-external-users.md) verfügbar sind.
- Unterhaltungen sind nur Einzelgespräche. Gruppenchats werden nicht unterstützt.
- Teams-Benutzer und Skype-Benutzer können die gegenseitige Anwesenheit nicht sehen.
- Die Suche nach Skype-Benutzern über ihre Skype-ID oder -Telefonnummer wird nicht unterstützt.
- Skype-Benutzer können keine Teams-Benutzer anrufen, die eine Anrufweiterleitung zur Nummer eines anderen Benutzers, einer Stellvertreter-Nummer oder einer Festnetz (Public Switched Telephone Network, PSTN)-Nummer eingerichtet haben.  Nur Voicemail wird unterstützt.
- Interoperabilitätseskalation, Gruppenanrufe und Besprechungen werden nicht unterstützt.
- Die Möglichkeit für einen Stellvertreter, einen Skype-Benutzer im Namen eines Teams-Benutzers anzurufen, wird nicht unterstützt.
- Die Bildschirmfreigabe mit Chat wird nicht unterstützt.

## <a name="set-whether-teams-users-can-communicate-with-skype-users"></a>Festlegen, ob Teams-Benutzer mit Skype-Benutzern kommunizieren können

Als Administrator verwenden Sie das Microsoft Teams Admin Center oder PowerShell, um externe Zugriffseinstellungen festzulegen, um zu steuern, ob Teams-Benutzer in Ihrer Organisation mit Skype-Benutzern kommunizieren können. Standardmäßig ist diese Funktion für neue Mandanten aktiviert. Voraussetzung ist jedoch, dass der folgende DNS-SRV-Eintrag vom IT-Administrator konfiguriert wird, falls er nicht bereits für Ihre Domäne vorhanden ist, z. B. _sipfederationtls.contoso.com.  

**Service (Dienst)**: sipfederationtls<br/>
**Protocol (Protokoll)**: TCP<br/>
**Priority (Priorität)**: 100<br/>
**Weight (Gewichtung)**: 1<br/>
**Port**: 5061<br/>
**Target (Ziel)**: sipfed.online.lync.com

Wenn Sie ein Upgrade von Skype for Business nach Teams durchgeführt haben, werden die externen Kommunikationseinstellungen, die Sie im Skype for Business Admin Center konfiguriert haben, nach Teams migriert.

### <a name="in-the-microsoft-teams-admin-center"></a>Im Microsoft Teams Admin Center

Wechseln Sie im Microsoft Teams Admin Center zu **Organisationsweite Einstellungen** > **Externer Zugriff**, und aktivieren Sie dann **Benutzer können mit Skype-Benutzern kommunizieren**. Eine schrittweise Anleitung, wie Sie dies und andere Einstellungen des externen Zugriffs konfigurieren, finden Sie unter [Externer Zugriff in Teams verwalten](./manage-external-access.md#allow-or-block-domains).

### <a name="using-powershell"></a>Verwendung von PowerShell

Gehen Sie folgendermaßen vor: 
1. Verwenden Sie das Cmdlet [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy) zusammen mit dem ```EnablePublicCloudAccess```-Parameter, um zu steuern, ob Teams-Benutzer mit Skype-Benutzern kommunizieren können. Das Einstellen des Parameters auf ```true``` erlaubt Teams-Benutzern die Kommunikation mit Skype-Benutzern. Sie können den ```EnablePublicCloudAudioVideoAccess```-Parameter verwenden, um Audio/Video-Anrufe zu aktivieren/deaktivieren.

2. Verwenden Sie das Cmdlet [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) zusammen mit dem auf ```"WindowsLive"``` festgelegten ```Provider```-Parameter, damit Teams-Benutzer mit Skype-Benutzern kommunizieren können.

## <a name="related-topics"></a>Verwandte Themen

- [Externer Zugriff in Teams verwalten](manage-external-access.md)
- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
