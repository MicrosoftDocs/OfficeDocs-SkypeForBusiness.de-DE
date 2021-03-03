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
localization_priority: Normal
ms.assetid: bfcb37ca-34eb-4d0d-9694-6edd2e7fe0f3
description: 'Zum Vorbereiten einer Domäne als Hostserver mit Skype for Business Server 2015- oder Skype for Business Server-Benutzern müssen Sie Schritt 5: Vorbereiten der aktuellen Domäne ausführen, wie im Thema "Verwenden von Setup zum Ausführen der Domänenvorbereitung" beschrieben. Zum Abschließen des Schritts müssen Sie als Mitglied der Gruppe "Domänenadmins" in der Domäne, die Sie vorbereiten, oder Mitglied der Gruppe "Organisations-Admins" der Gesamtstruktur, zu der die Domäne gehört, angemeldet sein. So bereiten Sie die Domäne vor:'
ms.openlocfilehash: b43af552983a5a7aae998fab6de9ace4e96084b2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804965"
---
# <a name="prepare-current-domain"></a>Vorbereiten der aktuellen Domäne

Zum Vorbereiten einer Domäne als Hostserver mit Skype for Business Server 2015- oder Skype for Business Server-Benutzern müssen Sie Schritt **5: Vorbereiten** der aktuellen Domäne ausführen, wie im Thema "Verwenden von [Setup zum](https://technet.microsoft.com/library/95dab800-1f2c-4506-b36c-99986643b149.aspx)Ausführen der Domänenvorbereitung" beschrieben. Zum Abschließen des Schritts müssen Sie als Mitglied der Gruppe "Domänenadmins" in der Domäne, die Sie vorbereiten, oder Mitglied der Gruppe "Organisations-Admins" der Gesamtstruktur, zu der die Domäne gehört, angemeldet sein. So bereiten Sie die Domäne vor:

1. Führen Sie im Skype for Business Server 2015-Installationsordner oder -Medium Setup.exe, um den Skype for Business Server-Bereitstellungs-Assistenten zu starten.

2. Klicken Sie auf **Active Directory vorbereiten**, und warten Sie das Bestimmen des Bereitstellungsstatus ab.

3. Klicken Sie bei **Schritt 5: Aktuelle Domäne vorbereiten** auf **Ausführen**.

4. Suchen Sie auf der Seite **Befehle ausführen** nach **Aufgabenstatus: Abgeschlossen**, und klicken Sie dann auf **Protokoll anzeigen**.

5. Erweitern **Sie** in der Spalte "Aktion" die Domänenvorbereitung, und suchen Sie am Ende jeder Aufgabe nach einem Ausführungsergebnis, um sicherzustellen, dass die Domänenvorbereitung erfolgreich abgeschlossen wurde, schließen Sie das Protokoll, und klicken Sie dann auf "Fertig **\<Success\>** **stellen".**

> [!TIP]
> Wenn Sie die vom Skype for Business Server-Bereitstellungs-Assistenten erstellten Protokolldateien überprüfen müssen, finden Sie sie auf dem Computer, auf dem der Bereitstellungsassistent ausgeführt wurde, im Verzeichnis "Benutzer" des Active Directory Domain Services-Benutzers, der den Schritt ausgeführt hat. Wenn sich der Benutzer beispielsweise als Domänenadministrator in der Domäne Contoso.net angemeldet hat, befinden sich die Protokolldateien unter: C:\Users\Administrator.Contoso\AppData\Local\Temp.


