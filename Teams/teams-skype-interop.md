---
title: Teams und Skype-Interoperabilität
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: vinbel
search.appverid: MET150
description: Erfahren Sie mehr über die Interoperabilitätsfunktionen zwischen Teams-Benutzern in Ihrer Organisation und Skype(Consumer-)Benutzern.
localization_priority: Normal
ms.openlocfilehash: e3203c03043dbcdb04370cf3aa26b435fad4a728
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093955"
---
# <a name="teams-and-skype-interoperability"></a>Teams und Skype-Interoperabilität

In diesem Artikel erhalten Sie einen Überblick über die Interoperabilitätsfunktionen zwischen Microsoft Teams und Skype (Consumer). Erfahren Sie, wie Teams-Benutzer und Skype-Benutzer über Chats und Anrufe und die dafür anwendbaren Administratorsteuerelemente kommunizieren können.

Teams-Benutzer in Ihrer Organisation können mit Skype-Benutzern chatten und diese anrufen, indem sie ihre E-Mail-Adresse verwenden und umgekehrt.

- Teams-Benutzer können nach einer 1:1-Unterhaltung oder einem Audio-/Videoanruf mit einem Skype-Benutzer suchen und beginnen.
- Skype-Benutzer können nach einer 1:1-Unterhaltung oder einem Audio-/Videoanruf mit einem Teams-Benutzer suchen und diese starten.

Diese Funktionen sind auf Desktop-, Web- und mobilen Clients (Android und iOS) für Teams und Skype verfügbar. Für eine optimale Benutzererfahrung empfehlen wir Skype, Version 8.58 und höher.

> [!NOTE]
> Die in diesem Artikel erläuterten In-App-Funktionen für Teams und Skype sind in GCC-, GCC-Hoch- oder DOD-Bereitstellungen oder in privaten Cloudumgebungen nicht verfügbar.

## <a name="chat-and-calling-experience"></a>Chat- und Anruferfahrung

Hier finden Sie eine Übersicht über die Chat- und Anruferfahrung.

### <a name="teams-user-starts-a-chat-or-call-with-a-skype-user"></a>Teams-Benutzer startet einen Chat oder Einen Anruf mit einem Skype-Benutzer

Teams-Benutzer können nach einem Skype-Benutzer suchen, indem sie ihre E-Mail-Adresse in einen neuen Chat oder in die Suchleiste eingeben.  Der Teams-Benutzer kann dann den Skype-Benutzer in den Suchergebnissen auswählen, um einen Chat zu starten oder mit ihm zu telefonieren.

Ein Skype-Benutzer kann auswählen, dass er nicht in den Suchergebnissen angezeigt wird. In diesem Fall werden sie in den Suchergebnissen in Teams nicht angezeigt, und Teams-Benutzer können sie nicht finden.

### <a name="skype-user-starts-a-chat-or-call-with-a-teams-user"></a>Skype-Benutzer startet einen Chat oder Einen Anruf mit einem Teams-Benutzer

Skype-Benutzer können mithilfe ihrer E-Mail-Adresse einen Chat mit einem Teams-Benutzer suchen und starten. Der Benutzer von Teams wird benachrichtigt, dass er eine neue Nachricht von einem Skype-Benutzer hat und muss die Nachricht zuerst annehmen, bevor er darauf antworten kann.

- Wenn der Teams-Benutzer Annehmen **auswählt,** wird die Unterhaltung angenommen, und beide Benutzer können miteinander chatten und anrufen.
- Wenn der Teams-Benutzer Blockieren **auswählt,** wird die Unterhaltung blockiert, und nachfolgende Nachrichten und Anrufe von diesem Skype-Benutzer werden blockiert.
- Wenn der Teams-Benutzer Nachrichten anzeigen auswählt, wird die Nachricht in Teams angezeigt, wodurch der Benutzer entscheiden kann, ob er die Unterhaltung annehmen oder blockieren soll.

> [!NOTE]
> Wenn Sie ein Upgrade von Skype for Business auf Teams durchgeführt haben und sich Ihre Benutzer im Modus "Nur Teams" befinden, werden Chats und Anrufe von Skype-Benutzern an Teams-Benutzer an Teams übermittelt. Wenn Sich Ihre Benutzer im Inselmodus befinden, werden Chats und Anrufe von Skype-Benutzern an Teams-Benutzer an Skype for Business übermittelt.

### <a name="teams-user-blocks-or-unblocks-a-skype-user"></a>Teams-Benutzer blockiert oder entblockt einen Skype-Benutzer

Nachdem ein Teams-Benutzer die ursprüngliche Unterhaltungsanfrage eines Skype-Benutzers akzeptiert oder blockiert hat, kann er diese Person jederzeit blockieren oder aufheben. Sie können dies entweder in der Unterhaltung oder in ihren Datenschutzeinstellungen in Teams tun. Skype-Benutzer wissen nicht, dass sie blockiert wurden.

Blockierte Skype-Benutzer sowie andere Personen und Festnetztelefonnummern(PSTN), die von einem Teams-Benutzer blockiert wurden, werden in Teams in der Liste blockierter Kontakte des Benutzers aufgeführt.

## <a name="limitations"></a>Einschränkungen

- Unterhaltungen sind nur Text. Dies bedeutet, dass keine umfangreiche Formatierung, keine @mentions, Emojis oder andere der anderen Chatfeatures vorhanden ist, die in einer nativen Teams-Chaterfahrung [verfügbar sind.](native-chat-for-external-users.md)
- Unterhaltungen sind nur 1:1-Unterhaltungen. Gruppenchats werden nicht unterstützt.
- Teams-Benutzer und Skype-Benutzer können die Anwesenheitspräsenz der anderen Benutzer nicht sehen.
- Die Suche nach Skype-Benutzern mithilfe ihrer Skype-ID oder Telefonnummer wird nicht unterstützt.
- Skype-Benutzer können keine Teams-Benutzer anrufen, die die Anrufleitung an die Nummer eines anderen Benutzers, die Nummer einer Stellvertretung oder eine PstN-Nummer (Public Switched Telephone Network) eingerichtet haben.  Nur Voicemail wird unterstützt.
- Die Inopeskalation, Gruppenanrufe und Besprechungen werden nicht unterstützt.
- Die Möglichkeit einer Stellvertretung, einen Skype-Benutzer im Auftrag eines Teams-Benutzers anrufen zu können, wird nicht unterstützt.
- Die Bildschirmfreigabe mit Chat wird nicht unterstützt.

## <a name="set-whether-teams-users-can-communicate-with-skype-users"></a>Festlegen, ob Teams-Benutzer mit Skype-Benutzern kommunizieren können

Als Administrator verwenden Sie das Microsoft Teams Admin Center oder PowerShell, um Einstellungen für den externen Zugriff zu festlegen, um zu steuern, ob Teams-Benutzer in Ihrer Organisation mit Skype-Benutzern kommunizieren können. Standardmäßig ist diese Funktion für neue Mandanten aktiviert. Es besteht jedoch die Voraussetzung, dass der folgende DNS-SRV-Eintrag vom IT-Administrator konfiguriert werden muss, wenn er nicht bereits für Ihre Domäne verfügbar ist, z. B. _sipfederationtls.contoso.com.  

**Dienst**: sipfederationtls<br/>
**Protokoll:** TCP<br/>
**Priorität:** 100<br/>
**Gewicht:** 1<br/>
**Port**: 5061<br/>
**Ziel**: sipfed.online.lync.com

Wenn Sie ein Upgrade von Skype for Business auf Teams durchgeführt haben, werden die externen Kommunikationseinstellungen, die Sie im Skype for Business Admin Center konfiguriert haben, zu Teams migriert.

### <a name="in-the-microsoft-teams-admin-center"></a>Im Microsoft Teams Admin Center

Wechseln Sie im Microsoft Teams Admin Center zu **Organisationsweite** Einstellungen Externer Zugriff, und aktivieren Sie dann Benutzer  >   **können mit Skype-Benutzern kommunizieren.** Schrittweise Anleitungen zum Konfigurieren dieser und anderer Einstellungen für den externen Zugriff finden Sie unter Verwalten des externen Zugriffs [in Teams.](./manage-external-access.md#allow-or-block-domains)

### <a name="using-powershell"></a>Verwendung von PowerShell

Gehen Sie folgendermaßen vor: 
1. Verwenden Sie [das Cmdlet Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy) zusammen mit dem Parameter, um zu steuern, ob ```EnablePublicCloudAccess``` Teams-Benutzer mit Skype-Benutzern kommunizieren können. Wenn Sie den Parameter auf ```true``` festlegen, können Teams-Benutzer mit Skype-Benutzern kommunizieren. Sie können den Parameter ```EnablePublicCloudAudioVideoAccess``` verwenden, um Audio-/Videoanrufe zu aktivieren/zu deaktivieren.

2. Verwenden Sie [das Cmdlet Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) zusammen mit dem auf festgelegten ```Provider``` ```"WindowsLive"``` Parameter, damit Teams-Benutzer mit Skype-Benutzern kommunizieren können.

## <a name="related-topics"></a>Verwandte Themen

- [Verwalten des externen Zugriffs in Teams](manage-external-access.md)
- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)