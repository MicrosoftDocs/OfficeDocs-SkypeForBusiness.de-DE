---
title: Probleme beim Empfangen von Nachrichten und Anrufen auf Legacysystemen in Teams
ms.reviewer: ''
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 05/29/2020
ms.topic: troubleshooting
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
description: Behandeln von Problemen im Zusammenhang mit dem empfangen von Nachrichten und Anrufen auf Legacysystemen
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 52038470e81b825391e4176c07af7a30f51356df
ms.sourcegitcommit: ef3cd762e799df43bdcde03363c501d7ca9bb6b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2020
ms.locfileid: "44489160"
---
<a name="issues-receiving-messages-and-calls-on-legacy-systems"></a>Probleme beim Empfangen von Nachrichten und Anrufen auf Legacysystemen
==============================================================

Möglicherweise haben die Benutzer Probleme beim Empfangen von Nachrichten oder anrufen, wenn Sie ältere Versionen von Teams verwenden oder sich mit anderen Anwendungen angemeldet haben.

## <a name="legacy-adu-setups"></a>Legacy-Adu-Setups

 Wenn Benutzer bei einem in eine Domäne eingebundenen Computer angemeldet sind und **Sie nicht möchten, dass ihre Benutzernamen im Anmeldebildschirm von Microsoft Teams vorab ausgefüllt werden**, können Administratoren die folgende Windows-Registrierung so einrichten, dass das Vorab-Ausfüllen des Benutzernamens (UPN) deaktiviert ist:

  Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams<br/>
  SkipUpnPrefill(REG_DWORD)<br/>
  0x00000001 (1)

> [!NOTE]
> Das Überspringen oder Ignorieren des Vorab-Ausfüllens von Benutzernamen ist für Benutzernamen, die in „.local“ oder „.corp“ enden, standardmäßig aktiviert, daher müssen Sie keinen Registrierungsschlüssel festlegen, um diese zu deaktivieren.

Weitere Informationen finden Sie unter [Anmelden bei Microsoft Teams mithilfe der modernen Authentifizierung](sign-in-teams.md) .

## <a name="skype-token-revocation"></a>Skype-Token-Sperrung

Wenn ein Kennwort geändert/zurückgesetzt wird, erhalten ältere Clients keine Nachrichten und Anrufe bis zu einer Stunde. Um dieses Problem zu beheben, starten Sie die APP entweder neu, oder wechseln Sie zu neueren Clients.
