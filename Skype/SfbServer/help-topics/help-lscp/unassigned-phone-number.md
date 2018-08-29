---
title: Nicht zugewiesene Telefonnummer
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaVacantNumMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24eca749-a9f3-40e7-839b-d21c3ef7d533
description: Nicht zugewiesene Nummern sind Rufnummern, die für Ihre Organisation gültig sind, jedoch keinem Benutzer oder Telefon zugewiesen sind. In der Tabelle mit den nicht zugewiesenen Nummern ist angegeben, wie Anrufe bei nicht zugewiesenen Nummern behandelt werden sollen.
ms.openlocfilehash: c5161fb083e9d251c05d39601e793b508590c61a
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2018
ms.locfileid: "23262561"
---
# <a name="unassigned-phone-number"></a>Nicht zugewiesene Telefonnummer

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

In der folgenden Liste sind die Befehle der Seite beschrieben.

- **Neue** Startet einen neuen Bereichs nicht zugewiesenen Nummern an.

- **Bearbeiten** Öffnet den ausgewählten nicht zugewiesenen Nummernbereich zur Bearbeitung, wählt alle nicht zugewiesenen Nummernbereiche in der Liste oder löscht den ausgewählten Bereich nicht zugewiesenen Nummern.

- **Nach oben verschieben** Verschiebt den ausgewählten Bereichs nicht zugewiesenen Nummern oben in der Liste an, sodass Skype für Business Server früher ermittelt und wendet die angegebene Aktion vor dem Anwenden von Aktionen für andere Bereiche in der Liste angegeben.

    > [!NOTE]
    > Skype für Business Server sucht den Tabelle nicht zugewiesenen Nummern von oben nach unten und verwendet den ersten Bereich, der nicht zugewiesene Nummer entspricht. Wenn Sie z. B. über einen Bereich verfügen, auf den als letzte Aktion zurückgegriffen werden soll, platzieren Sie diesen Bereich ganz unten in der Liste.

- **Nach unten verschieben** Verschiebt den ausgewählten Bereich nicht zugewiesenen Nummern in der Liste nach unten.

- **Alle Commit** Speichert alle nicht zugewiesenen Nummernbereiche vorgenommenen Änderungen.

    > [!IMPORTANT]
    > Mit diesem Befehl werden alle Änderungen gespeichert, die Sie auf der Seite **Neue nicht zugewiesene Nummer** und der Seite **Nicht zugewiesene Nummer bearbeiten** vorgenommen haben.

- **Aktualisieren** Aktualisiert die Liste der nicht zugewiesenen Nummernbereiche.

In der folgenden Liste werden die Felder der Seite beschrieben.

- **Name** Der eindeutige Name, der den Bereich nicht zugewiesener Nummern.

- **Zustand** Mit der Datenbank und die keinen wurden dargestellt, welche Nummernbereiche gespeichert.

- **Anfangsbereich gibt** Die Anfangsnummer des Bereichs nicht zugewiesener Nummern.

- **Endbereich** Die Endnummer des Bereichs nicht zugewiesener Nummern.

- **Ziel** Die Dienst-ID des Anwendungsdiensts, die die ankündigungsanwendung hostet, die eingehende Anrufe für diesen Bereich nicht zugewiesener Nummern behandelt werden sollen.

- **Ankündigung** Die Ankündigung, die für diesen Bereich nicht zugewiesener Nummern wiedergegeben werden.

Ausführliche Informationen zur Ankündigung Features und Funktionen finden Sie unter [Planen für die ankündigungsanwendung in Skype für Business 2015](../../plan-your-deployment/enterprise-voice-solution/announcement.md) in der Planungsdokumentation. Ausführliche Informationen zur Verwendung von nicht zugewiesenen Nummernbereiche finden Sie unter [Konfigurieren von Routing von nicht zugewiesenen Telefonnummern](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) in der Betriebsdokumentation.


