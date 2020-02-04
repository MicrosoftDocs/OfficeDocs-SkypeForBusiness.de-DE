---
title: Vorbereiten der aktuellen Domäne
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployMainDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bfcb37ca-34eb-4d0d-9694-6edd2e7fe0f3
description: 'Wenn Sie eine Domäne auf Hostserver vorbereiten möchten, auf denen Skype for Business Server 2015 oder Skype for Business Server-Benutzer ausgeführt werden, müssen Sie Schritt 5: Vorbereiten der aktuellen Domäne ausführen, wie im Thema Verwenden von Setup zum Ausführen der Domänenvorbereitung beschrieben. Zum Abschließen des Schritts müssen Sie als Mitglied der Gruppe „Domänenadmins“ in der Domäne, die Sie vorbereiten, oder der Gruppe „Organisations-Admins“ der Gesamtstruktur, zu der die Domäne gehört, angemeldet sein. So bereiten Sie die Domäne vor:'
ms.openlocfilehash: 58ff8ff515d171f7d0d1b0c2fb7d653e25c3ad31
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41687408"
---
# <a name="prepare-current-domain"></a>Vorbereiten der aktuellen Domäne

Wenn Sie eine Domäne auf Hostserver vorbereiten möchten, auf denen Skype for Business Server 2015 oder Skype for Business Server-Benutzer ausgeführt werden, müssen Sie **Schritt 5: Vorbereiten der aktuellen Domäne**ausführen, wie im Thema [Verwenden von Setup zum Ausführen der Domänenvorbereitung](https://technet.microsoft.com/library/95dab800-1f2c-4506-b36c-99986643b149.aspx)beschrieben. Zum Abschließen des Schritts müssen Sie als Mitglied der Gruppe „Domänenadmins“ in der Domäne, die Sie vorbereiten, oder der Gruppe „Organisations-Admins“ der Gesamtstruktur, zu der die Domäne gehört, angemeldet sein. So bereiten Sie die Domäne vor:

1. Führen Sie im Skype for Business Server 2015-Installationsordner oder-Medium die Datei "Setup. exe" aus, um den Skype for Business Server-Bereitstellungs-Assistenten zu starten.

2. Klicken Sie auf **Active Directory vorbereiten** und warten Sie das Bestimmen des Bereitstellungsstatus ab.

3. Klicken Sie unter **Schritt 5: Aktuelle Domäne vorbereiten** auf **Ausführen**.

4. Suchen Sie auf der Seite **Befehle ausführen** nach **Aufgabenstatus: Abgeschlossen** und klicken Sie dann auf **Protokoll anzeigen**.

5. Erweitern Sie in der Spalte " **Aktion** " die **Domäne prep**, suchen Sie nach einem ** \<\> ** Ergebnis der erfolgreichen Ausführung am Ende jeder Aufgabe, um zu überprüfen, ob die Domänenvorbereitung erfolgreich abgeschlossen wurde, schließen Sie das Protokoll, und klicken Sie dann auf **Fertig stellen**.

> [!TIP]
> Wenn Sie die Protokolldateien überprüfen müssen, die vom Bereitstellungs-Assistenten für Skype for Business Server erstellt wurden, können Sie diese auf dem Computer finden, auf dem der Bereitstellungs-Assistent im Verzeichnis Benutzer des Active Directory-Domänendienste-Benutzers ausgeführt wurde, der den Schritt ausgeführt hat. Wenn sich der Benutzer beispielsweise als Domänenadministrator im Domänen contoso.net angemeldet hat, befinden sich die Protokolldateien in: C:\users\administrator.Contoso\AppData\Local\Temp.


