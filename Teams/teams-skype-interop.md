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
- m365initiative-externalcollab
ms.reviewer: vinbel
search.appverid: MET150
description: Erfahren Sie mehr über die Interoperabilitätsfunktionen zwischen den Teams-Benutzern in Ihrer Organisation und Skype (Consumer)-Benutzern.
localization_priority: Normal
ms.openlocfilehash: 8bb6a83eddc60ff680d1a08c7266e082dd8b0188
ms.sourcegitcommit: 2639da2c9f903a9a82866be9db2b69a705c54200
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2021
ms.locfileid: "50055647"
---
# <a name="teams-and-skype-interoperability"></a>Interoperabilität von Teams und Skype

Dieser Artikel enthält eine Übersicht über die Interoperabilitätsfunktionen zwischen Microsoft Teams und Skype (Consumer). Erfahren Sie, wie Teams-Benutzer und -Skype-Benutzer über Chats und Anrufe und die administratorrechten Steuerungen kommunizieren können, die angewendet werden.

Teams-Benutzer in Ihrer Organisation können mit ihren E-Mail-Adressen chatten und Die Benutzer von Skype anrufen und umgekehrt.

- Benutzer von Teams können nach einer 1:1-Unterhaltung (nur Text) oder einem Audio-/Videoanruf mit einem Skype-Benutzer suchen und diese starten.
- Benutzer von Skype können nach einer 1:1-Unterhaltung (nur Text) oder einem Audio-/Videoanruf mit einem Benutzer von Teams suchen und diese starten.

Diese Funktionen sind auf desktop-, web- und mobilen Clients (Android und iOS) sowohl für Teams als auch für Skype verfügbar. Für eine optimale Erfahrung empfehlen wir Skype Version 8.58 und höher.

> [!NOTE]
> Die in diesem Artikel erläuterten Inopfunktionen von Teams und Skype sind in GCC-, GCC High- oder DOD-Bereitstellungen oder in Umgebungen in der privaten Cloud nicht verfügbar.

## <a name="chat-and-calling-experience"></a>Chats und Anrufe

Hier ist eine Übersicht über die Chat- und Anruferfahrung.

### <a name="teams-user-starts-a-chat-or-call-with-a-skype-user"></a>Der Benutzer von Teams beginnt einen Chat oder Anruf mit einem Skype-Benutzer.

Teams können nach einem Skype-Benutzer suchen, indem sie seine E-Mail-Adresse in einen neuen Chat oder in die Suchleiste eingeben.  Der Benutzer von Teams kann dann den Benutzer in den Suchergebnissen auswählen, um einen Chat oder Anruf mit ihm zu starten.

Möglicherweise entscheidet sich ein Skype-Benutzer dafür, nicht in den Suchergebnissen zu erscheinen. In diesem Fall werden sie nicht in den Suchergebnissen in Teams angezeigt, und Die Benutzer von Teams können sie nicht finden.

### <a name="skype-user-starts-a-chat-or-call-with-a-teams-user"></a>Ein Skype-Benutzer startet einen Chat oder Anruf mit einem Teams-Benutzer.

Skype-Benutzer können mithilfe ihrer E-Mail-Adresse nach einem Teambenutzer suchen und einen Chat starten. Der Benutzer von Teams wird benachrichtigt, dass er eine neue Nachricht von einem Skype-Benutzer hat, und muss die Nachricht zuerst annehmen, bevor er darauf antworten kann.

- Wenn der Benutzer von Teams **"Annehmen"** auswählt, wird die Unterhaltung angenommen, und beide Benutzer können chatten und sich anrufen.
- Wenn der Benutzer von Teams **"Blockieren"** auswählt, wird die Unterhaltung blockiert, und nachfolgende Nachrichten und Anrufe von diesem Benutzer werden blockiert.
- Wenn der Benutzer von Teams "Nachrichten anzeigen" auswählt, wird die Nachricht in Teams angezeigt, wodurch der Benutzer entscheiden kann, ob er die Unterhaltung annehmen oder blockieren soll.

> [!NOTE]
> Wenn Sie ein Upgrade von Skype for Business auf Teams durchgeführt haben und sich Ihre Benutzer im Nur-Teams-Modus befinden, werden Chats und Anrufe von Skype-Benutzern an Teams-Benutzer an Teams übermittelt. Wenn sich Ihre Benutzer im Islands-Modus befinden, werden Chats und Anrufe von Skype-Benutzern an Die Nutzer von Teams an Skype for Business übermittelt.

### <a name="teams-user-blocks-or-unblocks-a-skype-user"></a>Der Benutzer von Teams blockiert oder blockiert einen Skype-Benutzer.

Nachdem ein Benutzer von Teams die erste Unterhaltungsanfrage eines Skype-Benutzers akzeptiert oder blockiert hat, kann er diese Person jederzeit blockieren oder entsperren. Sie können dies entweder in der Unterhaltung oder in ihren Datenschutzeinstellungen in Teams tun. Skype-Benutzer wissen nicht, dass sie blockiert wurden.

Blockierte Skype-Benutzer sowie andere Personen und Telefonnetznummern im öffentlichen Telefonnetz, die ein Benutzer in Teams blockiert hat, werden in Teams in der Liste blockierter Kontakte des Benutzers aufgeführt.

## <a name="limitations"></a>Einschränkungen

- Unterhaltungen sind nur Text. Dies bedeutet, dass es keine umfangreiche Formatierung, keine @mentions, Emojis oder andere der anderen Chatfeatures gibt, die in einer nativen Teams-Chaterfahrung [verfügbar sind.](native-chat-for-external-users.md)
- Unterhaltungen sind nur 1:1-Unterhaltungen. Gruppenchats werden nicht unterstützt.
- Teams-Benutzer und -Skype-Benutzer können die Anwesenheitspräsenzen der anderen Benutzer nicht sehen.
- Die Suche nach Skype-Benutzern mithilfe ihrer Skype-ID oder Telefonnummer wird nicht unterstützt.
- Skype-Benutzer können teams-Benutzer, die eine Anrufanrufleitung an die Nummer eines anderen Benutzers, die Nummer einer Stellvertretung oder eine Rufnummer im öffentlichen Telefonnetz (PSTN) eingerichtet haben, nicht anrufen.  Nur Voicemail wird unterstützt.
- Die Inopeskalation, Gruppenanrufe und Besprechungen werden nicht unterstützt.
- Die Möglichkeit einer Stellvertretung, einen Skype-Benutzer im Auftrag eines Teams-Benutzers anrufen zu können, wird nicht unterstützt.
- Die Bildschirmfreigabe mit Chat wird nicht unterstützt.

## <a name="set-whether-teams-users-can-communicate-with-skype-users"></a>Festlegen, ob Benutzer von Teams mit den Benutzern von Skype kommunizieren können

Als Administrator verwenden Sie das Microsoft Teams Admin Center oder PowerShell zum Festlegen von Einstellungen für den externen Zugriff, um zu steuern, ob die Benutzer von Microsoft Teams in Ihrer Organisation mit den Skype-Benutzern kommunizieren können. Standardmäßig ist diese Funktion für neue Mandanten aktiviert. Es ist jedoch eine Voraussetzung dafür, dass der folgende DNS -SRV-Eintrag vom IT-Administrator konfiguriert werden muss, wenn er nicht bereits für Ihre Domäne verfügbar ist, z. B. _sipfederationtls.contoso.com.  

**Dienst:** sipfederationtls<br/>
**Protokoll:** TCP<br/>
**Priorität:** 100<br/>
**Gewichtung:** 1<br/>
**Port:** 5061<br/>
**Ziel:** sipfed.online.lync.com

Wenn Sie ein Upgrade von Skype for Business auf Teams durchgeführt haben, werden die Einstellungen für externe Kommunikation, die Sie im Skype for Business Admin Center konfiguriert haben, zu Teams migriert.

### <a name="in-the-microsoft-teams-admin-center"></a>Im Microsoft Teams Admin Center

Wechseln Sie im Microsoft Teams Admin Center zu **"Organisationsweite** Einstellungen Externer Zugriff", und aktivieren Sie dann die "Benutzer können  >  mit **den Skype-Benutzern kommunizieren".** Eine schritt-für-Schritt-Anleitung zum Konfigurieren dieser und anderer Einstellungen für den externen Zugriff finden Sie unter "Verwalten des externen Zugriffs [in Teams".](https://docs.microsoft.com/microsoftteams/manage-external-access#allow-or-block-domains)

### <a name="using-powershell"></a>Verwendung von PowerShell

Gehen Sie folgendermaßen vor: 
1. Verwenden Sie [das Cmdlet "Set-CsExternalAccessPolicy"](https://docs.microsoft.com/powershell/module/skype/set-csexternalaccesspolicy) zusammen mit dem Parameter, um zu steuern, ob Die Benutzer von Teams mit ```EnablePublicCloudAccess``` den Benutzern von Skype kommunizieren können. Wenn Sie den Parameter so ```true``` festlegen, dass die Benutzer von Teams mit den Skype-Benutzern kommunizieren können. Mit dem Parameter können ```EnablePublicCloudAudioVideoAccess``` Sie Audio-/Videoanrufe aktivieren/deaktivieren.

2. Verwenden Sie [das Cmdlet "Set-CsTenantPublicProvider" zusammen mit dem auf "Set-CsTenantPublicProvider"](https://docs.microsoft.com/powershell/module/skype/Set-CsTenantPublicProvider) festgelegten Parameter, damit die Benutzer von Teams mit ```Provider``` den Benutzern von Skype kommunizieren ```"WindowsLive"``` können.

## <a name="related-topics"></a>Verwandte Themen

- [Verwalten des externen Zugriffs in Teams](manage-external-access.md)
- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
