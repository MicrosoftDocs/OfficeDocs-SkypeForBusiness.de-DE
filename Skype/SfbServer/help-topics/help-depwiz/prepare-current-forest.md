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
description: Zum Vorbereiten der Active Directory Domain Services-Gesamtstruktur müssen Sie das Schema erfolgreich erweitern, wie im Thema "Ausführen der Schemavorbereitung" beschrieben, und sicherstellen, dass das Schema repliziert wurde.
ms.openlocfilehash: eaeabfb543d258e65b387afeafddf15367f6caf7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815435"
---
# <a name="prepare-current-forest"></a>Vorbereiten der aktuellen Gesamtstruktur

Zum Vorbereiten der Active Directory Domain Services-Gesamtstruktur müssen Sie das Schema erfolgreich erweitern, wie im Thema ["Ausführen](https://technet.microsoft.com/library/067726ae-fd3f-4133-a32f-26d2603ac674.aspx)der Schemavorbereitung" beschrieben, und sicherstellen, dass das Schema repliziert wurde.

Sobald diese Voraussetzungen erfüllt sind, können Sie mit **Schritt 3: Aktuelle Gesamtstruktur vorbereiten** beginnen. Melden Sie sich zum Vorbereiten der Gesamtstruktur bei einem Computer in der Stammdomäne der Gesamtstruktur als Mitglied der Gruppe "Domänen-Admins" in der Stammdomäne der Gesamtstruktur oder der Gruppe "Organisations-Admins" für die Gesamtstruktur an, die Sie vorbereiten.

1. Klicken Sie im Bereitstellungs-Assistenten bei **Schritt 3: Aktuelle Gesamtstruktur vorbereiten** auf **Ausführen**.

2. Klicken Sie auf der Seite **Gesamtstruktur vorbereiten** auf **Weiter**.

    > [!NOTE]
    > Bei der Gesamtstrukturvorbereitung können Sie auswählen, wo die universellen Gruppen für Skype for Business Server 2015 gespeichert werden. Wählen Sie einen Speicherort entsprechend den Anforderungen Ihrer Organisation.

3. Suchen Sie auf der Seite **Befehle ausführen** nach **Aufgabenstatus: Abgeschlossen**, und klicken Sie dann auf **Protokoll anzeigen**. Vergewissern Sie sich, dass keine Fehler vorliegen. Überprüfen Sie die Warnungen dahingehend, ob sie erwartet werden und für Ihre Infrastruktur typisch sind.

4. Erweitern  Sie unter der Spalte "Aktion" im Protokoll die Gesamtstrukturvorbereitung, und suchen Sie am Ende jeder Aufgabe nach einem Ausführungsergebnis, um sicherzustellen, dass die Gesamtstrukturvorbereitung erfolgreich abgeschlossen wurde, schließen Sie das Protokoll, und klicken Sie dann auf "Fertig **\<Success\>** stellen". 

5. Warten Sie, bis die Replikation der Active Directory Domain Services abgeschlossen ist, oder erzwingen Sie die Replikation auf alle Domänencontroller, die im **Active Directory-Standort-** und -Dienste-Snap-In für den Stammdomänencontroller der Gesamtstruktur aufgeführt sind, bevor Sie die Domänenvorbereitung ausführen. Erzwingen Sie die Replikation zwischen den Domänencontrollern an allen Active Directory-Standorten, damit die Replikation an den Standorten innerhalb von Minuten durchgeführt werden kann.

    > [!TIP]
    > Wenn Sie die vom Skype for Business Server-Bereitstellungs-Assistenten erstellten Protokolldateien überprüfen müssen, finden Sie sie auf dem Computer, auf dem der Bereitstellungsassistent ausgeführt wurde, im Verzeichnis "Users" des Active Directory Domain Services-Benutzers, der den Schritt ausgeführt hat. Wenn sich der Benutzer beispielsweise als Domänenadministrator in der Domäne Contoso.net angemeldet hat, befinden sich die Protokolldateien unter: C:\Users\Administrator.Contoso\AppData\Local\Temp


