---
title: Teams und Skype-Interoperabilität
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: vinbel
search.appverid: MET150
description: Informieren Sie sich über die Interoperabilitätsfunktionen zwischen Teams-Benutzern in Ihrer Organisation und Skype (Consumer)-Benutzern.
localization_priority: Normal
ms.openlocfilehash: 9bb38fa33e7ef3692f5946fef4769bb45f782f1a
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2020
ms.locfileid: "49030971"
---
# <a name="teams-and-skype-interoperability"></a>Teams und Skype-Interoperabilität

In diesem Artikel erhalten Sie einen Überblick über die Interoperabilitätsfunktionen zwischen Microsoft Teams und Skype (Consumer). Erfahren Sie, wie Teams-Benutzer und Skype-Benutzer über Chats und Anrufe sowie über die anwendbaren Administrator Steuerelemente kommunizieren können.

Benutzer von Teams in Ihrer Organisation können mit Ihrer e-Mail-Adresse chatten und Skype-Nutzer anrufen und umgekehrt.

- Benutzer von Teams können mit einem Skype-Nutzer nach einer einzigen Text Unterhaltung oder einem Audio/Video-Anruf suchen und damit beginnen.
- Skype-Nutzer können mit einem Teams-Benutzer nach einer einzigen Text Unterhaltung oder einem Audio/Video-Anruf suchen und damit beginnen.

Diese Funktionen stehen auf den Desktop-, Web-und mobilen (Android-und IOS-Clients) für Teams und Skype zur Verfügung. Für eine optimale Nutzung empfehlen wir Skype Version 8,58 und höher.

> [!NOTE]
> Die in diesem Artikel besprochenen Funktionen für Teams und Skype-Interop stehen in gcc-, gcc-oder DoD-Bereitstellungen oder in privaten Cloud-Umgebungen nicht zur Verfügung.

## <a name="chat-and-calling-experience"></a>Chat-und Anruferlebnis

Hier finden Sie eine Übersicht über die Benutzeroberfläche für Chats und Anrufe.

### <a name="teams-user-starts-a-chat-or-call-with-a-skype-user"></a>Der Benutzer von Teams startet einen Chat oder einen Anruf mit einem Skype-Nutzer

Benutzer von Teams können nach einem Skype-Nutzer suchen, indem Sie deren e-Mail-Adresse in einem neuen Chat oder in der Suchleiste eingeben.  Der Benutzer von Teams kann dann in den Suchergebnissen den Skype-Nutzer auswählen, um einen Chat zu starten oder mit ihm zu telefonieren.

Ein Skype-Nutzer kann wählen, nicht in den Suchergebnissen angezeigt zu werden. In diesem Fall werden Sie in den Suchergebnissen in Teams nicht angezeigt, und die Benutzer von Teams können Sie nicht finden.

### <a name="skype-user-starts-a-chat-or-call-with-a-teams-user"></a>Skype-Nutzer startet einen Chat oder einen Anruf mit einem Teams-Nutzer

Skype-Nutzer können mithilfe Ihrer e-Mail-Adresse nach einem Team-Nutzer suchen und einen Chat beginnen. Der Nutzer der Teams wird benachrichtigt, dass er eine neue Nachricht von einem Skype-Nutzer hat, und muss zuerst die Nachricht annehmen, bevor er darauf antworten kann.

- Wenn der Benutzer von Teams **akzeptieren** auswählt, wird die Unterhaltung akzeptiert, und beide Benutzer können chatten und sich gegenseitig anrufen.
- Wenn der Benutzer von Teams den **Block** auswählt, wird die Unterhaltung blockiert, und nachfolgende Nachrichten und Anrufe von diesem Skype-Nutzer werden blockiert.
- Wenn der Benutzer von Teams die Option **Nachrichten anzeigen** auswählt, wird die Nachricht in Teams angezeigt, sodass der Benutzer entscheiden kann, ob die Unterhaltung akzeptiert oder blockiert wird.

> [!NOTE]
> Wenn Sie ein Upgrade von Skype for Business auf Teams durchgeführt haben und sich Ihre Nutzer nur im Modus "Teams" befinden, werden Chats und Anrufe von Skype-Nutzern zu Teams-Benutzern an Teams ausgeliefert. Wenn sich Ihre Nutzer im Modus "Inseln" befinden, werden Chats und Anrufe von Skype-Nutzern an Teams-Nutzer an Skype for Business ausgeliefert.

### <a name="teams-user-blocks-or-unblocks-a-skype-user"></a>Teams Nutzer blockiert oder entsperrt einen Skype-Nutzer

Nachdem ein Team Nutzer die anfängliche Konversations Anfrage von einem Skype-Nutzer akzeptiert oder blockiert hat, kann er diese Person jederzeit blockieren oder freigeben. Sie können dies entweder in der Unterhaltung oder in den Privatsphäre-Einstellungen in Microsoft Teams tun. Skype-Nutzer wissen nicht, dass Sie blockiert wurden.

Blockierte Skype-Nutzer, zusammen mit anderen Personen und PSTN-Telefonnummern, die ein Team-Nutzer blockiert hat, werden in der Liste der blockierten Kontakte des Benutzers in Teams aufgeführt.

## <a name="limitations"></a>Einschränkungen

- Unterhaltungen sind nur Text. Das bedeutet, dass es keine Rich-Formatierung, @Mentions, Emojis oder andere andere Chat-Funktionen gibt, die in einer [nativen Teamchat-Umgebung](native-chat-for-external-users.md)zur Verfügung stehen.
- Konversationen sind nur eins-zu-eins. Gruppen-Chats werden nicht unterstützt.
- Teams-Nutzer und Skype-Nutzer können die Anwesenheit Ihres Gesprächspartners nicht sehen.
- Die Suche nach Skype-Nutzern über Ihre Skype-ID oder Telefonnummer wird nicht unterstützt.
- Skype-Nutzer können keine Teams anrufen, die die Anrufweiterleitung an die Nummer eines anderen Benutzers, die Nummer einer Stellvertretung oder eine PSTN-Nummer (Public Switched Telephone Network) eingerichtet haben.  Nur Voicemail wird unterstützt.
- Interop-Eskalation, Gruppenanrufe und Besprechungen werden nicht unterstützt.
- Die Möglichkeit für eine Stellvertretung, einen Skype-Nutzer im Auftrag eines Teams-Benutzers anzurufen, wird nicht unterstützt.
- Bildschirmübertragung mit Chat wird nicht unterstützt.

## <a name="set-whether-teams-users-can-communicate-with-skype-users"></a>Festlegen, ob Benutzer von Teams mit Skype-Nutzern kommunizieren können

Als Administrator verwenden Sie das Microsoft Teams Admin Center oder PowerShell, um Einstellungen für den externen Zugriff festzulegen, um zu steuern, ob Teams-Benutzer in Ihrer Organisation mit Skype-Benutzern kommunizieren können. Diese Funktion ist standardmäßig für neue Mandanten aktiviert. Es gibt jedoch eine Voraussetzung, dass der folgende DNS-SRV-Eintrag vom IT-Administrator konfiguriert werden muss, wenn er nicht bereits für Ihre Domäne verfügbar ist, beispielsweise _sipfederationtls. contoso. com.  

**Dienst** : sipfederationtls<br/>
**Protokoll** : TCP<br/>
**Priorität** : 100<br/>
**Gewicht** : 1<br/>
**Port** : 5061<br/>
**Ziel** : sipfed.online.lync.com

Wenn Sie ein Upgrade von Skype for Business auf Teams durchgeführt haben, werden die Einstellungen für externe Kommunikation, die Sie im Skype for Business Admin Center konfiguriert haben, in Teams migriert.

### <a name="in-the-microsoft-teams-admin-center"></a>Im Microsoft Teams Admin Center

Wechseln Sie im Microsoft Teams Admin Center zu **organisationsweiten Einstellungen**  >  **externer Zugriff** , und aktivieren Sie dann **Benutzer können mit Skype-Benutzern kommunizieren**. Eine Schritt-für-Schritt-Anleitung zum Konfigurieren dieser und anderer Einstellungen für den externen Zugriff finden Sie unter [Verwalten des externen Zugriffs in Teams](https://docs.microsoft.com/microsoftteams/manage-external-access#allow-or-block-domains).

### <a name="using-powershell"></a>Verwendung von PowerShell

Gehen Sie folgendermaßen vor: 
1. Verwenden Sie das Cmdlet " [Satz-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/set-csexternalaccesspolicy) " zusammen mit dem ```EnablePublicCloudAccess``` Parameter, um zu steuern, ob die Benutzer von Teams mit Skype-Benutzern kommunizieren können. Durch Festlegen des Parameters ```true``` können die Benutzer von Teams mit Skype-Nutzern kommunizieren. Sie können den ```EnablePublicCloudAudioVideoAccess``` Parameter verwenden, um Audio-und Videoanrufe zu aktivieren/deaktivieren.

2. Verwenden Sie das Cmdlet " [Satz-CsTenantPublicProvider](https://docs.microsoft.com/powershell/module/skype/Set-CsTenantPublicProvider) " zusammen mit dem ```Provider``` Parametersatz, ```"WindowsLive"``` damit die Benutzer von Teams mit Skype-Benutzern kommunizieren können.

## <a name="related-topics"></a>Verwandte Themen

- [Verwalten des externen Zugriffs in Teams](manage-external-access.md)
- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
