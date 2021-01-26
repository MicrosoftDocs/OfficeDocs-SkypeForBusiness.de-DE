---
title: Nicht zugewiesene Telefonnummer
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.VoiceFeaVacantNumMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24eca749-a9f3-40e7-839b-d21c3ef7d533
description: Nicht zugewiesene Nummern sind Rufnummern, die für Ihre Organisation gültig sind, jedoch keinem Benutzer oder Telefon zugewiesen sind. In der Tabelle mit den nicht zugewiesenen Nummern ist angegeben, wie Anrufe bei nicht zugewiesenen Nummern behandelt werden sollen.
ms.openlocfilehash: 4b736aef028421bca6c4945095f9d293d18f3550
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826885"
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

- **Neu** Startet einen neuen Bereich nicht zugewiesener Nummern.

- **Bearbeiten** Öffnet den ausgewählten Bereich nicht zugewiesener Nummern zur Bearbeitung, wählt alle Bereiche nicht zugewiesener Nummern in der Liste aus oder löscht den ausgewählten Bereich nicht zugewiesener Nummern.

- **Nach oben** Verschiebt den ausgewählten Bereich nicht zugewiesener Nummern in der Liste nach oben, sodass Skype for Business Server ihn früher findet und die angegebene Aktion vor dem Anwenden von Aktionen angewendet, die für andere Bereiche in der Liste angegeben sind.

    > [!NOTE]
    > Skype for Business Server durchsucht die Tabelle nicht zugewiesener Nummern von oben nach unten und verwendet den ersten Bereich, der der nicht zugewiesenen Nummer entspricht. Wenn Sie z. B. über einen Bereich verfügen, auf den als letzte Aktion zurückgegriffen werden soll, platzieren Sie diesen Bereich ganz unten in der Liste.

- **Nach unten** Verschiebt den ausgewählten Bereich nicht zugewiesener Nummern in der Liste nach unten.

- **Commit für alle** Speichert alle Änderungen, die Sie an Bereichen nicht zugewiesener Nummern vorgenommen haben.

    > [!IMPORTANT]
    > Mit diesem Befehl werden alle Änderungen gespeichert, die Sie auf der Seite **Neue nicht zugewiesene Nummer** und der Seite **Nicht zugewiesene Nummer bearbeiten** vorgenommen haben.

- **Aktualisieren** Aktualisiert die Liste der Bereiche nicht zugewiesener Nummern.

In der folgenden Liste sind die Felder der Seite beschrieben.

- **Name** Der eindeutige Name, der den Bereich nicht zugewiesener Nummern identifiziert.

- **Status** Zeigt an, welche Nummernbereiche in der Datenbank gespeichert wurden und welche nicht.

- **Startbereich** Die Anfangsnummer des Bereichs nicht zugewiesener Nummern.

- **Endbereich** Die Endnummer des Bereichs nicht zugewiesener Nummern.

- **Ziel** Die Dienst-ID des Anwendungsdiensts, der die Ansageanwendung hostet, die eingehende Anrufe für diesen Bereich nicht zugewiesener Nummern verarbeiten wird.

- **Ankündigung** Die Ansage, die für diesen Bereich nicht zugewiesener Nummern abgespielt wird.

Ausführliche Informationen zu Ankündigungsfeatures und -funktionen finden Sie unter "Planen der Ankündigungsanwendung [in Skype for Business 2015"](../../plan-your-deployment/enterprise-voice-solution/announcement.md) in der Planungsdokumentation. Ausführliche Informationen zur Verwendung von Bereichen nicht zugewiesener Nummern finden Sie unter [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) in der Betriebsdokumentation.


