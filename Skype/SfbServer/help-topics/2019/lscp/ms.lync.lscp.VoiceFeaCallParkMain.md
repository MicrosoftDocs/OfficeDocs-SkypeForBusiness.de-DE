---
title: Parken von Anrufen
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaCallParkMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b752617d-554d-470e-b17b-387403ac74ed
ROBOTS: NOINDEX, NOFOLLOW
description: Wenn Sie ein Anruf geparkt wurde, wird er übertragen in eine temporäre Zahl ist, in dem der Anruf gehalten, bis jemand ruft sie ab, oder das Zeitlimit überschritten. Sie müssen eine Tabelle mit den Bereichen von Durchwahlnummern konfigurieren, die Sie für Geparkte Anrufe reservieren. Dabei muss es sich um virtuelle Durchwahlnummern handeln (also Nummern, denen kein Benutzer oder Telefon zugeordnet ist). Jeder Pool, der die Anwendung zum Parken ausgeführt wird kann eine oder mehrere Bereiche von Erweiterungen verfügen. Diese Bereiche müssen innerhalb der Bereitstellung eindeutig sein.
ms.openlocfilehash: f23ec10607c8cd1f6ec15dca3f9e3b99666abf1a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32221581"
---
# <a name="call-park"></a>Parken von Anrufen

Wenn Sie ein Anruf geparkt wurde, wird er übertragen in eine temporäre Zahl ist, in dem der Anruf gehalten, bis jemand ruft sie ab, oder das Zeitlimit überschritten. Sie müssen eine Tabelle mit den Bereichen von Durchwahlnummern konfigurieren, die Sie für Geparkte Anrufe reservieren. Dabei muss es sich um virtuelle Durchwahlnummern handeln (also Nummern, denen kein Benutzer oder Telefon zugeordnet ist). Jeder Pool, der die Anwendung zum Parken ausgeführt wird kann eine oder mehrere Bereiche von Erweiterungen verfügen. Diese Bereiche müssen innerhalb der Bereitstellung eindeutig sein.

Die Seite **Anruf Parken** zeigt eine Liste aller die Nummer des Parkens von Anrufen-Bereiche, die für Ihre Organisation definiert sind.

## <a name="tasks-you-can-perform"></a>Mögliche Aufgaben

Auf der Seite **Anruf parken** können Sie die folgenden Aufgaben ausführen:

- Erstellen eines neuen Nummernbereichs

- Ändern eines vorhandenen Nummernbereichs

- Löschen eines Nummernbereichs

## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In der folgenden Liste werden die Befehle der Seite beschrieben.

- **Neue** Startet einen neuen Nummernbereich Parken.

- **Bearbeiten** Öffnet den ausgewählten Nummernbereich zur Bearbeitung, wählt alle Nummernbereiche in der Liste aus oder löscht den ausgewählten Nummernbereich.

- **Aktualisieren** Aktualisiert die Liste der Nummernbereiche.

In der folgenden Liste werden die Felder der Seite beschrieben.

- **Name** Der eindeutige Name, der den Nummernbereich.

- **Anfangsbereich gibt** Die Anfangsnummer des Bereichs.

- **Endbereich** Die Endnummer des Bereichs.

- **Ziel** Der vollqualifizierte Domänenname (FQDN) oder Dienst-ID des Anwendungsdiensts, die die Anwendung zum Parken von Anrufen für den Nummernbereich hostet.

Informationen zu parken Features und Funktionen finden Sie unter [Planen des Parkens von Anrufen in Skype für Unternehmen](../../../plan-your-deployment/enterprise-voice-solution/call-park.md). Ausführliche Informationen zum Arbeiten mit Parken Nummernbereiche finden Sie unter [Konfigurieren Telefon Anzahl Erweiterungen für das Parken von Anrufen](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).


