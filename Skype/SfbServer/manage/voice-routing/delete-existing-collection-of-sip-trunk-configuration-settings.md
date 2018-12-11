---
title: Löschen einer vorhandenen Auflistung von SIP-Trunk-Konfigurationseinstellungen in Skype für Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'SIP-trunkkonfigurationseinstellungen definieren die Beziehung und Funktionen zwischen einem Vermittlungsserver und das Gateway public switched Telephone Network, (PSTN), eine öffentliche IP-PBX (Branch Exchange) oder eine Session Border Controller (SBC) des Dienstanbieters. '
ms.openlocfilehash: 3d568e07dd4baec59f050453087b2857a72377d4
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "27223479"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Löschen einer vorhandenen Auflistung von SIP-Trunk-Konfigurationseinstellungen in Skype für Business Server

SIP-trunkkonfigurationseinstellungen definieren die Beziehung und Funktionen zwischen einem Vermittlungsserver und das Gateway public switched Telephone Network, (PSTN), eine öffentliche IP-PBX (Branch Exchange) oder eine Session Border Controller (SBC) des Dienstanbieters. Diese Einstellungen geben unter anderem Folgendes an:

- Ob Medienumgehung für die Trunks aktiviert werden soll.
- Die Bedingungen, unter denen Pakete Real-Time Transport Control Protocol (RTCP) gesendet werden.
- Unabhängig davon, ob die Verschlüsselung secure Real-Time Transport Protocol (SRTP) für jeden Trunk erforderlich ist.

Wenn Sie Skype für Business Server installieren, wird eine globale Auflistung von SIP-trunkkonfigurationseinstellungen für Sie erstellt. Diese globale Auflistung von Einstellungen kann nicht gelöscht werden. Die Skype für Business ServerControl Systemsteuerung oder [Remove-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration) -Cmdlet können Sie jedoch "die Eigenschaften in der globalen Auflistung auf ihre Standardwerte zurückgesetzt". Wenn Sie beispielsweise die Eigenschaft „Enable3pccRefer“ auf „True“ setzen, wird diese Eigenschaft beim Zurücksetzen der globalen Auflistung auf den Standardwert „False“ zurückgesetzt.

Administratoren können auch benutzerdefinierte Trunkkonfigurationseinstellungen für den Standort- oder Dienstbereich (für ein einzelnes PSTN-Gateway) erstellen. Diese benutzerdefinierten Einstellungen können entfernt werden. Beachten Sie beim Entfernen dieser benutzerdefinierten Einstellungen Folgendes:

- Wenn Sie Einstellungen für den Dienstbereich entfernen, wird der mit diesen Einstellungen verwaltete SIP-Trunk mit den Einstellungen verwaltet, die für den entsprechenden Standort gelten, sofern vorhanden. Wenn keine Standorteinstellungen vorhanden sind, werden diese Trunks mit der globalen Auflistung der Trunkkonfigurationseinstellungen verwaltet.
- Wenn Sie Einstellungen für den Standortbereich entfernen, werden alle mit diesen Einstellungen verwalteten SIP-Trunks jetzt mit der globalen Auflistung der Trunkkonfigurationseinstellungen verwaltet.

**So entfernen Sie Trunk-Konfigurationseinstellungen mit dem Skype Business Server-Systemsteuerung** 

1. Klicken Sie in der Skype Business Server-Systemsteuerung klicken Sie auf **VoIP-Routing**, und klicken Sie dann auf **Trunkkonfiguration**.
2. Wählen Sie auf der Registerkarte **Trunkkonfiguration** die Sammlung der SIP-trunkkonfigurationseinstellungen gelöscht werden, klicken Sie auf **Bearbeiten**und klicken Sie dann auf **Löschen**. Klicken Sie zum Löschen mehrerer Auflistungen auf die erste zu löschende Auflistung, halten Sie die STRG-TASTE gedrückt und klicken Sie dann auf die weiteren Auflistungen, die Sie entfernen möchten.
3. Die Eigenschaft **State** für die Sammlung wird als **Commit nicht ausgeführt** angezeigt. Um die Änderungen zu übernehmen und die Sammlung zu löschen, klicken Sie auf **Commit ausführen** und anschließend auf **Commit für alle Elemente ausführen**.
4. Klicken Sie im Dialogfeld **VoIP-Konfigurationseinstellungen, für die kein Commit ausgeführt wurde** auf **OK**.
5. Klicken Sie im Dialogfeld **Skype Business Server-Systemsteuerung** auf **OK**.
6. Wenn Sie Ihre Meinung ändern und nicht die Auflistung löschen möchten, klicken Sie auf **Commit**, und klicken Sie dann auf **Abbrechen alle nicht übernommenen Änderungen**. Wenn das Dialogfeld **Skype Business Server-Systemsteuerung** angezeigt wird, klicken Sie auf **OK**.

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a>Entfernen der trunkkonfigurationseinstellungen mithilfe von Windows PowerShell-cmdlets


Sie können mithilfe von Windows PowerShell und das Cmdlet **Remove-CsTrunkConfiguration** trunkkonfigurationseinstellungen löschen. Sie können dieses Cmdlet entweder von der Skype für Business Server-Verwaltungsshell oder aus einer Remotesitzung von Windows PowerShell ausführen. 

**So entfernen Sie eine angegebene Auflistung von Einstellungen**

Mit dem folgenden Befehl werden die Trunkkonfigurationseinstellungen gelöscht, die auf den Standort „Redmond“ angewendet wurden:

`Remove-CsTrunkConfiguration -Identity site:Redmond`

**So entfernen Sie alle Auflistungen, die im Standortbereich angewendet wurden**

Mit dem folgenden Befehl werden alle Trunkkonfigurationseinstellungen entfernt, die auf den Dienstbereich angewendet wurden:

`Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration`

**So entfernen Sie alle Auflistungen, bei denen die Medienumgehung aktiviert ist**

Mit dem folgenden Befehl werden alle Trunkkonfigurationseinstellungen entfernt, bei denen die Medienumgehung aktiviert ist:

`Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration`

Weitere Informationen finden Sie im Hilfethema zum [Remove-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration) -Cmdlet.