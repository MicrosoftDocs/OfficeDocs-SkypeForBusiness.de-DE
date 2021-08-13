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
description: Für die Migration von Einwahlnummern zu Skype for Business Server 2019 muss das Cmdlet Move-CsApplicationEndpoint ausgeführt werden, um die Kontaktobjekte zu migrieren. Während des Legacyinstallations- und Skype for Business Server Koexistenzzeitraums 2019 verhalten sich die von Ihnen in Skype for Business Server 2019 erstellten Einwahlnummern ähnlich wie die Einwahlnummern, die Sie in der Legacyinstallation erstellen, wie in diesem Abschnitt beschrieben.
ms.openlocfilehash: a65f0252dd4899ef196701d282a1b14673c5c22b7851029b35a15c4685c2b28d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54318050"
---
# <a name="migrate-dial-in-access-numbers"></a>Migrieren von Zugriffsnummern für die Einwahl

Zum Migrieren von Einwahlnummern zu Skype for Business Server 2019 muss das Cmdlet **"Move-CsApplicationEndpoint"** ausgeführt werden, um die Kontaktobjekte zu migrieren. Während des Legacyinstallations- und Skype for Business Server Koexistenzzeitraums 2019 verhalten sich die von Ihnen in Skype for Business Server 2019 erstellten Einwahlnummern ähnlich wie die Einwahlnummern, die Sie in der Legacyinstallation erstellen, wie in diesem Abschnitt beschrieben. 

Zugriffsnummern für die Einwahl, die Sie in der Legacyinstallation erstellt, aber zu Skype for Business Server 2019 verschoben haben oder die Sie in Skype for Business Server 2019 vor, während oder nach der Migration erstellt haben, weisen die folgenden Merkmale auf:

- Sie werden nicht in Office Communications Server 2007 R2-Besprechungseinladungen und auf der Einwahlnummernseite angezeigt.

- Wird auf den Besprechungseinladungen für die Legacyinstallation und auf der Zugriffsnummernseite für die Einwahl angezeigt.

- Wird auf Skype for Business Server 2019-Besprechungseinladungen und auf der Zugriffsnummernseite für die Einwahl angezeigt.

- Sie können nicht im Verwaltungstool von Office Communications Server 2007 R2 angezeigt oder geändert werden.

- Kann in der Legacyinstallations-Systemsteuerung und in der Legacyinstallations-Verwaltungsshell angezeigt und geändert werden.

- Kann in der Systemsteuerung Skype for Business Server 2019 und in Skype for Business Server 2019-Verwaltungsshell angezeigt und geändert werden.

- Sie können innerhalb des Bereichs durch Verwendung des Set-CsDialinConferencingAccessNumber-Cmdlets mit dem Priority-Parameter neu sequenziert werden.

Sie müssen die Migration von Einwahlnummern abschließen, die auf den Legacyinstallationspool verweisen, bevor Sie den Legacyinstallationspool außer Betrieb genommen haben. Wenn Sie die Migration von Einwahlnummern nicht wie im folgenden Verfahren beschrieben abschließen, schlagen eingehende Anrufe an die Einwahlnummern fehl.

> [!IMPORTANT]
> Sie müssen dieses Verfahren vor der Außerbetriebnahme des Legacyinstallationspools ausführen. 

> [!NOTE]
> Wir empfehlen, das Verschieben von Einwahlen zu einem Zeitpunkt vorzunehmen, zu dem die Netzwerkauslastung möglichst gering ist, für den Fall, dass es zu einem kurzen Dienstausfall kommt. 

## <a name="to-identify-and-move-dial-in-access-numbers"></a>So identifizieren und verschieben Sie Einwahlnummern

1. Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **"Start",** **"Alle Programme",** **"Microsoft Skype for Business Server 2019"** und dann auf **Skype for Business Server Verwaltungsshell.**

2. So verschieben Sie jede Einwahlnummer aus der Befehlszeile in einen Pool, der Skype for Business Server 2019 gehostet wird: 

   ```PowerShell
   Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>
   ```

3. Öffnen Sie Skype for Business Server Systemsteuerung.

4. Klicken Sie in der linken Navigationsleiste auf **Konferenz**.

5. Klicken Sie auf die Registerkarte **Einwahlnummer**. 

6. Stellen Sie sicher, dass für den Legacyinstallationspool, von dem Sie migrieren, keine Einwahlnummern übrig bleiben.

    > [!NOTE]
    > Wenn alle Einwahlnummern auf den Pool Skype for Business Server 2019 verweisen, können Sie den Legacyinstallationspool außer Betrieb genommen. 

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-control-panel"></a>Überprüfen der Migration von Einwahlnummern mithilfe Skype for Business Server Systemsteuerung

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle **CsUserAdministrator** oder **CsAdministrator** zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an. 

2. Öffnen Sie Skype for Business Server Systemsteuerung.

3. Klicken Sie in der linken Navigationsleiste auf **Konferenz**.

4. Klicken Sie auf die Registerkarte **Einwahlnummer**. 

5. Stellen Sie sicher, dass alle Zugriffsnummern für die Einwahl in den Pool migriert werden, der Skype for Business Server 2019 gehostet wird.

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-management-shell"></a>Überprüfen der Migration von Einwahlnummern mithilfe Skype for Business Server Verwaltungsshell

1. Öffnen Sie Skype for Business Server Verwaltungsshell.

2. Um alle migrierten Einwahlnummern für Konferenzen zurückzugeben, führen Sie an der Befehlszeile folgenden Befehl aus:

   ```PowerShell
   Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}
   ```

3. Stellen Sie sicher, dass alle Zugriffsnummern für die Einwahl in den Pool migriert werden, der Skype for Business Server 2019 gehostet wird.


