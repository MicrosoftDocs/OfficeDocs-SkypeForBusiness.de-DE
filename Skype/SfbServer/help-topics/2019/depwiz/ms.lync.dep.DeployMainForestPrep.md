---
title: Vorbereiten der aktuellen Gesamtstruktur
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainForestPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 11f5e359-97eb-45f7-a730-9ddbbaa40b83
ROBOTS: NOINDEX, NOFOLLOW
description: Zum Vorbereiten der Active Directory Domain Services-Gesamtstruktur müssen Sie das Schema erfolgreich erweitern, wie im Thema Ausführen der Schemavorbereitung beschrieben, und sicherstellen, dass das Schema repliziert wurde.
ms.openlocfilehash: 3a143ebc58fe14712c194abb18eb9de98c2ca2cb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097321"
---
# <a name="prepare-current-forest"></a>Vorbereiten der aktuellen Gesamtstruktur

Zum Vorbereiten der Active Directory-Domänendienste-Gesamtstruktur müssen Sie das Schema erfolgreich erweitern, wie im Thema Ausführen der [Schemavorbereitung](/previous-versions/office/lync-server-2013/lync-server-2013-preparing-the-active-directory-schema)beschrieben, und sicherstellen, dass das Schema repliziert wurde.

Sobald diese Voraussetzungen erfüllt sind, können Sie mit **Schritt 3: Aktuelle Gesamtstruktur vorbereiten** beginnen. Melden Sie sich zum Vorbereiten der Gesamtstruktur bei einem Computer in der Stammdomäne der Gesamtstruktur als Mitglied der Gruppe "Domänen-Admins" in der Stammdomäne der Gesamtstruktur oder der Gruppe "Organisations-Admins" für die Gesamtstruktur an, die Sie vorbereiten.

1. Klicken Sie im Bereitstellungs-Assistenten bei **Schritt 3: Aktuelle Gesamtstruktur vorbereiten** auf **Ausführen**.

2. Klicken Sie auf der Seite **Gesamtstruktur vorbereiten** auf **Weiter**.

    > [!NOTE]
    > Mit der Gesamtstrukturvorbereitung können Sie auswählen, wo die universellen Gruppen für Skype for Business Server gespeichert werden. Wählen Sie einen Speicherort entsprechend den Anforderungen Ihrer Organisation.

3. Suchen Sie auf der Seite **Befehle ausführen** nach **Aufgabenstatus: Abgeschlossen**, und klicken Sie dann auf **Protokoll anzeigen**. Vergewissern Sie sich, dass keine Fehler vorliegen. Überprüfen Sie die Warnungen dahingehend, ob sie erwartet werden und für Ihre Infrastruktur typisch sind.

4. Erweitern Sie **unter** der Spalte Aktion im Protokoll die Spalte Gesamtstrukturvorbereitung, suchen Sie am Ende jeder Aufgabe nach einem Ausführungsergebnis, um sicherzustellen, dass die Gesamtstrukturvorbereitung erfolgreich abgeschlossen wurde, schließen Sie das Protokoll, und klicken Sie dann auf Fertig **\<Success\>** **stellen.**

5. Warten Sie, bis die Active Directory-Domänendienstereplikation abgeschlossen ist, oder erzwingen Sie die Replikation auf alle Domänencontroller, die im Active Directory Sites and Services-Snap-In für den Stammdomänencontroller der Gesamtstruktur aufgeführt sind, bevor Sie die Domänenvorbereitung ausführen.  Erzwingen Sie die Replikation zwischen den Domänencontrollern an allen Active Directory-Standorten, damit die Replikation an den Standorten innerhalb von Minuten durchgeführt werden kann.

    > [!TIP]
    > Wenn Sie die Protokolldateien überprüfen müssen, die vom Skype for Business Server-Bereitstellungs-Assistenten erstellt wurden, finden Sie sie auf dem Computer, auf dem der Bereitstellungs-Assistent ausgeführt wurde, im Verzeichnis Benutzer des Active Directory Domain Services-Benutzers, der den Schritt ausgeführt hat. Wenn sich der Benutzer beispielsweise als Domänenadministrator in der Domäne Contoso.net angemeldet hat, befinden sich die Protokolldateien in: C:\Users\Administrator.Contoso\AppData\Local\Temp