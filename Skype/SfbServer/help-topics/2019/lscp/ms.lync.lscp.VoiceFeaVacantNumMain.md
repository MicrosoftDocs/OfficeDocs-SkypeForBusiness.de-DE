---
title: Nicht zugewiesene Telefonnummer
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.VoiceFeaVacantNumMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24eca749-a9f3-40e7-839b-d21c3ef7d533
ROBOTS: NOINDEX, NOFOLLOW
description: Nicht zugewiesene Nummern sind Rufnummern, die für Ihre Organisation gültig sind, jedoch keinem Benutzer oder Telefon zugewiesen sind. In der Tabelle mit den nicht zugewiesenen Nummern ist angegeben, wie Anrufe bei nicht zugewiesenen Nummern behandelt werden sollen.
ms.openlocfilehash: 910b83f18350bc2a26da281f2e0660e8aa8913b9
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41690390"
---
# <a name="unassigned-phone-number"></a>Nicht zugewiesene Telefonnummer

> [!NOTE]
> Exchange um bleibt in Skype for Business Server 2019 verfügbar, wenn Sie Skype for Business 2019 mit Exchange 2013 oder Exchange 2016 integrieren. Aufgrund von Änderungen an der Unterstützung in Exchange 2019 wird die Exchange um-Integration zu Gunsten der Features Cloud Voicemail und Cloud-automatische Telefonzentrale de-hervorgehoben.

Nicht zugewiesene Nummern sind Rufnummern, die für Ihre Organisation gültig sind, jedoch keinem Benutzer oder Telefon zugewiesen sind. In der Tabelle mit den nicht zugewiesenen Nummern ist angegeben, wie Anrufe bei nicht zugewiesenen Nummern behandelt werden sollen.

Wie Sie die Tabelle nicht zugewiesener Rufnummern konfigurieren, richtet sich danach, wie Sie diese verwenden möchten. Sie können die Tabelle mit allen gültigen Durchwahlnummern für Ihre Organisation konfigurieren, nur mit nicht zugewiesenen Durchwahlnummern oder als eine Kombination beider Nummerntypen. Die Tabelle nicht zugewiesener Rufnummern kann sowohl zugewiesene als auch nicht zugewiesene Rufnummern enthalten, wird jedoch nur ausgelöst, wenn ein Anrufer eine derzeit nicht zugewiesene Rufnummer wählt. Wenn Sie alle gültigen Durchwahlnummern in die Tabelle nicht zugewiesener Nummern aufnehmen, können Sie eine Aktion angeben, die bei Ausscheiden eines Mitarbeiters aus der Organisation ausgeführt werden soll. In diesem Fall ist eine Neukonfiguration der Tabelle nicht erforderlich. Wenn Sie nicht zugewiesene Durchwahlnummern in die Tabelle aufnehmen, können Sie die Aktion anpassen, die für bestimmte Nummern ausgeführt wird. Wenn Sie beispielsweise die Durchwahlnummer für Ihren Kundendienst ändern, können Sie die alte Rufnummer des Kundendiensts in die Tabelle aufnehmen und ihr eine Ansage zuweisen, in der die neue Rufnummer bereitgestellt wird.

> [!IMPORTANT]
> Bevor Sie die Tabelle nicht zugewiesener Nummern konfigurieren, müssen Sie bereits eine oder mehrere Ansagen definiert oder eine automatische Telefonzentrale von Exchange eingerichtet haben.

Auf der Seite **Nicht zugewiesene Nummer** wird eine Liste mit den nicht zugewiesenen Nummernbereichen Ihrer Organisation angezeigt.

## <a name="tasks-you-can-perform"></a>Mögliche Aufgaben

Auf der Seite **Nicht zugewiesene Nummer** können Sie die folgenden Aufgaben ausführen:

- Erstellen eines neuen Bereichs nicht zugewiesener Nummern

- Ändern eines Bereichs nicht zugewiesener Nummern

- Löschen eines Bereichs nicht zugewiesener Nummern

- Ändern der Reihenfolge eines Bereichs nicht zugewiesener Nummern, um zu ermitteln, welche Aktion bei einer nicht zugewiesenen Nummer zuerst auf einen eingehenden Anruf angewendet werden soll

## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In der folgenden Liste werden die Befehle der Seite beschrieben.

- **Neu** Startet einen neuen nicht zugewiesenen Nummernbereich.

- **Bearbeiten** von Öffnet den ausgewählten nicht zugewiesenen Nummernbereich für die Bearbeitung, wählt alle nicht zugewiesenen Nummernbereiche in der Liste aus oder löscht den ausgewählten nicht zugewiesenen Nummernbereich.

- Nach **oben** Verschiebt den ausgewählten nicht zugewiesenen Nummernbereich in der Liste nach oben, sodass er von Skype for Business Server früher gefunden wird, und wendet die angegebene Aktion an, bevor die für andere Bereiche in der Liste angegebenen Aktionen angewendet werden.

    > [!NOTE]
    > Skype for Business Server durchsucht die Tabelle nicht zugewiesene Nummern von oben nach unten und verwendet den ersten Bereich, der der nicht zugewiesenen Zahl entspricht. Wenn Sie z. B. über einen Bereich verfügen, auf den als letzte Aktion zurückgegriffen werden soll, platzieren Sie diesen Bereich ganz unten in der Liste.

- **Nach unten** Verschiebt den ausgewählten nicht zugewiesenen Nummernbereich in der Liste nach unten.

- **Alle** übernehmen Speichert alle Änderungen, die Sie an nicht zugewiesenen Nummernbereichen vorgenommen haben.

    > [!IMPORTANT]
    > Mit diesem Befehl werden alle Änderungen gespeichert, die Sie auf der Seite **Neue nicht zugewiesene Nummer** und der Seite **Nicht zugewiesene Nummer bearbeiten** vorgenommen haben.

- **Aktualisieren** Aktualisiert die Liste der nicht zugewiesenen Nummernbereiche.

In der folgenden Liste werden die Felder der Seite beschrieben.

- **Name** Der eindeutige Name, der den nicht zugewiesenen Nummernbereich identifiziert.

- **Bundesland** Zeigt, welche Nummernbereiche in der Datenbank gespeichert wurden und welche nicht.

- **Start Bereich** Die Anfangszahl des nicht zugewiesenen Nummernbereichs.

- **Endbereich** Die letzte Nummer des nicht zugewiesenen Nummernbereichs.

- **Ziel** Die Dienst-ID des Anwendungsdiensts, der die Ankündigungs Anwendung hostet, die eingehende Anrufe an diesen Bereich nicht zugewiesener Nummern abwickeln soll.

- **Ankündigung** Die Ansage, die für diesen Bereich nicht zugewiesener Nummern abgespielt wird.

Details zu Ankündigungs Features und-Funktionen finden Sie unter [Planen der Ankündigungs Anwendung in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) in der Planungsdokumentation. Ausführliche Informationen zur Verwendung von Bereichen nicht zugewiesener Nummern finden Sie in der Betriebsdokumentation unter [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx).


