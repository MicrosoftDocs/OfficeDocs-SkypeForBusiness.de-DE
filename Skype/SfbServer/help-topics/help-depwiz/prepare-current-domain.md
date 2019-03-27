---
title: Vorbereiten der aktuellen Domäne
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bfcb37ca-34eb-4d0d-9694-6edd2e7fe0f3
description: 'Um eine Domäne und Hostservern, die mit Skype für Business Server 2015 oder Skype für Benutzer von Business Server vorzubereiten, müssen Sie Schritt 5: aktuelle Domäne vorbereiten, wie im Thema Verwenden des Setups zum Ausführen der Domänenvorbereitung beschrieben. Zum Abschließen des Schritts müssen Sie als Mitglied der Gruppe „Domänenadmins“ in der Domäne, die Sie vorbereiten, oder der Gruppe „Organisations-Admins“ der Gesamtstruktur, zu der die Domäne gehört, angemeldet sein. So bereiten Sie die Domäne vor:'
ms.openlocfilehash: 920640a32895c9168ca70ccb416541ae54ae0c79
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879413"
---
# <a name="prepare-current-domain"></a>Vorbereiten der aktuellen Domäne

Um eine Domäne und Hostservern, die mit Skype für Business Server 2015 oder Skype für Benutzer von Business Server vorzubereiten, müssen Sie **Schritt 5: aktuelle Domäne vorbereiten**, wie im Thema [Verwenden des Setups zum Ausführen der Domänenvorbereitung](https://technet.microsoft.com/library/95dab800-1f2c-4506-b36c-99986643b149.aspx)beschrieben. Zum Abschließen des Schritts müssen Sie als Mitglied der Gruppe „Domänenadmins“ in der Domäne, die Sie vorbereiten, oder der Gruppe „Organisations-Admins“ der Gesamtstruktur, zu der die Domäne gehört, angemeldet sein. So bereiten Sie die Domäne vor:

1. Führen Sie aus der Skype für Business Server 2015-Installationsordner oder auf dem Installationsmedium Setup.exe, um die Skype für Business Server-Bereitstellungs-Assistenten zu starten.

2. Klicken Sie auf **Active Directory vorbereiten** und warten Sie das Bestimmen des Bereitstellungsstatus ab.

3. Klicken Sie unter **Schritt 5: Aktuelle Domäne vorbereiten** auf **Ausführen**.

4. Suchen Sie auf der Seite **Befehle ausführen** nach **Aufgabenstatus: Abgeschlossen** und klicken Sie dann auf **Protokoll anzeigen**.

5. Erweitern Sie unter der Spalte **Aktion** **Domäne vorbereiten**, suchen Sie nach einer ** \<Erfolg\> ** Ausführungsergebnis am Ende jeder Aufgabe zu überprüfen, domänenvorbereitung erfolgreich abgeschlossen wurde, schließen Sie das Protokoll, und klicken Sie dann auf **Fertig stellen**.

> [!TIP]
> Wenn Sie die Protokolldateien überprüfen, die durch die Skype für Business Server-Bereitstellungs-Assistenten erstellt werden müssen, können sie auf dem Computer finden Sie dem Bereitstellungs-Assistenten im Verzeichnis Benutzer des Benutzers Active Directory Domain Services ausgeführt wurde, die im Schritt ausgeführt hat. Angenommen, wenn der Benutzer als Domänenadministrator in der Domäne Contoso.net angemeldet, die Protokolldateien befinden sich im: C:\Users\Administrator.Contoso\AppData\Local\Temp.


