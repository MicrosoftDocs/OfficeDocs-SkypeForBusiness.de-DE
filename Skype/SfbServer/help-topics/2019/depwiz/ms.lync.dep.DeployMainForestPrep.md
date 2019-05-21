---
title: Vorbereiten der aktuellen Gesamtstruktur
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11f5e359-97eb-45f7-a730-9ddbbaa40b83
ROBOTS: NOINDEX, NOFOLLOW
description: Wenn Sie die Active Directory-Domänendienst-Gesamtstruktur vorbereiten möchten, müssen Sie das Schema erfolgreich erweitern, wie im Thema Ausführen der Schemavorbereitung beschrieben, und sicherstellen, dass das Schema repliziert wurde.
ms.openlocfilehash: 810bfae1fd308ef943f41846a8baef774f4f724e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303397"
---
# <a name="prepare-current-forest"></a>Vorbereiten der aktuellen Gesamtstruktur

Wenn Sie die Active Directory-Domänendienst-Gesamtstruktur vorbereiten möchten, müssen Sie das Schema erfolgreich erweitern, wie im Thema [Ausführen der Schemavorbereitung](https://technet.microsoft.com/library/067726ae-fd3f-4133-a32f-26d2603ac674.aspx)beschrieben, und sicherstellen, dass das Schema repliziert wurde.

Sobald diese Voraussetzungen erfüllt sind, können Sie mit **Schritt 3: Aktuelle Gesamtstruktur vorbereiten** beginnen. Melden Sie sich zum Vorbereiten der Gesamtstruktur bei einem Computer in der Stammdomäne der Gesamtstruktur als Mitglied der Gruppe „Domänen-Admins“ in der Stammdomäne der Gesamtstruktur oder der Gruppe „Organisations-Admins“ für die Gesamtstruktur an, die Sie vorbereiten.

1. Klicken Sie im Bereitstellungs-Assistenten unter **Schritt 3: Vorbereiten der aktuellen Gesamtstruktur** auf **Ausführen**.

2. Klicken Sie auf der Seite **Vorbereiten der aktuellen Gesamtstruktur** auf **Weiter**.

    > [!NOTE]
    > Mit der Gesamtstrukturvorbereitung können Sie auswählen, wo die universellen Gruppen für Skype for Business Server platziert werden sollen. Wählen Sie einen Speicherort entsprechend den Anforderungen Ihrer Organisation.

3. Suchen Sie auf der Seite **Befehle ausführen** nach **Aufgabenstatus: Abgeschlossen** und klicken Sie dann auf **Protokoll anzeigen**. Vergewissern Sie sich, dass keine Fehler vorliegen. Überprüfen Sie die Warnungen dahingehend, ob sie erwartet werden und für Ihre Infrastruktur typisch sind.

4. Erweitern Sie in der Spalte **Aktion** im Protokoll die **Gesamtstruktur**Vorbereitung, suchen Sie am Ende jeder Aufgabe nach einem ** \<\> ** Ergebnis der erfolgreichen Ausführung, um zu überprüfen, ob die Gesamtstrukturvorbereitung erfolgreich abgeschlossen wurde, schließen Sie das Protokoll, und klicken Sie dann auf **Fertig stellen. **.

5. Warten Sie, bis die Active Directory-Domänendienst Replikation abgeschlossen ist, oder erzwingen Sie die Replikation auf alle Domänencontroller, die im Snap-in **Active Directory-Standorte und-Dienste** für den Gesamtstruktur-Stammdomänencontroller aufgelistet sind, bevor Sie die Domänenvorbereitung ausführen. Erzwingen Sie die Replikation zwischen den Domänencontrollern an allen Active Directory-Standorten, damit die Replikation innerhalb der Websites innerhalb weniger Minuten erfolgen kann.

    > [!TIP]
    > Wenn Sie die Protokolldateien überprüfen müssen, die vom Bereitstellungs-Assistenten für Skype for Business Server erstellt wurden, können Sie diese auf dem Computer finden, auf dem der Bereitstellungs-Assistent ausgeführt wurde, und zwar im Verzeichnis Benutzer des Active Directory-Domänendienste-Benutzers, der den Schritt ausgeführt hat. Wenn sich der Benutzer beispielsweise als Domänenadministrator im Domänen contoso.net angemeldet hat, befinden sich die Protokolldateien in: C:\users\administrator.Contoso\AppData\Local\Temp


