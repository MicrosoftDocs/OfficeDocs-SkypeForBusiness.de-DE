---
title: Migrieren von Zugriffsnummern für die Einwahl
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Zum Migrieren der Kontaktobjekte müssen Sie das Cmdlet "CsApplicationEndpoint" ausführen, um die Zugriffsnummern für die Einwahl in Skype for Business Server 2019 zu migrieren. Während des Zeitraums für die Legacy Installation und Skype for Business Server 2019-Koexistenz Verhalten sich Einwahlnummern, die Sie in Skype for Business Server 2019 erstellt haben, ähnlich wie die in diesem Abschnitt beschriebenen Zugriffsnummern für Einwahlen, die Sie in der Legacy Installation erstellt haben.
ms.openlocfilehash: 0df71debe8a6d5c686d8bce17b837f32a4ca2bab
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752697"
---
# <a name="migrate-dial-in-access-numbers"></a>Migrieren von Zugriffsnummern für die Einwahl

Zum Migrieren der Kontaktobjekte müssen Sie das Cmdlet " **CsApplicationEndpoint** " ausführen, um die Zugriffsnummern für die Einwahl in Skype for Business Server 2019 zu migrieren. Während des Zeitraums für die Legacy Installation und Skype for Business Server 2019-Koexistenz Verhalten sich Einwahlnummern, die Sie in Skype for Business Server 2019 erstellt haben, ähnlich wie die in diesem Abschnitt beschriebenen Zugriffsnummern für Einwahlen, die Sie in der Legacy Installation erstellt haben. 

Einwahlnummern, die Sie in der Legacy Installation erstellt, aber auf Skype for Business Server 2019 verschoben haben oder die Sie in Skype for Business Server 2019 vor, während oder nach der Migration erstellt haben, weisen die folgenden Merkmale auf:

- Sie werden nicht in Office Communications Server 2007 R2-Besprechungseinladungen und auf der Einwahlnummernseite angezeigt.

- In den Legacy-Installations-Besprechungseinladungen und auf der Seite für die Einwahl Zugriffsnummer angezeigt.

- Auf Skype for Business Server 2019-Besprechungseinladungen und auf der Seite für die Einwahl Zugriffsnummer angezeigt.

- Sie können nicht im Verwaltungstool von Office Communications Server 2007 R2 angezeigt oder geändert werden.

- Kann in der Systemsteuerung der Legacy Installation und in der Legacy install Management Shell angezeigt und geändert werden.

- Kann in der Skype for Business Server 2019-Systemsteuerung und in Skype for Business Server 2019-Verwaltungsshell angezeigt und geändert werden.

- Sie können innerhalb des Bereichs durch Verwendung des Set-CsDialinConferencingAccessNumber-Cmdlets mit dem Priority-Parameter neu sequenziert werden.

Sie müssen die Migration von Einwahlnummern, die auf den Legacy-Installations Pool deuten, abschließen, bevor Sie den Legacy-Installations Pool außer Betrieb nehmen. Wenn Sie die Migration von Einwahlnummern nicht wie im folgenden Verfahren beschrieben abschließen, schlagen eingehende Anrufe an die Einwahlnummern fehl.

> [!IMPORTANT]
> Sie müssen dieses Verfahren ausführen, bevor Sie den Legacy Installations Pool außer Betrieb nehmen. 

> [!NOTE]
> Wir empfehlen, das Verschieben von Einwahlen zu einem Zeitpunkt vorzunehmen, zu dem die Netzwerkauslastung möglichst gering ist, für den Fall, dass es zu einem kurzen Dienstausfall kommt. 

## <a name="to-identify-and-move-dial-in-access-numbers"></a>So identifizieren und verschieben Sie Einwahlnummern

1. Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft Skype for Business Server 2019**, und klicken Sie dann auf **Skype for Business Server Management Shell**.

2. Um jede Zugriffsnummer für die Einwahl in einen Pool zu migrieren, der auf Skype for Business Server 2019 gehostet wird, führen Sie über die Befehlszeile Folgendes aus: 

   ```PowerShell
   Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>
   ```

3. Öffnen Sie Skype for Business Server Systemsteuerung.

4. Klicken Sie in der linken Navigationsleiste auf **Konferenz**.

5. Klicken Sie auf die Registerkarte **Einwahlnummer**. 

6. Stellen Sie sicher, dass keine Einwahlnummern für den Legacy-Installations Pool verbleiben, von dem Sie migrieren.

    > [!NOTE]
    > Wenn alle Zugriffsnummern für Einwahlen auf den Skype for Business Server 2019-Pool deuten, können Sie den Legacy-Installations Pool außer Betrieb nehmen. 

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-control-panel"></a>Überprüfen der Migration von Zugriffsnummern für die Einwahl mit Skype for Business Server Systemsteuerung

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle **CsUserAdministrator** oder **CsAdministrator** zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an. 

2. Öffnen Sie Skype for Business Server Systemsteuerung.

3. Klicken Sie in der linken Navigationsleiste auf **Konferenz**.

4. Klicken Sie auf die Registerkarte **Einwahlnummer**. 

5. Stellen Sie sicher, dass alle Einwahlnummern zu dem auf Skype for Business Server 2019 gehosteten Pool migriert wurden.

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-management-shell"></a>Überprüfen der Migration der Zugriffsnummern für die Einwahl mit Skype for Business Server Verwaltungsshell

1. Öffnen Sie Skype for Business Server Management Shell.

2. Um alle migrierten Einwahlnummern für Konferenzen zurückzugeben, führen Sie an der Befehlszeile folgenden Befehl aus:

   ```PowerShell
   Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}
   ```

3. Stellen Sie sicher, dass alle Einwahlnummern zu dem auf Skype for Business Server 2019 gehosteten Pool migriert wurden.


