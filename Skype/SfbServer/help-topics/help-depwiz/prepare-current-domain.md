---
title: Vorbereiten der aktuellen Domäne
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
- ms.lync.dep.DeployMainDomainPrep
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: bfcb37ca-34eb-4d0d-9694-6edd2e7fe0f3
description: 'Um eine Domäne auf Hostserver vorzubereiten, auf denen Skype for Business Server 2015- oder Skype for Business Server-Benutzer ausgeführt wird, müssen Sie Schritt 5: Vorbereiten der aktuellen Domäne ausführen, wie im Thema "Verwenden von Setup zum Ausführen der Domänenvorbereitung" beschrieben. Zum Abschließen des Schritts müssen Sie als Mitglied der Gruppe "Domänenadmins" in der Domäne, die Sie vorbereiten, oder Mitglied der Gruppe "Organisations-Admins" der Gesamtstruktur, zu der die Domäne gehört, angemeldet sein. So bereiten Sie die Domäne vor:'
ms.openlocfilehash: 61340981324aa32abfb97a8e33cd8e89e460b9c2
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58635469"
---
# <a name="prepare-current-domain"></a>Vorbereiten der aktuellen Domäne

Um eine Domäne auf Hostserver vorzubereiten, auf denen Skype for Business Server 2015- oder Skype for Business Server-Benutzer ausgeführt werden, müssen Sie **Schritt 5: Vorbereiten** der aktuellen Domäne ausführen, wie im Thema "Verwenden von Setup zum Ausführen der [Domänenvorbereitung"](/previous-versions/office/lync-server-2013/lync-server-2013-running-domain-preparation)beschrieben. Zum Abschließen des Schritts müssen Sie als Mitglied der Gruppe "Domänenadmins" in der Domäne, die Sie vorbereiten, oder Mitglied der Gruppe "Organisations-Admins" der Gesamtstruktur, zu der die Domäne gehört, angemeldet sein. So bereiten Sie die Domäne vor:

1. Führen Sie Setup.exe aus dem Installationsordner oder den Medien Skype for Business Server 2015 aus, um den Skype for Business Server Bereitstellungs-Assistenten zu starten.

2. Klicken Sie auf **Active Directory vorbereiten**, und warten Sie das Bestimmen des Bereitstellungsstatus ab.

3. Klicken Sie bei **Schritt 5: Aktuelle Domäne vorbereiten** auf **Ausführen**.

4. Suchen Sie auf der Seite **Befehle ausführen** nach **Aufgabenstatus: Abgeschlossen**, und klicken Sie dann auf **Protokoll anzeigen**.

5. Erweitern Sie unter der Spalte **"Aktion"** die Option **"Domänenvorbereitung",** suchen Sie am Ende jeder Aufgabe nach einem **\<Success\>** Ausführungsergebnis, um zu überprüfen, ob die Domänenvorbereitung erfolgreich abgeschlossen wurde, schließen Sie das Protokoll, und klicken Sie dann auf **"Fertig stellen".**

> [!TIP]
> Wenn Sie die Vom Skype for Business Server Bereitstellungs-Assistenten erstellten Protokolldateien überprüfen müssen, finden Sie diese auf dem Computer, auf dem der Bereitstellungs-Assistent im Verzeichnis "Benutzer" des Active Directory Domain Services-Benutzers ausgeführt wurde, der den Schritt ausgeführt hat. Wenn sich der Benutzer beispielsweise als Domänenadministrator in der Domäne Contoso.net angemeldet hat, befinden sich die Protokolldateien in: C:\Users\Administrator.Contoso\AppData\Local\Temp.