---
title: Nicht zugewiesene Telefonnummer
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.VoiceFeaVacantNumMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 24eca749-a9f3-40e7-839b-d21c3ef7d533
ROBOTS: NOINDEX, NOFOLLOW
description: Nicht zugewiesene Nummern sind Rufnummern, die für Ihre Organisation gültig sind, jedoch keinem Benutzer oder Telefon zugewiesen sind. In der Tabelle mit den nicht zugewiesenen Nummern ist angegeben, wie Anrufe bei nicht zugewiesenen Nummern behandelt werden sollen.
ms.openlocfilehash: 9dbb95d66fda093d8a094e92a84201b12a3baa6f2b454a75e2e3f7ab7b90a37c
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54280160"
---
# <a name="unassigned-phone-number"></a>Nicht zugewiesene Telefonnummer

> [!NOTE]
> Exchange UM bleibt in Skype for Business Server 2019 verfügbar, wenn Sie Skype for Business 2019 mit Exchange 2013 oder Exchange 2016 integrieren. Aufgrund von Änderungen bei der Unterstützung in Exchange 2019 wird Exchange UM-Integration zugunsten Cloud-Voicemail- und Cloud-Funktionen für die automatische Telefonzentrale deaktiviert.

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

- **Nach oben** Verschiebt den ausgewählten Bereich nicht zugewiesener Nummern in der Liste nach oben, sodass Skype for Business Server ihn schneller findet und die angegebene Aktion anwendet, bevor Aktionen angewendet werden, die für andere Bereiche in der Liste angegeben sind.

    > [!NOTE]
    > Skype for Business Server durchsucht die Tabelle nicht zugewiesener Nummern von oben nach unten und verwendet den ersten Bereich, der der nicht zugewiesenen Nummer entspricht. Wenn Sie z. B. über einen Bereich verfügen, auf den als letzte Aktion zurückgegriffen werden soll, platzieren Sie diesen Bereich ganz unten in der Liste.

- **Nach unten** Verschiebt den ausgewählten Bereich nicht zugewiesener Nummern in der Liste nach unten.

- **Commit für alle Ausführen** eines Commits Speichert alle Änderungen, die Sie an bereichen nicht zugewiesener Nummern vorgenommen haben.

    > [!IMPORTANT]
    > Mit diesem Befehl werden alle Änderungen gespeichert, die Sie auf der Seite **Neue nicht zugewiesene Nummer** und der Seite **Nicht zugewiesene Nummer bearbeiten** vorgenommen haben.

- **Aktualisieren** Aktualisiert die Liste nicht zugewiesener Nummernbereiche.

In der folgenden Liste sind die Felder der Seite beschrieben.

- **Name** Der eindeutige Name, der den Bereich nicht zugewiesener Nummern identifiziert.

- **Status** Zeigt an, welche Nummernbereiche in der Datenbank gespeichert wurden und welche nicht.

- **Startbereich** Die Anfangsnummer des Bereichs nicht zugewiesener Nummern.

- **Endbereich** Die Endnummer des Bereichs nicht zugewiesener Nummern.

- **Ziel** Die Dienst-ID des Anwendungsdiensts, der die Ankündigungsanwendung hostet, die eingehende Anrufe für diesen Bereich nicht zugewiesener Nummern verarbeitet.

- **Ankündigung** Die Ankündigung, die für diesen Bereich nicht zugewiesener Nummern wiedergegeben wird.

Ausführliche Informationen zu ankündigungsfeatures und -funktionen finden Sie [unter "Plan for the Announcement application in Skype for Business"](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) in der Planungsdokumentation. Ausführliche Informationen zur Verwendung von Bereichen nicht zugewiesener Nummern finden Sie unter [Configure Routing of Unassigned Phone Numbers](/previous-versions/office/lync-server-2013/lync-server-2013-configure-unassigned-phone-numbers) in der Betriebsdokumentation.