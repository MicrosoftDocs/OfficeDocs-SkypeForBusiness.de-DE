---
title: Migrieren von Zugriffsnummern für die Einwahl
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Zum Migrieren der Kontaktobjekte muss das Cmdlet Move-CsApplicationEndpoint ausgeführt werden, um Einwahlnummern in Skype for Business Server 2019 zu migrieren. Während des Koexistenz Zeitraums für Legacy Installationen und Skype for Business Server 2019 Verhalten sich Einwahlnummern, die Sie in Skype for Business Server 2019 erstellt haben, ähnlich wie die Einwahl Zugriffsnummern, die Sie in der Legacy Installation erstellt haben, wie in diesem Beispiel beschrieben. Abschnitt.
ms.openlocfilehash: 35c1e665f8affdbf84628f9a7d532405779648f0
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991140"
---
# <a name="migrate-dial-in-access-numbers"></a>Migrieren von Zugriffsnummern für die Einwahl

Zum Migrieren der Kontaktobjekte muss das Cmdlet **Move-CsApplicationEndpoint** ausgeführt werden, um Einwahlnummern in Skype for Business Server 2019 zu migrieren. Während des Koexistenz Zeitraums für Legacy Installationen und Skype for Business Server 2019 Verhalten sich Einwahlnummern, die Sie in Skype for Business Server 2019 erstellt haben, ähnlich wie die Einwahl Zugriffsnummern, die Sie in der Legacy Installation erstellt haben, wie in diesem Beispiel beschrieben. Abschnitt. 

Einwahl Zugriffsnummern, die Sie in der Legacy Installation erstellt, aber in Skype for Business Server 2019 verschoben haben oder die Sie in Skype for Business Server 2019 vor, während oder nach der Migration erstellt haben, weisen die folgenden Merkmale auf:

- Sie werden nicht auf Office Communications Server 2007 R2-Besprechungseinladungen und auf der Seite Einwahl Zugriffsnummer angezeigt.

- In den Legacy-Installations Einladungen für Besprechungen und auf der Seite Einwahl Zugriffsnummer angezeigt.

- In den Skype for Business Server 2019-Besprechungseinladungen und auf der Seite "Einwahl Zugriffsnummer" angezeigt.

- Kann im Office Communications Server 2007 R2-Verwaltungstool nicht angezeigt oder geändert werden.

- Kann in der Systemsteuerung für Legacy Installationen und in der Legacy-Installations Verwaltungsshell angezeigt und geändert werden.

- Kann in der Skype for Business Server 2019-Systemsteuerung und in der Skype for Business Server 2019-Verwaltungsshell angezeigt und geändert werden.

- Kann innerhalb des Bereichs mithilfe des Cmdlets "CsDialinConferencingAccessNumber" mit dem Priority-Parameter neu sequenziert werden.

Sie müssen die Migration von Einwahl Zugriffsnummern beenden, die auf den Legacy Installations Pool verweisen, bevor Sie den Legacy Installations Pool außer Betrieb setzen. Wenn Sie die Migration von Einwahlnummern wie im folgenden Verfahren beschrieben nicht abschließen, treten bei eingehenden Anrufen an die Zugriffsnummern keine Fehler auf.

> [!IMPORTANT]
> Sie müssen dieses Verfahren vor der Außerbetriebnahme des Legacy Installations Pools ausführen. 

> [!NOTE]
> Es wird empfohlen, Einwahlnummern zu verschieben, wenn die Netzwerkauslastung gering ist, falls es einen kurzen Zeitraum für einen Ausfall des Diensts gibt. 

## <a name="to-identify-and-move-dial-in-access-numbers"></a>So identifizieren und verschieben Sie Einwahl Zugriffsnummern

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft Skype for Business Server 2019**, und klicken Sie dann auf **Skype for Business Server-Verwaltungsshell**.

2. Um jede Einwahl-Zugriffsnummer in einen Pool zu verschieben, der in Skype for Business Server 2019 gehostet wird, führen Sie in der Befehlszeile Folgendes aus: 

   ```PowerShell
   Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>
   ```

3. Öffnen Sie die Skype for Business Server-Systemsteuerung.

4. Klicken Sie in der linken Navigationsleiste auf **Konferenz**.

5. Klicken Sie auf die Registerkarte **Einwahlnummer** . 

6. Stellen Sie sicher, dass keine Einwahl Zugriffsnummern für den Legacy Installations Pool verbleiben, von dem aus Sie migrieren.

    > [!NOTE]
    > Wenn alle Einwahl Zugriffsnummern auf den Skype for Business Server 2019-Pool verweisen, können Sie den Legacy-Installations Pool außer Betrieb nehmen. 

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-control-panel"></a>Überprüfen der Migration von Einwahl Zugriffsnummern mit der Skype for Business Server-Systemsteuerung

1. Melden Sie sich bei einem Benutzerkonto, das der **CsUserAdministrator** -Rolle oder der **CsAdministrator** -Rolle zugewiesen ist, bei jedem Computer in ihrer internen Bereitstellung an. 

2. Öffnen Sie die Skype for Business Server-Systemsteuerung.

3. Klicken Sie in der linken Navigationsleiste auf **Konferenz**.

4. Klicken Sie auf die Registerkarte **Einwahlnummer** . 

5. Überprüfen Sie, ob alle Einwahl Zugriffsnummern in den Pool migriert werden, der in Skype for Business Server 2019 gehostet wird.

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-management-shell"></a>Überprüfen der Migration von Einwahl Zugriffsnummern mit der Skype for Business Server-Verwaltungsshell

1. Öffnen Sie die Skype for Business Server-Verwaltungsshell.

2. Um alle migrierten Zugriffsnummern für Einwahlkonferenzen zurückzugeben, führen Sie über die Befehlszeile Folgendes aus:

   ```PowerShell
   Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}
   ```

3. Überprüfen Sie, ob alle Einwahl Zugriffsnummern in den Pool migriert werden, der in Skype for Business Server 2019 gehostet wird.


