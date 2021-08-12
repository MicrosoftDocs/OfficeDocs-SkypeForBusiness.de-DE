---
title: Vorbereiten der aktuellen Gesamtstruktur
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11f5e359-97eb-45f7-a730-9ddbbaa40b83
description: Um die Active Directory Domain Services-Gesamtstruktur vorzubereiten, müssen Sie das Schema wie im Thema "Schemavorbereitung ausführen" beschrieben erfolgreich erweitern und sicherstellen, dass das Schema repliziert wurde.
ms.openlocfilehash: 6b02ae0139c4ac813dd8562b237022112f76201d79e82b856e5bfe7e8d6972e7
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54309644"
---
# <a name="prepare-current-forest"></a>Vorbereiten der aktuellen Gesamtstruktur

Um die Active Directory Domain Services-Gesamtstruktur vorzubereiten, müssen Sie das Schema wie im Thema ["Schemavorbereitung ausführen"](/previous-versions/office/lync-server-2013/lync-server-2013-preparing-the-active-directory-schema)beschrieben erfolgreich erweitern und sicherstellen, dass das Schema repliziert wurde.

Sobald diese Voraussetzungen erfüllt sind, können Sie mit **Schritt 3: Aktuelle Gesamtstruktur vorbereiten** beginnen. Melden Sie sich zum Vorbereiten der Gesamtstruktur bei einem Computer in der Stammdomäne der Gesamtstruktur als Mitglied der Gruppe "Domänen-Admins" in der Stammdomäne der Gesamtstruktur oder der Gruppe "Organisations-Admins" für die Gesamtstruktur an, die Sie vorbereiten.

1. Klicken Sie im Bereitstellungs-Assistenten bei **Schritt 3: Aktuelle Gesamtstruktur vorbereiten** auf **Ausführen**.

2. Klicken Sie auf der Seite **Gesamtstruktur vorbereiten** auf **Weiter**.

    > [!NOTE]
    > Mit der Gesamtstrukturvorbereitung können Sie auswählen, wo die universellen Gruppen für Skype for Business Server 2015 platziert werden sollen. Wählen Sie einen Speicherort entsprechend den Anforderungen Ihrer Organisation.

3. Suchen Sie auf der Seite **Befehle ausführen** nach **Aufgabenstatus: Abgeschlossen**, und klicken Sie dann auf **Protokoll anzeigen**. Vergewissern Sie sich, dass keine Fehler vorliegen. Überprüfen Sie die Warnungen dahingehend, ob sie erwartet werden und für Ihre Infrastruktur typisch sind.

4. Erweitern Sie unter der Spalte **"Aktion"** im Protokoll **"Gesamtstrukturvorbereitung",** suchen Sie nach einem **\<Success\>** Ausführungsergebnis am Ende jeder Aufgabe, um zu überprüfen, ob die Gesamtstrukturvorbereitung erfolgreich abgeschlossen wurde, schließen Sie das Protokoll, und klicken Sie dann auf **"Fertig stellen".**

5. Warten Sie, bis die Replikation der Active Directory-Domänendienste abgeschlossen ist, oder erzwingen Sie die Replikation auf allen Domänencontrollern, die im **Active Directory-Snap-In "Standorte und Dienste"** für den Stammdomänencontroller der Gesamtstruktur aufgeführt sind, bevor Sie die Domänenvorbereitung ausführen. Erzwingen Sie die Replikation zwischen den Domänencontrollern an allen Active Directory-Standorten, damit die Replikation an den Standorten innerhalb von Minuten durchgeführt werden kann.

    > [!TIP]
    > Wenn Sie die Vom Skype for Business Server Bereitstellungs-Assistenten erstellten Protokolldateien überprüfen müssen, finden Sie sie auf dem Computer, auf dem der Bereitstellungs-Assistent ausgeführt wurde, im Verzeichnis "Benutzer" des Active Directory Domain Services-Benutzers, der den Schritt ausgeführt hat. Wenn sich der Benutzer beispielsweise als Domänenadministrator in der Domäne Contoso.net angemeldet hat, befinden sich die Protokolldateien in: C:\Users\Administrator.Contoso\AppData\Local\Temp