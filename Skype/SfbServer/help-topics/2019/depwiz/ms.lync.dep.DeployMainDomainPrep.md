---
title: Vorbereiten der aktuellen Domäne
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainDomainPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: bfcb37ca-34eb-4d0d-9694-6edd2e7fe0f3
ROBOTS: NOINDEX, NOFOLLOW
description: 'Um eine Domäne auf Hostserver mit Skype for Business Server- oder Skype for Business Server-Benutzern vorzubereiten, müssen Sie Schritt 5: Vorbereiten der aktuellen Domäne ausführen, wie im Thema Using Setup to Run Domain Preparation beschrieben. Zum Abschließen des Schritts müssen Sie als Mitglied der Gruppe "Domänenadmins" in der Domäne, die Sie vorbereiten, oder Mitglied der Gruppe "Organisations-Admins" der Gesamtstruktur, zu der die Domäne gehört, angemeldet sein. So bereiten Sie die Domäne vor:'
ms.openlocfilehash: a71e50b0f3d55709c3c22709177b41e541f7075f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097340"
---
# <a name="prepare-current-domain"></a>Vorbereiten der aktuellen Domäne

Zum Vorbereiten einer Domäne auf Hostserver mit Skype for Business Server- oder Skype for Business Server-Benutzern müssen Sie Schritt **5:** Vorbereiten der aktuellen Domäne ausführen, wie im Thema Using [Setup to Run Domain Preparation beschrieben.](/previous-versions/office/lync-server-2013/lync-server-2013-running-domain-preparation) Zum Abschließen des Schritts müssen Sie als Mitglied der Gruppe "Domänenadmins" in der Domäne, die Sie vorbereiten, oder Mitglied der Gruppe "Organisations-Admins" der Gesamtstruktur, zu der die Domäne gehört, angemeldet sein. So bereiten Sie die Domäne vor:

1. Führen Sie im Installationsordner oder den Medien von Skype for Business Server Setup.exe, um den Skype for Business Server-Bereitstellungs-Assistenten zu starten.

2. Klicken Sie auf **Active Directory vorbereiten**, und warten Sie das Bestimmen des Bereitstellungsstatus ab.

3. Klicken Sie bei **Schritt 5: Aktuelle Domäne vorbereiten** auf **Ausführen**.

4. Suchen Sie auf der Seite **Befehle ausführen** nach **Aufgabenstatus: Abgeschlossen**, und klicken Sie dann auf **Protokoll anzeigen**.

5. Erweitern Sie **unter** der Spalte Aktion den Bereich Domänenvorbereitung, suchen Sie am Ende jeder Aufgabe nach einem Ausführungsergebnis, um sicherzustellen, dass die Domänenvorbereitung erfolgreich abgeschlossen wurde, schließen Sie das Protokoll, und klicken Sie dann auf Fertig **\<Success\>** **stellen.**

> [!TIP]
> Wenn Sie die Protokolldateien überprüfen müssen, die vom Skype for Business Server-Bereitstellungs-Assistenten erstellt wurden, finden Sie sie auf dem Computer, auf dem der Bereitstellungs-Assistent ausgeführt wurde, im Verzeichnis Benutzer des Active Directory Domain Services-Benutzers, der den Schritt ausgeführt hat. Wenn sich der Benutzer beispielsweise als Domänenadministrator in der Domäne Contoso.net angemeldet hat, befinden sich die Protokolldateien in: C:\Users\Administrator.Contoso\AppData\Local\Temp.